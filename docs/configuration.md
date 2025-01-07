# Configuration

## Excluding functions

Functions can be excluded from analysis by putting a `nocl` comment
(case-insensitive) on the line of the name of function.

For example, to ignore a Python function:

```python
def some_function(): # nocl
    ...
```

or to ignore this Python function:

```python
def some_functions( # nocl
        some_numbers: list[int]
) -> int:
    ...
```

or to ignore this C function:

```c
void some_function(int a, const char *b) { // nocl
    ...
```

## Excluding files

Files can be excluded from analysis by using the `--exclude` option.
This option can be used multiple times and takes a [glob pattern](https://en.wikipedia.org/wiki/Glob_(programming)) as a
value, for example:

```shell
codelimit --exclude "*.generated.py" --exclude "docs/*" ...
```

The `--exclude` option extends the default exclusion list.
The default exclusion list is:

```python
[
    ".bzr",
    ".direnv",
    ".eggs",
    ".git",
    ".git-rewrite",
    ".hg",
    ".ipynb_checkpoints",
    ".mypy_cache",
    ".nox",
    ".pants.d",
    ".pytest_cache",
    ".pytype",
    ".ruff_cache",
    ".svn",
    ".tox",
    ".venv",
    ".vscode",
    "__pypackages__",
    "_build",
    "buck-out",
    "build",
    "dist",
    "node_modules",
    "venv",
    "test",
    "tests",
]
```
