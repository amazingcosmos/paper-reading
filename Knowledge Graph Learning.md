# Deep Neural Networks for Learning Graph Representation

TODO

# Learning a Health Knowledge Graph from Electronic Medical Records

## Brief glance

- Publication: Nature - scientific reports(March 2017)

- Authors: Maya Rotamensch(NYU), Yoni Helpern(NYU), Abdulhakim Tlimat(ER-Boston), Steven Horng, David Sontag.

- Topic: Knowledge graph, EHR, Noisy OR

- About: Using the shallow machine learning mathod(Logistic Regression, Naive Bayes and Noisy OR) to extract a knowledge graph about the diseases and symptoms from electronic health(medical) records. Evaluate their model by compare with the crucial-made Google Health Knowledge Graph by automatical algorithm and professional physicians as both recall and accuracy.

## Intro

Motivation:

Automated tools to support medical diagnostic reasoning is widely used by patients and clinicians. Diagnostic reasoning system showed great success in several application area of medical.

Drawbacks:

Current methodology is the demanding of tremendous amount of expert time to manually build the system and its brittle and difficult to adapt to new disease or clinical setting. While automatic extract medical knowledge graph could speed up the devolopment of diagnosing tools.

Previous work mostly using the NLP to find relationship between diseases and symptoms, but it could not deal with the electronic medical records(EHR).

Difficult:

- Text by medical stuff is unformal.

- EHR is rich of reality commordities which hard to handle.

- Link between disease and symptom in EHR is statical & confuse.

- EHR is filtered which could cause information missing.

## Data Source

EHR: 273,174 records of emergency department patient between 2008 to 2013 from department of emergency medicine, Beth Isreal Deaconess Medical Center, Boston.

GHKG: Google Health Knowledge Graph. The nodes are diseases and symptoms, the edges are relation between disease and symptom.

## Data Preparation

Concept extraction from EHR:















