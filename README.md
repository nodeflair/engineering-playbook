# NodeFlair Engineering Playbook

## Workflow

### Naming git branches

Please follow these naming conventions
- `feature/XXX-title-of-issue` where `XXX` is the ticket number on Jira.
- `bug/XXX-title-of-issue` where `XXX` is the ticket number on Jira.
- `hotfix/name-of-hot-fix`. For urgent hotfixes that don't have a ticket.
- `epic/name-of-epic`. Only use this for very large feature sets.
- `enhancement/title-of-enhancement`. Use this when there are general feature enhancements that don't fall under any ticket.
- `debt/scope-of-things`. Use this when there are purely code enhancements or refactoring to do.
- `tests/scope-of-test`. Use then when writing new tests.


## Submitting bug tickets

Please follow the format below as much as possible when submitting a ticket for engineering to work in.

- Steps to reproduce problem
  - List down the steps in sequential order to get to the bug.
  - If there are some specific conditions that must be satisfied, also list it down.
- Current result
  - Give a brief descripition of what currently happens.
  - Screenshots and screen recordings are helpful here if any.
- Expected result
  - Give a brief descripition of what is expected to happen.

## Tooling

- Tickets, issues and feature requests
  - Jira
- Code repo, pull requests, code review
  - Github 
- Continuous integration & testing
  - AWS Elastic Beanstalk
- Routing and DNS
  - AWS Route 53


## Resources

### React 
React useEffect complete guide: https://overreacted.io/a-complete-guide-to-useeffect/
