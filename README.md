# OTTO Recommender System (Kaggle Competition)

This repository contains experimental notebooks developed for the Kaggle competition:

**OTTO – Multi-Objective Recommender System**

Competition page:  
https://www.kaggle.com/competitions/otto-recommender-system

---

## Overview

The goal of this competition is to build a recommender system that predicts user interactions in an e-commerce environment.

For each user session, the model must predict:

- clicks
- cart additions
- orders

based on the user's previous interactions during the same session.

The recommendation system aims to improve the online shopping experience by suggesting relevant products in real time.

---

## Competition Context

Online retailers offer millions of products, making it difficult for users to discover relevant items.

Recommender systems help guide users toward products they are most likely to interact with.

The OTTO competition dataset contains session-based interaction logs from one of the largest German online retailers.

Key characteristics:

- More than 10 million products
- Over 19,000 brands
- Session-based user behavior data

---

## Dataset

The dataset is provided by Kaggle and **cannot be redistributed in this repository**.

Please download the dataset from:

https://www.kaggle.com/competitions/otto-recommender-system/data

Main dataset files:

train.jsonl  
test.jsonl  
sample_submission.csv

### Data Structure

Each session contains a sequence of events:

| Field   | Description                         |
|--------|-------------------------------------|
| session | unique session id                   |
| aid     | article id (product id)            |
| ts      | Unix timestamp                      |
| type    | event type (click / cart / order)  |

---

## Task

The test dataset contains **sessions truncated by timestamp**.

The task is to predict the interactions that occur **after the truncation point**.

For each session, predictions must be generated for:

- next clicked item
- items added to cart
- items ordered

Up to **20 item IDs** may be predicted for each interaction type.

---

## Evaluation Metric

The competition uses **Recall@20** as the evaluation metric.

Recall is computed separately for:

- clicks
- carts
- orders

The final score is a **weighted average of the three recall values**.

Predictions are truncated to the **top 20 recommended items**.

---

## Repository Structure

Kaggle_OTTO/

├── OTTO_v0.ipynb  
├── OTTO_v0.0.ipynb  
├── OTTO_v1.2.ipynb  
├── otto_v2.1.ipynb  
├── otto_v2.2.ipynb  
├── otto_v2.3.ipynb  
├── otto_v2.4.ipynb  
├── otto_v3.1.ipynb  
├── otto_v3.2.ipynb  
├── otto_v4.1.ipynb  
├── otto_v4.2.ipynb  
├── otto_v4.fin.ipynb  
└── README.md

Each notebook represents different experiments or iterations of the recommender system pipeline.

---

## Method Overview

Typical recommender system workflow used in the experiments:

1. Session event preprocessing
2. Candidate item generation
3. Feature engineering
4. Ranking model training
5. Evaluation using Recall@20

---

## References

Wand, A., Normann, P., Baumeister, S., Wilm, T., Reade, W., Demkin, M.

OTTO – Multi-Objective Recommender System  
Kaggle Competition, 2022.

https://kaggle.com/competitions/otto-recommender-system