# Setup malbolge action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-malbolge-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-malbolge-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-malbolge-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-malbolge-action/actions/workflows/linting.yml/badge.svg)

This action installs [malbolge](https://en.wikipedia.org/wiki/Malbolge) interpreter.

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[gcc](https://gcc.gnu.org).

> `Windows` and `Linux` are the only supported OS at this moment

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
      - uses: actions/checkout@main
      - uses: fabasoad/setup-malbolge-action@main
      - name: Run script
        run: malbolge hello-world.mal
        shell: sh
```

### Result

```text
Run malbolge hello-world.mal
Hello, world.
```
