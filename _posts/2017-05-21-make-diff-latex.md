---
layout: post
title: "Automatically generate an annotated PDF for revision with Latex"
date: 2017-05-21
---

After submitting a paper, the reviews may ask you to make a revision. You'd better annotate all the changes you have made. Here, a handy tool called `latexdiff` can help.

Simply invoke it like this (below is a Makefile).

```
DIFF=diff

diff:
    latexdiff --flatten ../path/to/ori/$(DOC).tex ./path/to/new/$(DOC).tex  > $(DIFF).tex
    pdflatex $(DIFF).tex
    bibtex $(DIFF)
    pdflatex $(DIFF).tex
    pdflatex $(DIFF).tex
```
