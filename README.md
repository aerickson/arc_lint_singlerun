# arc_lint_singlerun

## Overview

A helper for <a href="https://secure.phabricator.com/book/phabricator/article/arcanist/">Arcanist</a>'s lint feature. 

Scenario: You'd like `arc lint` to compile your source as a preflight check. You compile several projects in the same repo with a single command (e.g. `make build`). The problem is that `arc lint` will invoke the linter once per file in your change. This solves that problem.


## Directions

1. copy singlerun to your repo
1. rename it something more appropriate for your env
1. change the log and debug paths
1. configure your .arclint file

## Debug Output

```
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:47:04: PPID 22149: no previous run detected. starting...
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:47:04: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:01: PPID 22149: test is in progress or already complete.
2017-05-17 22:48:10: PPID 22149: run complete. 66 seconds elapsed.
--
```


## .arclint block

```
    "go-compile": {
      "type": "compile",
      "include": "(\\.go$)",
      "bin": ["tools/singlerun"]
    },
```
