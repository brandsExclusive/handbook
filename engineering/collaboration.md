# Collaboration

## Architecture Changes

Before making an architectural change a [project plan](https://aussiecommerce.atlassian.net/wiki/spaces/TEC/pages/451608677/Project+plans)
should be created outlining the proposed change and what the problem being
solved is.

After the initial draft has been generated a link should be posted in the
\#engineering channel for feedback. A code owner should sign off on the top-level approach prior to implementation.
A project plan could be a quick paragraph or two, if that's all that's needed. 

Examples of architectural changes:

* new deployment pipeline strategies
* new data flows
* new usage of cloud product
* new services, or new relationships between services
* major refactors within a service
* significant changes to customer portal (As our largest and least isolated codebase, and the one with the most hidden - but soon to be documented! - rules and conventions, even medium-sized features can warrant more planning)

## Code Ownership

Each codebase should have a list of maintainers and collaborators on the readme.

Maintainers are responsible the quality, maintenance, deployment and
architecture of the codebase.

Collaborators have sufficient knowledge to review pull requests.

## Pull Requests

Each significant code change should go through a code review. All developers are encouraged to review code,
though the final "thumbs up to merge" should come from a collaborator or maintainer of the codebase.
Small non-functional changes can be made without a pull request.
Critical github repositories are configured to disallow merging pull requests that lack an approval.

Pull requests should be small and many to allow rapid review by team members.

Code should be written with reviewability in mind - so commits should be granular,
self-contained, and with an appropriate commit message.

## Weekly Kickoff

At the start of each week it's encouraged that everyone posts a message in the \#general room with what they intend to achieve for the week. This is so eveyone gets a general overview of what everyone else is doing.
