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
   - State of the Art:  
     - ACT-R + SGOMS modeling of novice/expert Python problem-solving, goal decomposition, error prediction  
     - Bayesian rational models of function learning, hint-based generalization, priors on code patterns  
   
4. **Model Structure**  
   - **Architecture**: ACT-R modules + Bayesian subsymbolic layers  
   - **Core flow**: Perceive → Bayesian prior/hypothesis → SGOMS goal decomposition → Production firing → Action → Feedback → Posterior update  
   - **Primitives**: chunks, productions, buffers, goals, priors, utilities, activations, noise  
   - **Symbolic instance example**: solving `def factorial(n): …` (recursive vs. iterative paths)


## License

MIT (or choose your preferred open-source license)

---

Created from a conversation on February 20, 2026  
Last updated: [insert date]
