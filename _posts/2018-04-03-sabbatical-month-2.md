---
layout: post
title: Sabbatical, Month 2
categories: personal
tags:
  - sabbatical
---

I started working during my second university year (my first job was being a tester in Grisoft,
which later became AVG, which later merged with Avast) and I was employed non-stop since then. I
spent ten years with Red Hat, from where I moved to SAP Labs and had not taken any free time between
the jobs. So when I decided to leave SAP Labs, the idea of taking few months off was irresistible. I
did not have any clear idea of what I would like to achieve during the sabbatical. People often take
a career break to pursue a specific project, to work on a dream project. I did not have any such
goal. I knew I would like to reduce my book backlog, to live more healthy (exercise and sleep more),
get the driving license and finally, do more for fun, open-source coding.

# Python projects

I am already quite proficient in Python, so I went on to build some projects I had in my head for
some time. The projects are not that technologically advanced, so I decided to intentionally try
some new tools while working on them, and learn in the process. I am trying to use
[pytest](https://docs.pytest.org/en/latest/) for testing (along with some plugins) and
[mypy](http://mypy-lang.org/) and [Pylint](https://www.pylint.org/) for static analysis. I also
connected few modern, cloudy, GitHub-connected tools to my repos to evaluate how they work - I tried
[Codacy](https://www.codacy.com/), [Code Climate](https://codeclimate.com/),
[Codecov](https://codecov.io/), [Coveralls](https://coveralls.io/), [Dependency
CI/Tidelift](https://tidelift.com/) and [Travis CI](https://travis-ci.org/). I like the direction
where these tools are going, and I might write a post about them in the future.

## [Python Diff](https://github.com/petr-muller/pyff)

This is a Python-based toy project that is supposed to compare two versions of a Python module (say,
a part of a Git commit) and determine the syntactical/semantical difference between them. I do not
have a clear idea about what exactly could the detected differences be, but I am starting with
simple stuff like added/removed classes or methods and continue with detecting methods with changed
API or just implementation, etc. The initial goal is to provide some machine-readable artifact
describing the difference and then try to build further tools over them. Possible directions for
this project might be a GitHub PR commenter bot posting human-readable summaries of changes (I could
learn more about cloud services, GitHub API and natural language generation in the process), or
combining the difference data with other sources like code coverage and perhaps some machine
learning, and building a tool to predict "riskiness" of a Python project PR.

Of all my current project, I probably like Python Diff the best. After it moves a bit, I will do a
separate post about it, and I will surely consider doing a talk about it on some Python conference.

## [VtES Game Log](https://github.com/petr-muller/vtes)

In last autumn, I started playing [Vampire: the Eternal Struggle](http://www.vekn.net/what-is-v-tes)
(nearly dead, old-school, multiplayer CCG) again after a period of hiatus. I play using various
decks against various players in various settings (friendlies in a pub, online, tournaments) so I
decided to build a simple tool for tracking my games and results, going from a local, CLI-oriented
utility to first an online REST API and then possibly a web application. The underlying data
structures are trivial, so I would like to learn more about writing REST APIs (possibly
experimenting with some API tools like [Apiary](https://apiary.io/),
[Dredd](http://dredd.org/en/latest/) or [3scale](https://www.3scale.net/)) and running them on some
cloud platform like AWS or Openshift.

# Collaborations

After I finished in SAP, I let some of my friends know, we met and discussed some possible
collaboration.

## Engeto Testing Course

My former Red Hat colleague Filip founded an [IT education startup](https://engeto.cz) where one of
the things they do are courses. They do not have a course focused on software testing yet, so we
agreed we would collaborate on creating one together. I was mostly researching on what content to
include in the course until now. Now we finally have the research done, and we are following with an
outline, and we will start producing the actual content soon.

## Perun

[Perun](https://github.com/tfiedor/perun) is a very interesting pet project of my former colleague
of [VeriFIT](http://www.fit.vutbr.cz/research/groups/verifit/), Tomáš Fiedor. It is a long-term
performance tracking/control system which attaches your project's performance metrics (performance
test results, profiling information and the like) to your Git revision tree, so you can track,
analyze and visualize them over time, possibly spotting performance regressions as they happen
during development. We had a nice talk with Tomáš about possible directions of this project, one of
which was taking it into the cloud and making a Git/GitHub-connected web application (like Travis CI
or Code Climate) out of it. Unfortunately, this was the one project for which I failed to allocate
sufficient time :(

# Books

## [Agile Testing](http://a.co/bRIw1v0)

I have started reading this one in January already but had a hard time finishing it because it
became quite tedious to read (it tends to be repetitive and vague). I managed to finish it in March,
finally. It is starting to show its age because it focuses so much on managing situations where a
tester's company is not that friendly to Agile, transitioning from Waterfall or other non-ideal
situations not that common today. I liked the Agile Testing Quadrant and the last part about how
testers can contribute in different stages of an agile project.

## [Coders at Work](http://www.codersatwork.com/)

This is also a fatty (around 600 pages), but it reads well being in an interview format; at least
for me, it does. I am currently somewhere in the middle. It does not give a reader any straight
applicable material, but it is interesting to read because the interviewees have different
achievements and backgrounds. I especially like to compare answers of different people to identical
questions.

# Misc

I was not doing just IT stuff. I finally obtained my driving license, which took quite a lot of
time, although I managed to pass both exams on a first try. I also spent a lot of time on
physiotherapy exercises to treat my [jumper's
knee](https://en.wikipedia.org/wiki/Patellar_tendinitis). It healed nicely, but it seems to be back
after few football matches :(
