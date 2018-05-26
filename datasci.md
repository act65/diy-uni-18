Course in data science, stats and related math.

# Semester 1

### Efficient tensor computation

Questions

* What is a tensor? Rank, dimension, ...? Want some intuition. How do/can they encode real world info? <!-- tensors that encode logic, dual algebra, -->
* Can the topology of data be build into the topology of a tensor network? Can the symmetry/structure in the tensor network be designed to match structure in the problem? <!-- lots of pretty pics of various network topologies? but also measures of their properties! -->
* Reshaping tensors, what is this really doing?
* What priors do various factorsations/decompositions/structures encode? Hankel, conv, CP, Cholesky, Toeplitz, QP, ... - locality, symmetry, ?
<!-- Invariant symmetries of linear operations - matmul/contraction, reshape, ...-->

Readings

* Singular value decomposition(s) - [HOSVD](https://lirias.kuleuven.be/bitstream/123456789/72517/1/94-31.pdf), [HSVD](http://epubs.siam.org/doi/abs/10.1137/090764189), [the geometry of HT](https://www.sciencedirect.com/science/article/pii/S0024379513002115), [of Orthogonally Decomposable Tensors](https://arxiv.org/abs/1603.09004)
* Contraction of TNs- [Review of Approaches](https://arxiv.org/abs/1708.09213), [Strassen's Algorithm for Tensor Contraction](https://arxiv.org/abs/1704.03092)
* [A graphical calculus for open quantum systems](https://arxiv.org/abs/1111.6950)
* ?
<!-- * Optimisation of tensornets. -->
<!--  [from group orbits](https://arxiv.org/abs/1612.01527), -->
<!-- Tensor calculus - Sochi -->

Projects

* Show (via proof and/or experiment) the representational capacity of a complex tensor network.
* Implement Strassen's algol - [Designing Strassen's algorithm](https://arxiv.org/abs/1708.09398)
* Benchmark tensor operation compilers - [tensor-comprehensions](https://research.fb.com/announcing-tensor-comprehensions/), [simit](http://simit-lang.org/tog16), [taco](http://tensor-compiler.org/)
* Write a wikipedia page (as none seems to exist), untill [now](https://en.wikipedia.org/wiki/Draft:Tensor_networks).
* Explore non-linear tensor-networks.
<!-- complexity of various SVD algols?! -->

### (Statistical) learning theory

Questions

* What would a theory of learning/generalisation look like? What would it tell us?
* What is necessary/sufficient for X to be learnable (aka constructed?)? What is necesary/sufficient to prove that humans are learnable via natural selection?
* What does it mean to generalise? What is the difference between visual/learned generalisation and symbolic generalisation?
* Define Occams razor! Flexibility vs complexity.

Readings

* Classics: [An Overview of Statistical Learning Theory](http://www.mit.edu/~6.454/www_spring_2001/emin/slt.pdf), [A theory of the learnable](https://people.mpi-inf.mpg.de/~mehlhorn/SeminarEvolvability/ValiantLearnable.pdf), [PAC learning framework](http://web.cs.iastate.edu/~honavar/pac.pdf)
* [Memory, Communication, and Statistical Queries](http://theory.stanford.edu/~valiant/papers/commMemDraft.pdf)
* Generalisation in NNs: [Analytical Learning Theory](https://arxiv.org/abs/1802.07426)
* [The Space of Transferable Adversarial Examples](https://arxiv.org/abs/1704.03453)

Projects

* Empirical learing theory. Design and explore metrics for data complexity on various Kaggle datasets.
* Training in a non-IID setting. Solution? <!-- (how do you even evaluate in non-IID settings?) -->
* Generalisation to different inputs. MINST - 1 vs 2 vs 3, ... (most autoencoders can over-generalise?! a linear network? can it do this? a property of the data!?)
* Find/design an example of where it is hard/impossible to generalise. Explain why.
<!-- Flat minima -->
<!-- Rewrite/annote proof of PCA p-np -->
<!-- -->

## Semester 2

#### Structured learning

<!--
- Databases,
- structured inputs and outputs (grammar/syntax), aka graphs!
- reasoning
- ?
-->

Questions

* How can graphs be encoded? list the different ways? does structure imply a graph?

Readings

* [Graph signal processing](https://arxiv.org/abs/1211.0053)
* Knlowedge bases (link prediction and factorisation -- find common patterns of connectivity and abstract!? What about disambiguation? When things are linked wit similar edges, but they really arent the same thing!?)
* [Knowledge Graph Completion via Complex Tensor Factorization](https://arxiv.org/abs/1702.06879)
* [CayleyNets: Graph Convolutional Neural Networks with Complex Rational Spectral Filters]()
* https://lagunita.stanford.edu/courses/DB/RD/SelfPaced/info

Projects

* Understand and visualise the laplacian (in cts and discrete)
* Graph embeddings for ML/NLP
* Message passing NNs for ???
<!-- Matrix-vector multiplication as graph convolution. -->


#### (Approximation) learning theory

* Neural networks as a tensor decomposition?
* Representation to match structure in the problem.
* Distributed representations,
<!-- * Capacity and simplicity. Measuring complexity of a given hypothesis -->

Readings

* Approximation theory []()
* The perceptron, universality of RNNs, ... [RNNs](https://arxiv.org/pdf/1711.00811.pdf)
* Neural networks. Deep vs wide, [Implicit Acceleration by Overparameterization](https://arxiv.org/abs/1802.06509/), [Generalization in Deep Learning](https://arxiv.org/abs/1710.05468)
* Building complex functions from simple ones (aka boosting?): [Weak learners](http://www.cs.princeton.edu/~schapire/papers/strengthofweak.pdf), [AdaBoost](https://www.cis.upenn.edu/~mkearns/teaching/COLT/adaboost.pdf), [as gradient descent](https://papers.nips.cc/paper/1766-boosting-algorithms-as-gradient-descent)


Projects

* Hierarchical taylor representation
* Splines
* Second order and Factorisation machines
* Holographic reduced representations?
* Iteratively construct a net. What does adding more flexibility do when at a local minima?


## Semester 3

#### Probabilistic inference

* Bayes rule
* PGMs
* Variational inference
* Causal inference

Readings

* https://ermongroup.github.io/cs228-notes/
* [Learning Polynomials with Neural Networks](http://theory.stanford.edu/~valiant/papers/andoni14.pdf)
* Causal Compression

Projects

* Moments, correlation, and their relation to gradients? Contractive, ...
* Learn a PGM
* ?


<!-- wishlist;
- online algols -- tree based frequency sketch. Efficient memory in online setting.  not optimisation, but interesting!?
- another on optimisation...
- transfer, active, meta, .. learning
- Topological data analysis, clustering, connectedness,
- causal inference
- boosting
-->
