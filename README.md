# check the Jira issue status

This action will check the Jira issue status if it's done or not.
You can you use this action with enable the Auto-Merge, if the issue is done on Jira, so the pull request will be merged.
The will fail if it's not follow the below rules:
1. The name of the PR head branch not started with feature/, hotfix/, bugfix/, and it does not contain the issue name like MBA-123.
2. The issue is not mark as Done on JIRA.

## How to use:
```
name: "JIRA Check"
on:
  pull_request:
    types: [opened, edited, reopened, synchronize]
  
jobs:
  test_job:
    runs-on: ubuntu-latest
    name: A job to check JIRA issue
    steps:
      - uses: knawat/github-actions-jira@v1
        with:
          organization-name: 'knawat'
          jira-token: '******'
```