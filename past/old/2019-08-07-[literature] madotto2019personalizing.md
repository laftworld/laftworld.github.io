---
layout: post
title: "Research Questions and Reading Questions"
date: 2019-08-07 16:00:00 +0800
categories: research literature
---

# Questions


## Research Questions: specific questions when writing a paper.

### Thesis Level Objective: high-quality sentence generation.

##### Q1) Why do we need this research? How are human language utterance, intention, and context represented computationally? How did the previous research do? What are the limitations of previous research? How can they be supplemented? How can the effectiveness of the proposed method be proved? What is the contribution of this research?

##### Q2) How can the questions in Q1 be applied to QA as Information Retrieval?


### Conference Level Objective: high-quality sentence generation in QA as a single-turn IR task for educational purpose.


##### Objective 1) To construct QA system as a answerer. _User_ asks, _system_ answers. QA with meta-learning for information retrieval.

##### Q1) Can the system retrieve appropriate answer and supporting facts on (HotpotQA) dataset?

##### Q2) What are the limitations of previous research w.r.t. model architecture? What is the consequence w.r.t. its performance?

##### Q3) How large does the training cost? Is there any previous research which tries to reduce the training cost?

##### Q4) Consider each of the set of appropriate answers from _system_ as each task in MAML, and consider each of a question from _user_ as a one-shot training sample. Can MAML be applied to specify the set of appropriate answers as IR task?

##### Q5) Since the performance is near or over the human performance, what could be other contribution of this research?

##### Q6) What would be the benefit exploiting MAML to single-turn QA as IR?

##### Q) What would be the difference of interest between QA people and IR people?

##### Q) Since current search engine is already good for natural language. It means that it would be very tough to satisfy IR people. What would be the selling point to IR people?

##### Q) Check the baseline like EPS+BERT is available not to start from scratch.

##### Q) Is that the nature of the dataset?

## Reading Questions: general questions when reading a paper.

#### Basic information
###### Q) Bibliography
@inproceedings{madotto2019personalizing,
  title={Personalizing Dialogue Agents via Meta-Learning},
  author={Madotto, Andrea and Lin, Zhaojiang and Wu, Chien-Sheng and Fung, Pascale},
  booktitle={Proceedings of the 57th Conference of the Association for Computational Linguistics},
  pages={5454--5459},
  year={2019}
}

Madotto, Andrea, et al. "Personalizing Dialogue Agents via Meta-Learning." Proceedings of the 57th Conference of the Association for Computational Linguistics. 2019.

###### Q) Paper
[[Link]](https://www.aclweb.org/anthology/P19-1542)

###### Q) Citation
1

#### Motivation
###### Q) What is the domain this paper belongs to?
###### Q) What is the desired task?
###### Q) Suggest the running example. What is the main point of the task?
###### Q) What is the limitation of the previous works?
###### Q) What is the objective of this paper? (to review / to prove / to supplement / to show)
###### Q) What is the term this work is called (suggest abbreviation, if exists)?
###### Q) What is the main figure? What is the main point of it?
###### Q) What is the contribution of this paper?

#### Background
###### Q) What kind of attempts was there to solve the same problem?
###### Q) What is the limitation of the previous works?
###### Q) Which paper is the most similar one? Why is that?
Zhang et al. [2018] [[Link]](https://arxiv.org/pdf/1801.07243.pdf).

This paper suggested personalized dialogue dataset conditioned by profile information. The proposed models are Seq2Seq, KV Memory, etc.

###### Q) What point is the difference between that similar work and this paper?

#### Model
###### Q) Which ML model did they use for baseline and suggestion?
###### Q) How many parameters are there?
###### Q) How much was the training cost? What facilities did the authors use?
###### Q) Describe the algorithm.
###### Q) Find the main formulation.
###### Q) Is the code available?
###### Q) What are the baseline models?

#### Dataset
###### Q) Which dataset is used?
###### Q) How large is the dataset (w.r.t. MB and w.r.t. the number of elements)?
###### Q) Is the dataset available in public? If yes, where can we get that?
###### Q) Suggest the sample data?

#### Results
###### Q) What kind of metrics did they use?
###### Q) How good is the result?
###### Q) Are those metrics reasonable for this work? why is that?
###### Q) What is the limitation of the results?
##### Q) Is there other methods?

#### Further Questions
###### Q) Has the algorithm been applied to any (NLP, vision, speech) application?
###### Q) If so, what are the tasks that the algorithm is applied to learn from?
###### Q) Is any change to the algorithm needed for the (NLP, vision, speech) application?
###### Q) Is this the only way to solve the problem?
###### Q) Is the work applicable to the Question Answering task?


<!---
|        |           |
|:-------------:|:-------------:|
| *a*  | *b*      |
--->
