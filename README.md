# RULES

### Branch protection
Setup branch protection for all branches with the following settings:
- Branch name pattern: *
- Require a pull reqeust before merging
    - Require review from **Code Owners**
- Require status checks to pass before merging
    - PR-security-checks
- **Lock branch**
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