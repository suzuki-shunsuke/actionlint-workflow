# actionlint-workflow

GitHub Actions Workflow for actionlint

## How to use

```yaml
---
name: actionlint
env:
  AQUA_POLICY_CONFIG: ${{ github.workspace }}/aqua-policy.yaml
on:
  pull_request:
    branches:
    - main
    paths:
    - .github/workflows/*.yaml
  push:
    branches:
    - main
    paths:
    - .github/workflows/*.yaml
permissions: {}
jobs:
  test:
    uses: suzuki-shunsuke/actionlint-workflow/.github/workflows/actionlint.yaml@main
    permissions:
      pull-requests: write
```

## Requirements

- reviewdog
- actionlint

```sh
aqua g -i reviewdog/reviewdog rhysd/actionlint
```

## LICENSE

[MIT](LICENSE)
