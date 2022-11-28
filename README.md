# Setup malbolge action

![Release](https://img.shields.io/github/v/release/fabasoad/setup-malbolge-action?include_prereleases)
![Functional Tests](https://github.com/fabasoad/setup-malbolge-action/workflows/Functional%20Tests/badge.svg)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/fabasoad/setup-malbolge-action/main.svg)](https://results.pre-commit.ci/latest/github/fabasoad/setup-malbolge-action/main)

This action installs [malbolge](https://en.wikipedia.org/wiki/Malbolge) interpreter.

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[gcc](https://gcc.gnu.org).

## Inputs

| Name    | Required | Description                                                                                                | Default | Possible values |
|---------|----------|------------------------------------------------------------------------------------------------------------|---------|-----------------|
| version | No       | Version of `malbolge` tool that can be found [here](https://launchpad.net/ubuntu/trusty/+package/malbolge) | `0.2`   | `0.2`           |

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

```shell
Run malbolge hello-world.mal
Hello, world
```
