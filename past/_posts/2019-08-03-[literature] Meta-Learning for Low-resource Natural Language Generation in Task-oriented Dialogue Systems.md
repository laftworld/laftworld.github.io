---
layout: post
title: "[literature] Meta-Learning for Low-resource Natural Language Generation in Task-oriented Dialogue Systems"
date: 2019-08-03 16:12:00 +0800
categories: research literature r1
---

# Questions for reading a paper
### This is a set of general questions that helps me to get involved in reading a paper.



## Basic information
### Q) Bibliography
@article{mi2019meta,
  title={Meta-Learning for Low-resource Natural Language Generation in Task-oriented Dialogue Systems},
  author={Mi, Fei and Huang, Minlie and Zhang, Jiyong and Faltings, Boi},
  journal={arXiv preprint arXiv:1905.05644},
  year={2019}
}

Mi, Fei, et al. "Meta-Learning for Low-resource Natural Language Generation in Task-oriented Dialogue Systems." arXiv preprint arXiv:1905.05644 (2019).

### Q) Link
[[Link]](https://arxiv.org/pdf/1905.05644.pdf)

### Q) Citation
0

## Motivation

### Q) What is the domain this paper is in?
Natural language generation in task-oriented dialogue tasks. In particular, low-resource NLG task.

### Q) What is the desired task?
to produce a natural language utterance containing the desired information given a semantic representation consisting of dialogue act types with a set of slot-value pairs.

### Q) Suggest the running example. What is the main point of the task?
![Running example](https://github.com/laftworld/laftworld.github.io/blob/master/img/figures/r1/running-example.png?raw=true)
*Running example*
The main point of the task is to fill in the slots with given information.

### Q) What is the limitation of the previous works?
Conventional methods using hand-crafted rules often generates monotonic utterances and __it requires a substantial amount
of human engineering work__. Recently, various neural approaches [Wen et al., 2015c; Tran and Nguyen, 2017; Tseng et al., 2018] have been proposed to generate accurate, natural and diverse utterances. However, __these methods are typically developed for particular domains__. Moreover, \emph{they are often data-intensive to train}. __The high annotation cost prevents developers to build their own NLG component from scratch__.

### Q) What is the objective of this paper? (to review / to prove / to supplement / to show)
To show Meta-NLG is more useful for the task.

### Q) What is the term this work is called (suggest abbreviation, if exists)?
Meta-NLG

### Q) What is the main figure? What is the main point of it?

They applied MAML (model-agnostic meta-learning) onto low-resource NLG task.

|   ![meta-learning-low-resource](https://github.com/laftworld/laftworld.github.io/blob/master/img/figures/r1/main.png?raw=true){:height="300px" width="450px"}      |      
|:------:|
| **Comparing meta-learning (Meta) to Multi-task learning (MTL)** |

### Q) What is the contribution of this paper?
They applied MAML (model-agnostic meta-learning) onto low-resource NLG task.

## Background
### Q) What kind of attempts was there to solve the same problem?
To solve the low-resource NLG task,
* simple data augmentation trick [Wen et al., 2016a]
* specialized model architectures, including conditional variational auto-encoders (CVAEs, [Tseng et al., 2018; Tran and Nguyen, 2018a; Tran and Nguyen, 2018b])
* adversarial domain adaptation critics [Tran and Nguyen, 2018a]
have been proposed to learn domain-invariant representations.

There are three categories of meta-learning methods:
* Metric-based: Siamese Network, Matching Network, Memory-augmented Neural Network, Prototype Net, Relation Network.
* Model-based: meta-learner based on LSTMs. Hypernetwork, MetaNet, TCML, etc.
* Optimization-based: Model-agnostic meta-learning (MAML)

### Q) What is the limitation of the previous works?
Datasets used by these methods are simple which tend to enumerate many slots and values in an utterance without many linguistic variations. As a consequence, over-fitting the slots and values in the low-resource target domain could even outperform those versions trained with rich source domain examples [Tran and Nguyen, 2018b].

### Q) Which paper is the most similar one? Why is that?
(Tran and Nguyen, 2018b) Van-Khanh Tran and Le-Minh Nguyen. Dual latent variable model for low-resource natural language generation in dialogue systems. In Proceedings of the 22nd Conference on Computational Natural Language Learning, pages 21–30, 2018.

This work tried to solve the same problem with model-based (dual latent variable model) method.

### Q) What point is the difference between that similar work and this paper?
[Tran and Nguyen, 2018b] is model-based, while this work is optimization-based.

## Model
### Q) Which ML model did they use?
* The baseline model is semantically conditioned LSTM (SCLSTM [Wen et al., 2015c])
* They implemented Meta-NLG based on the PyTorch SCLSTM implementation from [Budzianowski et al., 2018].

### Q) How many parameters are there?
Unknown.

### Q) How much was the training cost? What facilities did the authors use?
Unknown.

### Q) Describe the algorithm.

| ![algo-meta-nlg](https://github.com/laftworld/laftworld.github.io/blob/master/img/figures/r1/algorithm-meta-nlg.png?raw=true){:height="250px" width="350px"}        | ![algo-maml](https://github.com/laftworld/laftworld.github.io/blob/master/img/figures/r1/algorithm-maml.png?raw=true){:height="250px" width="350px"}           |
|:-------------:|:-------------:|
| *Algorithm Meta-NLG*  | *Algorithm MAML*      |


### Q) Suggest the main formulation.

$$
\theta^{Meta} = MetaLearn(\mathcal{T}_1, \ldots, \mathcal{T}_K) = \argmax_\theta \mathbb{E}_i\mathbb{E}_{\mathcal{D}_{\mathcal{T}_i}, \mathcal{D}_{\mathcal{T}_i^{\prime}}}(f_{\theta_i^{\prime}})
$$

$$
\theta^{\prime}_i = Adapt(\mathcal{D_{\mathcal{T}_i}, \theta}) = \theta-\alpha\nabla_\theta\mathcal{L}_{\mathcal{D}_{\mathcal{T}_i}}(f_\theta)
$$

### Q) What are the limitations of the model?
Task-oriented dialogue is severely restricted by its definition.

### Q) Is the code for replication available?
False.

### Q) What are the baseline models?
* Scratch-NLG
* MTL-NLG
* Zero-NLG
* Supervised-NLG
* Meta-NLG (proposed)

## Dataset
### Q) Which dataset is used?
Large-scale dialog dataset (MultiWoz, [Budzianowski et al., 2018].

### Q) How large is the dataset (w.r.t. MB and w.r.t. the number of elements)?
305.6MB, A total of 69,607 annotated utterances are used, with 55,026, 7,291, 7,290 utterances for training, validation, and testing respectively.

### Q) Is the dataset available in public? If yes, where can we get that?
Yes. Currently, MultiWoz 2.1 is available. [[Link]](http://dialogue.mi.eng.cam.ac.uk/index.php/corpus/)

### Q) Suggest the sample data?
{% highlight python %}
"SNG0827.json": {
     "goal": {
         "taxi": {},
         "police": {},
         "hospital": {},
         "hotel": {
             "info": {
                 "parking": "yes",
                 "pricerange": "moderate",
                 "area": "north"
             },
             "fail_info": {
                 "parking": "yes",
                 "pricerange": "expensive",
                 "area": "north"
             },
             "book": {
                 "stay": "4",
                 "day": "friday",
                 "invalid": false,
                 "people": "2"
             },
             "fail_book": {}
         },
         "attraction": {},
         "train": {},
         "message": [
             "You are looking for a <span class='emphasis'>place to stay</span>.
             The hotel should <span class='emphasis'>include free parking</span>
             and should be in the <span class='emphasis'>north</span>",
             "The hotel should be in the <span class='emphasis'>expensive</span>
             price range",
             "If there is no such hotel, how about one that is in the
             <span class='emphasis'>moderate</span> price range",
             "Once you find the <span class='emphasis'>hotel</span>
             you want to book it for <span class='emphasis'>2 people</span>
             and <span class='emphasis'>4 nights</span> starting from
             <span class='emphasis'>friday</span>",
             "Make sure you get the <span class='emphasis'>reference number</span>"
         ],
{% endhighlight %}



## Results
### Q) What kind of metrics did they use?
BLEU-4 and ERR

### Q) How good is the result?
BLEU-4 score [Papineni et al., 2002].

ERR is computed by the ratio of the sum of the number of missing and redundant slots in a generated utterance divided by the total number of slots in the DA.

### Q) Are those metrics reasonable for this work? why is that?
0.4365 - 0.6782 in BLUE-4

23.33\% - 2.19\% in ERR
ERR seems to be more reasonable than BLEU-4 because ERR is defined only for this domain adaptation task. However, in some situations, missing slots can be more important than redundant slots, and vice versa.

### Q) What is the limitation of the results?
* The absolute accuracy of the results does not seem high. 0.6782 (BLEU-4) is the highest.
* The fixed number of the window in BLEU-4 could be analyzed more as an ablation study.

## Further Questions
### Q) Has the algorithm been applied to any (NLP, vision, speech) application?
This is an implementation of the MAML algorithm onto NLP.

### Q) If so, what are the tasks that the algorithm is applied to learn from?
Task-oriented dialogue system. Each task represents each domain (hospital, taxi, etc).

### Q) Is any change to the algorithm needed for the (NLP, vision, speech) application?
The original MAML algorithm is applied to the task almost directly. The only difference is the domain deals with NLP. Thus the dataset and measure are different.

### Q) Is this the only way to solve the problem?
No. Four baseline models were suggested for comparison. Moreover, I have read these two pieces of literature similar to this work.
* **Text style manipulation:** Logeswaran, Lajanugen, Honglak Lee, and Samy Bengio. "Content preserving text generation with attribute controls." Advances in Neural Information Processing Systems. 2018.
* **Text content manipulation:** Wang, Wentao, et al. "Toward Unsupervised Text Content Manipulation." arXiv preprint arXiv:1901.09501 (2019).


### Q) Is the work applicable to the Question Answering task?
Domain-specific words in this work might be redefined as each speaker's context. Then the task would be regarded as each term of narration, which is needed to converge in a few shots onto the context of the speaker on the context of speakers.
