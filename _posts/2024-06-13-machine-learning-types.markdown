---
layout: post
title: "Machine learning types"
date: 2024-06-13 22:10:00 +0100
categories: Machine Learning
author: Luigi Assenza
comments_id: 2
image: /images/neural_network.png
---
<style>
  .footer-heading, .p-name {
    display: none;
  }
</style>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript">
</script>

# Types of machine learning
1. Supervised learning
    1. Regression (continous data [variables])
    2. Classification (categorical data: class/category)
    3. Deep learning
2. Unsupervised learning
    1. Clustering (segmentation)
    2. Dimentionality reduction
3. Semi-supervised learning    
4. Reinforcement learning

# Supervised learning
The machine is taught by example.
Algorithms:
1. Regression
    1. Linear Regression
    2. Decision Tree
    3. Random Forest
2. Classification
    1. Naïve Bayes Classifier
    2. Support Vector Machine
    3. Logistic Regression
    4. Decision Tree
    5. Random Forest
    6. K-nearest neighbour

# Unsupervised learning
Data with no label.
Algorithms:
1. K-means clustering

# Semi supervised learning

# Reinforcement learning
Reinforcement learning teaches the machine by trial and error.
Algorithms:
1. Artificial Neural Networks (ANN)

# Question to ask
1. What data do we have? (structured vs unstructured)
2. What is the quality of the data? (i.e. missing data, wrong data, misspelled data)
2. What is the size of the data?
3. What computentional power do we have (i.e. hardware: RAM, CPU, GPU...)
4. How much time do we have? (How urgent the task is)
5. What kind of goal are you trying to achieve?

{% if page.comments_id %}
    {% include comments.html issue_id=page.comments_id %}
{% endif %}