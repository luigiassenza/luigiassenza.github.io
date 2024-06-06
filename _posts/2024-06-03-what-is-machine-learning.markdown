---
layout: post
title: "What is machine learning?"
date: 2024-06-03 19:22:00 +0100
categories: Machine Learning
author: Luigi Assenza
comments_id: 2
image: /images/neural_network.png
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript">
</script>

To understand what machine learning is, it’s better to look at its goal: to produce a prediction given an input. Or better to produce an outcome given an input.

So it needs to transform an input into an output. This is done through a mathematical function: a mathematical function is nothing but something (a technology if you like) that takes an input and gives back an output.

So the role of machine learning is to produce that mathematical function.
A mathematical function is a combination of its parameters (also called model parameters).

We then need to determine what function to use. Essentially its shape.
A "shape" of a function is defined by its parameters and how these parameters are combined together.

For example, in a linear regression we have two parameters, $$m$$ (the slope) and $$b$$ (the intercept, the bias in machine learning language) and they are combianed (guess how) linearly:

$$y = mx + b$$

These parameters are combined in a linear fashion with their input (only one input in this case, $$x$$). So the role of machine learning is to find out the value of $$m$$ and $$b$$. But not just any value of course, but the best values for $$m$$ and $$b$$.

If we have more than one variable, let's say $$n$$, our linear function looks like:

$$y = m_1x_1 + m_2x_2 + \dotsc + m_nx_n + b$$

In matrix notation:

$$
y =
\begin{bmatrix}
m_1 & m_2 & \dotsc & m_n
\end{bmatrix} 
\times
\begin{bmatrix}
x_1\\
x_2\\
\dotsc\\
x_n
\end{bmatrix}
+ b
= m^Tx + b
$$

Even deep learning model is a function. A big one but a function.
Considering a simple neural network with one input layer, one hidden layer and one otput layer:

<figure>
    <img src="{{ page.image }}"/>
    <figcaption>Figure 1 - A simple neural network</figcaption>
</figure>

The function of this simple neural network can be built starting from its matrix elements.

In the input lavyer we have:

$$
x =
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
=
\begin{bmatrix}
a_1^0 \\
a_2^0 \\
\end{bmatrix}
=
a^0
$$

In the hidden lavyer we have:

$$
W^1 =
\begin{bmatrix}
w_{11}^1 & w_{12}^1 \\
w_{21}^1 & w_{22}^1 \\
\end{bmatrix}
,
Z^1=
\begin{bmatrix}
z_1^1 \\
z_2^1 \\
\end{bmatrix}
,
A^1 =
\begin{bmatrix}
a_1^1 \\
a_2^1 \\
\end{bmatrix}
,
b^1
$$

And in the output layer we have:

$$
W^2 =
\begin{bmatrix}
w_{11}^2 \\
w_{21}^2 \\
\end{bmatrix}
,
Z =
\begin{bmatrix}
z_1^2
\end{bmatrix}
,
A^2 = 
\begin{bmatrix}
a_1^2
\end{bmatrix}
,
b^2
$$

So the function in matrix notations becomes:

$$
Z^1 = W^{1T}A^0 + b^1 \\
A^1 = \sigma(Z^1) \\
Z^2 = W^{2T}A^1 + b^2 \\
\widehat{y} = \sigma(Z^2)
$$

$$\sigma(x)$$ is the activation fuction.

As a single formula it becomes:

$$
a_1^2 = 
    \sigma^2\Bigg(
        w_1^2
        \sigma^1\left(
            w_{11}^1x_1 + w_{21}^1 + b^1
        \right) 
        + 
        w_2^2
        \sigma^1\left(
            w_{12}^1x_1 + w_{22}^1 + b^1
        \right)
        +
        b^2
    \Bigg)
$$

If we choose the activation function $$\sigma()$$ to be the `ReLU` function:

$$f(x) = max(x, 0)$$

for both $$\sigma^1$$ and $$\sigma^2$$, then we have:

$$
a_1^2 = 
    max\Bigg(
        w_1^2
        max\left(
            w_{11}^1x_1 + w_{21}^1 + b^1,
            0
        \right) 
        + 
        w_2^2
        max\left(
            w_{12}^1x_1 + w_{22}^1 + b^1,
            0
        \right)
        +
        b^2,
        0
    \Bigg)
$$

In this case the parameters to adjust are:

$$w_{11}^1, w_{12}^1, w_{21}^1, w_{22}^1, b^1, w_1^2, w_2^2, b^2$$
 
But what do we mean by the best values?

In order to have a best value we need to determine what value we are aiming at. Once we know what the value is, we'll try to get closer and closer.

The value we are looking for is determined by the so called loss function (sometimes also called cost function or objective function).

The loss function, as the name implies, is something negative, something that we need to minimise. In a mathematical term, the goal is to reach the lowest point (a global mininum).

This process of optimisation aims at finding those function parameters such that the value of the loss function is minimal.

The best values are determined by the input values we use. We iteratively feed the input value trying to reduce the value of the loss function at each iteration untill a minimum is reached.

In this interation process the machine (our algorithm) “learns” from past experiences (the data we feed our model with).

In the iteration process we use hyperparameters: unlike the (model) paramters which are used by the machine learning model (the mathematical model) then are those that define the model, used for prediction once the model has been optimised, hyperparameters instead are not used directly by the mathematical model; they are indirectly used to build the mathematical model.

Example of hyperparameters are:
1. the maxiumum number of iterations to perform before the algorithm stops;
2. the learning rate, that is the step done by the gradient descent algorithm;
3. the number of neighbours ($$k$$) in the k-nearest neighbour algorithm.

{% if page.comments_id %}
    {% include comments.html issue_id=page.comments_id %}
{% endif %}