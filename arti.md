Course in AI related math.

# Semester 1

### Deep learning and gradient estimation

<!-- > _How can you estimate how a function will change?_ -->

Questions

* Why do we want gradients/why do we care?
* What is necessary/sufficient for calculating a gradient? <!-- Some kind of locality/connectedness? --> For what reasons can a mathematical operation be non-differentiable? What are the solutions?
* Is there a more general formuation of differences that unifies; finite, temporal, counterfactual, ...?
* What we really want to know is how Y changes with chages in X. A derivative gives us a linear approximation at some X. What alternatives are there?

Readings

<!-- Derivation for typical SGD. Want \del L but sample from dataset to estimate the true grad -->
* Automatic differentiation: [stability](https://link.springer.com/article/10.1007/s00607-011-0162-z), [checkpointing](https://arxiv.org/abs/1708.06799), [ILC](https://arxiv.org/abs/1611.03429) <!-- * What problem does AD solve? What about their implementation in practice!? fast algols for gpus? -->
* Non differentiable ops: [DICE](https://arxiv.org/abs/1802.05098), [Backpropagation through the Void](https://arxiv.org/abs/1711.00123), [Black box bprop via jacobian sensing](https://papers.nips.cc/paper/7230-on-blackbox-backpropagation-and-jacobian-sensing)
* [True online TD](https://arxiv.org/abs/1512.04087)
* ?

<!--
* synthetic grads???
* kronecker factored...
* ?
-->

Projects

* Reproduce [Non-linearities in linear networks exploited by ES](https://blog.openai.com/nonlinear-computation-in-linear-networks/ ) <!-- difference in how you calculate the gradients leads to ... -->
* Implement [doubly recursive AD](http://dankalman.net/preprints/mmgautodiff.pdf)
* Gradient estimation with;
    * _local queries_. If the model is very large, would it be easier/efficient to do local pertubations to estimate the gradients?
    * _structured information_.  If I have some information about the structure of a function (aka black box) we are taking the derivatve of (ie, not a black box...) how can this help me estimate gradients? <!-- If I gave you the jacobian of a CNN could you tell me whether it is invariant to translations/rotations? -->
* Aggregation for noisy estimates?
<!-- What about estimation of the hessian or higher orders? -->
<!-- * Approximate gradients: synthetic gradients, ?  * Add AD for non-differentiable ops to tensorflow?!
http://blog.otoro.net/2017/10/29/visual-evolution-strategies/
-->

#### Reasoning

!?

## Semester 2

#### Backpropagation and credit assignment

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
* [Mixed convex-combinatorial optimisation](https://arxiv.org/abs/1710.11573), [target propagation](), [ADMM]()

Projects

<!-- What about the complexity of propagating higher order info - second order? -->
* Implement efficient graph based reverse AD (not sure about this one...)
* Show that there exist pathological problems where learning long-term dependencies is hard. Explore the relationship  between what makes long-term dependencies hard and entropy. (where am I going to get some data!?)
* Approximate credit assignment (for greater efficiency?)
* Implement a credit assignment algorithm in a non-cts setting. For example; rewards in economies or citation networks.

#### Reasoning 2

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
<!-- Derivative-Free Optimization via Classification -->

Projects

<!-- * Alternatives to SGD. ES? ADMM? CG? Newtons? Fisher?  ... -->
* Local gradient statistics (must be distributed/collected over time or space -- the batch) <!-- Why is the necessary? Pathological surfaces that make point estimates useless. Want cheap, no-bias, estimates of the gradients -->
* Why don't higher order optimisation algols work with NNs? Kronecker-factored approximation, hessian free, block hessian, ...?
* Model based optimisation rather than black box optimisation!?!
<!-- * A derivative of a function as a linear model? Of that function. So when we do black box optimisation we do it by modeling the function-->
* Regularisation via early stopping
<!-- What if you tried to model the entire surface you are descending?! Model based optimisation!? Although we might be optimisating a black box, that doesnt stop us from using a model of it?! -->
<!-- * Reproduce [The marginal value of adaptive gradients](https://arxiv.org/abs/1705.08292) and explore -->

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

#### Reasoning 3


<!-- wishlist;
- online algols -- tree based frequency sketch. Efficient memory in online setting.  not optimisation, but interesting!?
- another on optimisation...
- transfer, active, meta, .. learning
- reasoning!
-->
