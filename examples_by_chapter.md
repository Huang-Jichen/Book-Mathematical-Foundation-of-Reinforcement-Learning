# Revision Notes: Example-Based Content by Chapter

Extraction method used in this revision:
- I extracted body text from each chapter PDF stream-by-stream (not only figure IDs), then searched for sections containing `Example`, `Illustrative examples`, and nearby derivations.
- For page numbers, I used the printed page numbers visible in extracted chapter text blocks.
- If a field could not be recovered reliably from body text, it is marked **needs manual check**.

---

## Chapter 2 — State Values and Bellman Equation

### Example 2.1 (Motivating): Why are returns important? (Figure 2.2, p. 17)
- **Local heading:** `2.1 Motivating example 1: Why are returns important?`
- **Topic:** Using discounted return to compare policies.
- **Setup:** Three policies differ at state \(s_1\); forbidden and target regions induce different trajectories.
- **Core equations:**
  - \(G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \cdots\)
  - Text shows return ranking conclusion: \(\text{return}_1 > \text{return}_3 > \text{return}_2\).
- **Derivation/update steps:** enumerate trajectories under each policy from \(s_1\), compute discounted sums, compare numerically.
- **Takeaway:** return is a quantitative policy-quality signal; intuition is formalized by return ordering.

### Example 2.2 (Motivating): How to calculate returns? (Figure 2.3, pp. 17–19)
- **Local heading:** `2.2 Motivating example 2: How to calculate returns?`
- **Topic:** Direct return expansion vs bootstrapping form.
- **Setup:** Four-state cyclic transition example with rewards \(r_1,r_2,r_3,r_4\).
- **Core equations:**
  - \(v_1 = r_1 + \gamma r_2 + \gamma^2 r_3 + \cdots\), similarly for \(v_2,v_3,v_4\).
  - Bootstrapped form: \(v_1=r_1+\gamma v_2,\; v_2=r_2+\gamma v_3,\; v_3=r_3+\gamma v_4,\; v_4=r_4+\gamma v_1\).
- **Derivation/update steps:** rewrite infinite sums into coupled linear equations; solve jointly (matrix form introduced immediately after).
- **Takeaway:** Bellman-style bootstrapping comes from algebraic rewriting of returns.

### Example 2.3: Two examples for illustrating Bellman equation (Figures 2.4 and 2.5, pp. 22–24)
- **Local heading:** `2.5 Examples for illustrating the Bellman equation`
- **Topic:** Writing Bellman equations state-by-state for deterministic and stochastic policies.
- **Setup:** Same grid structure with different policy stochasticity.
- **Core equations:**
  - Deterministic case sample equation: \(v(s_1)=0+\gamma v(s_3)\) (from the text’s substitution).
  - Stochastic case sample equation: \(v(s_1)=0.5\,[0+\gamma v(s_3)] + 0.5\,[ -1+\gamma v(s_2)]\).
  - Additional equations shown for \(s_2,s_3,s_4\), then solved as a system.
