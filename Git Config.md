## Configure the Git with GitHub with your system
```
git config --global user.name "Your Name"
```
```
git config --global user.email "your.email@example.com"
```

### initialize the repo for git
```
git init
```
### add all the file, you can add the specific file with their name (like git add Readme.md)
```
git add .
```
### 
```
git commit -m "write-your-beautiful-comment-here, for your repo"
```
### add or make branch
```
git branch -M main
```
### set the remote
```
git remote add origin https://github.com/your-git-username/your-repo-name.git
```
### push or upload or github 😊
```
git push -u origin main
```

### to update your repo later
```
git remote add origin https://github.com/your-git-username/your-repo-name.git
```
### this is the same as previous 
```
git branch -M main
```
### this is the same as previous
```
git push -u origin main
```
### some time you had to forcefully push your repo on github



/*
git push -u origin main
To https://github.com/anupjais/minicontext.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/anupjais/minicontext.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
*/


git pull origin main --rebase
git add .
git commit -m "Resolved merge conflicts"
"git push origin main" or "git push --force origin main"

