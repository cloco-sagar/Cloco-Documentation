# Github Workflow



## Steps to Setup project
1. Make sure there is **SSH** setup in your system and is linked with the gitub.

   Follow this link if you haven't setup SSH //TODO: TO be added later on
2. Clone the project using SSH.

    ```
   git clone <project_link_ssh>  //Replace project_link_ssh with your project ssh link
   
   Example:
   git clone https://github.com/cloco/cloco_project1
   ```
3. Move to the cloned project

   ```
   cd <folder_name>  //Replace folder_name with your project folder name
   
   Example:
   cd cloco_project1
   ```

4. There will be make file and then follow the commands mentioned in the make file accordingly to run the project



## Branching
There are certain number of branches in every project here in **Cloco** and every branch carry its own meaning and its purpose. 
Let's discuss each branches that we organize our codes on: 




1. **master Branch**  
    This branch is production branch. Only devops teams and project leader should be able to edit this or make pr requests to this branch.
    ```
   git checkout master
   ```

2. **hotfix Branch**

   This branch is responsible for quick patch for issues/bugs found in production environment. This could be a bug causing a major problem in production. This branch should be created from `master` and merged to `staging` and then `master`
   ```
   git checkout -b hotfix/<issue_description> master 
   
   Example: 
   git checkout -b hotfix/reloading_issue_fixed master
   ```

3. **staging Branch**
   
   This branch is responsible for next production release branch with all latest features and bugfix from develop branch. All tagging should be done here before creating **_PR_** to `master`.
   ```
   git checkout staging 
   ```
   
4. **develop Branch**
   This branch is responsible for active development branch where all new features and bugfixes are merged. This branch should be deployed in dev environmemt for testing
   ```
   git checkout develop
   ```
   
5. **feature/ Branch**
   This branch is responsible for creating specific feature. This branch needs to be created or updated with latest develop branch. After creating the feature and throughly reverifying it, PR needs to be created against develop branch.
   ```
   git checkout -b feature/123 develop
   ```

6. **bugfix/ Branch**
   This branch is responsible for fixing specific bug or issues found in develop environment. This branch needs to be created or updated with latest develop branch. After fixing the bug or issue and throughly reverifying it, PR needs to be created against develop branch.
   ```
   git checkout -b bugfix/123 develop
   ```

## Branch Access Levels

Only Team Leads and Project Manager should have direct push access to `master`, `staging` and `develop` branch.

## Guidelines For Pull Requests (PR)
1. Make sure your current working branch is updated with latest changes of `develop` branch or the branch from which this branch was created.
2. Latest changes from your code should not **break** previously written tests.
3. Your branch for bugfix and feature should not touch multiple issues/features/bugs. One branch should fix/add only one bug/feature.
4. Make sure required feature/bug works/fixed perfectly as per your understanding.
5. Make sure there isn't any performance issues.(Don't forget to check any console or log errors)
6. Make sure your commit message gives proper gist of the changes.(In some scenarios where commit message doesn't cover the gist, clear and concise description of changelog should be written.)
7. Reviewers and assignee needs to be mentioned in the PR


## Basic Guidelines for Code Review

Following things should be kept in mind while doing code review.

1. Make sure requested PR doesn't **break** existing features in any kind.
2. Verify that previously written tests doesn't break.
3. Make sure the requested PR doesn't touch multiple features/bugs.
4. Check if the changes meets the feature/bug requirements mentioned in the ticket.
5. OOP concept has been followed in class based component. 
6. DRY(Don't Repeat Yourself) and KISS (Keep It Simple, Stupid) principle must be followed.
7. Proper Enums should be used if possible.

## Merge Strategy

Team Member/any person who are Reviewers or assignee in PR is only responsible for approving the changes, which need to merged as soon as it is approved to the respective branch. Also reviewers and assignes needs to be mentioned. After checking the PR and checking don't forget to change the assignee and reviewers.

## Tagging Strategy

A tag is like a branch that doesn’t change. Unlike branches, tags, after being created, have no further history of commits.

**Major Tag** - Major version is a definite release of the product. It increases when there are significant changes in functionality.

**Minor/Feature Tag** - Minor version is incremented when only new features or major bug fixes have been added.

**Upgrade/Patch Tag** - Upgrade refers to the replacement of a product with a newer version of product. It is incremented only when upgrade is provided on designated major release.Patch version starts with 0 and incremented only when bug has been resolved.

**Date** - Release date should be with underscore format `mm_dd_YYYY`


Example: **v1_3.2.5.01_04_2020**:

1. v1: This indicates the version number. It suggests that this tag corresponds to version 1 of the software.

2. 3.2.5: This represents a more detailed version number or release identifier. It follows a convention where the version consists of multiple components (major, minor, and patch version numbers respectively). In this case, it means version is 3.2.5.

3. 01_04_2020: This part represents a date. In this case, it is January 4, 2020, formatted as day_month_year.

Please follow this link to clarify further and make changes accordingly for tagging.

https://atlassian.com/git/tutorials/inspecting-a-repository/git-tag

## Ways to do some actions in git branch (For Newbies)
1. To Create Branch in github

    ```
   git branch -b <branch_name>  //Replace branch_name with your own branch name
   
   Example:
   git branch -b feature/123
   
   OR
   
   git checkout -b <branch_name>  //Here this command will create a new branch and will move to that branch
   
   Example:
   git checkout -b feature/123
   ```
2. To Change Branch in github

   ```
   git checkout <branch_name>  //Here replace branch_name with your own branch name 
   
   Example:
   git checkout feature/123
   ```
   If there is no such branch it will throw some small error.

   **NOTE: Take a pull request before moving out to another branch if branch is recent push on remote**
   ```
   git pull
   ```

3. To delete branch in github
    ```
   //This will delete branch locally
   //Make sure that you are not in the branch that is to be deleted. 
   git branch --delete <branch_name>
   
   or
   git branch -d <branch_name>
   
   Example
   git branch --delete feature/123
   ```

4. To list out all branches in git that are in projects
   ```
   git branch -a
   ```

5. To see the commits in git

   ```
   git log
   ``` 

6. To Merge two branches
   ```
   // First checkout to your branch then merge that branch to current branch 
   git merge <branch_name>  // Replace with your Branch_name 
   
   Example:
   git checkout main
   git merge trial_cloco
   ```

7. To push local branch to remote
   ```
   git push origin <branch_name>  //Replace branch_name with your own branch 
   
   Example:
   git push origin feature/123
   ```

8. To Stash your changes

   ```
   git stash // To Discard the changes that you made on that branch and save that changes in recent stash
   
   git stash pop //This will apply the stashed changes that was made and delete that stash
   
   git stash apply // This will apply the stashed changes and will not delete that stash ::Reusuable stash
   ```


## Knowledge Based
Problems that you may encounter related to github
## <ins>Error-1: Unable to detect email address </ins>
<ins>**Solution**</ins>

if You get these types of error please follow these steps to resolve the issue

```
fatal: unable to auto-detect email address
```



**Step-1:** Insert these commands in the CMD

```
cd <project_directory>
git config user.email "your github email"
git config user.name "your github name"

Example:
cd cloco_project
git config global user.email "cloco@gmail.com"
git config global user.name "Cloco"
```

**Step-2:** A pop-up with sign in with browser will appear. Make sure you are logged in your GitHub Account. Click on the
sign in with browser and then click **Authorize**

These Steps should resolve your issue now and rerun the process to push your code to the remote repository
