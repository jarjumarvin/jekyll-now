---
layout: post
title: An Introduction to Artificial Intelligence - Part 1
published: true
---


Over the past couple of months, I have been quite fascinated by **machine learning [ML]** and **artificial intelligence [AI]**. So much so that I am now even considering going into AI / ML research after I finish my bachelors degree in computer science.

That being said there's still quite a lot of time until then so let's move on to today's topic: real neurons vs cyber neurons

<!--more-->

# What is a Neural Network?

> In neuroscience, a biological neural network is a series of interconnected neurons whose activation defines a recognizable linear pathway.The interface through which neurons interact with their neighbors usually consists of several axon terminals connected via synapses to dendrites on other neurons.

# The Structure of a Neuron

<p align="center">
  <img src="{{ "/images/neuron.png"}}" alt="Image of a Neuron"/>
</p>

Let's consider the biological Neuron. It is a cell that receives, processes and transmits information. It can generally be broken down into four major parts:

* **Dendrites** receive signals from another neuron
* The **cell body** processes all incoming signals and fires a signal once a certain threshold value is reached
* The **axon** guides the signal towards the dendrites of other neurons
* **Synapses** connect two neurons and transmits the signal from neuron #1 to neuron #2

Neurons exhibit an **all-or-nothing** behaviour. They either fire a signal, or they don't. Hence, their output is binary. In the case of a signal being fired, it travels along the axon to the synapses, where it is transmitted to the next neuron down the line.

These connections between two neurons are **weighed**. The strength of a signal transmitted through any synapse is dependent on the [**synaptic potential**](https://en.wikipedia.org/wiki/Synaptic_potential). Such a weighed connection can either decrease the transmitted signals strenght, or increase it.

# What is an Artificial Neural Network?

> Artificial Neural Networks or connectionist systems are computing systems inspired by the biological neural networks that constitute animal brains.

Artificial Neural Networks **[ANN]** are systems derived from the human (animal) nervous system. Their basic structure represents that of the nerve cells (neurons) which are present in the nervous systems of the human (animal) body.

## The Artificial Neuron

<p align="center">
  <img width="665" height="303" src="{{ "/images/artificialneuron.png"}}" alt="Diagram of an Artificial Neuron"/>
</p>

The artificial neuron is closely modeled after the biological ones present in our nervous systems:

* The **inputs** represent the signals the neuron receives from other nearby neurons
* **Weights** determine the strenght of an individual signal
* These signals are then **summed** to calculate the total input
* A **bias** is added to the total input, to allow for transformation
* An **activation function** calculates the neurons **output** from the input

## The Perceptron

The most basic form of an artificial neuron calculates it's output using an activation function called the **Heaviside step function**.

<p align="center">
  <img width="384" height="288" src="{{ "/images/512px-Dirac_distribution_CDF.svg.png" }}" alt="Heaviside step function"/>
</p>

$$				
	H[n] :=  \left\{\begin{matrix} 0, & n<0, \\ 1, & n>0 \\ \end{matrix}\right.
$$

This functions value is either 0 for negative arguments and 1 for positive arguments. A neuron with an activation function like this is called a [**perceptron**](https://en.wikipedia.org/wiki/Perceptron). The first implementation of such an algorithm dates back to the 1950s.

In general, a simple perceptron can be written as a mathematical function that maps it's input $\vec{x}$, a vector, to it's output $y$, a binary value.

$$
	y(\vec{x}) =\varphi\left(\sum\limits_{i=0}^n\omega_ix_i + b\right) = \varphi\left(W^T+b\right)
$$

where $\vec{\omega}$ are the weights to each input, $\varphi$ is the activation function, and $b$ is the bias

$$
	\vec{\omega} = \left[\begin{matrix}\omega_0\\\omega_1\\\vdots\\\omega_n\end{matrix}\right] 
$$


In mathematical terms, the output of a neuron is equal to the output of the step function $\varphi$, given the sum of all the dot products $\vec{x}*\vec{\omega}$ and the bias as an input.

It's simple to think that a single perceptron is no good on it's own, given that it can only output one of two values - 0 or 1. There is however a class of problems that even a single perceptron can solve on it's own:

<p align="center">
  <img width="480" height="360" src="{{ "/images/figure_scatterplot.png"}}" alt="Scatter Plot"/>
</p>

Imagine two sets of points, divided by a line. Such a collection is **linearly seperable** by a line. As such, a single perceptron can learn where that line is and after enough training correctly predict which set any given point P(x, y) in the plane belongs to. A problem like this is called a **classification problem**. It turns out, artificial neurons and neural networks are very efficient in solving them.

The line the perceptron comes up with to seperate the two sets is called the **decision boundary**. The **bias** mentioned above, allows the algorithm to shift that line along a direction. We will be talking about this in detail in the next post.

# Conclusion

As you can see, even a single perceptron can solve problems that were thought to be unsolvable by machines for a very long time.

Next time, we will be implementing a perceptron to solve a classification problem like the one above!
See you then and thank you for reading~
