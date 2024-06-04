---
layout: post
title: "What is machine learning?"
date: 2024-06-03 19:22:00 +0100
categories: Machine Learning
author: Luigi Assenza
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript">
</script>

To understand what machine learning is, it’s better to look at its goal: to produce a prediction given an input. Or better to produce an outcome given an input.

So it needs to transform an input into an output. This is done through a mathematical function: a mathematical function is nothing but something (a technology if you like) that takes an input and gives back an output.

So the role of machine learning is to produce that mathematical function.
A mathematical function is a combination of its parameters (high parateres in the language of machine learning).

We then need to determine what function to use. Essentially its shape.
A "shape" of a function is defined by its parameters and how these parameters are combined together.

For example, in a linear regression we have two parameters, $$m$$ (the slope) and $$b$$ (the intercept, the bias in machine learning language) and they are combianed (guess how) linearly:

$$y = mx + b$$

These parameters are combined in a linear fashion with their input (only one input in this case x). So the role of machine learning is to find out the value of m and b. But not just any value of course, but the best values for m and b.

In matrix notation:

$$y = m_1x_1 + m_2x_2 + \dotsc + m_nx_n + b$$

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
$$

$$y = m^Tx + b$$

Even deep learning model is a function. A big one but a function.
Considering a simple neural network with two input layers, two hidden layers and one otput layer, the fuction is

$$
x =
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
=
\begin{bmatrix}
a_0^1 \\
a_0^1 \\
\end{bmatrix}
=
a^0
$$

$$
W^1 =
\begin{bmatrix}
w_{11}^1 & w_{12}^1 \\
w_{21}^1 & w_{22}^1 \\
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

$$
W^2 =
\begin{bmatrix}
w_{11}^2 \\
w_{21}^2 \\
\end{bmatrix}
,
A^2 = a^2
,
b^2
$$

$$
o =
\widehat{y}
,
\sigma(x)
$$

So the function becomes:

$$
Z^1 = W^{1T}A^0 + b^1 \\
A^1 = \sigma(Z^1) \\
Z^2 = W^{2T}A^1 + b^2 \\
\widehat{y} = \sigma(Z^2)
$$

Then as a single formula it becomes:

$$
\widehat{y} = 
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

And if $$\sigma()$$ is the `ReLU` function:

$$f(x) = max(x, 0)$$

for both $$\sigma^1$$ and $$\sigma^2$$, then we have:

$$
\widehat{y} = 
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
 
What do we mean by the best values? The best values are determined by the input values we use. It’s from the input values we use that the machine (our algorithm) “learns”. In this context we need to define an algorithm that learns from the input data we pass. But the algorithm, to be considered as such, needs to have a goal. The goal is defined by the so-called loss function (or objective function). Or more precisely the minimisation of the loss function. The algorithm is then a problem of mathematical optimization.
