# CogniCode: Bayesian-ACT-R Model of Thought Processes in Python Programming

## Project Overview

This project explores the creation of a **hybrid cognitive model** that simulates a student's thought processes while solving a Python coding task. The model combines:

- **ACT-R cognitive architecture** (with SGOMS hierarchical goal structuring) for symbolic, production-rule-based cognition  
- **Bayesian rational models** (inspired by Williams et al.) for probabilistic function learning, generalization from examples, and inductive biases in novices

The goal is to represent how thoughts emerge, connect, and evolve in a bounded, goal-directed activity (e.g., writing a `factorial(n)` function), capturing novice-to-expert transitions, error patterns, and learning dynamics.

The discussion originated from interest in dynamic, interactive 3D visualizations of personal knowledge graphs (inspired by @poetengineer__'s Obsidian → 3D embeddings project), then narrowed to modeling **cognition during coding** — specifically using symbolic, equation-based descriptions rather than purely visual graphs.

## Key Discussion Stages

1. **Initial Inspiration**  
   - 3D property-graph visualization of thought patterns from Obsidian notes  
   - Centralized, Decentralized, and Distributed topologies  
   - Hand-gesture interaction in TouchDesigner  
   - Hybrid embeddings + LLM labeling for semantic edges

2. **Application to Coding Cognition**  
   - Shifted focus: model a student's thought process during a Python task (e.g., prime checker, factorial)  
   - Goal: turn static notes/code fragments into a dynamic, explorable model of cognition  
   - Early idea: parse Markdown vault → build NetworkX graph → 3D matplotlib visualization with topologies

3. **Theoretical Foundations**  
   - Preference for two key research strands:  
     - **Vorobeva (2021)** — ACT-R + SGOMS modeling of novice/expert Python problem-solving, goal decomposition, error prediction  
     - **Williams et al. (2008–2019)** — Bayesian rational models of function learning, hint-based generalization, priors on code patterns  
   - Decision: create a novel hybrid that does not yet exist in the literature

4. **Model Structure**  
   - **Architecture**: ACT-R modules + Bayesian subsymbolic layers  
   - **Core flow**: Perceive → Bayesian prior/hypothesis → SGOMS goal decomposition → Production firing → Action → Feedback → Posterior update  
   - **Primitives**: chunks, productions, buffers, goals, priors, utilities, activations, noise  
   - **Symbolic instance example**: solving `def factorial(n): …` (recursive vs. iterative paths)

5. **Mathematical Formalization**  
   - **ACT-R equations**  
     - Chunk activation:  
       $$ A_i = B_i + \sum_j W_j S_{ji} + \sum_k MP_k \text{Sim}_{kl} + \mathcal{N}(0, \sigma) $$  
     - Base-level learning:  
       $$ B_i = \ln \left( \sum_{k=1}^n t_k^{-d} \right) \quad (d \approx 0.5) $$  
     - Retrieval probability & time:  
       $$ P_i = \frac{e^{A_i / \tau}}{\sum_j e^{A_j / \tau}}, \quad T_i = F e^{-A_i} $$  

   - **Bayesian rational inference** (function learning & pattern generalization)  
     - Prior: $$ p(f) \sim \mathcal{N}(\mathbf{0}, \Sigma_b) $$ or Beta for discrete choices (e.g., recursion)  
     - Posterior:  
       $$ p(f | \mathbf{x}_n, \mathbf{t}_n) = \frac{p(\mathbf{t}_n | f, \mathbf{x}_n) \, p(f)}{\int p(\mathbf{t}_n | f, \mathbf{x}_n) \, p(f) \, df} $$  
     - Predictive distribution:  
       $$ p(y_{n+1} | x_{n+1}, \mathbf{x}_n, \mathbf{t}_n) = \int p(y_{n+1} | f, x_{n+1}) \, p(f | \mathbf{x}_n, \mathbf{t}_n) \, df $$

## Current Status & Next Steps

- Conceptual & mathematical skeleton is defined  
- No implementation yet (neither simulation in ACT-R software nor Python prototype)  
- Potential future directions:  
  - Implement model in Python (using e.g. `pyactr` + `pymc` or `numpyro` for Bayesian parts)  
  - Simulate novice/expert behavior on simple Python tasks  
  - Predict common errors & optimal hint timing  
  - Visualize thought trajectories (3D graph evolution over time)  
  - Compare model predictions to real student data/logs

## License

MIT (or choose your preferred open-source license)

---

Created from a conversation on February 20, 2026  
Last updated: [insert date]
