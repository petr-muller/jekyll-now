---
layout: post
title: Radamsa: A general-purpose fuzzer
categories: tools
tags:
  - security
  - fuzzing
---

**Radamsa** is a general-purpose, black-box oriented mutating fuzzer. It is written in
Scheme and is available on its [GitHub page](https://github.com/aoh/radamsa) under a MIT
license. While the project is not completely abandoned (there are occasional commits on
`develop` branch, but last commit on `master` branch is a PR merge six months ago) there
does not seem much development going on anymore. The project is a side result of the
research done by [Oulu University Secure Programming
Group](https://www.ee.oulu.fi/roles/ouspg/FrontPage). The project has simple, but
straightforward and information documentation in the repository README file.

## Basics

Radamsa is described by its documentation as an "extremely black-box fuzzer": it does not
need any information about neither the input format nor the internals of the fuzzed
program. The tool starts with a sample input (probably valid) for a program, on which it
applies a mutation while trying to keep the general format valid(-ish). The root of
Radamsa was a research on automatic analysis of communication protocols.

Radamsa claims to be applicable, without any configuration, on programs processing any
format of input - binary or text.  Quick experiment s(see below) show that Radamsa is
quite successful - the applied mutations go well beyond random garbage being injected,
leading to valuable testing inputs for a program.



## Installation and usage

The instructions say building Radamsa is a simple clone-and-run-make process and I was
able to build a single, dependency-free binary without any problem. Mimicking few examples
from the documentation worked as expected: feeding my name to Radamsa's standard input
yielded multiple mangled variants which I imagine can cause havoc to naive string
processing routines.

The next experiment I tried was running Radamsa with a simple Python program as an input.
Again, the results were quite interesting, the applied modifications varied a lot but kept
a general structure of Python code. I saw lines being removed or duplicated, tokens being
changed (for example, integer literals being changed to a different value), but also quite
interesting mutations like the whole expression in a parenthesis being replaced by a
recursive-ish expression (think something like `a(a(a(a(a(a(a(a(a(b)))))))))`). Again,
several tries made me convinced these inputs would be valuable when trying to fuzz
something that processes Python grammar.

## When would I use it?
