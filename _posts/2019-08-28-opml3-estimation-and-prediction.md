---
layout: post
title: "Estimation and prediction"
date: 2019-08-28 22:08:00 +0800
categories: one-page-learning
---

![alt](/img/figures/ml/drawing/estimation_and_prediction.png)

One of the machine learning basic is the concept of a model in a general view. Model is like a hypothesis, which represents some **GUESS** on something real.

For example, when we toss a coin several times in a row, let’s say it’s 10,000 times. Then the number of heads might be some value around 5,000 when the coin is ideal. As the number of flips $$(=N)$$ increases, the approximation gets closer to $$\frac{1}{2}$$. Note that each $$x$$ represents a random variable which contains 1 (head) or 0 (tail), i.e., $$x\in\{0, 1\}$$.

As $$N$$ increases, the variance of the parameter $$p_0$$ gets small. For instance, if N=100,000,000, just one or two more or fewer trials will not affect that much on the result. As the very same analogy, we say that the model M learns data more and more and gets stable. Then stop learning at some point when $$p$$ seems stable enough. When we find the optimal parameter $$p$$ for the model, then we call the parameter in a new term, $$\hat{p}$$. The process of finding the optimal $$\hat{p}$$ from data is parameter estimation.

Now the model $$\mathcal{M}$$ with the estimated parameter $$\hat{p}$$ can be used to decide whether the unknown trial will be ‘head’ or ‘tail’. This is called prediction of outcome (i.e., we can easily guess the coin will be head in $$\frac{1}{2}$$ probability without tossing it 10,000 times. It’s because we already get the estimated parameter $$\frac{1}{2}$$ in our memory.)

The left part of the figure depicts the parameter **estimation**, while the right part is the **prediction** of outcome. Most of the (parametric) machine learning models are built (=estimated) and used(in prediction) in this scheme.

Though the figure illustrates a naive parameter $$p$$ which is easy to know. More advanced and complex parametric models are still based on this concept of estimation and prediction.
