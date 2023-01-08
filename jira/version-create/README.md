# Version Create
The composite action retrives the jira project id and version id and creates a new jira project version if none currently exists

## Inputs
| Name | Description | Required |
| ---- | ----------- | -------- |
| jira-project-key | The Jira Project Key | yes |
| jira-subdomain | The subdomain of your Jira cloud instance | yes |
| jira-email | Email of the machine user to make the call to Jira | yes |
| jira-token | Token of the machine user to make the call to Jira | yes |
| version-name | The name of the Jira version to assign tickets to | yes |

## Usage
```
jobs:
  jira:
    runs-on: ubuntu-22.04
    steps:
      - name: Create Jira Version
        uses: slypreceipts/actions-pub/jira/version-create@develop
        id: jira
        with:
          jira-project-key: ${{ env.JIRA_PROJECT }}
          jira-email: ${{ secrets.JIRA_EMAIL }}
          jira-token: ${{ secrets.JIRA_TOKEN }}
          jira-subdomain: ${{ env.JIRA_SUBDOMAIN }}
          version-name: 'test version'
```