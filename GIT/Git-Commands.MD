
## Commands Workflow

To configure the local repository with name for reviewing changes

```bash
  git config --global user.name " "
```

To configure the local repository with email for reviewing changes

```bash
  git config --global user.email " "
```

To Initialize a existing directory as a git repository

```bash
  git init
```

To clone a git remote repository into our local repository

```bash
  git clone "URL"
```

To view the modified changes in the repository
```bash
  git status
```
To add a file created/modified in the directory to the repository
```bash
  git add "file_name"
```
To add all the files to the repository
```bash
  git add .
```
To commit the files which have been added with a commit message
```bash
  git commit -m "commit_message"
```
To push the changes into specific branch after commiting changes
```bash
  git push -u origin "branch_name"
```

To view all the local repository branches
```bash
  git branch
```
To view all the branches (Local/Remote)
```bash
  git branch -a
```
To log into a specific branch and make changes there
```bash
  git checkout "branch_name"
```
To merge a branch into the current logged in branch
```bash
  git merge "branch_name
```
To view the history of all commits
```bash
  git log
```
To change a branch name by logging into that branch
```bash
  git branch -m dev-nlp
```
To delete a branch locally
```bash
  git branch --delete "branch_name"
```
To delete a repository from remote (GITHUB)
```bash
  git push origin --delete features-nlp
```
To push a newly created branch to the remote reposioory
```bash
  - git push -u origin dev-nlp
```

