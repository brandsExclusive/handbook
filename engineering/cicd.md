# CI/CD

LE has multiple end to end test suites. These are run against our testing environment constantly. All of the applications in our testing environments are running on the master branch. If all the builds are green we can have confidence that our **critical** features are working. With this confidence we are constantly promoting our changes to production.

The mentality behind this is that computers are better at finding problems than humans. Manual tests can and should be scripted. Write lots of tests and have confidence in your code base.

If you merge your PR, it **is** going to production. No code is to live in master in an unreleased state. Make sure you have written tests to confirm your feature works.

## CD Setup guideline

https://aussiecommerce.atlassian.net/wiki/spaces/TEC/pages/1422884958/CD+setup+guideline+for+services

## Dependent changes

Changes must be released in order. 

E.g. if you have a change for a web app that depends on a specific route in an api you must make sure that your api deployment reaches production first. 

Service A depends on a feature in service B

1. Merge feature change in service B
2. Merge dependent change in service A

It is **strongly advisable** to release changes across two distinct set of pull requests with shims to avoid the need for dependent changes. 

## Red green builds

You can write your e2es before you deploy to production. Merge these into the test repo and watch it go red. Merge your applications PR, the tests go green, it gets deployed.

## E2E roster

A roster for keeping our builds green. 

https://aussiecommerce.atlassian.net/wiki/spaces/TEC/pages/990445572/E2E+Roster

## Jira Board 

A board to track improvements/fixes to our CI/CD pipeline.

https://aussiecommerce.atlassian.net/secure/RapidBoard.jspa?projectKey=CICD&rapidView=77
