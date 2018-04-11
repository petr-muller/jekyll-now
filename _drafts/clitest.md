---
layout: post
title: clitest: Command Line Tester
categories: tools
tags:
  - shell
  - command line
---

It’s like Python’s [doctest](https://docs.python.org/3/library/doctest.html) but
for CLIs.

## Basics

Given a text file containing snippets of shell sessions (prompts with commands
and their expected outputs), `clitest` executes the snippets and verifies that
the actual output matches the described output.

## Installation and usage

Installation and usage is trivial: the whole `clitest` is just a single shell
script with no external dependencies. This makes it easy to include copies of
`clitest` in repositories. I was curious how is the little tool implemented in
shell and I discovered the code is actually quite nice and readable. I could not
resist to quickly run [ShellCheck](https://www.shellcheck.net/) on it and it
only spat out few style issues, so nice job.

## When would I use it?
