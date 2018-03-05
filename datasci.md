Course in data science, machine learning and related math.

## Semester 1

#### Gradient estimation

<!-- > _How can you estimate how a function will change?_ -->

Questions

* Why do we want gradients/why do we care?
* What is necessary/sufficient for calculating a gradient? <!-- Some kind of locality/connectedness? --> For what reasons can a mathematical operation be non-differentiable? What are the solutions?
* Is there a more general formuation of differences that unifies; finite, temporal, counterfactual, ...?
* What we really want to know is how Y changes with chages in X. A derivative gives us a linear approximation at some X. What alternatives are there?

Readings

<!-- Derivation for typical SGD. Want \del L but sample from dataset to estimate the true grad -->
* Automatic differentiation: [stability](https://link.springer.com/article/10.1007/s00607-011-0162-z), [checkpointing](https://arxiv.org/abs/1708.06799), [ILC](https://arxiv.org/abs/1611.03429) <!-- * What problem does AD solve? What about their implementation in practice!? fast algols for gpus? -->
* Non differentiable ops: [Rebar](https://arxiv.org/abs/1703.07370), [DICE](https://arxiv.org/abs/1802.05098), [Backpropagation through the Void](https://arxiv.org/abs/1711.00123), [Mixed convex-combinatorial optimisation](https://arxiv.org/abs/1710.11573)
* [Jacobian sensing](https://papers.nips.cc/paper/7230-on-blackbox-backpropagation-and-jacobian-sensing)
* Temporal differences: [True online TD](https://arxiv.org/abs/1512.04087), [Gradient TD](http://proceedings.mlr.press/v24/silver12a/silver12a.pdf)

Projects

* Reproduce [Non-linearities in linear networks exploited by ES](https://blog.openai.com/nonlinear-computation-in-linear-networks/ ) <!-- difference in how you calculate the gradients leads to ... -->
* Implement [doubly recursive AD](http://dankalman.net/preprints/mmgautodiff.pdf)
* Gradient estimation with;
    * _local queries_. If the model is very large, would it be easier/efficient to do local pertubations to estimate the gradients?
    * _structured information_.  If I have some information about the structure of a function (aka black box) we are taking the derivatve of (ie, not a black box...) how can this help me estimate gradients? <!-- If I gave you the jacobian of a CNN could you tell me whether it is invariant to translations/rotations? -->
<!-- What about estimation of the hessian or higher orders? -->
<!-- * Approximate gradients: synthetic gradients, ?  * Add AD for non-differentiable ops to tensorflow?!
http://blog.otoro.net/2017/10/29/visual-evolution-strategies/ 
-->
* Aggregation for noisy estimates?

#### Tensors

Questions

* What is a tensor? Rank, dimension, ...? Want some intuition. How do/can they encode real world info? <!-- tensors that encode logic, dual algebra, -->
* Can the topology of data be build into the topology of a tensor network? Can the symmetry/structure in the tensor network be designed to match structure in the problem? <!-- lots of pretty pics of various network topologies? but also measures of their properties! -->
* Reshaping tensors, what is this really doing?
* What priors do various factorsations/decompositions/structures encode? Hankel, conv, CP, Cholesky, Toeplitz, QP, ... - locality, symmetry, ?

Readings

* Singular value decomposition(s) - [HOSVD](https://lirias.kuleuven.be/bitstream/123456789/72517/1/94-31.pdf), [HSVD](http://epubs.siam.org/doi/abs/10.1137/090764189), [the geometry of HT](https://www.sciencedirect.com/science/article/pii/S0024379513002115), [of Orthogonally Decomposable Tensors](https://arxiv.org/abs/1603.09004)
* [Matrix multiplication algorithms from group orbits](https://arxiv.org/abs/1612.01527)
* [A graphical calculus for open quantum systems](https://arxiv.org/abs/1111.6950)
* [Review of Tensor Network Contraction Approaches](https://arxiv.org/abs/1708.09213)

Projects

* Show (via proof and/or experiment) the representational capacity of a complex tensor network.
* Implement [Strassen's Algorithm for Tensor Contraction](https://arxiv.org/abs/1704.03092) / [Designing Strassen's algorithm](https://arxiv.org/abs/1708.09398)
* Benchmark tensor operation compilers - [tensor-comprehensions](https://research.fb.com/announcing-tensor-comprehensions/), [simit](http://simit-lang.org/tog16), [taco](http://tensor-compiler.org/)
* Write a wikipedia page (as none seems to exist), untill [now](https://en.wikipedia.org/wiki/Draft:Tensor_networks).

#### (Statistical) learning theory

<!-- Fitting the data is not enough, needs to generalise! -->
Questions

* What is necessary/sufficient for X to be learnable (aka constructed?)? What is necesary/sufficient to prove that humans are learnable via natural selection?
* What would a theory of learning/generalisation look like? What would it tell us?
* What does it mean to generalise? What is the difference between visual/learned generalisation and symbolic generalisation?
* Define Occams razor! Flexibility vs complexity. <!-- parameterised relus versus vanilla relu. same represational capacity/complexity, different learnability/flexibility. formulate some measures and test them -->


Readings

* Classics: [An Overview of Statistical Learning Theory](http://www.mit.edu/~6.454/www_spring_2001/emin/slt.pdf), [A theory of the learnable](https://people.mpi-inf.mpg.de/~mehlhorn/SeminarEvolvability/ValiantLearnable.pdf), [PAC learning framework](http://web.cs.iastate.edu/~honavar/pac.pdf)
<!-- * Capacity and simplicity. Measuring complexity of a given hypothesis -->
* Building complex functions from simple ones (aka boosting?): [Weak learners](http://www.cs.princeton.edu/~schapire/papers/strengthofweak.pdf), [AdaBoost](https://www.cis.upenn.edu/~mkearns/teaching/COLT/adaboost.pdf), [as gradient descent](https://papers.nips.cc/paper/1766-boosting-algorithms-as-gradient-descent)
* Generalisation in NNs: [Analytical Learning Theory](https://arxiv.org/abs/1802.07426)
* [The Space of Transferable Adversarial Examples](https://arxiv.org/abs/1704.03453)

Projects

* Training in a non-IID setting. Solution? <!-- (how do you even evaluate in non-IID settings?) -->
* Generalisation to different inputs. MINST - 1 vs 2 vs 3, ... (most autoencoders can over-generalise?! a linear network? can it do this? a property of the data!?)
* Iteratively construct a net. What does adding more flexibility do when at a local minima? <!-- saddle splitting network? -->
* Find/design an example of where it is hard/impossible to generalise. Explain why.
<!-- * Margin based classification. The patterns are a property of the data!! Visualise them... If we pick some decision boundaries on test data and overlay the test data we should be able to see where the boundaries wont generalise? Explore how margin effects accuracy. -->
<!-- Flat minima -->

## Semester 2

#### Credit assignment

Questions

* What conditions make assigning credit hard?
* Can credit assignment be framed in a communication setting?
* What if the network of interactions is too complex to accurately assign credit? In what way do we mean complex here?
* Is credit assignment necessary or sufficient for learning? (hebbian clearning does seem to clearly assign credit but it learns?)
<!-- To assign credit, you need the ops to be connected/locally linear? No, that is just for propagating via chain rule. -->
<!-- must be connected in some sense? Ability to communicate feedback. -->

Readings

* Backprop: [Backprop as Functor](https://arxiv.org/abs/1711.10455) and [?]()
* Is hard: [long-term dependencies](http://www.iro.umontreal.ca/~lisa/pointeurs/ieeetrnn94.pdf), memory usage?, shattered grads?, 
* Biologically plausible credit assignment: [Equilibrium Propagation](), [Backprop in deep cortical microcircuits](), 
* Alternatives: real-time recurrent learning (RTRL), temporal difference propagation, synthetic gradients

Projects

<!-- What about the complexity of propagating higher order info - second order? -->
* Implement efficient graph based reverse AD (not sure about this one...)
* Show that there exist pathological problems where learning long-term dependencies is hard. Explore the relationship  between what makes long-term dependencies hard and entropy. (where am I going to get some data!?)
* Approximate credit assignment (for greater efficiency?)
* Implement a credit assignment algorithm in a non-cts setting. For example; rewards in economies or citation networks.

#### Structured learning

Questions

* How can graphs be encoded? list the different ways? does structure imply a graph?

Readings

* [Graph signal processing](https://arxiv.org/abs/1211.0053)
* Knlowedge bases (link prediction and factorisation -- find common patterns of connectivity and abstract!? What about disambiguation? When things are linked wit similar edges, but they really arent the same thing!?)
* [Knowledge Graph Completion via Complex Tensor Factorization](https://arxiv.org/abs/1702.06879)

Projects

* Understand and visualise the laplacian (in cts and discrete)
* Graph embeddings for ML/NLP
* Message passing NNs for ???
<!-- Matrix-vector multiplication as graph convolution. -->

#### Representation/approximation theory

* Neural networks as a tensor decomposition?
* Representation to match structure in the problem.
* Distributed representations, 

Readings

* Approximation theory []()
* Neural networks. Deep vs wide; [Implicit Acceleration by Overparameterization](https://arxiv.org/abs/1802.06509/), [Generalization in Deep Learning](https://arxiv.org/abs/1710.05468)
* VC and Rachmader
* ?

Projects

* Hierarchical taylor representation
* Splines
* Second order and Factorisation machines
* Holographic reduce representations?

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
* [High-dimensional dynamics](https://arxiv.org/abs/1710.03667)
<!-- * Momentum for non-convex optimisation: [ADAM]() and its update [AMSGRAD]() (a lack of theory here, or am I just unaware?) -->
<!--* Implicit bias. Neyshabur? -->
<!-- * Time and memory complexity -->
<!-- * Natural gradient descent (using the fisher) -->

Projects

<!-- * Alternatives to SGD. ES? ADMM? CG? Newtons? Fisher?  ... -->
* Local gradient statistics (must be distributed/collected over time or space -- the batch) <!-- Why is the necessary? Pathological surfaces that make point estimates useless. Want cheap, no-bias, estimates of the gradients -->
* Why don't higher order optimisation algols work with NNs? Kronecker-factored approximation, hessian free, block hessian, ...?
* Model based optimisation rather than black box optimisation!?!
<!-- * A derivative of a function as a linear model? Of that function. So when we do black box optimisation we do it by modeling the function--> 
* Regularisation via early stopping
<!-- What if you tried to model the entire surface you are descending?! Model based optimisation!? Although we might be optimisating a black box, that doesnt stop us from using a model of it?! -->
<!-- * Reproduce [The marginal value of adaptive gradients](https://arxiv.org/abs/1705.08292) and explore -->

#### Probabilistic inference

* Bayes rule
* PGMs
* Variational inference
* Causal inference

Readings

* https://ermongroup.github.io/cs228-notes/
* [Learning Polynomials with Neural Networks](http://theory.stanford.edu/~valiant/papers/andoni14.pdf)

Projects

* Moments, correlation, and their relation to gradients? Contractive, ...
* Learn a PGM
* ?

#### Compression 

<!-- (and beauty) -->
<!-- What about learning PGMs -->

Questions

* Is compression the same thing as quantisation and formalisation? If not, how is it different?
* Relationship between sketching, quantising, distilling, ...
* How do compression and prediction relate?
* 

Readings

* [A theory of fun, beauty, ...](Schmidhuber 2009), 
* Hand designed compression of ?! (images/audio/text?)
<!-- * Automata theory? -->
* AIT?
* Compression limits?

Projects

* Automata theory and RNNs
  * Extract/distill an automata from a (recurrent) neural network. 
  * Can a RNN learn a push down or turing machine ??
* Quantisation, distillation, ...? [TernGrad]()
* Adaptive/online compression/coding (predictive coding?)
* A flexible/variable 
* Gradient w.r.t compression!?



<!-- wishlist;
- online algols -- tree based frequency sketch. Efficient memory in online setting.  not optimisation, but interesting!?
- another on optimisation...
- transfer, active, meta, .. learning
- Topological data analysis, clustering, connectedness, 
-->
