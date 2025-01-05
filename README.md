# Setup malbolge action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-malbolge-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-malbolge-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-malbolge-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-malbolge-action/actions/workflows/linting.yml/badge.svg)

This action installs [malbolge](https://en.wikipedia.org/wiki/Malbolge) interpreter.

## Supported OS

<!-- prettier-ignore-start -->
| OS      |                    |
|---------|--------------------|
| Windows | :white_check_mark: |
| Linux   | :white_check_mark: |
| macOS   | :x:                |
<!-- prettier-ignore-end -->

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[gcc](https://gcc.gnu.org).

## Inputs

```yaml
- uses: fabasoad/setup-malbolge-action@v0
  with:
    # (Optional) If "false" skips installation if malbolge is already installed.
    # If "true" installs malbolge in any case. Defaults to "false".
    force: "false"
```

## Outputs

<!-- prettier-ignore-start -->
| Name      | Description                           | Example |
|-----------|---------------------------------------|---------|
| installed | Whether malbolge was installed or not | `true`  |
<!-- prettier-ignore-end -->

## Example usage

### Input

This program should print "Hello, world":

```text
(=<`#9]~6ZY327Uv4-QsqpMn&+Ij"'E%e{Ab~w=_:]Kw%o44Uqp0/Q?xNvL:`H%c#DD2^WV>gY;dts76qKJImZkj
```

### Workflow configuration

```yaml
name: Test

on: push

jobs:
  example:
    name: malbolge
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: fabasoad/setup-malbolge-action@v0
      - name: Run script
        run: malbolge hello-world.mal
```

### Result

```text
Run malbolge hello-world.mal
Hello, world.
```
