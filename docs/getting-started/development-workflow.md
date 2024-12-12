# Development workflow

## GitHub Action

CodeLimit is available as a [GitHub
Action](https://github.com/getcodelimit/codelimit-action)

When running as a GitHub Action, CodeLimit only checks modified files and
*warns* about functions that *should* be refactored and *fails* for functions
that *need* to be refactored.

To run CodeLimit on every push and before every merge to `main`, append it to
your GH Action workflow:

```yaml
name: 'main'

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
      - name: 'Checkout'
        uses: actions/checkout@v2

      - name: 'Run CodeLimit'
        uses: getcodelimit/codelimit-action@v1
```

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
