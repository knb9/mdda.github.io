---
layout: post
category: AI
title: Evaluating entity linking with wikipedia - 2013
tagline: Paper Takeaway
date: 2014-10-30
tags: [NLP,NER,NEL,PaperTakeaway]
published: true
---
{% include JB/setup %}

{% include custom/paper_review %}

This write-up contains my first impressions of the paper : 
[Evaluating entity linking with wikipedia - (Hachey, Radford, Nothman, Honnibal &amp; Curran - 2013)](http://benhachey.info/pubs/hachey-aij12-evaluating.pdf).

### Paper Background

In this paper, the authors set out to recreate some of the key different methodologies in the NER space, only to find that benchmark results were difficult to reproduce - often for reasons extraneous to what the original authors claimed to have been demonstrating in their papers.  At the margin, experimental details dominated new breakthroughs.


### Surprising stuff

*  The authors found that 'simple stuff' made a difference at least as large as the reported algorithmic advances between the different sophisticated techniques

*  This 'simple stuff' were usually hand-crafted features that were found to work well, such as acronym expansion.  Or the way in which an exact indentification 'falls back' to other types of resolution

*  The competition format that has arisen recently (cite ...) gives rise to a 'beat the state-of-the-art in order to get published' mentality that is often detrimental to clear methodologies, and repeatable results


### Takeaway

In many ways, this is a meta-analysis paper.  In the process of evaluating the methodologies in several other papers, its main conclusions stem from the commonalities concerning 'minor' issues.  This, in itself, may be a more revealing : It's more important for pracititioners in the field to have the 'tricks of the trade' distilled out than just to hear on how each research group's own methodology incrementally pushes the frontier forward.

<!--
NEL = Named Entity Linking
IE  = Information Extraction (what is really required for Financial Task)
!-->
