# Devops-git-workflow
#### 1- Create a  new respository and clone it
#### 2- Create a new branch using `git branch feature/add-login`
#### 3- In branch `feature/add-login` created a demo file named `app.js` and added some random content in it
#### 4- Created a `pre-commit` file in directory `.git/hooks/pre-commit` and added the following rules like "NO trailing whitespace allowed" with this script 
`#!/bin/bash
if git diff --cached --check; then
    :
else
    echo "ERROR: Trailing whitespace detected. Please remove it before committing."
    exit 1
fi
if git diff --cached | grep -E '^(+|-).*console\.log' -q; then
    echo "ERROR: Debugging statements (e.g., console.log) detected. Please remove them before committing."
    exit 1
fi
exit 0`
#### 5- Pushed features branch to remote github repo
#### 6- Created a pull request  from `feature/add-login`  branch to repo
#### 7- Accepted the Pull request.
#### 8- Implemented post-commit hook to send webhook message 
#### 9- Setup webhook to observe pull and push requests.