- **Derivation/update steps:** substitute \(\pi(a|s)\), \(p(s'|s,a)\), \(p(r|s,a)\) into Bellman expectation equation; solve linear system.
- **Takeaway:** the “complex” Bellman expression becomes simple after plugging transition/reward probabilities.

### Example 2.4: Matrix-vector Bellman form demonstration (Figure 2.6, p. 27)
- **Local heading:** `2.6 Matrix-vector form of the Bellman equation`
- **Topic:** Compact linear-system view of policy evaluation.
- **Setup:** small grid example converted from element-wise equations.
- **Core equations:**
  - \(v = r + Pv\)
  - \(v = (I-P)^{-1}r\)
- **Derivation/update steps:** define state indexing, construct \(P\) and \(r\), rewrite all state equations in one matrix equation.
- **Takeaway:** policy evaluation is a linear-algebra problem; this form is the basis for later algorithms.

### Example 2.5: Illustrative policy-evaluation comparisons (Figure 2.7, pp. 28–29)
- **Local heading:** `2.7.3 Illustrative examples`
- **Topic:** Comparing “good” and “bad” policies via computed state values.
- **Setup:** grid with boundary/forbidden/target rewards; multiple candidate policies.
- **Core equations:** iterative evaluation from \(v^{j+1}=r+Pv^j\) (algorithm in Sec. 2.7 used in text).
- **Derivation/update steps:** run evaluation for each policy, compare resulting value maps entry-wise.
- **Takeaway:** value maps objectively rank policies; “bad” policies show uniformly lower values.

### Example 2.6: Action-value calculation and common mistake (Figure 2.8, p. 31)
- **Local heading:** `2.8.1 Illustrative examples`
- **Topic:** Computing \(q(s,a)\) even for actions not chosen by current policy.
- **Setup:** stochastic policy; focus on state \(s_1\), analyze actions \(a_2,a_3\) and non-selected actions.
- **Core equations:**
  - \(q(s,a)=\sum_r p(r|s,a)r + \gamma\sum_{s'}p(s'|s,a)v(s')\)
  - Text examples: \(q(s_1,a_2)= -1 + \gamma v(s_2)\), \(q(s_1,a_3)=0+\gamma v(s_3)\) (notation follows chapter style).
- **Derivation/update steps:** evaluate each action by transition/reward model, regardless of whether \(\pi\) currently picks it.
- **Takeaway:** non-selected actions still have valid action-values; setting them to zero is incorrect.

---

## Chapter 3 — Optimal State Values and Bellman Optimality Equation

### Example 3.1 (toy max problem for BOE solving) (p. 38)
- **Local heading:** `Example 3.1`
- **Topic:** How to solve nested unknowns on RHS maximization.
- **Setup:** scalar equation \(x=\max_y(2x-1-y^2)\).
- **Core equations:** maximize over \(y\) first (attained at \(y=0\)), then solve \(x=2x-1\Rightarrow x=1\).
- **Derivation/update steps:** two-stage solve: optimize RHS policy variable, then solve value variable.
- **Takeaway:** same decomposition is used in BOE: optimize policy term first, then value fixed-point.

### Example 3.2 (weighted-sum maximization) (p. 38)
- **Local heading:** `Example 3.2`
- **Topic:** Why greedy choice solves policy maximization.
- **Setup:** maximize \(\sum_i c_i q_i\) with \(c_i\ge0\), \(\sum_i c_i=1\).
- **Core equations:** optimal \(c_i\) puts all mass on index with largest \(q_i\).
- **Derivation/update steps:** upper-bound weighted sum by \(\max_i q_i\), show bound is tight by one-hot coefficients.
- **Takeaway:** BOE-implied optimal policy is greedy in \(q(s,a)\).

### Example 3.3 and 3.4 (fixed-point/contraction examples) (pp. 40–42)
- **Local heading:** `Example 3.3`, `Example 3.4`
- **Topic:** contraction mapping theorem for BOE existence/uniqueness and iterative solution.
- **Setup:** examples \(x=0.5x\), \(x=Ax\) with \(\|A\|<1\), \(x=0.5\sin x\).
- **Core equations:** iterate \(x_{k+1}=f(x_k)\) to fixed point.
- **Derivation/update steps:** verify contraction inequality, apply theorem, obtain unique fixed point and iterative convergence.
- **Takeaway:** justifies value-iteration style updates for BOE.

### Example set: factors influencing optimal policy (Figure 3.4, pp. 49–50)
- **Local heading:** `3.5 Factors that influence optimal policies`
- **Topic:** effect of reward shaping and discount factor on optimal policies.
- **Setup:** baseline \(r_{boundary}=r_{forbidden}=-1, r_{target}=1, \gamma=0.9\); then vary \(\gamma\) and forbidden penalty.
- **Core equations:** BOE
  \[
  v(s)=\max_{\pi_s}\sum_a\pi(a|s)\Big(\sum_r p(r|s,a)r + \gamma\sum_{s'}p(s'|s,a)v(s')\Big).
  \]
- **Derivation/update steps:** solve BOE under parameter changes and compare resulting optimal policy/value maps.
- **Takeaway:** \(\gamma\) controls short-sighted vs far-sighted behavior; larger forbidden penalty changes risk-taking policy.

### Example set: no-meaningless-detour argument (Figure 3.5, pp. 52–53)
- **Local heading:** figure discussion near chapter summary
- **Topic:** discounting discourages detours even without per-step penalty tweaks.
- **Setup:** two policies differ by direct path vs detour to target.
- **Core equations:** direct-path return larger due to fewer discount multipliers (text computes two returns explicitly and compares).
- **Derivation/update steps:** compute both trajectory returns under same reward model; compare numerically.
- **Takeaway:** discounting alone can induce shortest-effective-path behavior.

---

## Chapter 4 — Value Iteration and Policy Iteration

### Example 4.1: Value-iteration walkthrough on 2x2 grid (Figure 4.2, pp. 59–61)
- **Local heading:** `4.1.2 Illustrative examples`
- **Topic:** stepwise implementation of value iteration.
- **Setup:** two-by-two grid, one forbidden and one target area, \(\gamma=0.9\), initial \(v_0(s)=0\).
- **Core equations:**
  - \(q_k(s,a)=\sum_r p(r|s,a)r + \gamma\sum_{s'}p(s'|s,a)v_k(s')\)
  - \(v_{k+1}(s)=\max_a q_k(s,a)\)
  - \(\pi_{k+1}(s)=\arg\max_a q_k(s,a)\)
- **Derivation/update steps:** compute tabled \(q_k\), update greedy policy and \(v_k\), repeat until policy stabilizes.
- **Takeaway:** value iteration alternates “evaluate current values” and “greedy improvement” implicitly.

### Example 4.2: Policy-iteration simple two-state example (Figure 4.3, pp. 67–68)
- **Local heading:** `4.2.3 Illustrative examples — A simple example`
- **Topic:** explicit policy evaluation then policy improvement.
- **Setup:** two-state toy system, actions {left, stay, right}, \(\gamma=0.9\).
- **Core equations:**
  - Policy evaluation: \(v^{\pi_k}=r^{\pi_k}+P^{\pi_k}v^{\pi_k}\)
  - Iterative evaluator: \(v^{j+1}_k=r_k+P_k v^j_k\)
  - Improvement: \(\pi_{k+1}=\arg\max_\pi(r^\pi+P^\pi v^{\pi_k})\)
- **Derivation/update steps:** solve Bellman equations for \(\pi_0\), compute \(q\)-table, switch to greedy actions, reach optimal policy quickly.
- **Takeaway:** policy iteration is conceptually clearer: full evaluation then improvement.

### Example 4.3: Policy-iteration evolution on larger grid (Figure 4.4, p. 69)
- **Local heading:** same subsection (`4.2.3`)
- **Topic:** convergence behavior across multiple policy updates.
- **Setup:** larger grid with boundary/forbidden/target rewards, \(\gamma=0.9\), random initial policy.
- **Core equations:** same PI update pair as above.
- **Derivation/update steps:** visualize policy/value snapshots across iterations until convergence.
- **Takeaway:** states near target stabilize first; value surface rises toward target.

### Example 4.4: Truncated policy iteration intuition (Figure 4.5, p. 72)
- **Local heading:** `4.3.2 Truncated policy iteration algorithm`
- **Topic:** tradeoff between value iteration and policy iteration.
- **Setup:** finite number of evaluation sweeps \(j_{truncate}\) before each policy improvement.
- **Core equations:** truncated evaluation \(v^{j+1}_k=r_k+P_kv^j_k\), then improvement.
- **Derivation/update steps:** compare regimes \(j_{truncate}=1\) (value-iteration-like) vs large \(j_{truncate}\) (PI-like).
- **Takeaway:** TPI unifies VI and PI and offers practical speed/accuracy balance.

---

## Chapter 5 — Monte Carlo Methods

### Example 5.1 (Motivating): Mean estimation from samples (Sec. 5.1, pp. 77–79)
- **Local heading:** `5.1 Motivating example: Mean estimation`
- **Topic:** model-free estimation via sample averages (foundation of MC value estimation).
- **Setup:** random variable \(X\), unknown distribution, samples \(x_1,\dots,x_n\).
- **Core equations:**
  - model-based: \(\mathbb{E}[X]=\sum_x p(x)x\)
  - sample-based: \(\hat x_n=\frac1n\sum_{i=1}^n x_i\)
  - incremental mean: \(\hat x_{n+1}=\hat x_n+\frac1{n+1}(x_{n+1}-\hat x_n)\)
- **Derivation/update steps:** convert batch average to recursive update used later in MC algorithms.
- **Takeaway:** MC learning is sample-mean estimation of returns.

### Example 5.2: MC-\(\varepsilon\)-greedy policy evolution (Figure 5.5, p. 92)
- **Local heading:** transition into `5.5 Exploration and exploitation of ε-greedy policies`
- **Topic:** policy snapshots after successive MC updates.
- **Setup:** single-episode updates with \(\varepsilon\)-greedy improvement.
- **Core equations:**
  - \(q\)-update by MC returns (chapter algorithm)
  - policy update: greedy action gets probability \(1-\varepsilon+\varepsilon/|A|\), others \(\varepsilon/|A|\).
- **Derivation/update steps:** generate episodes, update action-value estimates, re-form ε-greedy policy repeatedly.
- **Takeaway:** visible shift from exploratory behavior toward near-optimal control.

### Example 5.3: State-value degradation with larger \(\varepsilon\) (Figure 5.6, p. 93)
- **Local heading:** `5.5 Exploration and exploitation of ε-greedy policies`
- **Topic:** exploration–exploitation tradeoff quantified in value maps.
- **Setup:** policies with same greedy backbone but different \(\varepsilon\).
- **Core equations:** ε-greedy probability rule as above.
- **Derivation/update steps:** evaluate value maps for multiple \(\varepsilon\), compare target/forbidden-region effects.
- **Takeaway:** larger \(\varepsilon\) improves exploration but lowers asymptotic policy quality.

### Example 5.4: Optimal ε-greedy policy changes with ε (Figure 5.7, p. 94)
- **Local heading:** same section
- **Topic:** optimal policy under ε-greedy constraint differs from globally greedy optimum when ε is large.
- **Setup:** solve for best policy within fixed-\(\varepsilon\) policy class.
- **Core equations:** constrained policy class objective (chapter’s ε-greedy optimization discussion).
- **Derivation/update steps:** compare optimal ε-greedy maps for ε = 0, 0.1, 0.2, 0.5.
- **Takeaway:** “best under exploration constraint” can differ from unconstrained optimal policy.

### Example 5.5: Exploration ability comparison (Figure 5.8, pp. 95–96)
- **Local heading:** end of Sec. 5.5 discussion
- **Topic:** visitation coverage under different ε values.
- **Setup:** long episodes (up to 1M steps) under ε-greedy behavior.
- **Core equations:** visitation-frequency statistics (empirical counts per state-action pair).
- **Derivation/update steps:** run long trajectories for ε=1 vs ε=0.5 and compare count distributions.
- **Takeaway:** lower ε can severely skew visitation and hurt sample efficiency.

---

## Chapter 7 — Temporal-Difference Methods

### Example 7.1: Sarsa path-learning example (Figure 7.2, pp. 135–136)
- **Local heading:** Sarsa simulation example text near Algorithm 7.1
- **Topic:** on-policy TD control behavior over episodes.
- **Setup:** fixed start/goal grid, reward setting \(r_{target}=0\), \(r_{forbidden}=r_{boundary}=-10\), \(r_{other}=-1\), \(\alpha=0.1\), \(\varepsilon=0.1\).
- **Core equations:**
  - Sarsa update: \(q_{t+1}(s_t,a_t)=q_t(s_t,a_t)+\alpha_t\big[r_{t+1}+\gamma q_t(s_{t+1},a_{t+1})-q_t(s_t,a_t)\big]\)
  - ε-greedy policy improvement.
- **Derivation/update steps:** update single visited pair per step, immediately refresh local policy, continue episode.
- **Takeaway:** episode return improves and path length tends to shrink, but occasional exploratory drops remain.

### Example 7.2: Q-learning on-policy version (Figure 7.3, p. 144)
- **Local heading:** `7.4.4 Illustrative examples`
- **Topic:** control to optimal path using max bootstrap target.
- **Setup:** same pathfinding-style grid task.
- **Core equations:**
  - \(q_{t+1}(s_t,a_t)=q_t(s_t,a_t)+\alpha_t\big[r_{t+1}+\gamma\max_{a'}q_t(s_{t+1},a')-q_t(s_t,a_t)\big]\)
- **Derivation/update steps:** run episodes, update by greedy next-state target; evaluate total reward and episode length curves.
- **Takeaway:** Q-learning can converge to optimal-path behavior in this setup.

### Example 7.3: Off-policy Q-learning and exploration dependence (Figures 7.4 and 7.5, pp. 145–147)
- **Local heading:** same subsection (`7.4.4`)
- **Topic:** effect of initial values and behavior-policy exploration in off-policy learning.
- **Setup:** behavior policy from uniform (ε=1 equivalent) to ε-greedy with smaller ε; compare RMSE convergence.
- **Core equations:** Q-learning update above; off-policy distinction between behavior policy \(b\) and target greedy policy \(\pi_T\).
- **Derivation/update steps:** hold target as greedy while changing behavior-policy exploration; compare learned policies and error curves.
- **Takeaway:** insufficient exploration slows or degrades convergence strongly.

---

## Chapter 8 — Value Function Methods

### Example 8.1: Curve-fitting motivation (Sec. 8.1, pp. 153–155)
- **Local heading:** `8.1 Value representation: From table to function`
- **Topic:** replacing tables with parameterized approximators.
- **Setup:** represent \(\hat v(s;w)\) by linear models with handcrafted features.
- **Core equations:**
  - \(\hat v(s;w)=\phi(s)^T w\)
  - Examples include \(\phi(s)=[s,1]^T\) and \(\phi(s)=[s^2,s,1]^T\).
- **Derivation/update steps:** fit points in \((s,\hat v)\)-space; compare representational capacity and storage.
- **Takeaway:** function approximation gains scalability but introduces approximation error.

### Example 8.2: Stationary-distribution illustration for weighting (Figure 8.5, around p. 160)
- **Local heading:** discussion before Sec. 8.2.4
- **Topic:** long-run visitation distribution \(d\) in objective weighting.
- **Setup:** ε-greedy policy on small grid; compare theoretical \(d\) vs empirical long-episode estimates.
- **Core equations:**
  - \(d_k^T=d_0^T P^k\)
  - \(\lim_{k\to\infty}P^k=\mathbf 1 d^T\), so \(d_k\to d\) under regularity.
- **Derivation/update steps:** compute theoretical stationary distribution from \(P\), then estimate by visit frequencies.
- **Takeaway:** weighting in approximation objectives is policy-dependent via visitation frequency.

### Example 8.3: TD-linear illustrative examples (Figure 8.6, pp. 164–165)
- **Local heading:** `8.2.4 Illustrative examples`
- **Topic:** approximating full value table with low-dimensional features.
- **Setup:** 5x5 grid, random policy (uniform over actions), true value table visualized as surface.
- **Core equations:**
  - objective: \(J(w)=\mathbb E[(v(S)-\hat v(S;w))^2]\)
  - TD-linear update (chapter algorithm): \(w_{t+1}=w_t+\alpha_t\delta_t\nabla_w\hat v(S_t;w_t)\), \(\delta_t=R_{t+1}+\gamma\hat v(S_{t+1};w_t)-\hat v(S_t;w_t)\).
- **Derivation/update steps:** choose features, run TD updates, inspect approximation quality and policy-evaluation accuracy.
- **Takeaway:** feature quality critically determines approximation fidelity and downstream control quality.

---

## Chapter 9 — Policy Gradient Methods

### Example-based explanation 9.1: Softmax policy parameterization (Figure 9.2, pp. 192–199)
- **Local heading:** `9.1 Policy representation: From table to function`
- **Topic:** converting tabular policy to differentiable parameterized policy.
- **Setup:** policy parameter \(\theta\in\mathbb R^m\), preferences \(h(s,a;\theta)\), softmax output over actions.
- **Core equations:**
  - \(\pi_\theta(a|s)=\dfrac{e^{h(s,a;\theta)}}{\sum_{a'} e^{h(s,a';\theta)}}\)
- **Derivation/update steps:** input state to function (or NN), compute action probabilities, sample actions, optimize scalar objective by gradient ascent.
- **Takeaway:** policy-gradient methods optimize policy directly in parameter space, not via explicit value tables.

### Example-based explanation 9.2: Undiscounted average-reward gradient nuance (around p. 208)
- **Local heading:** theorem discussion near `Theorem 9.5`
- **Topic:** handling non-uniqueness of differential value while keeping unique average reward gradient.
- **Setup:** Poisson-equation form in undiscounted case; additive constant ambiguity in value function.
- **Core equations:** text shows cancellation argument leading to uniqueness of \(\bar r\) gradient even when \(v\) is non-unique.
- **Derivation/update steps:** use Poisson equation identities to eliminate additive constant; derive valid policy gradient for average reward.
- **Takeaway:** policy-gradient derivation remains well-posed in average-reward setting despite value-shift ambiguity.

