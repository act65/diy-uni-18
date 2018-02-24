Course in data science, machine learning and related math.

## Semester 1

#### Gradient computation

Questions

* What is necessary/sufficient for calculating a gradient? <!-- Some kind of locality/connectedness? -->
* Why do we want gradients/why do we care?
* Estimation versus derivation? <!-- (complexity? sample versus coputational?) -->
* Biased and/or variant estimates of a gradient, why does it matter?

Readings

<!-- Derivation for typical SGD. Want \del L but sample from dataset to estimate the true grad -->
* Automatic differentiation: [?](), [?]() <!-- * What problem does AD solve? -->
* Non differentiable ops: Stochastic, discrete, unknown... [Rebar](), [concrete distribution](https://arxiv.org/abs/1611.00712), [DICE](https://arxiv.org/abs/1802.05098), A\* sampling, 
* [Backpropagation through the Void](https://arxiv.org/abs/1711.00123)
* Alternatives and approximations to gradients; Synthetic gradients, ?
<!-- * Counterfactuals -->

Projects

* [Jacobian sensing](https://papers.nips.cc/paper/7230-on-blackbox-backpropagation-and-jacobian-sensing) and (?) structure in the jacobian, invariance. What if I already know something about the structure of the function? How can that help me estimate its jacobian?
* Explore [Non-linearities in linear networks exploited by ES](https://blog.openai.com/nonlinear-computation-in-linear-networks/ ) <!-- difference in how you calculate the gradients leads to ... -->
* Implement [doubly recursive AD](http://dankalman.net/preprints/mmgautodiff.pdf)
* Add AD for non-differentiable ops to tensorflow?!

<!-- 
http://blog.otoro.net/2017/10/29/visual-evolution-strategies/ 
-->

#### Tensor networks

Questions

* Rank of high order tensors. Various types of decomposition. Solving for those decompositions. Notation.
* Reshaping tensors, what is this really doing?
* What priors do various structures encode? Hankel, conv, ... - locality, symmetry, ?
* How can the topology of data be build into the topology of a tensor network? Symmetry/structure in the tensor network reflected in the problem?
<!-- * Relationship to learning? (matrix completion?) [X_train, Y_train], [X_test, ?]. -->
<!-- * What is happening when you contract over two paths? (marginalisation of two variables?) -->
<!-- how are they trained? -->

Readings

* Case study: Singular value decomposition(s) - [HOSVD](), [HSVD](http://epubs.siam.org/doi/abs/10.1137/090764189)
* [Matrix multiplication algorithms from group orbits](https://arxiv.org/abs/1612.01527)
* A graphical language for linalg. [A graphical calculus for open quantum systems](https://arxiv.org/abs/1111.6950), ?
* ?
<!-- [Deep multi grids](https://arxiv.org/abs/1711.03825) maybe do in dynamical systems? -->
<!-- What about a TNs topology? -->

Projects

* Implement and explore the properties of a complex tensor network. Does it have the same represeantional capacity?
* Implement [Strassen's Algorithm for Tensor Contraction](https://arxiv.org/abs/1704.03092) / [Designing Strassen's algorithm](https://arxiv.org/abs/1708.09398)
* Benchmark tensor operation compilers - [tensor-comprehensions](https://research.fb.com/announcing-tensor-comprehensions/), [simit](http://simit-lang.org/tog16), [taco](http://tensor-compiler.org/)
* Tensor network visualisation tool? 

<!-- * Differentiable learning of tensor nets? -->

#### (Statistical) learning theory

Questions

* Occams razor! Flexibility vs complexity. <!-- parameterised relus versus vanilla relu. same represational capacity/complexity, different learnability/flexibility-->
* What is necessary/sufficient for X to be learnable (aka constructed?)? What is necesary/sufficient to prove that humans are learnable via natural selection?
* What would a theory of learning/generalisation look like? What would it tell us?
* How could training in a non-IID setting work?

Readings

* Classics: [An Overview of Statistical Learning Theory](http://www.mit.edu/~6.454/www_spring_2001/emin/slt.pdf), [A theory of the learnable](https://people.mpi-inf.mpg.de/~mehlhorn/SeminarEvolvability/ValiantLearnable.pdf), PAC learning framework
* Capacity and simplicity
* Measuring complexity of a given hypothesis
* [High-dimensional dynamics of generalization error](https://arxiv.org/abs/1710.03667) <!-- reproduce experiments from-->

Projects

* Compress/annotate XXX proof (Implicit biases? easuring capacity? generalisation via spectral norm? ???)
* Add measure of complexity to tensorflow <!-- measure by non-linearity? -->
* The patterns are a property of the data!! Visualise them... If we pick some decision boundaries on test data and overlay the test data we should be able to see where the boundaries wont generalise? Explore how margin effects accuracy.
* Generalisation to different inputs. MINST - 1 vs 2 vs 3, ... (most autoencoders can over-generalise?!)
* Iteratively construct a net<!-- saddle splitting network? -->
<!-- * Searching through hypothesis space, ... -->
<!-- Flat minima -->

<!--
* Sample complexity
* Assumptions about the data (IID, noise, ...)
-->

<!-- Fitting the data is not enought, needs to generalise! -->
## Semester 2

#### Credit assignment

Questions

* What conditions make assigning credit hard?
* ?
* ?
* Can credit assignment be framed in a communication setting?
<!-- To assign credit, two things need to be, in some sense, connected. Ability to communicate feedback. -->

Readings

* Backprop: [Backprop as Functor](https://arxiv.org/abs/1711.10455) and [?]()
* Is hard: [long-term dependencies](http://www.iro.umontreal.ca/~lisa/pointeurs/ieeetrnn94.pdf), memory usage?
* Alternatives: Temporal differences, ?
* Biologically plausible credit assignment: [Equilibrium Propagation](), [Backprop in deep cortical microcircuits](), 

Projects

<!-- * Implement efficient graph based reverse AD (not sure about this one...) -->
* Show that there exist pathological problems where learning long-term dependencies is hard. Explore the relationship  between what makes long-term dependencies hard and entropy. (where am I going to get some data!?)
* Approximate credit assignment (for greater efficiency?)
* ?
<!-- * Implement a credit assignment algorithm in a non-cts setting. For example; rewards in economies or citation networks. -->

#### Structured learning/statistical relation learning

* (Graph) signal processing
* Sparse representations: The fourier transformation
* The laplacian
* Graph embeddings for ML

#### Representation/approximation theory

* Neural networks as a tensor decomposition?

Readings

* Curve fitting
* Deep vs wide
* Alternative representations?
* Factorisation machines
* [Boosting dilated conv-nets with tensor decompositions](https://openreview.net/forum?id=S1JHhv6TW)

## Semester 3

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
* Combinatorial optimisation: Satisfiability, (related to saticficing?)
<!-- * Momentum for non-convex optimisation: [ADAM]() and its update [AMSGRAD]() (a lack of theory here, or am I just unaware?) -->
<!--* Implicit bias. Neyshabur? -->
<!-- * Time and memory complexity -->
<!-- * Natural gradient descent (using the fisher) -->

Projects

<!-- * Alternatives to SGD. ES? ADMM? CG? Newtons? Fisher?  ... -->
* Local gradient statistics (must be distributed/collected over time or space -- the batch) <!-- Why is the necessary? Pathological surfaces that make point estimates useless. Want cheap, no-bias, estimates of the gradients -->
* Why don't higher order optimisation algols work with NNs? Kronecker-factored approximation, hessian free, block hessian, ...?
* Model based optimisation rather than black box optimisation!?
* Regularisation via early stopping
<!-- What if you tried to model the entire surface you are descending?! Model based optimisation!? Although we might be optimisating a black box, that doesnt stop us from using a model of it?! -->
<!-- * Reproduce [The marginal value of adaptive gradients](https://arxiv.org/abs/1705.08292) and explore -->

#### Probabilistic inference

* PGMs
* Variational inference
* Causal inference
* https://ermongroup.github.io/cs228-notes/

#### Compression 

<!-- (and beauty) -->
<!-- What about learning PGMs -->

Questions

* 

Readings

* A theory of fun, beauty, ... Schmidhuber 2009
* Hand designed compression of ?! (images/audio/text?)


Projects

* Automata theory and RNNs
  * Extract/distill an automata from a (recurrent) neural network. 
  * Can a RNN learn a push down or turing machine ??
* Quantisation, distillation, ...? [TernGrad]()
* Adaptive/online compression/coding



## Project

> Automated science and math.

Math and science have become too big for individuals. We find it hard to keep up and to cram the relevant knowledge into our small heads. We need better tools to continue push the boundaries.

<!-- wishlist;
- online algols -- tree based frequency sketch. Efficient memory in online setting.  not optimisation, but interesting!?
- another on optimisation...
- transfer, active, meta, .. learning
- Topological data analysis, clustering, connectedness, 
-->
