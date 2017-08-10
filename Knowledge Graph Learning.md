# [Deep Neural Networks for Learning Graph Representation](https://www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/view/12423)

## Brief glance

- Publication: AAAI 2016

- Authors: Shaoshen Cao(Xidian), Wei Lu(sutd), QiongKai Xu(ANU).

- Topic: Graph representation, neural network.

- About: Learning low-dimentional vector representation for each vertex by capturing the graph structural information. Model use random surfing to capture graph structural directly.

![fig1](/figs/DNN-for-graph-prepresentation-fig1.png)

## Introduction

**Motivation:**

It's crucial to develop automated algorithms to extract useful information from graph.

**Drawbacks:**



TODO

# [Learning a Health Knowledge Graph from Electronic Medical Records](https://www.nature.com/articles/s41598-017-05778-z#Abs1)

## Brief glance

- Publication: Nature - scientific reports(March 2017)

- Authors: Maya Rotamensch(NYU), Yoni Helpern(NYU), Abdulhakim Tlimat(ER-Boston), Steven Horng, David Sontag.

- Topic: Knowledge graph, EHR, Noisy OR

- About: Using the shallow machine learning mathod(Logistic Regression, Naive Bayes and Noisy OR) to extract a knowledge graph about the diseases and symptoms from electronic health(medical) records. Evaluate their model by compare with the manually curated Google Health Knowledge Graph using automatical algorithm and professional physicians on both recall and accuracy.

## Introduction

**Motivation:**

Automated tools to support medical diagnostic reasoning is widely used by patients and clinicians. Diagnostic reasoning system showed great success in several application area of medical.

**Drawbacks:**

Current methodology demanded tremendous amount of expert time to manually build the system although it's brittle and difficult to adapt to new disease or clinical setting. At the mean time, automatic extract medical knowledge graph could speed up the devolopment of such diagnosing tools.

Previous work mostly using the NLP to find relationship between diseases and symptoms, but it could not deal with the electronic medical records(EHR).

**Difficult:**

- Text by medical stuff is informal.

- EHR is rich of reality commordities which is hard to handle.

- Links between disease and symptom in EHR are statical & confuse.

- EHR is filtered which could lead to unwilling information missing.

## Data Source

EHR: 273,174 records of emergency department patient between 2008 to 2013 from department of emergency medicine, Beth Isreal Deaconess Medical Center, Boston.

GHKG: Google Health Knowledge Graph. The nodes are diseases and symptoms, the edges are relation between disease and symptom.

## Data Preparation

Concept extraction from EHR: Extract positive mentions of disease and symptom contains ICD-9 codes and free-text(chief complaint, triage assesment, nursing notes, medical doctor comments).

GHKG: Subset of August 2015 where disease had at least 100 positive mentions and for symptom had at least 10 positive mentions (156 diseases and 491 symptoms).

## Model

**Construct the knowledge graph:** Learn the importance of edge should be included between symptom and disease with a threshold or edge numbers (Link prediction). 

**Logistic Regression (LR) & naive Bayes (NB):** Learn a model for each diseases.

*IMPT<sub>LR</sub> = Max(b<sub>ij</sub>, 0)*, where *b<sub>ij</sub>* is the weight in LR model.

*IMPT<sub>NB</sub> = log(p(x<sub>i</sub> = 1 | y<sub>j</sub> = 1)) - log(p(x<sub>i</sub> = 1 | y<sub>j</sub> = 0))*, If the appearance of disease makes the observation of symptom more likely.

**Baysian network with noisy OR gates** probablistic model that jointly models diseases and symptoms.

*P(x<sub>i</sub> = 1 | y<sub>1</sub>, ..., y<sub>n</sub>) = 1 - (1 - l<sub>i</sub>) ∏<sub>j</sub>(f<sub>ij</sub>)<sup>y<sub>j</sub></sup>*, where l<sub>i</sub> is leak probability, f<sub>ij</sub> is disease y<sub>j</sub> fail to turn on symptom x<sub>i</sub>.

*IMPT<sub>noisy-or</sub> = 1 - f<sub>ij</sub>*, for noisy OR, the diseases are not independent.


## Evaluation

1. auto-evaluate with GHKG on recall-precision.

2. two best model evaluate by physicians.

Compared by existance of edge, the physicians evaluate the top N result. Follow the rules:

disease A causes symptom B: always, somtimes, rarely, never.


## Result

1. GHKG is not exhaustive.

2. higer recall than GHKG

3. more precise language than GHKG

4. involve more sever edge

## Limitation

Could not infer causal relation from observation.


