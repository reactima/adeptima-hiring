# Git Flow (with rebasing)
See http://nvie.com/posts/a-successful-git-branching-model/

## Features

A feature is based off the `develop` branch and merged back into the `develop` branch.
It will eventually get into `master` when we make a release.

### Working Locally

```
# checkout develop, fetch the latest changes and pull them from remote into local
git checkout develop
git fetch
git pull origin develop

# create a feature branch that is based off develop
git checkout -b feature/XX-123/some-description

# do your work
git add something
git commit -m "first commit"
git add another
git commit -m "second commit"

# rebase against develop to pull in any changes that have been made
# since you started your feature branch.
git fetch
git rebase origin/develop

# push your local changes up to the remote
git push

# if you've already pushed changes and have rebased, your history has changed
# so you will need to force the push
git fetch
git rebase origin/develop
git push --force-with-lease
````

### GitHub workflow

- Open a Pull Request against `develop`
- When the Pull Request has been approved, merge using `squash and merge`, adding the ticket number and a brief description:
ie, `MQ-330 enable users to order a pizza from the dashboard`.
- This squashes all your commits into a single clean commit.

If you are unable to squash merge because of conflicts, you need to rebase against `develop` again:

```
# in your feature branch
git fetch
git rebase origin/develop
git push --force-with-lease
```



## Releases

A release takes the changes in `develop` and applies them to `master`.


### Working locally


```
# create a release branch from develop
git checkout develop
git fetch
git pull origin develop
git checkout -b release/3.2.1

# finalise the change log, local build, etc
git add CHANGELOG.md
git commit -m "Changelog"

# rebase against master, which we're going to merge into
git fetch
git rebase origin/master
git push --force-with-lease
```


Usually at this point you will want to deploy the release branch to the staging server for final QA.
If there are any issues, fixes should be committed to the release branch.

### Github workflow

- Open a Pull Request against `master`
- When the PR is approved and the staging deploy has been verified by QA, merge using `rebase and merge`.
- **DO NOT SQUASH MERGE**. We don't want a single commit for the release, we want to maintain the feature commits in the history.
- Repeat the steps above against `develop` (may need to rebase first).
- Tag a release on master. Use the version number and put the changelog in the description.




## Hotfixes

A hotfix is a patch that needs to go directly into `master` without going through the regular release process.
The most common use case is to patch a bug that's on production when `develop` contains code that isn't yet ready for release.


### Working locally

```
# create a hotfix branch based on master, because master is what will be deployed to production
git checkout master
git fetch
git pull origin master
git checkout -b hotfix/describe-the-problem

git add patch.fix
git commit -m "fix the problem"
git push
```

### Github workflow

- Open a Pull Request against `master`
- When the PR's approved and the code is tested, `squash and merge` to squash your commits into a single commit.
- Open a Pull Request against `develop` (may need to rebase first).
- Tag a release on `master`. Describe the issue in the name, feel free to put details in the description.

> ### Atomic Approach
> 
> - Commit each fix or task as a separate change
> - Only commit when a block of work is complete
> - Commit each layout change separately
> - Joint commit for \[JSX and CSS changes\], and additional resources
> 
> ### Benefits
> 
> - Easy to roll back without affecting other changes
> - Easy to make other changes on the fly
> - Easy to merge features to other branches

Then, each PR is a set of commits related to one change or task.
Sometimes, this means a single commit per PR.
Other times, it means many commits for a PR.



## Github
* Use Gitflow as a principle: http://nvie.com/posts/a-successful-git-branching-model/
* Don't directly commit any code to develop or master branch
* Open Pull Request to merge your code in develop branch
* Code needs to get approval and build successfully in order for it to get merge 
* The job is done only if the PR is merged


## Making a pull request

* *Branching out* before submitting a PR make sure that you're on a fresh branch that's named after the work that you're doing
* *Committing your changes* with descriptive messages. 
* *Test and lint* Run `yarn run test` to check for any linting or test errors and make sure they're all fixed. CI should catch these once you submit the PR, but it's good to catch them early.

## CI Ready
Why? CI will run `yarn test` and `yarn lint` for your repo every time you push to GitHub and the results will be shown in the GitHub UI. It will help us maintain code quality and restrict us merging branches that fail tests.


### Advanced Git
- Pro Git: https://git-scm.com/book/en/v2
- How to teach Git, Rachel M. Carmena https://rachelcarmena.github.io/2018/12/12/how-to-teach-git.html
- Flight rules for Git https://github.com/k88hudson/git-flight-rules
- Become a git guru, Atlassian https://www.atlassian.com/git/tutorials
- Welcome to Learn Git Branching ;) https://learngitbranching.js.org/
- Git from the bottom up, John Wiegley http://ftp.newartisans.com/pub/git.from.bottom.up.pdf



