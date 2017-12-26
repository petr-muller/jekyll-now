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

## Installation and usage

The instructions say building Radamsa is a simple clone-and-run-make process and I was
able to build a single, dependency-free binary without any problem. Mimicking few examples
from the documentation worked as expected: feeding my name to Radamsa's standard input
yielded multiple mangled variants which I imagine can cause havoc to naive string
processing routines.

## When would I use it?
