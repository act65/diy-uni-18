
Course in data science, machine learning and related math.

## Semester 1

#### Optimisation

Questions

<!-- * Is online optimisation equivalent to memory-limited optimisation? -->
* Optimisation as a search. Why dont typical search algols apply here?
* What are the distinct problems that non-convex optimisation brings?
* Why SGD for NNs? Why stochastic? Why (mini)-batched? Why does it work in practice? <!-- lack of spurious minima, ?, ... -->
* (How) Could/should past information effect current decisions? (aka momentum? relationship to dynamical/physical systems?!)
<!-- * As a dynamical system!? huh, it's possible for this to be in a limit cycle! what about bifurications based on hyperparams?) -->
<!-- * Bias and variance of gradient estimates?? -->

Readings

* Online optimisation: Mirror descent,  and [Potential-Function Proofs](https://arxiv.org/abs/1712.04581)
* Convex optimisation: Lagrangian duals, [Leveling with Lagrange](), ? (constrained optimisation?!)
* Combinatorial optimisation: (related to saticficing?)
<!-- * Momentum for non-convex optimisation: [ADAM]() and its update [AMSGRAD]() (a lack of theory here, or am I just unaware?) -->
<!--* Implicit bias. Neyshabur? -->
<!-- * Time and memory complexity -->
<!-- * Natural gradient descent (using the fisher) -->

Projects

<!-- * Alternatives to SGD. ES? ADMM? CG? Newtons? Fisher?  ... -->
* Local gradient statistics (must be distributed/collected over time or space -- the batch) <!-- Why is the necessary? Pathological surfaces that make point estimates useless. Want cheap, no-bias, estimates of the gradients -->
* Why don't higher order optimisation algols work with NNs? Kronecker-factored approximation, hessian free, block hessian, ...?
* Model based optimisation rather than black box optimisation!?
<!-- What if you tried to model the entire surface you are descending?! Model based optimisation!? Although we might be optimisating a black box, that doesnt stop us from using a model of it?! -->
<!-- * Reproduce [The marginal value of adaptive gradients](https://arxiv.org/abs/1705.08292) and explore -->


#### Credit assignment

Questions

* What conditions make assigning credit hard?
* Why do we want gradients/why do we care?
* What problem does AD solve?
* Can credit assignment be framed in a communication setting?
<!-- To assign credit, two things need to be, in some sense, connected. Ability to communicate feedback. -->

Readings

* Backprop and AD: [Backprop as Functor](https://arxiv.org/abs/1711.10455) and [?]()
* Is hard: [long-term dependencies](http://www.iro.umontreal.ca/~lisa/pointeurs/ieeetrnn94.pdf), memory usage?
* Alternatives: Temporal differences, 
* Biologically plausible credit assignment: [Equilibrium Propagation](), [Backprop in deep cortical microcircuits](), 

Projects

<!-- * Implement efficient graph based reverse AD (not sure about this one...) -->
* Implement [doubly recursive AD](http://dankalman.net/preprints/mmgautodiff.pdf)
* Show that there exist pathological problems where learning long-term dependencies is hard. Explore the relationship  between what makes long-term dependencies hard and entropy. (where am I going to get some data!?)
* Approximate credit assignment (for greater efficiency?)
* ?

#### Tensor networks

Questions

* Rank of high order tensors. Various types of decomposition. Solving for those decompositions. Notation.
* Reshaping tensors, what is this really doing?
* What priors do various structures encode? Hankel, conv, ... - locality, symmetry, ?
* Relationship to learning? (matrix completion?) [X_train, Y_train], [X_test, ?].
<!-- * What is happening when you contract over two paths? (marginalisation of two variables?) -->

Readings

* Case study: Singular value decomposition(s) - [HOSVD](), [HSVD](http://epubs.siam.org/doi/abs/10.1137/090764189)
* [Matrix multiplication algorithms from group orbits](https://arxiv.org/abs/1612.01527)
* [Deep multi grids](https://arxiv.org/abs/1711.03825)
* []() ??? A graphical language. Composition, ...

Projects

* Implement and explore the properties of a complex tensor network. Does it have the same represeantional capacity?
* Implement [Strassen's Algorithm for Tensor Contraction](https://arxiv.org/abs/1704.03092) / [Designing Strassen's algorithm](https://arxiv.org/abs/1708.09398)
* Play with/benchmark tensor operation compilers - [tensor-comprehensions](https://research.fb.com/announcing-tensor-comprehensions/), [simit](http://simit-lang.org/tog16), [taco](http://tensor-compiler.org/)
* Symmetry in the tensor network reflectin in the problem?
* Differentiable learning of tensor nets?

## Semester 2

#### Gradient estimation

Readings

* Non differentiable ops: Stochastic, discrete, unknown... [Rebar](), [concrete distribution](https://arxiv.org/abs/1611.00712), [DICE](https://arxiv.org/abs/1802.05098), A\* sampling, 
* [Backpropagation through the Void](https://arxiv.org/abs/1711.00123)
* Alternatives and approximations to gradients
* Counterfactuals

Projects

* Non-linearities in linear networks exploited by ES
* Metalearning?
* Implement a credit assignment algorithm in a non-cts setting. For example; rewards in economies or citation networks.
* Jacobian sensing, structure in the jacobian, invariance


#### (Graph) signal processing

* Sparse representations: The fourier transformation
* The laplacian
* Graph embeddings for ML

#### (Statistical) learning theory

* Sample complexity
* Assumptions about the data (IID, noise, ...)
* Complexity measures and bounding generalisation
* Overfitting

## Semester 3

#### Representation/approximation theory

* Neural networks as a tensor decomposition?

Readings

* Curve fitting
* Deep vs wide
* Alternative representations?
* Factorisation machines
* [Boosting dilated conv-nets with tensor decompositions](https://openreview.net/forum?id=S1JHhv6TW)


#### Topological data analysis OR probabilistic inference

* Clustering
* Connectedness
* ?

#### Compression 

<!-- (and beauty) -->
<!-- What about learning PGMs -->

Questions

* 

Readings

* A theory of fun, beauty, ... Schmidhuber 2009
* Hand designed compression of ?! (images/audio/text?)
* 

Projects

* Extract/distill an automata from a (recurrent) neural network
* Quantisation, distillation, ...? [TernGrad]()
* Adaptive/online compression/coding


## Project

> Automated science and math.

Math and science have become too big for individuals. We find it hard to keep up and to cram the relevant knowledge into our small heads. We need better tools to continue push the boundaries.

<!-- wishlist;
- variational methods
- causal inference
- online algols -- tree based frequency sketch. Efficient memory in online setting.  not optimisation, but interesting!?
- another on optimisation...
- transfer, active, meta, .. learning
- focus on stability, sparsity, 
-->
