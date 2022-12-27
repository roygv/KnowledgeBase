## Create a github repository from a local folder
1. Log into GIthub and create the new repository
2. `cd <folder>`
3. `git init`
5. `git add .`
6. `git commit -m "initial commit"`
7. `git remote add origin https://github.com/<github login>/<repository>.git` 
8. [Create an access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) to github. Use it as a password when asked
9. `git remote -v`  # verify the remote
10. `git push -u *origin* main`
## Setting your user name and e-mail
```git config [--global] user.name "<name>"```  # --global applies to all repositories on this computer
`git config [--global] user.email roy@gvirtsman.com`
## Branching
#### Create a branch and check it out (switch into the branch)
`git checkout -b <branch>`
#### Commit changes
`git commit`
#### Create remote branch and push local changes
`git push --set-upstream origin <branch>`
#### Merge to main
`git checkout main`
`git merge <branch>`
#### Delete branch
`git branch -d --remote <branch>`


