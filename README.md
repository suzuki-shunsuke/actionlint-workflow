# actionlint-workflow

GitHub Actions Workflow for actionlint

## How To Use

Add `actionlint` to `Status checks that are required`.

```yaml
---
name: actionlint
on: pull_request
permissions: {}
jobs:
  actionlint:
    runs-on: ubuntu-24.04
    if: failure()
    timeout-minutes: 10
    permissions: {}
    needs:
      - actionlint
    steps:
      - run: exit 1
  main:
    uses: suzuki-shunsuke/actionlint-workflow/.github/workflows/actionlint.yaml@6196583ab88cd36f36f7260fca4e8e4b2c4c9b66 # v0.4.1
    permissions:
      pull-requests: write
      contents: read
```
