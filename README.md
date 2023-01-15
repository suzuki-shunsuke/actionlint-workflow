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
    - aqua/actionlint.yaml
    - aqua/reviewdog.yaml
  push:
    branches:
    - main
    paths:
    - .github/workflows/*.yaml
    - aqua/actionlint.yaml
    - aqua/reviewdog.yaml
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
mkdir aqua
aqua g -o aqua/reviewdog.yaml reviewdog/reviewdog
aqua g -o aqua/actionlint.yaml rhysd/actionlint
```

```yaml
- import: aqua/*.yaml
```

## LICENSE

[MIT](LICENSE)
