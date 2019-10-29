# Logging

We are using Rapid7 (previously log entries) as a log aggregation service and alerting

You can login at the following [URL](https://eu.ops.insight.rapid7.com/op/DD706D3736A22B254AD1)

If you don't have a login, ask the Head of Engineering Timothy Downs to sign you up

## Adding heroku logs

1) Log into Rapid7

2) Click `Add data` button

3) On the `Add Data Source` page click the `Quick add` button

4) Enter the log name, the convention is `<env> <service> <type>` e.g Prod Order Service, Test Customer Portal

5) Choose the log set it belongs to

6) Select Token TCP as the method

7) Click the `Add new log` button

8) Copy the field called `Your log token`

9) Add a log drain to you heroku app `heroku drains:add https://eu.webhook.logs.insight.rapid7.com/v1/drain/<your log token> --app <heroku app name>`

## Adding lambda logs

No idea yet
