# Project management

## Table of Contents

1. [Workflow](#workflow)
2. [Branch naming](#branch-naming)
3. [Rules](#rules)
  1. [Business value](#business-value)
  2. [Commits messages](#commits-messages)
  3. [Waffle issues](#waffle-issues)
  4. [PR management](#pr-management)

Other doc:
  * [Git workflow](git-workflow.md)

## Workflow

Disclaimer: the word `issue` refers to a GitHub issue, not an actual issue.

All issues are going to the `Backlog`. No real specification is required yet for those issues, although it's better to give them a proper description, business value, milestone and labels.

The project sprints are defined by GitHub milestones, be it a minor a major version. For ongoing sprint, the issues should be placed in the `Ready` waffle column.

Once someone start to work on the issue, he should place the issue on the `In progress` waffle column. When the work is ready and the PR done, he can put it in the `Needs review` column. Once the work merged, the issue should be put in the `Done` column.

The issues should be removed of the `Done` column by closing them when the sprint is over.

## Branch naming

To attach a branch to a GitHub issue, just put the issue number in the branch name. For instance if you are working on the ticket #15 which is a bugfix, you should name your branch `bugfix/something-#15`. When the branch is pushed, the issue is automatically moved to the `In Progress` Waffle column.

When creating a PR, if the PR closes an issue of number #15, the PR name should include `Close #15`. Check [the valid keywords](https://help.github.com/articles/closing-issues-via-commit-messages/).

If the PR is related to another issue but does not close it, you can use the `connected` keyword: `Close #15, connected to #52`.

## Rules

### Business value

The business value or size of a ticket should reflect the difficult to tacke the issue and is not the estimated time. If a ticket is not well specified or there is a lot of doubts about how much time it would take, the business value should be hight.

The business value should follow the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number): 1, 2, 3, 5, 8, 13, 21, 34...

### Commits messages

* Separate subject from body with a blank line
* Limit the subject line to 50 characters
* Capitalize the subject line
* Do not end the subject line with a period
* Use the imperative mood in the subject line
* Wrap the body at 72 characters
* Use the body to explain what and why vs. how

### Waffle issues

* All the tickets in the `Ready` column should have all the required elements to be workable.
* The overall business value of a sprint should not exceed 30
* The mixumum number of issues in `In Progress` should not exceed 3
* The mixumum number of issues in `Needs Review` should not exceed 2

### PR management

* A PR should be review before being merged
* A PR should be rebased with a proper commit history before being merged
* When being merged, the PR description should be added to the message of the merging commit