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

## General code practices

### Always seperate business logic from application logic

Business logic is defined as steps that needs to be taken to conform data and information to fit our business needs. For example:
- Fetching specific multiple pieces of data from the database, transforming the data and before displaying in the view layer.
- When creating a resource, have to manipulate other data
- [More info here](https://en.wikipedia.org/wiki/Business_logic) 

If you find yourself writing 50 lines of code to handle business logic in the controller (for Rails) or in the component (in React) then likely you need to refactor these into a helper function.

### Bear in mind your Source Of Truth

When you find yourself having to set magic constants or hardcode a list of information, always ask yourself if is that a new source of truth or has it existed somewhere. 

If it has existed somewhere, use the same source of truth. If the shape doesn't fit exactly, you can write a helper that conforms the data shape.

**Absolutely do not** create duplicate sources of truth. This makes it very very hard to refactor code as we do not know where the single source of truth is so we don't know what breaks the system.

Ideally, source of truth should originate deep from the system, in this case in the form of a Rails API. If that is not possible, consolidate the source of truth in the javascript `constants` folder.

### When dealing with large and deep state shapes, `useReducer`.

Refer to this article https://matthamlin.me/2019/february/why-you-should-useReducer

### Functional components + large state shapes + liberal use of hooks = Disaster 🤯

If you have to use functional components, then you should not have large state shapes.
If you need to deal with validations and logic, then you should exclusively use React class components.
Even though you can use React Hooks with functional components, treat them as _escape hatches_. 

## Resources

### React 
React useEffect complete guide: https://overreacted.io/a-complete-guide-to-useeffect/
