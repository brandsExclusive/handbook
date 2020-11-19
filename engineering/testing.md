# Testing

We take a pragmatic approach to testing, code coverage is not a metric we track. All key purchase paths should be covered by end-to-end testing - this includes:

- API testing with test-e2e-le-api
- WWW end-to-end testing built into www-le-customer
- Email end-to-end testing within test-e2e-email

All business logic with sufficient complexity should always be covered by unit testing.

We [encourage Test Driven Development](engineering/principles.md#test-driven-development)

## Bugs

As a rule of thumb if your code change fixes a bug it should be accompanied by a
test covering the scenario.
