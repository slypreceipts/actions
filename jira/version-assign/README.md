# Version Assign
This composite action retrives assigns all tickets in the current repo performs a 
diff between the 2 commits and assigns all tickets to inputed release. This action should be used with version-create

## Inputs
| Name | Description | Required |
| ---- | ----------- | -------- |
| jira-project-key | The Jira Project Key | yes |
| jira-subdomain | The subdomain of your Jira cloud instance | yes |
| jira-email | Email of the machine user to make the call to Jira | yes |
| jira-token | Token of the machine user to make the call to Jira | yes |
| git-target | The git sha or branch to compare to | yes |
| git-source | The git sha or branch that has the lastest changes. Will be compared with the 'git-target' | yes |
| version-name | The name of the Jira version to assign tickets to | yes |

## Usage
```
jobs:
  jira:
    runs-on: ubuntu-22.04
    steps:
      - name: Assign Jira Tickets to Version
        uses: slypreceipts/actions-pub/jira/version-assign@develop
        with:
          jira-project-key: ${{ env.JIRA_PROJECT }}
          jira-email: ${{ secrets.JIRA_EMAIL }}
          jira-token: ${{ secrets.JIRA_TOKEN }}
          jira-subdomain: ${{ env.JIRA_SUBDOMAIN }}
          version-name: ${{ steps.version.outputs.NAME }}
          git-target: 'feature/branch'
          git-source: ${{ github.ref_name }}
```


      