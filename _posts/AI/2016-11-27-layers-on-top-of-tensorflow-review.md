---
layout: post
category: AI
title: Layers on top of TensorFlow - Summary
tagline: Compare and Contrast
date: 2016-11-27
tags: [NeuralNetworks,TensorFlow]
published: false
---
{% include JB/setup %}


## Review of TensorFlow Sugar Coatings

>  NB:  This is an opinionated review, which I put together to help me make a decision.


As someone who has worked most extensively with ```Theano```/```Lasagne``` (with a bit of ```Blocks``` thrown in),
looking at raw ```TensorFlow``` makes me want to reach out for some additional helper 
layers.  There are lots of contenders, several of which are backed by Googlers, each 
with a different emphasis and style.


### Basic considerations

```TensorFlow``` itself is too raw : Something that would help smooth out the defaults, and 
figure out the sizing, etc would be useful.  Even better if there were several of the more
sophisticated modules prebuilt (Bi-LSTM, attention, dropout, sane initialisation, batch normalisation, etc).

```Keras``` is an obvious contender, however : 

*  Because it has switchable backends, Keras much effectively 'take over' the computational graph.
*  However, I feel that getting access to the 'raw layers' may be helpful in some circumstances,
   which means that ```Keras``` is basically ruled out as a contender.
   

### Google-related offerings

*  ```TF-Slim```
*  ```PrettyTensor```
*  ```TFlearn```

```TF-Slim``` is part of the main ```TensorFlow``` repo, and initially looked promising.  However,
it appears that the main focus is on CNN applications - and the breadth of other modules isn't really there.
For instance, there has been an Issue requesting an RNN implementation open for the last 6 months without
any positive response other than 'we (i.e. Google) will get to it soon' - which is pretty unhelpful for a nominally Open Source package.

```PrettyTensor``` is apparently produced by Googlers, but not in the official ```TensorFlow``` mainline.



### Third-Party ```TensorLayer```
