---
layout: post
title: Python Diff
categories: projects
tags:
  - python
  - static-analysis
---

**GitHub repository:** [petr-muller/pyff](https://github.com/petr-muller/pyff)

The idea of syntactic/semantic-aware diff tool was in my head since we needed
something similar for a project we were working in [Red Hat
Lab](https://research.redhat.com/) together with
[VeriFIT](http://www.fit.vutbr.cz/research/groups/verifit/) research group. We
wanted to connect code differences (git commits or PRs) with test results and
build a “riskiness classifier”. The rough idea was something like *”whenever
people change I/O code in method M of class C, test T tends to break”*. We were
missing the analyzer that would easily give us, in machine-readable format, what
actually changed in the code, besides changed lines that a simple `diff` tool
can give you. We somehow managed to build something ad-hoc for C code
differences and continued, but since then I thought the smart diff could be an
interesting project.

## Comparing abstract syntax trees

I decided to start in a simple way: take two versions of a Python file as in
input, and work over their AST to detect differences. There is an [AST
module](https://docs.python.org/3/library/ast.html) in Python standard library
that can parse Python code easily but I remembered a talk on Pylint which
described [Astroid](https://github.com/PyCQA/astroid) as an improved module
with more functionality (build for usage in Pylint). I wanted to use it but
failed to find a current documentation link; for some reason I kept discovering
`www.astroid.org` which is dead for some time (I discovered the [current
documentation](http://astroid.readthedocs.io) later).

So I decided to go with “vanilla” `ast` module for a while. I discovered the
very helpful [Green Tree Snakes - the missing Python AST
docs](https://greentreesnakes.readthedocs.io/en/latest/) documentation for it
and from there, the first steps were quite simple. I chose the approach of
driving the development by examples: I selected a git commit from a different
project, looked at the diff and asked myself *“what changed in that code?”*,
then went to implement the necessary code.

I have started with detecting added and removed imports, classes and high-level
methods in the module, followed by detecting simple changes of these entities
such as added/removed methods and changed implementations. The entities are
currently identified by name, which means renaming is not properly detected (it
will be reported as one class/method removed and another added). At the moment,
the only supported output is the natural language summary of the changes.

After I had this MVP version of `pyff` ready I went on to set up some necessary
project infrastructure: README, tests and some helper code.

## Further steps

I would like to implement a programatical API and a machine readable output format
(probably JSON), then follow with implementing further change types detection. I
will probably continue with the example-driven approach, but I would like to
implement some “smart” detection soon: something like recognizing that the
program was not semantically changed (for example, a simple variable rename) and
not reporting an implementation change in that case.
