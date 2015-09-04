# Repository ownership

Each repository has a single owner who is responsible for reviewing and merging pull requests. Everyone else is considered a contributor.

## Owners

You are the repo admin and should review and merge PRs. Try to be timely and help avoid blocking others.

## Contributors

You do not have the rights to directly write on the project. To work on the project and submit changes, you should **fork** the project, and submit changes to your fork.

From there, you should push upstream to the origin to create a pull request.

<img src="https://cloud.githubusercontent.com/assets/1319791/8943755/5dcdcae4-354a-11e5-9f82-915914fad4f7.png" alt="Triangular workflow" title="Triangular workflow" height="auto" width="100%">

You are repsonsible for keeping your fork up to date. To do this, you make your local fork **track** the upstream origin.

To see which repositories are currently being tracked, use `git remote -v`:

```
origin	git@bitbucket.org:yourNameSpace/Example.git (fetch)
origin	git@bitbucket.org:yourNameSpace/Example.git (push)
```

Now, add the original repository to tracked repositories:
```
git remote add upstream git@github.com:haircvt/Example.git.
```

Now if you do `git remote -v` again you should have:

```
origin	git@bitbucket.org:yourNameSpace/Example.git (fetch)
origin	git@bitbucket.org:yourNameSpace/Example.git (push)
upstream	git@bitbucket.org:haircvt/Example.git (fetch)
upstream	git@bitbucket.org:haircvt/Example.git (push)
```

That's it! Now, if you wish to update your repository, you can do:

* `git fetch upstream`: get the updates from the original repository.
* `git fetch origin`: get the updates of your remote repository (the fork).

Source: [GitHub: syncing a fork](https://help.github.com/articles/syncing-a-fork/)

**As a contributor, you should avoid working on the key branches**: `master`,  `staging`, `develop`. This will mean you can stay in sync with the upstream repo without any conflicts (imagine somebody else has a PR merged into `develop` whilst you we're working on it).

### Pushing changes upstream

To get your changes merged, you need to

1. Pull down any changes if you're working with other contributors
2. Rebase changes from the upstream repo:

  ```
  git fetch upstream
  git fetch origin
  git rebase upstream/develop
  ```
  **Notes**
  - We assume the main dev branch here is `develop`.
  - Also resolve any conflicts that occur. If you have to fix conflicts, you may need to force push.

3. Push your branch to your personal origin
4. Create a pull request on Bitbucket/Github

Cool! Now the owner can merge your changes after reviewing into `develop`, with a nice clean history.

To make further contributions, switch back to `develop`, then into your new feature branch.

# Branches

## Development

- `develop`
- `develop` --> `feature/my-new-feature`

## Staging

- `staging`

## Production

- `master`

## Bugfixing

- `master` --> `hoxfix/my-new-hotfix`


# Sources

* [Git-flow Cheatcheet](http://danielkummer.github.io/git-flow-cheatsheet/) - Daniel Kummer
* [Incipio](https://github.com/xNok/Incipio) - Theo Fidry
* [Git Workflows For Successful Deployment](http://bocoup.com/weblog/git-workflows-for-successful-deployment/) - Matt Surabian (*bocoup*) | May 07, 2015
* [Git Best Practices: Workflow Guidelines](https://www.lullabot.com/blog/article/git-best-practices-workflow-guidelines) - Andrew Berry (*Lullabot*) | June 14, 2012
* [GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html) - Scott Chacon | August 31, 2011
* [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/) - Vincent Driessen | January 05, 2010
* [Practical Git: A Workflow to Preserve Your Sanity](http://www.kdgregory.com/index.php?page=scm.git) - Keith D Gregory
* [Understanding the Git Workflow](https://sandofsky.com/blog/git-workflow.html) - Ben Sandofsky
* [Git Workflows That Work](http://blog.endpoint.com/2014/05/git-workflows-that-work.html) - Spencer Christensen | May 2, 2014
* [Git branch strategy for small dev team](http://stackoverflow.com/questions/2428722/git-branch-strategy-for-small-dev-team) - Bilal and Olga | March 11, 2010
* [Git Branching - Branching Workflows](http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows) - Git official doc
* [Comparing Workflows](https://www.atlassian.com/git/tutorials/comparing-workflows/) - *Atlassian*
* [Git Workflow in Invenio](http://invenio-software.org/wiki/Tools/Git/Workflow) - *Invenio*
