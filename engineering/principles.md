# Principles

Some principles we follow

## Always keep your worksite clean

In our case, codebases are our worksite. Keeping them clean means:

- "no junk in the trunk": Don't put anything in master branches that is not ready to go to production.
- keep packages up to date (we suggest using rennovate bot; start with the same config as [svc-order](https://github.com/lux-group/svc-order/blob/master/renovate.json))
- keep node versions (and versions of any other languages used) up to date
- each repo should have an up-to-date readme that will allow a new-comer to self-onboard to that codebase
- delete merged branches, and delete obsolete unmerged branches in git

## Delete thoroughly

Deleting a feature? No one will ever be in a better position than you, now, to completely remove every trace of it.

Think there's still a small chance we might want this code in future? Just delete it. We can usually get it back with git.
And anyway, the cost of occasionally re-writing is less than the cumulative cost of all future devs tripping over dead-but-not-deleted code.

## Code Quality

As a rough heuristic, aim for at least a 7 out of 10. "Cleaning up later" is not something that happens, so unless we have a truly urgent deadline to meet,
we do a good job on the first pass.

## Test Driven Development

We agree with Sarah Mei's [five factor testing](https://madeintandem.com/blog/five-factor-testing/).

For server-side code, we also encourage Test Driven Development. This doesn't mean that a complete test must be written before any non-test code is written.
However, it does mean that tests shouldn't be an after-thought. Tests and code should evolve side by side, and during development, the primary means 
to run code should be to write a test for it, and run that test.

We'd expect that senior devs are regularly deploying API changes to production having not run them any other way but via tests.
That's the level of confidence we want in our test suite.
