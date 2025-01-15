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
![App Screenshot](https://github.com/YenishRadadiya/01-Git/blob/develop/images/chery-pick.png)

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
2. Add a commit message hook to the repo.
3. Perform multiple commits in the new branch
4. Create PR to develop.
5. Create another branch from develop given your previous PR is still in review state 
6. Now commit something in your current branch and push it
7. In the meantime, your previous PR has been merged to develop
8. Create a PR for the current branch given your branch should be up to date with develop branch
9. For any new build release add a version tag to that specific commit to keep track of each version.
10. Create 2 another branch (3rd and 4th) from develop, push read me changes to 3rd branch.
11. Cherry pick 3rd branch's commit to 4th branch. 
12. Change commit message in 4th branch
13. add 3 commits to 4th branch and delete last commit.
