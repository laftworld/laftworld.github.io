---
layout: post
title: "Research Questions and Reading Questions"
date: 2019-08-07 01:00:00 +0800
categories: research
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




##### Objective 2) To construct QA system as a questioner. _System_ asks, _user_ answers.  QA as dual learning for educational purpose.

##### Q1) Can system generate appropriate questions on (MARCO, SQUAD, WikiQA) datasets?

##### Q2) What are the limitations of previous research w.r.t. model architecture? What is the consequence w.r.t. its performance?

##### Q3) How large does the training cost? Is there any previous research which tries to reduce the training cost?

##### Q4) Is there any literature which applied dual learning that the role of the answerer is held by _user_ so that _user_ is included in the learning cycle of dual learning? If yes, how does the model look like? If no, what would be the benefit of the model?





## Reading Questions: general questions when reading a paper.

#### Basic information
###### Q) Bibliography
###### Q) Link
###### Q) Citation

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
