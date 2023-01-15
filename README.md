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
    uses: suzuki-shunsuke/actionlint-workflow/.github/workflows/actionlint.yaml@31ce3ededd2a8e3037ed9ea42033a6ad0d137d2b # v0.1.0
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
