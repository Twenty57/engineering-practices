# T57 Git Workflow

To learn more about git, see https://www.atlassian.com/git .

The following is the git workflow we commonly use when developing applications with Linx and Stadium.

## General rules
1. "main" branch contains the latest code. This branch should always contain working, tested code.
1. Changes are made on feature branches called "feature/my-new-feature". Feature branches are merged into "main" after code review.
1. "release" branch contains code that is ready for release.
1. When code in "main" is ready to release, it is merged into "release".
1. When code is released to UAT, the head in "release" is tagged with "uat-version".
1. When code is released to PROD, the head in "release" is tagged with "prod-version".
1. When we need a fix to UAT or PROD, we
    1. Create a "hotfix/my-fix" branch from "main", make the fix, and merge to "main"
    1. Merge the fix to "release"
    1. Release and tag the new UAT version (or PROD version if it is at the head)
1. When we need a fix to PROD and PROD is not at the head of "release", we additionally
    1. Create a "release/version" branch from the commit with the last PROD tag in "release" 
    1. Merge the fix to the "release/version" branch
    1. Release the code in the "release/version" branch and tag it

## Workflow

To get the remote repository the first time, we `git clone "repo"`
If we want to get the latest code from the remote repository, we switch to the branch we want to get the latest code for, like `git checkout "main"`, and then `git pull`.

To start work on a new feature

1. Create a branch
    1. From the head of the branch `git branch "feature/my-branch"` + `git checkout "feature/my-branch"` or `git checkout -b "feature/my-branch"`
    1. From a specific commit (like when doing a fix on PROD) `git checkout [commit_id]​ -b "feature/my-branch"`
1. Make changes, committing to the branch as you work `git add .` + `git commit -m "commit message"`

When done, get things ready for a code review

1. Rebase (assuming we're mostly working alone on a feature) from "main" to make sure you include all the changes others have made 
    1. Get all the changes to "main" with `git checkout "main"` + `git pull`
    1. Incorporate the changes into the branch with `git checkout "feature/my-branch"` + `git rebase main`
1. Check your changes and make sure it all makes sense `git diff`
1. Make sure everything works by running the tests

For a local code review

1. Ask the reviewer to look at your code
1. Make any changes
1. Merge your code into "main" with `git checkout "main"` + `git merge "feature/my-branch"`
1. Push changes to the remote repository `git push`

For a review using a pull request

1. Push the branch to the remote repo `git push`
1. Browse to the remote repo and create a pull request
1. Make any changes flowing from the review and push to the remote repo
1. The reviewer merges the pull request into "main" when approved