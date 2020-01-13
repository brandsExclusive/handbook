# migrations
All chnages in database should go through migrations files. 
Each services which use a database have migrations folder and scripts for generating special files.

For example

```sh
yarn db:migrate-create my-migrations
```

# big data update
If you have some update the big data table you need to make migrations script which will be doing it by part.

For example 

```sh
#! /bin/bash

if [ -z "$DATABASE_URL" ]
  then
    DATABASE_URL=postgres://@127.0.0.1:5432/svc_order_development
fi 

if [ -z "$LIMIT" ]
  then
    LIMIT=1000
fi


QUERY_DISABLE_TRIGGERS="ALTER TABLE orders DISABLE TRIGGER salesforce_purchase_trigger;"
QUERY_ENABLE_TRIGGERS="ALTER TABLE orders ENABLE TRIGGER salesforce_purchase_trigger;"
QUERY_COUNT="SELECT COUNT(*) FROM public.orders;"
QUERY_UPDATE="UPDATE public.orders AS orders SET order_items_types = array_append(orders.order_items_types, 'accommodation') WHERE orders.id_orders = ANY (SELECT o.id_orders FROM public.orders AS o WHERE EXISTS (SELECT items.fk_order_id FROM public.items AS items WHERE items.fk_order_id = o.id_orders LIMIT 1) AND (o.order_items_types = '{}' OR NOT ('accommodation' = ANY(o.order_items_types::text[]))) LIMIT $LIMIT);"
QUERY="BEGIN; $QUERY_DISABLE_TRIGGERS $QUERY_UPDATE $QUERY_ENABLE_TRIGGERS COMMIT;"


COUNT=$(psql ${DATABASE_URL} -q -c "${QUERY_COUNT}" | grep -m1 -E "([0-9].*)" | sed 's/(/ /g' | awk '/[0-9]/{print $1}')

UPDATED=0

echo "count: $COUNT"

echo -n "updated: $UPDATED"

while [[ $UPDATED -lt $COUNT ]]
do
psql ${DATABASE_URL} -q -c "${QUERY}"
(( UPDATED+=$LIMIT ))
printf "\r%b" "\033[2K"
if [[ $UPDATED -lt $COUNT ]]; then
printf 'updated: %d' $UPDATED
else 
printf 'updated: %d' $COUNT
fi
sleep 1
done

echo -e ""
```

# important
Some tables can have a lot of triggers and you should research which can disable.