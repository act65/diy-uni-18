Course in data science, machine learning and related math.

## Semester 1

#### Gradient computation

Questions

* Why do we want gradients/why do we care?
* What is necessary/sufficient for calculating a gradient? <!-- Some kind of locality/connectedness? -->
* Is there a more general formuation of differences that unifies; finite, temporal, counterfactual, ...?
* ?


Readings

<!-- Derivation for typical SGD. Want \del L but sample from dataset to estimate the true grad -->
* Automatic differentiation: [stability](https://link.springer.com/article/10.1007/s00607-011-0162-z), [checkpointing](https://arxiv.org/abs/1708.06799), [ILC](https://arxiv.org/abs/1611.03429) <!-- * What problem does AD solve? What about their implementation in practice!? fast algols for gpus? -->
* Non differentiable ops: Stochastic, discrete, unknown... [Rebar](https://arxiv.org/abs/1703.07370), [Concrete distribution](https://arxiv.org/abs/1611.00712), [DICE](https://arxiv.org/abs/1802.05098), [Backpropagation through the Void](https://arxiv.org/abs/1711.00123)
* [Jacobian sensing](https://papers.nips.cc/paper/7230-on-blackbox-backpropagation-and-jacobian-sensing)
* Temporal differences [?]()

Projects

* Reproduce [Non-linearities in linear networks exploited by ES](https://blog.openai.com/nonlinear-computation-in-linear-networks/ ) <!-- difference in how you calculate the gradients leads to ... -->
* Implement [doubly recursive AD](http://dankalman.net/preprints/mmgautodiff.pdf)
* Gradient estimation with;
    * _local queries_. If the model is very large, would it be easier/efficient to do local pertubations to estimate the gradients?
    * _structured information_.  If I have some information about the structure of the black box (ie, not a black box...) how can this help me estimate gradients?

<!-- * Approximate gradients: synthetic gradients, ?  * Add AD for non-differentiable ops to tensorflow?!
http://blog.otoro.net/2017/10/29/visual-evolution-strategies/ 
-->

#### Tensor networks

Questions

<!-- * Rank of high order tensors. Various types of decomposition. Solving for those decompositions. Notation. -->
* What is the difference between a tensor decomposition and a tensor network?
* Reshaping tensors, what is this really doing?
* What priors do various factorsations/decompositions/structures encode? Hankel, conv, CP, Cholesky, ... - locality, symmetry, ? 
* What is a tensor? Rank, dimension, ...? Want some intuition. How do/can they encode real world info?
<!-- how are they trained? -->

Readings

<!-- * [Introduction](https://arxiv.org/abs/1711.10781) to Tensor decompositions for ML -->
* Singular value/Tucker decomposition(s) - [HOSVD](), [HSVD](http://epubs.siam.org/doi/abs/10.1137/090764189), [the geometry of HT](https://www.sciencedirect.com/science/article/pii/S0024379513002115)
* [Matrix multiplication algorithms from group orbits](https://arxiv.org/abs/1612.01527)
* [A graphical calculus for open quantum systems](https://arxiv.org/abs/1111.6950)
* [Review of Tensor Network Contraction Approaches](https://arxiv.org/abs/1708.09213)
<!-- [Deep multi grids](https://arxiv.org/abs/1711.03825) maybe do in dynamical systems? -->
<!-- What about a TNs topology? -->

Projects

* Show (via proof or experiment) the representational of a complex tensor network.
* Implement [Strassen's Algorithm for Tensor Contraction](https://arxiv.org/abs/1704.03092) / [Designing Strassen's algorithm](https://arxiv.org/abs/1708.09398)
* Benchmark tensor operation compilers - [tensor-comprehensions](https://research.fb.com/announcing-tensor-comprehensions/), [simit](http://simit-lang.org/tog16), [taco](http://tensor-compiler.org/)
* Can the topology of data be build into the topology of a tensor network? Can the symmetry/structure in the tensor network be designed to match structure in the problem? <!-- lots of pretty pics of various network topologies? but also measures of their properties! -->
<!-- * Tensor network visualisation tool?  Not sure what this would be... --> 
<!-- * Differentiable learning of tensor nets? -->

#### (Statistical) learning theory

<!-- Fitting the data is not enought, needs to generalise! -->
Questions

* Occams razor! Flexibility vs complexity. <!-- parameterised relus versus vanilla relu. same represational capacity/complexity, different learnability/flexibility-->
* What is necessary/sufficient for X to be learnable (aka constructed?)? What is necesary/sufficient to prove that humans are learnable via natural selection?
* What would a theory of learning/generalisation look like? What would it tell us?
* WHat does it mean to generalise? WHat is the different between visual/learned generalisaation and symbolic generalisation?

Readings

* Classics: [An Overview of Statistical Learning Theory](http://www.mit.edu/~6.454/www_spring_2001/emin/slt.pdf), [A theory of the learnable](https://people.mpi-inf.mpg.de/~mehlhorn/SeminarEvolvability/ValiantLearnable.pdf), PAC learning framework
* Capacity and simplicity
* Measuring complexity of a given hypothesis
* Generalisation in NNs. [Generalization in Deep Learning](https://arxiv.org/abs/1710.05468), [High-dimensional dynamics of generalization error](https://arxiv.org/abs/1710.03667) <!-- reproduce experiments from-->

Projects

* Training in a non-IID setting. Correlated mnist, you recieve the digits in numerical order.
* The patterns are a property of the data!! Visualise them... If we pick some decision boundaries on test data and overlay the test data we should be able to see where the boundaries wont generalise? Explore how margin effects accuracy.
* Generalisation to different inputs. MINST - 1 vs 2 vs 3, ... (most autoencoders can over-generalise?!)
* Iteratively construct a net<!-- saddle splitting network? -->
<!-- Validate a measure of complexity and add it to tensorflow -->
<!-- Searching through hypothesis space, ... -->
<!-- Flat minima -->
<!-- Find an example of something a NN cant learn -->

## Semester 2

#### Credit assignment

Questions

* What conditions make assigning credit hard?
* Can credit assignment be framed in a communication setting?
* ?
* ?
<!-- To assign credit, you need the ops to be connected/locally linear? No, that is just for propagating via chain rule. -->
<!-- must be connected in some sense? Ability to communicate feedback. -->

Readings

* Backprop: [Backprop as Functor](https://arxiv.org/abs/1711.10455) and [?]()
* Is hard: [long-term dependencies](http://www.iro.umontreal.ca/~lisa/pointeurs/ieeetrnn94.pdf), memory usage?
* Biologically plausible credit assignment: [Equilibrium Propagation](), [Backprop in deep cortical microcircuits](), 
* ?

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
* Biased and/or variant estimates of a gradient, why does it matter? <!-- This is really a question about what we do with the gradients. Does it belong here?-->


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
