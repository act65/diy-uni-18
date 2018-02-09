
Course in data science, machine learning and related math.

## Semester 1

#### Math 441: (Online and/or convex) Optimisation

* Is online optimisation equivalent to memory-limited optimisation?
* What are the distinct problems that non-convex optimisation brings?

Readings

* [Potential-Function Proofs for First-Order Methods](https://arxiv.org/abs/1712.04581)
* Time and memory complexity
* Case study on [ADAM]() and its repair [AMSGRAD]()
* Lagrangian duals
* Regularisers as projections into the 'right' geometry.

Projects

* Implement streaming PCA
* Tree based frequency sketch. Efficient memory in online setting.
* Local gradient statistics <!-- Why is the necessary? Pathological surfaces that make point estimates useless -->
* Kronecker-factored approximation (Higher order gradients)

#### Data science 452: Credit assignment

* What conditions make assigning credit hard?
* Why do we want gradients/why do we care?
* What problem does AD solve?

<!-- How do ES assign credit? A counterfactual. -->

Readings

* Biologically plausible credis assignment: [Equilibrium Propagation](), [Backprop in deep cortical microcircuits](), 
* [Backprop as Functor](https://arxiv.org/abs/1711.10455)
* [Learning long-term dependencies w GD is difficult](http://www.iro.umontreal.ca/~lisa/pointeurs/ieeetrnn94.pdf)
* Temporal differences?

<!-- * [Understanding Synthetic gradients]() -->

Projects

* Implement [doubly recursive AD](http://dankalman.net/preprints/mmgautodiff.pdf)
* Implement efficient graph based reverse AD (not sure about this one...)
* Long-term dependencies: pathological settings and the relationship to entropy (?)
* Alternative credit assignment

## Semester 2

#### Math 447: Tensor networks

Readings

* Case study: Singular value decomposition(s) - HOSVD, HSVD
* [Matrix multiplication algorithms from group orbits](https://arxiv.org/abs/1612.01527)
* ?

Projects

* Reshaping tensors, what is this really doing?
* Implement and explore the properties of a complex tensor network
* Implement [Strassen's Algorithm for Tensor Contraction](https://arxiv.org/abs/1704.03092) / [Designing Strassen's algorithm](https://arxiv.org/abs/1708.09398)
* ?


#### Data science 453: Learning discrete models

_Somewhat based off [David's course on Learning Discrete Latent Structure](https://duvenaud.github.io/learn-discrete/)_

<!-- What about learning PGMs -->

Readings

* Non differentiable ops: Stochastic, discrete, unknown. [Rebar](), [concrete distribution](https://arxiv.org/abs/1611.00712), ?. 
* [Backpropagation through the Void](https://arxiv.org/abs/1711.00123)
* Alternatives and approximations to gradients
* Combinatorial optimisation
* [TernGrad]()

Projects

* Extract/distill an automata from a (recurrent) neural network
* Non-linearities in linear networks exploited by ES
* Quantisation ... ?
* Quantised gradients

## Semester 3

#### Eng 377: (Graph) signal processing

* Sparse representations: The fourier transformation
* The laplacian
* Graph embeddings for ML

#### Stats 323: (Statistical) learning theory

* Sample complexity
* Assumptions about the data (IID, noise, ...)
* Complexity measures and bounding generalisation
* Overfitting

## Semester 4

#### Representation/approximation theory

* Curve fitting
* Deep vs wide
* Alternative representations?
* Factorisation machines
* Neural networks as a tensor decomposition?

#### Natural language processing
<!-- Could spend a whole year on this... Linguistics, evolution of language, programming languages, types, ... ?-->

Readings

* Question answering
* Summarisation
* Entailment

Projects

* ?


## Project

> Automated science and math.

Math and science have become too big for individuals. We find it hard to keep up and to cram the relevant knowledge into our small heads. We need better tools to continue push the boundaries.
