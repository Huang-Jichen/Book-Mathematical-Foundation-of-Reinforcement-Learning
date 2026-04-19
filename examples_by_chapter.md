# Examples by Chapter (Mathematical Foundations of Reinforcement Learning)

> Extraction note: this repository only contains PDFs (no LaTeX book source). In this environment, reliable full PDF text extraction was unavailable, so the list below is built from detectable PDF/bookmark figure IDs plus README context. Any missing or uncertain fields are marked **needs manual check**.

## Chapter 1 — Basic Concepts

### Example: `fig_gridIntuition`
- **Page:** needs manual check
- **Local heading/title:** needs manual check (figure ID detected)
- **RL topic illustrated:** grid-world intuition for states/actions
- **Setup/assumptions:** small grid world MDP; details need manual check
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** conceptual illustration; details need manual check
- **Final takeaway:** introduces MDP intuition in a concrete grid world

### Example: `fig_gridDemoAction`
- **Page:** needs manual check
- **Local heading/title:** needs manual check (figure ID detected)
- **RL topic illustrated:** action effects in grid world
- **Setup/assumptions:** single-step or short-horizon movement demo; details need manual check
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** action-to-transition illustration; details need manual check
- **Final takeaway:** demonstrates how actions map to transitions/rewards

## Chapter 2 — State Values and Bellman Equation

### Example: `gridStateValue/gridPolicy_random`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** state values under a random policy
- **Setup/assumptions:** fixed random policy in grid world
- **Key equations (LaTeX):** Bellman expectation equation (needs manual check for exact form in text)
- **Main derivation/update steps:** evaluate value function for fixed policy; details need manual check
- **Final takeaway:** policy choice strongly changes value landscape

### Example: `gridStateValue/gridPolicy_moveRight`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** directional deterministic policy evaluation
- **Setup/assumptions:** policy biased to moving right
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** compute/evaluate values under directional policy
- **Final takeaway:** poor policy structure yields poor values even with same environment

### Example: `gridStateValue/gridPolicy_good1`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** improved hand-crafted policy evaluation
- **Setup/assumptions:** manually improved policy in same grid world
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** compare value map against weaker baselines
- **Final takeaway:** better policy quality increases state values

### Example: `gridStateValue/gridPolicy_good`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** high-quality policy and corresponding value function
- **Setup/assumptions:** good policy candidate
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** final comparison among candidate policies
- **Final takeaway:** Bellman-based evaluation distinguishes policy quality clearly

## Chapter 3 — Optimal State Values and Bellman Optimality Equation

### Example: `gridStateValue/gridPolicy_fastest2` and `fastest1`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** shortest-path style optimality behavior
- **Setup/assumptions:** goal-reaching grid world with competing routes
- **Key equations (LaTeX):** Bellman optimality equation (exact expression needs manual check)
- **Main derivation/update steps:** compare policies maximizing optimal value
- **Final takeaway:** optimal policies depend on reward/transition structure and may be non-unique

### Example: `optimal_rFobiddenMinus10`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** effect of penalty on optimal policy
- **Setup/assumptions:** forbidden-region penalty set to -10
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** resolve optimal value/policy under harsher penalty
- **Final takeaway:** reward shaping can alter optimal route qualitatively

### Example: `optimal_gamma00`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** discount factor edge case 
- **Setup/assumptions:** \(\gamma=0\)
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** optimize immediate reward objective
- **Final takeaway:** with zero discount, only immediate reward matters

### Example: `optimal_gamma05`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** moderate discount-factor behavior
- **Setup/assumptions:** \(\gamma=0.5\)
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** compare policy/value with other gamma settings
- **Final takeaway:** discounting balances short-term and long-term rewards

### Example: `optimal_norminal`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** nominal/default-parameter optimum
- **Setup/assumptions:** default chapter setting
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** final optimal value/policy under nominal parameters
- **Final takeaway:** serves as baseline optimal solution for later algorithm chapters

## Chapter 4 — Value Iteration and Policy Iteration

### Example: `fig_demoPIAlgo1D2Grid`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** policy-iteration workflow on a simple grid
- **Setup/assumptions:** small 1D/2D demo grid
- **Key equations (LaTeX):** PI policy-evaluation + policy-improvement steps (exact forms need manual check)
- **Main derivation/update steps:** alternate evaluation and improvement
- **Final takeaway:** PI converges through monotone policy improvements

### Example: `fig_gridPolicy_PIValue0..10` and `fig_gridPolicy_PIPolicy0..10`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** iteration-by-iteration evolution of values and policy
- **Setup/assumptions:** repeated PI iterations (at least iterations 0,1,2,3,4,5,9,10 visible)
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** snapshot sequence across iterations
- **Final takeaway:** visualizes convergence trajectory of PI

