# Lecture 7: Decision Making 2 — Free Energy Principle & Bayesian Models

## From Signal Integration to Bayesian Brain

Recap: Optimal signal integration uses Bayes' rule to combine cues weighted by reliability.

Now: Apply Bayesian framework to **all of perception and cognition**.

## Bayes' Rule in Cognitive Modeling

P(θ|D) = P(D|θ) · P(θ) / P(D)

| Term | Name | Role |
|------|------|------|
| P(θ\|D) | Posterior | Updated belief after seeing data |
| P(D\|θ) | Likelihood | How probable data is given cause |
| P(θ) | Prior | Belief before seeing data |
| P(D) | Marginal likelihood (model evidence) | Normalizing constant |

## Helmholtz's Theory of Perception

- **Likelihood principle:** We perceive what is most probable given past experience
- **Unconscious inference:** Perceptions constructed based on unconscious assumptions
- Perception is always learned — never "raw"

## The Forward and Backward Problems

### Forward Problem (Generative Model / Decoder)
- **Given causes θ** → predict sensory data D
- P(D|θ): "If there's a cat, what should my retina show?"
- Top-down process: higher areas → lower areas
- Training a decoder is often simpler than training an encoder

### Backward Problem (Inference / Encoder)
- **Given data D** → infer most probable causes θ
- P(θ|D): "Given this pattern, what's out there?"
- Bottom-up process: sensory input → updates beliefs
- This is usually intractable to compute exactly

## Hierarchical Autoencoder

- Perception causes θ = low-dimensional encoding of sensory stimuli
- Prior P(θ) is constrained by **higher levels** of hierarchy
- Context matters: seeing green in a forest vs. desert activates different priors
- Multiple hierarchical levels: each level constrains the one below

## Predictive Processing

### Core Idea
Instead of building perception bottom-up from raw data:
1. Start with a **decoder** (generative model) to generate predictions
2. Work with **prediction errors** rather than raw sensory signals
3. Predictions flow top-down; errors flow bottom-up

### Process
1. Higher areas generate predictions about expected input
2. Lower areas compare actual input with predictions
3. **Prediction error** = mismatch between expected and actual
4. Error propagates upward → model updates → better predictions
5. **Perception** = the hypothesis that best minimizes prediction error

### Key Insight
> We don't perceive the world directly — we perceive our brain's best explanation of sensory data.

## Approximate Variational Inference

### Problem
Computing true posterior P(θ|D) is intractable for complex models.

### Solution
Approximate it with a simpler distribution Q(θ|D) ≈ P(θ|D)

Minimize KL divergence between Q and true posterior:
- D_KL(Q(θ) ‖ P(θ|D))

Simultaneously:
- Learn parameters of P (generative model) to minimize prediction error
- Learn parameters of Q (recognition model) to approximate the posterior

## Free Energy Principle (FEP)

### Definition
**Free Energy = −ELBO** (negative Evidence Lower Bound)

Equivalent formulations:
- F = E_Q[−log P(D,θ)/Q(θ)]
- F = E_Q[−log P(D,θ)] − H(Q(θ)) ← expected energy minus entropy
- F = −log P(D) + D_KL(Q(θ) ‖ P(θ|D)) ← surprise + divergence

### Interpretation
- **Surprise** (−log P(D)): how unexpected the data is under the model
- **KL divergence:** how far Q is from the true posterior
- Minimizing Free Energy → minimizes both surprise and inference error

### Friston's Framework
- All biological systems minimize free energy
- Perception = updating Q to minimize F (inference)
- Action = changing D to minimize F (active inference)

## Active Inference

Free Energy can be minimized in two ways:
1. **Perception:** Adjust internal distributions P and Q (update beliefs to match data)
2. **Action:** Choose actions to change sensory states D (make the world match predictions)

This unifies perception and action under one principle.

## Relation to Variational Autoencoders (VAEs)

| | FEP (Brain) | VAE (ML) |
|---|---|---|
| Encoder | Q(θ\|D) ≈ P(θ\|D) | Encoder network |
| Decoder | P(D\|θ) | Decoder network |
| Objective | Minimize Free Energy | Maximize ELBO |
| Action | Active inference (change world) | N/A |

**Key:** FEP models are biological analogs of VAEs. Both use variational inference. FEP adds action selection, making it broader.

## Summary

According to Predictive Processing, sensory experiences are constructed by:
- Continuously generating and refining hypotheses about the world
- Using sensory input primarily to **correct prediction errors**
- NOT building perception from scratch each moment
- The brain is constantly guessing the world — and checking how wrong it is

## Literature
- Lee & Wagenmakers (2014). Bayesian Cognitive Modeling: A Practical Course.
- Friston, K. (2010). The free-energy principle: a unified brain theory?
