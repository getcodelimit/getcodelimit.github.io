# Development

After installing dependencies with `uv sync`, CodeLimit can be run from the
repository root like this:

```shell
uv run codelimit
```

For example, to check a codebase at `~/projects/fastapi` run:

```shell
uv run codelimit scan ~/projects/fastapi
```

## Local installation using pipx

To install the development repository locally run:

```shell
pipx install .
```

To install the `main` branch locally run:

```shell
pipx install git+https://github.com/getcodelimit/codelimit.git
```

Or to install another branch locally run:

```shell
pip install git+https://github.com/getcodelimit/codelimit.git@issue-123
```

## Building the binary distribution

Generate a self-contained binary:

```shell
uv run poe bundle
```

## Static documentation

Generating the static documentation:

```shell
uv run mkdocs build
```

See the output:

```shell
uv run mkdocs serve
```

Terminal sessions in the documentation are recorded with the [Asciinema
CLI](https://docs.asciinema.org/getting-started/) and stored in the `assets`
folder:

```shell
asciinema rec scan.cast
```
