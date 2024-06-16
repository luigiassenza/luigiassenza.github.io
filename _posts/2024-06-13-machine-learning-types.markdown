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
1. Supervised learning (the model is traines on a labeled dataset, i.e. the target outcome variable is known)
    1. Regression (continous data [variables])
        1. Linear Regression
        2. Decision Tree
        3. Random Forest
        4. Gradient Boosting
    2. Classification (categorical data: class/category)
        1. Naïve Bayes Classifiers
        2. Support Vector Machines (SVMs)
        3. Logistic Regression
        4. Decision Tree
        5. Random Forest
        6. K-nearest neighbours
        7. K-means
        8. Hierarchical clustering
        9. Gaussian mixture models
        10. Hidden Markov models [? check if it's a classification model]
        11. Apriori [?]
    3. Deep learning
        1. Neural networks
2. Unsupervised learning (Used for clustering anlysis, like market segmentation or anomaly detection)
    1. Clustering (segmentation)
        1. K-means clustering
    2. Dimentionality reduction
        1. Principal Component Analysis (PCA)
3. Semi-supervised learning    
4. Reinforcement learning
    1. Artificial Neural Networks (ANN)
5. Self-supervised learning [?]

# Examples
1. Supervised learning
    1. Predicting real estate prices
    2. Classifying whether bank transactions are fraudulent or not
    3. Finding disease risk factors
    4. Determining whether loan applicants are low-risk or high-risk
    5. Predicting the failure of industrial equipement's mechanical parts
2. Unsupervised learning
    1. Creating customer groups based on purchase bahaviour
    2. Grouping inventory according to sales and/or manufacturing metrics
    3. Associations in customer purchase (customers who something may be interested in something else)
3. Reinforcement learning
    1. Teaching cars to park themselves and drive autonomously
    2. Dynamically controlling traffic lights to reduce traffic jams
    3. Training robots to learn policies using raw video images as input that they can use to repcliate the actions they see    

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