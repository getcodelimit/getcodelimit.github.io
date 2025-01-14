# Standalone Usage

## Installation

### Homebrew

CodeLimit is available on
[Homebrew](https://formulae.brew.sh/formula/codelimit):

```shell
brew install codelimit
```

### Pipx

To install the standalone version of CodeLimit in an isolated Python
environment using [pipx](https://pypa.github.io/pipx) run:

```
pipx install codelimit
```

### PyPi

To install the standalone version of CodeLimit for your default Python
installation run:

```shell
python -m pip install codelimit
```

### Platform binaries

Binaries for different platforms (macOS, Linux, Windows) are available on the
[latest release
page](https://github.com/getcodelimit/codelimit/releases/latest).

## Usage

Run CodeLimit without arguments to see the usage page:

```shell
$ codelimit

 Usage: codelimit [OPTIONS] COMMAND [ARGS]...

 CodeLimit: Your refactoring alarm.

╭─ Options ────────────────────────────────────────────────────────────────────╮
│ --verbose  -v            Verbose output                                      │
│ --exclude          TEXT  Glob patterns for exclusion [default: None]         │
│ --version  -V            Show version                                        │
│ --help                   Show this message and exit.                         │
╰──────────────────────────────────────────────────────────────────────────────╯
╭─ Commands ───────────────────────────────────────────────────────────────────╮
│ check          Check file(s)                                                 │
│ scan           Scan a codebase                                               │
│ report         Show report for codebase                                      │
│ app            CodeLimit GitHub App commands                                │
╰──────────────────────────────────────────────────────────────────────────────╯
```

### Scanning a codebase

To scan a complete codebase run:

```shell
codelimit scan path/to/codebase
```

<div id="scan.cast" style="z-index: 1; position: relative;"></div>

### Viewing a report

To view the report with hard-to-maintain and unmaintainable functions of a
codebase that was scanned before run:

<div id="report.cast" style="z-index: 1; position: relative;"></div>

<script>
  window.onload = function(){
    AsciinemaPlayer.create('/assets/scan.cast', document.getElementById('scan.cast'));
    AsciinemaPlayer.create('/assets/report.cast', document.getElementById('report.cast'));
}
</script>

### Checking files

To check a single file or list of files for functions that need refactoring,
run:

```shell
codelimit check a.py b.py c.py
```
