# CI/CD

LE has multiple end to end test suites. These are run against our testing environment constantly. All of the applications in our testing environments are running on the master branch. If all the suites builds are green we can have confidence that our **critical** features are working. If you merge your pr it is going to production. Make sure you have written tests to confirm your feature works.

The mentality behind this is that computers are better at finding problems than humans. Manual tests can and should be scripted. Write lots of tests and have confidence in your code base.

## Dependent changes

Changes must be released in order. If a web app depends on a specific route in an api you must make sure that your api deployment reaches production before you merge the other.

## Red green builds.

You can write your e2es before you deploy to production. Merge these into the test repo and watch it go red. Merge your applications PR, tests go green it gets deployed.
