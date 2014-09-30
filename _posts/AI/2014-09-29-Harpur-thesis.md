---
layout: post
category: AI
title: Low Entropy Coding with Unsupervised Neural Networks - Harpur 1997
tagline: Thesis Takeaway
date: 2014-10-01
tags: [NeuralNetworks,PaperTakeaway]
published: false
---
{% include JB/setup %}

{% include custom/paper_review %}

This write-up contains a few takeaways that I had from the thesis :
[Low Entropy Coding with Unsupervised Neural Networks - (Harpur 1997)](http://mi.eng.cam.ac.uk/reports/svr-ftp/auto-pdf/harpur_thesis.pdf).


### Chapter 3 : Background

* Very nice, coherent overview of different approaches to unsupervised learning


#### 3.2.5 Do PCA neural networks have a role?

> While interesting from a biological perspective, neural PCA models in their simplest form have little practical use since they will almost always be outperformed by the method of singular value decomposition.

But it should be pointed out that showing that biological networks can be made to perform PCA using only local interactions validates the idea that using SVD in a more typical computer setting should not be dismissed as being biologically implausible.

* Could backpropagation be justified simply by putting the training target as an extension of the training data, and letting it self-reinforce?

* Isn't that 'just' a Restricted Boltzman Machine (modulo binary vs reals)?

* To show that backpropagation in deeper networks with nonlinearities could be taught using only local data, one would need to build up, showing, for instance, what class of non-linear single-layers would give rise to an near-equivalent Hebbian learning update rule.  For a start, check out references in "3.8.3 Nonlinear PCA"


### Chapter 4 : Introduction of Recurrent Error Correction (REC) networks

* Maybe it's because we're now spoilt by riches, but the toy problems the linear REC are demonstrated on (in 1997) are *really* small


#### 4.8 Novelty Detection

* Kohonen apparently had an interesting approach (and also mentioned earlier for his work on localisation and inhibition)

#### 4.10 Minimum reconstruction error as maximum likelihood

* It feels like a fast one has been pulled here.  What if 2 'x's are close enough for 'v' to blur over the two of them?  Not clear that the argument justifies the MLE claim as it stands.


### Chapter 5 : Constraints

* Rectified Linear Units are the first constraint considered (which is refreshing).  BUT the basic REC networks don't have a bias term (left for "future work"), however this could just be implemented as a constant ```ONE``` input (unless I'm thinking about it wrong).

* Local penalties per output unit maintain the biologically plausible theme

* In 5.4, the assumption that the ```a```s are independent is mentioned only briefly - but leads to a fruitful correspondence of terms

* The (loose) correspondence with the steps of the EM algorithm are suggestive.  On the other hand, it's interesting to consider the tradeoff of the (local) REC training steps, with the (global) EM optimisation.  If the REC does well, perhaps the EM could be justified as 'biologically plausible', in the same way that SVD is just a more efficient way of computing PCA by local networks.  Whether or not the EM correspondence holds, its interesting to think what 'global and efficient' methods can be supported by 'local but inefficient' implementations on biological networks.

