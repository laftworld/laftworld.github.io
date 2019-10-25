---
layout: post
title: "Parameter tuning"
date: 2019-10-25 22:48:00 +0800
categories: one-page-learning
---

![alt](/img/figures/ml/drawing/optimization.png)

Each figure shows a decision boundary of classifying blue and red dots. The decision boundary of the above plot is not good for discriminating colored dots. The plot below shows the decision boundary which discriminates each dot well. The decision boundary above is an unlearned model, which is represented as $$\theta^0$$, while the decision boundary below is represented as $$\theta^*$$. $$\theta$$ is a symbol to represent the parameters of each model.

For supervised learning, the dataset is usually represented as $$\mathcal{D} = \{(\mathbf{x}^{(\ell)}, y^{(\ell)})\}_{\ell=1}^N$$. $$\mathbf{x}$$ is bold because it represents a vector, and $$\ell$$ is to count each datapoint (i.e., there are N data points).

The total loss $$L$$ for a batch is a sum of loss $$\mathcal{L}$$ for each datapoint. Note that $$\phi(\mathbf{x}^{\ell})$$ is a predicted value of $$\mathbf{x}^{(\ell)}$$. Here $$\phi$$ represents a model, and $$\theta$$ represents parameters in a model.

***Symbols***

$$\theta^0$$: unlearned parameters.

$$\theta^*$$: learned parameters (i.e., optimized parameters)

$$L = \sum_{\ell=1}^N \mathcal{L}(\phi(\mathbf{x}^{(\ell)}), y^{(\ell)})>\epsilon$$: Loss is larger than certain threshold $$\epsilon$$

$$L = \sum_{\ell=1}^N \mathcal{L}(\phi(\mathbf{x}^{(\ell)}), y^{(\ell)})<\epsilon$$: Loss is larger than certain threshold $$\epsilon$$
