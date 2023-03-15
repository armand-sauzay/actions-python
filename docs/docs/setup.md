# Set up your repository

Once you have created a repository, you can set up your repository to use the actions in this repo.

Usually, in most CI/CD workflows, you'll need two actions:

- `CI` to run [lint](actions/lint.md) and [test](actions/test.md) on every push
- `Release` to run [lint](actions/lint.md), [test](actions/test.md) and [release](actions/release.md) on every push to `main` or `master`

## Required files in your repo for the actions to work

The actions in this repo require the following files to be present in your repository:

- [.commitlintrc.yaml](#commitlintrcyaml)
- [.pre-commit-config.yaml](#pre-commit-configyaml)
- [.releaserc.json](#releasercjson)

You can copy the files below and paste them in your repository:

### .commitlintrc.yaml

```yaml
extends:
  - "@commitlint/config-conventional"
```

### .pre-commit-config.yaml

```yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.3.0
    hooks:
      - id: check-yaml
      - id: end-of-file-fixer
      - id: trailing-whitespace
  - repo: https://github.com/alessandrojcm/commitlint-pre-commit-hook
    rev: v9.0.0
    hooks:
      - id: commitlint
        stages: [commit-msg]
        additional_dependencies: ["@commitlint/config-conventional"]
  - repo: https://github.com/python/black.git
    rev: 22.6.0
    hooks:
      - id: black
        language_version: python3
  - repo: https://github.com/pycqa/flake8.git
    rev: 3.9.2
    hooks:
      - id: flake8
        additional_dependencies:
          - flake8-black>=0.1.1
        language_version: python3
  - repo: https://github.com/PyCQA/isort
    rev: 5.12.0
    hooks:
      - id: isort
  - repo: https://github.com/pre-commit/mirrors-prettier
    rev: v2.7.1
    hooks:
      - id: prettier
        stages: [commit]
  - repo: https://github.com/rhysd/actionlint
    rev: v1.6.17
    hooks:
      - id: actionlint
  - repo: https://github.com/jumanjihouse/pre-commit-hooks
    rev: 3.0.0 # or specific git tag
    hooks:
      - id: shellcheck
      - id: shfmt
  - repo: https://github.com/pre-commit/mirrors-mypy
    rev: 0b037c2b59aa62dc3be3287d175295f1a5547eb9
    hooks:
      - id: mypy
        args: [--strict, --ignore-missing-imports, --allow-untyped-decorators]
        exclude: tests/
```

### .releaserc.json

```json
{
  "branches": ["main"],
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/github"
  ]
}
```

## CI

To set up CI, you need to create a workflow file in `.github/workflows/ci.yaml` with the following content:

```yaml
name: CI

on:
  workflow_dispatch:
  push:

jobs:
  lint:
    name: Lint
    runs-on: ubuntu-latest
    steps:
      - uses: armand-sauzay/actions-python/lint@v1

  test:
    name: Test
    runs-on: ubuntu-latest
    steps:
      - uses: armand-sauzay/actions-python/test@v1
```

You can just copy and paste this content in your `.github/workflows/ci.yaml` file.

## Release

To set up Release, you need to create a workflow file in `.github/workflows/release.yaml` with the following content:

```yaml
name: Release

on:
  workflow_dispatch:
  push:
    branches:
      - main
      - master

jobs:
  lint:
    name: Lint
    runs-on: ubuntu-latest
    steps:
      - uses: armand-sauzay/actions-python/lint@v1

  test:
    name: Test
    runs-on: ubuntu-latest
    steps:
      - uses: armand-sauzay/actions-python/test@v1

  release:
    name: Release
    runs-on: ubuntu-latest
    steps:
      - uses: armand-sauzay/actions-python/release@v1
```
