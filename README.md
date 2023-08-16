# Automated Way To Download Source Code and Upload to Your Personal Repo

Install gh (sudo snap install gh)
Set login credentials (gh auth login)
  choose github.com & https
Create a script file (touch automatedDeployment.sh)
Open script file (nano autpmatedDeployment.sh)
Tell operating system the script should be using bash by writing a shebang as first line (#!/bin/bash)
Set variable for repo where the source code is located (SOURCE_REPO="https://github.com/kura-labs-org/c4_deployment-1.git")
Set a variable for the name for your new repo (NEW_REPOSITORY_NAME="firstDeploymentAutomated")
Set a variable for your username to use for you GitHub url string (GITHUB_USERNAME='djtoler')
Download the code from the source repo (git clone $SOURCE_REPO)
Move into the directory where your newly downloaded code is located (cd c4_deployment-1)
Create a new public GitHub repo (gh repo create $NEW_REPOSITORY_NAME --public)
Make the repo remote (git remote add new-auto-deployment https://github.com/$GITHUB_USERNAME/$NEW_REPOSITORY_NAME.git)
Push the code to your remote repo (git push new-auto-deployment main)