### Example: `fig_demoConvergenceThreeCurves`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** convergence-rate comparison among DP methods
- **Setup/assumptions:** three methods/curves; exact metrics need manual check
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** compare convergence curves
- **Final takeaway:** different planning methods trade off per-iteration cost vs convergence speed

## Chapter 5 — Monte Carlo Methods

### Example: `fig_demoLawLargeNum`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** law of large numbers motivation for MC estimation
- **Setup/assumptions:** repeated sampling / empirical averaging
- **Key equations (LaTeX):** MC average estimator (exact form needs manual check)
- **Main derivation/update steps:** sample mean approaches expectation
- **Final takeaway:** justifies return-averaging strategy in MC methods

### Example: `gridStateValue/gridPolicy_epL1, epL2`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** early-stage MC prediction/control snapshots
- **Setup/assumptions:** episode-based updates; low episode counts
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** policy/value evolution after initial episodes
- **Final takeaway:** MC estimates are noisy early, stabilize with more data

### Example: `gridPolicy_epL3, epL4, epL14, epL15, epL30, epL100` + `gridOptimalPolicy_epsilon00`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** epsilon-greedy MC control learning progression
- **Setup/assumptions:** increasing episode counts; epsilon-greedy behavior
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** iterative policy refinement from exploration to near-optimal behavior
- **Final takeaway:** exploration then exploitation yields better control policies

### Example: `trajectory_Step1000/10000_uniform` vs `trajectory_Step1000/10000_epsiGreedy`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** trajectory behavior under different behavior policies
- **Setup/assumptions:** compare uniform random vs epsilon-greedy sampling, two training horizons
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** side-by-side trajectory comparisons over training time
- **Final takeaway:** guided exploration improves trajectory quality/sample efficiency

## Chapter 6 — Stochastic Approximation

### Example: `chapterSA_fig_RMAlgoDemo`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** Robbins–Monro style stochastic approximation intuition
- **Setup/assumptions:** noisy observations of target/root quantity
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** recursive estimate update under diminishing stepsize
- **Final takeaway:** stochastic approximation converges despite noise under conditions

### Example: `fig_GDmeanEstTraj` and `fig_GDmeanEstErr`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** stochastic gradient / mean estimation trajectory and error decay
- **Setup/assumptions:** iterative gradient-like updates with noisy samples
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** track estimate trajectory and estimation error
- **Final takeaway:** step-size design governs stability and convergence speed

## Chapter 7 — Temporal-Difference Methods

### Example: `fig_offPolicy_episode`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** off-policy TD episode behavior
- **Setup/assumptions:** behavior policy differs from target policy
- **Key equations (LaTeX):** TD-style bootstrapped update (exact form needs manual check)
- **Main derivation/update steps:** episode-level learning under off-policy sampling
- **Final takeaway:** TD can learn target values from non-target behavior data

### Example: `fig_offPolicy_episode_nonexploratory_epsi05 / epsi01 / epsi01_rand`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** exploration level impact in off-policy temporal-difference learning
- **Setup/assumptions:** non-exploratory tendencies with varying epsilon and randomization
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** compare outcomes under different exploration configurations
- **Final takeaway:** insufficient exploration can degrade off-policy learning quality

## Chapter 8 — Value Function Methods

### Example: `fig_SarsaLinear_rewardLength` and `fig_SarsaLinear_fianlPolicy`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** linear function approximation with Sarsa
- **Setup/assumptions:** linear parameterization for action-value approximation
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** monitor reward/episode length and final learned policy
- **Final takeaway:** linear approximation can produce workable policies with limited representation

### Example: `fig_QlearningLinear_rewardLength`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** linear function approximation with Q-learning
- **Setup/assumptions:** off-policy Q-learning with linear approximator
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** training metric progression via reward/length curves
- **Final takeaway:** off-policy learning with approximation has distinct stability/performance profile

### Example: `fig_QLearningOffPolicyNN_episode_epiLenth1000`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** neural-network value approximation in off-policy Q-learning
- **Setup/assumptions:** NN approximator, long-horizon training episodes
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** training curve snapshot at/through episode-length scale ~1000
- **Final takeaway:** motivates deep RL value-function methods from tabular/linear baselines

## Chapter 9 — Policy Gradient Methods

- No explicit example-title strings were reliably extractable from repository PDFs with available tooling.
- **Status:** needs manual check (likely example content exists in chapter body).

## Chapter 10 — Actor-Critic Methods

### Example: `fig_importanceSampling`
- **Page:** needs manual check
- **Local heading/title:** needs manual check
- **RL topic illustrated:** importance sampling in actor-critic / off-policy correction
- **Setup/assumptions:** behavior-target policy mismatch with IS weights
- **Key equations (LaTeX):** needs manual check
- **Main derivation/update steps:** reweight sampled updates to approximate target-policy objective
- **Final takeaway:** IS enables off-policy actor-critic at variance-cost tradeoff
