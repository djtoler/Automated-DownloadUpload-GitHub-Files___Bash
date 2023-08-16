# Automated Way To Download Source Code and Upload to Your Personal Repo

1. **Install gh**: `sudo snap install gh`
2. **Set login credentials**: `gh auth login`
   - choose github.com & https
3. **Create a script file**: `touch automatedDeployment.sh`
4. **Open script file**: `nano automatedDeployment.sh`
5. **Tell the operating system the script should be using bash by writing a shebang as the first line**: `#!/bin/bash`
6. **Set variable for the repo where the source code is located**: `SOURCE_REPO="https://github.com/kura-labs-org/c4_deployment-1.git"`
7. **Set a variable for the name for your new repo**: `NEW_REPOSITORY_NAME="firstDeploymentAutomated"`
8. **Set a variable for your username to use for your GitHub URL string**: `GITHUB_USERNAME='djtoler'`
9. **Download the code from the source repo**: `git clone $SOURCE_REPO`
10. **Move into the directory where your newly downloaded code is located**: `cd c4_deployment-1`
11. **Create a new public GitHub repo**: `gh repo create $NEW_REPOSITORY_NAME --public`
12. **Make the repo remote**: `git remote add new-auto-deployment https://github.com/$GITHUB_USERNAME/$NEW_REPOSITORY_NAME.git`
13. **Push the code to your remote repo**: `git push new-auto-deployment main`

## Full Script...

```bash
#!/bin/bash
SOURCE_REPO="https://github.com/kura-labs-org/c4_deployment-1.git"
NEW_REPOSITORY_NAME="firstDeploymentAutomated"
GITHUB_USERNAME='djtoler'
git clone $SOURCE_REPO
cd c4_deployment-1
gh repo create $NEW_REPOSITORY_NAME --public
git remote add new-auto-deployment https://github.com/$GITHUB_USERNAME/$NEW_REPOSITORY_NAME.git
git push new-auto-deployment main

