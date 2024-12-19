# Development workflow

## GitHub Action

CodeLimit is available as a [GitHub
Action](https://github.com/getcodelimit/codelimit-action)

Insert CodeLimit in your workflow like this: 

```yaml
- name: 'Run CodeLimit'
  uses: getcodelimit/codelimit-action@v1
```

When running as a GitHub Action, CodeLimit only checks modified files and
*warns* about functions that *should* be refactored and *fails* for functions
that *need* to be refactored.

An example of a workflow that runs CodeLimit on every push and before every
merge to `main`:

```yaml
name: 'codelimit'

on:
  push:
    branches: 
      - main
  pull_request:
    branches: 
      - main

jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - name: 'Checkout sources'
        uses: actions/checkout@v4

      - name: 'Run CodeLimit'
        uses: getcodelimit/codelimit-action@v1
```

### Status badge

A status badge is stored after each run in the `_codelimit_reports` branch of
the repository.

To get the Markdown for the badge run the CodeLimit CLI in a local checkout of
the repository, for example:

```shell

$ codelimit badge
[![CodeLimit](https://github.com/getcodelimit/codelimit/blob/_codelimit_reports/
main/badge.svg)](https://github.com/getcodelimit/codelimit/blob/_codelimit_repor
ts/main/codelimit.md)

✔ Badge Markdown copied to clipboard!
```

#### Meaning of the badge

If a repository contains functions that *exceed 60 lines of code*, the badge
will show:

<div align="center">
    <img src="../../../assets/badge-needs-refactoring.svg" alt="Badge needs refactoring" class="off-glb">
</div>

If a repository contains *no functions that exceed 30 lines of code*, the badge
will show:

<div align="center">
    <img src="../../../assets/badge-100.svg" alt="Badge needs refactoring" class="off-glb">
</div>

Otherwise, the badge will show the percentage of code that does not exceed 30
lines of code.

If that percentage is 80% or higher, the badge will be green:

<div align="center">
    <img src="../../../assets/badge-88.svg" alt="Badge needs refactoring" class="off-glb">
</div>

If that percentage is below 80%, the badge will be orange.

## Pre-commit hook

CodeLimit can be installed as a [pre-commit](https://pre-commit.com/) hook so
it alarms you during development when it's time to refactor:

```yaml
-   repo: https://github.com/getcodelimit/codelimit
    rev: 0.6.2
    hooks:
    - id: codelimit
```

CodeLimit is intended to be used alongside formatting, linters and other hooks
that improve the consistency and quality of your code (such as
[Black](https://github.com/psf/black),
[Ruff](https://github.com/astral-sh/ruff) and
[MyPy](https://github.com/python/mypy).) As an example pre-commit configuration
see the
[`pre-commit-config.yaml`](https://github.com/getcodelimit/codelimit/blob/main/.pre-commit-config.yaml)
from CodeLimit itself.

When running as a hook, CodeLimit *warns* about functions that *should* be
refactored and *fails* for functions that *need* to be refactord.
