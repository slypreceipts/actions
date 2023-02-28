# Base Ref
The composite action gets the base ref to compare the difference between the current/new ref

## Inputs
No inputs

## Ouputs
| Name | Description |
| ---- | ----------- |
| base-ref | The base ref to compare to |

## Usage
```
jobs:
  jira:
    runs-on: ubuntu-22.04
    steps:
      - name: Get base ref
        id: git
        uses: slypreceipts/actions-pub/git/base-ref@develop
      - name: Generate Version Name
        id: version
        run: |
          BRANCH=${{ github.ref_name }}
          echo "NAME=${BRANCH#release/}" >> $GITHUB_OUTPUT
```


      