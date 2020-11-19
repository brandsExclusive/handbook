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

At the start of each week, a representative from each team should post in the \#general room with what their team intends to achieve for the week. This is so eveyone gets a general overview of what everyone else is doing.

## 2 week sprints

We work in 2 week sprints. Teams have some autonomy in how they run sprints but we suggest a format like this:

**1st Monday:** Sprint start. Each team to meet, decide what their goals are for that sprint, and post in the \#general channel.  
**1st Thursday:** Delivery Lead to remind teams of their action items from the previous sprint  
**2nd Monday:** Team to review progress against sprint goals and ensure focus is maintained  
**2nd Thursday:** Team retro. Delivery Lead to capture action items.  
**2nd Friday:** Tidy up day. Polish things you rushed. Scratch your own itches within the code base.  

