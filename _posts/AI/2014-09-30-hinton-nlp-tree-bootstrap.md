---
layout: post
category: AI
title: Scalable Hierarchical Distributed Language Model - Mnih and Hinton 2009
tagline: Paper Takeaway
date: 2014-10-07
tags: [NeuralNetworks,NLP,WordEmbedding,PaperTakeaway]
published: true
---
{% include JB/setup %}

{% include custom/paper_review %}

This write-up contains my first impressions of the paper :
[A Scalable Hierarchical Distributed Language Model - (Mnih and Hinton 2009)](https://www.cs.toronto.edu/~amnih/papers/hlbl_final.pdf).

### Paper Background

The main aim of the paper was to reduce the output stage of a next-word prediction task from an ```O(V)``` representation (where ```V``` is the vocabulary size) to a tree-based representation that is ```O(log(V))```.

This tree creation algorithm was a two-stage method : stage 1 involved operating on a random tree, so that some vector embedding could be performed, then stage 2 produced a tree based on the word vectors found in stage 1, and then produced the final word embeddings from there.  

### Surprising stuff

  * The paper reported that if words were allowed to appear multiple times in the tree, the training didn't seem to pick up multiple senses : The duplicate entries favoured rare words, in similar settings, rather than common, multi-sense words
  
  * The issues addressed in building trees (eg: how to reasonably divide up the samples at the node between left and right children) were those common in the tree recursive methods (e.g. CART) community - and it seemed like a less-than-in-depth treatment of an area that is actively researched
  
  * Unlike some other papers, this one included generous attribution of other people's ideas, and a clear exposition of the reasoning behind each choice at each decision point
  
  * Hierarchical methods were plainly a computational win over the 'full-V' LBL model.  However, it seemed like the authors had to 'pull out all the stops' to get perplexity performance to beat the complexity-competitive KN5 model
  
  * Also interesting, for using Restricted Boltzman Machines (though not explained here why they've "moved on", nor even mentioned, but to refer to previous benchmark results) : [Three new graphical models for statistical language modelling - (Mnih and Hinton 2007)](https://www.cs.toronto.edu/~amnih/papers/threenew.pdf)
  

### Ideas to Follow-Up

The paper [Learning word embeddings efficiently with noise-contrastive estimation - (Mnih 2013)](https://www.cs.toronto.edu/~amnih/papers/wordreps.pdf) seems to supercede this approach (the tree-element of which is also taken up in [Efficient Estimation of Word Representations in Vector Space - (Mikolov et al, 2013)](http://arxiv.org/abs/1301.3781)).  Will look at the former next.

