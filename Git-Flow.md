Please read https://datasift.github.io/gitflow/IntroducingGitFlow.html

**Notes:** 

*  If you're not familiar with git, please download https://www.gitkraken.com/ so as to lessen problems with branching and merging.
* There should be one branch per feature (or user story). If a subset of developers are working on the same feature, please use one feature branch
* Please follow the naming convention
  * For feature branches, prefix with `feature/` and then follow with a short feature description (all in small letters and delimited by dash '-'). For example, `feature/filter-accounts`
  * For bug fixes, prefix with 'bugfix/' and then follow it with a short description of the bug. for example, `bugfix/accounts-screen-layout`
  * For hot fixes (prod fixes), please prefix with `hotfix/`
* If you've submitted your code for code review, please make sure that your branch does not have conflicts with the dev branch. github will notify you if your branch cannot be merged automatically. Please check the conversation section of the pull request page
* Make sure that all unit tests pass before submitting your code for review.

## Creating a New Feature
1. Get latest from dev - `git checkout dev` and then `git pull`
1. From the dev branch, create a new branch for your new feature - `git checkout -b feature/some-stuff`
1. Start coding
1. Commit often. If one small part is already working, commit your files. Make sure to commit files that you have changed for the development of the feature. Do not just perform a `git add .` without checking the files list.

## Setting for Code Review
1. Make sure that you get the latest from dev and then merge the latest code from dev to your branch. 
1. Resolve conflicts in your branch if you have to
1. Push your branch to origin
1. Go to github.dxc.com and then create a pull request (PR). Click the "New Pull Request" button. In the compare field, select your branch. In the base field, select dev. Click on the "Create Pull Request" button afterwards.
1. Please set the reviewer at the right panel after creating a new pull request

