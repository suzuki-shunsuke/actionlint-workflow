# actionlint-workflow

[![License](http://img.shields.io/badge/license-mit-blue.svg?style=flat-square)](https://raw.githubusercontent.com/suzuki-shunsuke/actionlint-workflow/main/LICENSE) | [source code](.github/workflows/actionlint.yaml)

`actionlint-workflow` is a GitHub Actions Reusable Workflow for actionlint.

## How To Use

1. Add `actionlint` to `Status checks that are required`.
2. Create a workflow:

[workflow](.github/workflows/example.yaml)

```sh
mkdir -p .github/workflows
curl -Lq -o .github/workflows/actionlint.yaml https://raw.githubusercontent.com/suzuki-shunsuke/actionlint-workflow/refs/heads/main/.github/workflows/example.yaml
```
