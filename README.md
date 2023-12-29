# RULES

## Introduction
The core idea is to use the main branch as a gateway to the *DeployDatabase* environment, this environment contains the access token to the website repo. *CODEOWNERS* & branch protection makes sure that contributors can not change workflows run in the environment. The environment only allows workflows in main to run within it. Note: contributors can still run workflows in different branches but those workflows don't have access to sensitive data in the environment.

## Settings

### Access token
Only select repositories -> select the website repo.\
Permissions:
- **Read and write**: Contents, Pull requests
- **Read-only**: metadata

All other repository permissions are **No access**.
All account permissions are **No access**

### Environments
No protection rules\
Allow administrators to bypass configured protection rules\
Deployment branches and tags:
- main

Environment secrets:
- access token to website repo

### Branch protection
Setup branch protection for all branches with the following settings:
- Branch name pattern: main
- Require a pull reqeust before merging
    - Require review from **Code Owners**
- Allow force pushes
    - Specify who can force push -> Admin
- Allow deletions

### CODEOWNERS
** @admin\
\<files you want to people to edit\>

### ACTIONS
- Allow Admin, and select non-Admin, actions and reusable workflows
    - Allow actions created by Github
    - Allow actions by Marketplace verified creators
- Require approval for all outside collaborators
- Read and write permissions
- Allow Github Actions to create and approve pull requests