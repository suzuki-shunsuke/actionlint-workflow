# actionlint-workflow

GitHub Actions Workflow for actionlint

## :warning: DEPRECATION: Use actionlint-action

https://github.com/suzuki-shunsuke/actionlint-action

## How to use

```yaml
---
name: actionlint
on:
  pull_request:
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
  actionlint:
    uses: suzuki-shunsuke/actionlint-workflow/.github/workflows/actionlint.yaml@6196583ab88cd36f36f7260fca4e8e4b2c4c9b66 # v0.4.1
    with:
      aqua_version: v1.32.3
      aqua_policy_config: aqua-policy.yaml
    permissions:
      pull-requests: write
      contents: read
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
