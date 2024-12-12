<style>
.md-content .md-typeset h1 { display: none; }
</style>

<div align="center">
    <img src="assets/logo.png"/>
</div>

<p align="center">
    <em>Your Refactoring Alarm</em>
</p>

<div align="center">
    <a href="https://github.com/getcodelimit/codelimit/blob/_codelimit_reports/main/codelimit.md" target="_blank">
        <img src="https://github.com/getcodelimit/codelimit/blob/_codelimit_reports/main/badge.svg?raw=true" alt="Badge" class="off-glb">
    </a>
</div>

No developer writes unmaintainable code on purpose, yet a lot of code is unmaintainable.

How does that happen?

Actually, most code start out easy, but over time it becomes harder to
maintain, until it's unmaintainable.

## How to prevent unmaintainable code?

The best way to prevent unmaintainable code is to refactor it before it becomes
unmaintainable.

Developers can make simple things complex, like unmaintainable code, but they
are much better at making complex things simple. Refactoring makes complex code
simple again.

But when to refactor? How much to refactor? What to refactor? That's where CodeLimit comes in.

## Meet CodeLimit

CodeLimit is a tool for developers with one goal: _it tells the developer when
it’s time to refactor_.

### Key features and design principles

* **A non-controversial code metric**: Most developers agree longer functions
  are harder to maintain
* **Actionable results**: There's always a refactoring possible to make
  functions smaller
* **Runs everywhere**: Fits your development workflow, whether it's in a [build
  pipeline](getting-started/development-workflow.md), a [pre-commit
hook](getting-started/development-workflow.md#pre-commit-hook), or
[standalone](getting-started/standalone-usage.md)
* **Covers many languages**: A single tool for all your projects
* **Sane defaults**: Zero configuration, but allows customization
* **Low threshold to get started**: Can only check new or modified code, so
  even if you have a backlog of technical debt, you can start using CodeLimit
today

*[functions]: Also called methods or procedures, depending on your programming language

## Next steps

Go to the [Getting Started](getting-started/development-workflow.md) section to
start using CodeLimit, or read more about the [function length
metric](why-function-length.md).
