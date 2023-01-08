# Version Release
The composite action release a Jira Project Version. This action should be used with version-create

## Inputs
| Name | Description | Required |
| ---- | ----------- | -------- |
| jira-subdomain | The subdomain of your Jira cloud instance | yes |
| jira-email | Email of the machine user to make the call to Jira | yes |
| jira-token | Token of the machine user to make the call to Jira | yes |
| version-id | The id of the Jira proversion version to release | yes |

## Usage
```
jobs:
  jira:
    runs-on: ubuntu-22.04
    steps:
      - name: Release Version
        uses: slypreceipts/actions-pub/jira/version-release@develop
        with:
          jira-email: ${{ secrets.JIRA_EMAIL }}
          jira-token: ${{ secrets.JIRA_TOKEN }}
          jira-subdomain: ${{ env.JIRA_SUBDOMAIN }}
          version-id: ${{ steps.jira.outputs.version-id }}
```