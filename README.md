# 01 - Basics of git

## Git Exercise:
1. Create a new repository with a template
```bash
git init
```
2. Initialize git-flow  
```bash
git flow init
```
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/git%20flow%20init.png)

3. Create a feature branch for project setup with the proper Zoho task ID (example: TP2-T1299_Project_Setup)

```bash
git flow feature start TE-T181-project-setup
``` 
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/project-setup.png)

4. Create a sub-branch from the project setup branch and perform squash, reset, rebase and cherrypick ​​​​​​​.
```bash
git checkout -b TE-T181-project-setup-sub-branch
``` 
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/sub-branch-commit.png)

### Squash
```bash
git rebase -i HEAD~3
```
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/squash.png)
 
### Reset
```bash
git reset 9082504 
``` 
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/reset.png)

### Rebase
```bash
git rebase feature/TE-T181-project-setup  develop 
``` 
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/rebase.png)

### Cherypick 
```bash
git cherry-pick 0ee3b79
```
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/chery-pick.png)

## Practical Task:
1. Create a branch from the develop
```bash
git checkout develop
git flow feature start feature1
```

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/1.png)

2. Add a commit message hook to the repo.
For adding commit-msg hook, go to .git/hooks directory and add following script into commit-msg file:

```bash
#! /usr/bin/bash

# cd ./git/hooks
# mv commit-msg.sample commit-msg
# Don't forget to add: chmod +x .git/hooks/commit-msg

COMMIT_MESSAGE=$(cat $1)

if [[ ! $COMMIT_MESSAGE =~ ^(feat|fix|refactor|test|docs|core) ]]; then
    echo "Error: Commit message must start with one of the following keywords: feat, fix, refactor, test, docs, core."
    exit 1
fi

exit 0
```
Now Try to commit with invalid format
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/2.png)

3. Perform multiple commits in the new branch
```bash
touch feature1.txt
git add .
git commit -m 'feat:adding desctiption for feature1'
git commit -m 'feat: feature list'
```
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/3.png)

4. Create PR to develop.

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/4.png)

5. PR should be small in size, It's recommended to do one commit per PR. However, based on the situation we can have multiple commits in PR. e.g. if someone is doing 10 bug fixes which are one-liner fixes in such cases instead of 10 different PRs you can do 10 commits in a single PR. 

6. Create another branch from develop given your previous PR is still in review state 

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/6_1.png)

7. Now commit something in your current branch and push it

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/7.png)

8. In the meantime, your previous PR has been merged to develop.

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/8.png)

9. Create a PR for the current branch given your branch should be up to date with develop branch

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/9.png)


10. For any new build release add a version tag to that specific commit to keep track of each version.

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/10.png)


11. Create 2 another branch (3rd and 4th) from develop, push read me changes to 3rd brach.

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/11.png)

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/11_1.png)


12. Cherry pick 3rd branch's commit to 4th branch.

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/12.png)


13. Change commit message in 4th branch

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/13.png)


14. add 3 commit to 4th branch and delete last commit.

![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/14.png)
