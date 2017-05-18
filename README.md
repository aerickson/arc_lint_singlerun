# arc_lint_singlerun

## Overview

A helper for <a href="https://secure.phabricator.com/book/phabricator/article/arcanist/">Arcanist</a>'s lint feature. 

Scenario: You'd like `arc lint` to compile your source as a preflight check. You compile several projects in the same repo with a single command (e.g. `make build`). The problem is that `arc lint` will invoke the linter once per file in your change. This solves that problem.


## Directions

1. copy singlerun to your repo
1. rename it something more appropriate for your env
1. change the log and debug paths
1. configure your .arclint file

## .arclint block

```
    "go-compile": {
      "type": "compile",
      "include": "(\\.go$)",
      "bin": ["tools/singlerun"]
    },
```
