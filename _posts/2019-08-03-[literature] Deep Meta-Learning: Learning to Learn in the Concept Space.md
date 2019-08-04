---
layout: post
title: "[literature] Deep meta-learning: Learning to learn in the concept space"
date: 2019-08-04 09:18:00 +0800
categories: research
---

# Questions for reading a paper
### This is a set of general questions that helps me to get involved in reading a paper.



## Basic information
### Q) Bibliography
@article{zhou2018deep,
  title={Deep meta-learning: Learning to learn in the concept space},
  author={Zhou, Fengwei and Wu, Bin and Li, Zhenguo},
  journal={arXiv preprint arXiv:1802.03596},
  year={2018}
}

Zhou, Fengwei, Bin Wu, and Zhenguo Li. "Deep meta-learning: Learning to learn in the concept space." arXiv preprint arXiv:1802.03596 (2018).

### Q) Link
[[Link]](https://arxiv.org/pdf/1802.03596.pdf)

### Q) Citation
25

## Motivation

### Q) What is the objective of this paper?
Presenting a good representation for meta-learning to reduce the workload to learn many related tasks.

### Q) What is the practical domain this paper conducted experiments (i.e., what is the desired task)?
N-way K-shot image recognition.

### Q) Is classification and recognition different?
Yes they are different. Image recognition task is to figure out an object from an image which contains multiple objects, while classification task is to put an target image into corresponding bucket.

### Q) Suggest the running example. What is the main point of the task?

|  ![Running example](/img/figures/zhou2018deep-running-example.png)      |
|:-------------:|
| *Running example*  |

The main point of the task is to recognize an image which is similar to pre-labeled images. However, the main point of the paper is meta-learning in concept space.

### Q) What is the limitation of the previous works?
The full potential of the previous works is still far from reach. For example, the accuracy of 5-way 5-shot recognition of natural images is around 60% despite humans surpass 90% with ease. They argue that this is __due to the lack of a good data representation__ for meta-learning.

### Q) What is the term this work is called (suggest abbreviation, if exists)?
DEML+Meta-SGD. DEML refers to deep meta-learning.

### Q) What is the objective of this paper? (to review / to prove / to supplement / to show)
To show the concept space representation increases the acc.

### Q) What is the main figure? What is the main point of it?

They applied MAML (model-agnostic meta-learning) onto low-resource NLG task.

|   ![Main-figure](/img/figures/zhou2018deep-main-figure.png){:height="300px" width="450px"}      |      
|:------:|
| Figure 1: Deep meta-learning: learning to learn in the concept space. The concept generator learns to extract concept-level representations to ease meta-learning, while being enhanced by the concept discriminator that recognizes the concepts. |

### Q) What is the contribution of this paper?
They proposed the concept space representation, which is good for learning-to-learn by increasing the data-effeciency.

## Background
### Q) What kind of attempts were there to solve the same problem?
There were many papers which try to increase the data- efficiency of the meta-learning. There might be some papers to resolve the workload for learning tasks, however, this paper does not introduces the trials of the same objective. Anyway, this paper is the first attempt to introduce the concept space in meta-learning.

*  (Li et al., 2006) present a Bayesian model for learning categories from a few examples per category.

* (Salakhutdinov et al., 2012) organize seen categories into super-categories to derive hierarchically structured priors for new categories using a hierarchical Bayesian model.

*  (Lake et al., 2011) develop a generative model that composes pen strokes into characters for handwritten character recognition

* (Wong & Yuille, 2015) extend this idea to natural images without relying on domain knowledge.

* (Bertinetto et al., 2016) suggest a feed-forward learner for learning deep neural networks to address the overfitting for few-shot learning

* (Hariharan & Girshick, 2016) generate dummy examples for the task of interest by using the geometric transformations inferred from existing examples of other categories.

*  Recently, (Xu et al., 2017) show a key-value memory networks for fewshot learning, which is not scalable due to the huge memory size and the heavy cost in memory retrieval.

* Other methods use metric learning to ease pairwise comparison between examples (Fink, 2005; Koch, 2015; Guillaumin et al., 2009; Schroff et al., 2015)

### Q) What is the limitation of the previous works?
Few-shot learning remains challenging for metalearning that learns a learning algorithm (metalearner) from many related tasks.

Few-shot learning is inherently challenging in the complicated instance space, where a few examples are insufficient
to describe the intended high-level information such as categories or concepts.

Current few-shot learning is complicated and heavy to learn.

### Q) Which paper is the most similar one? Why is that?
Not directly suggested.

Concepts more likely consist of rules rather than definitions (Ahn & Brewer, 1993). Instead of designing the rules by hand, we intend to leverage the power of deep learning. It is known that a deep convolutional neural network trained on large-scale image dataset can provide effective features for generic tasks (Donahue et al., 2014; Razavian et al., 2014; Zeiler & Fergus, 2014).

### Q) What point is the difference between that similar work and this paper?
This paper introduces concept space representation for meta-learner. This can be considered as one of model-based method.

## Model
### Q) Which ML model did they use?

The concept generator $\mathcal{G}$, parametrized by $\theta_{\mathcal{G}}$, is a deep neural network that could be any popular convolutional neural network such as AlexNet (Krizhevsky et al., 2012), Inception (Szegedy et al., 2015), VGG (Simonyan & Zisserman, 2014), or ResNet (He et al., 2016).

The meta-learner $\mathcal{M}$, parametrized by $\theta_{\mathcal{M}}$, learns to learn a learner for each task $\mathcal{T}$ based on train($\mathcal{T})$. Any existing meta-learner can be used in our framework (Vinyals et al., 2016; Ravi & Larochelle, 2017; Finn et al., 2017; Li et al., 2017; Snell et al., 2017). Matching Nets (Vinyals et al., 2016) is a non-parametric model for few-shot learning based on metric learning.

### Q) How many parameters are there?
When choosing Matching Nets as the meta-learner, the learner is a neural network with an input layer of size 2048, followed by one hidden layer of size 1024 with ReLU nonlinearities, and then an output layer of size 512. When choosing MAML or Meta-SGD as the meta-learner, the learner is a neural network with the same input layer, followed by two hidden layers of size 1024 and 512 with ReLU nonlinearities, and then an output layer of size 5.

### Q) How much was the training cost? What facilities did the authors use?
The batch size of examples for image recognition is set to 64 and the batch size of tasks is set to 4 and 2 for 1-shot and 5-shot recognition, respectively. The number of iterations is 60,000 in the experiments on MiniImagenet, Caltech-256, and CIFAR-100, and 20,000 in the experiments on CUB200.

### Q) Describe the algorithm.
| ![algo-meta-nlg](/img/figures/zhou2018deep-running-example.png) |
|:------------------:|
|  *Deep Meta-Learning* |

| ![algo-meta-learning-sgd](/img/figures/zhou2018deep-algorithm-deep-meta-learning-with-meta-sgd.png){:height="250px" width="350px"} |
|:----------------------:|
| *Deep Meta-Learning with Meta-SGD*  |



### Q) Suggest the main formulation.

$$
\min_{\theta_{\mathcal{G}},\theta_{\mathcal{M}},\theta_{\mathcal{D}}} \mathbb{E}_{\mathcal{T}\sim p(\mathcal{T}), (\mathbf{x},\mathbf{y})\sim \mathbb{D}}\left[ J(\mathcal{L}_{\mathcal{T}}(\theta_{\mathcal{M}}, \theta_{\mathcal{G}}), \mathcal{L}_{(\mathbf{x},\mathbf{y})}(\theta_{\mathcal{D}}, \theta_{\mathcal{G}} \right]
$$

### Q) What are the limitations of the model?


### Q) Is the code for replication available?
False.

### Q) What are the baseline models?

* Matching Nets
* DEML+Matching Nets
* MAML.
* DEML+MAML
* Meta-SGD
* DEML+Meta-SGD

## Dataset
### Q) Which dataset is used?
For concept discrimination tasks, we perform experiments on a subset of ImageNet (Deng et al., 2009).

For meta-learning tasks, we perform experiments on MiniImagenet (Vinyals et al., 2016), Caltech-256 (Griffin et al., 2007), CIFAR-100 (Krizhevsky, 2009), and CUB-200 (Wah
et al., 2011).

### Q) How large is the dataset (w.r.t. MB and w.r.t. the number of elements)?

##### Dataset for concept discrimination.
ImageNet-200. ImageNet(Deng et al., 2009) contains 14,197,122 images of 1,000 classes, including person, vehicle, plant, and so on. The whole dataset is too large, and so in our experiments we use a subset ImageNet-200 with 200 classes sampled from 900 classes (excluding the 100 classes used in MiniImagenet(Vinyals et al., 2016)). For images in each selected category, 90% examples are randomly chosen for training, and the remaining images are used for testing

##### Dataset for Meta-learning

*MiniImagenet.* The MiniImagenet dataset, first used in (Vinyals et al., 2016), consists of 60,000 color images of 100 classes, with 600 examples per class. For our experiments, we use the splits introduced by (Ravi & Larochelle, 2017). Their splits use a different set of 100 classes, which are divided into three disjoint subsets: 64 classes for metatraining, 16 classes for meta-validation, and 20 classes for meta-testing. Particularly, MiniImagenet and ImageNet-200 are mutually exclusive at class level.

*Caltech-256.* The Caltech-256 dataset (Griffin et al., 2007) is a successor to the well-known dataset Caltech-101. It consists of 30,607 color images of 256 classes. We use 150,
56, and 50 classes for meta-training, meta-validation, and meta-testing, respectively.

*CIFAR-100.* The CIFAR-100 dataset (Krizhevsky, 2009) contains 60,000 32 × 32 color images of 100 classes. We use 64, 16, and 20 classes for meta-training, meta-validation,
and meta-testing, respectively. In CIFAR-100, images are rescaled to 32 × 32. Consequently, the difficulty in recognizing different categories is greatly increased.

*Caltech-UCSD Birds-200-2011 (CUB-200).* The CUB200 dataset (Wah et al., 2011) contains 11,788 color images of 200 different bird species. We use 140 classes for meta-training, 20 classes for meta-validation, and test on the remaining 40 classes. In this fine-grained dataset, subtle differences between very similar classes can hardly be recognized even by humans.

### Q) Is the dataset available in public? If yes, where can we get that?
It seems that all dataset are available in public.

### Q) Suggest the sample data?
.

## Results
### Q) What kind of metrics did they use?
Accuracy.

### Q) How good is the result?
3\% - 11\% improvement for each experiment setting.

### Q) Are those metrics reasonable for this work? why is that?
Since the task is image recognition and all dataset are public, the metric (accuracy) is clear to be used.

### Q) What is the limitation of the results?
* The theoretical support for the concept space does not seem to be sufficient.

* The previous attempts for the same objective (i.e., to reduce the learning cost for meta-learning) were not precisely described.

* Accuracy table is suggested, but the training cost comparison table is not suggested. As the authors proposed their *concept space representation* to argue that previous approaches of meta-learning feels heavy to learn many tasks.

## Further Questions
### Q) Has the algorithm been applied to any (NLP, vision, speech) application?
The concept of concept space might be applied to NLP tasks. There seems to such literatures (Note that the citation is 25). I couldn't find such a literature yet. Let me figure them out soon.

### Q) If so, what are the tasks that the algorithm is applied to learn from?
.


### Q) Is any change to the algorithm needed for the (NLP, vision, speech) application?
.

### Q) Is this the only way to solve the problem?
.

### Q) Is the work applicable to the Question Answering task?
.
