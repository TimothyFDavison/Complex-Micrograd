# Complex-Micrograd
Opening this repository to track my experiments with complex valued neural networks.

## Background
Many optimization problems which deal with complex valued parameters (e.g. 
in signal processing) treat the real and imaginary components of complex numbers as separate real valued channels. 

The reason for this separation is that complex differentiability - also known as holomorphicity - imposes rich 
but much stricter conditions on a function. Most functions used in neural networks do not satisfy these stricter 
conditions. In fact, Liouville’s theorem states that any bounded, entire (i.e., holomorphic everywhere on ℂ) function 
is constant which renders
such functions unusable for frameworks like gradient descent. For an intuition about this challenge, consider that 
in real-valued optimization, the gradient points in a single direction in the real domain. In contrast, the 
complex plane admits infinitely many directions of variation due to the additional degree of freedom introduced 
by phase.

This is unfortunate, because the practice of separation of a signal into its constituent real and complex parts 
necessarily loses structure and information about the input signal. To address this issue, Wirtinger calculus was
introduced.

Wirtinger calculus introduces partial derivatives with respect to a complex variable and its conjugate, allowing
for generalization of gradient-based optimization to non-holomorphic functions. It provides a framework by which 
one can build complex valued neural networks, and even complex valued transformers. 

## Experimentation
See `CVNN.ipynb` for what I'm working on so far. Beginning with a class to represent complex values, I intend to 
build a personal library for complex valued modeling. I'm using Karpathy's `micrograd` approach and strategy as a 
guide for my implementation.

## Resources
[The Complex Gradient Operator
and the CR-Calculus (Kreutz-Delgado, 2009)](https://arxiv.org/pdf/0906.4835)
[A short tutorial on Wirtinger Calculus with applications in
quantum information (Koor, 2023)](https://arxiv.org/pdf/2312.04858)
[nput Convex Neural Networks (Amos, 2017)](https://arxiv.org/pdf/1609.07152)
[Deep Complex Networks (Trabelsi, 2018)](https://arxiv.org/pdf/1705.09792)
