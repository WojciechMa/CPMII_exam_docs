# Lecture 5: Game Theory

## Overview

Game theory: mathematical framework for studying strategic interaction between rational decision-makers.

**Applications to cognitive science:** modeling collective behavior, social coordination, emergence of conventions, evolutionary dynamics.

## Agent Assumptions in Game Theory

1. **Rational** — maximizes own utility/payoff
2. **Strategic** — considers others' possible actions
3. **Self-interested** — motivated by individual payoff
4. **Informed** — knows rules, payoffs, available strategies (in basic models)
5. **Simultaneous** — decisions made without knowing others' choices

## Key Concepts

### Normal Form Game
- Players, strategies, payoff matrix
- Each cell: outcome for all players given their strategy choices

### Nash Equilibrium (NE)
A strategy profile where **no player can unilaterally improve** their payoff by changing strategy, given others stay fixed.

Properties:
- Every player plays best response to others
- Stable state — no incentive to deviate
- May have 0, 1, or multiple NE
- Not necessarily socially optimal (Prisoner's Dilemma: both defect = NE but suboptimal)

### Mixed Strategies
- Probability distribution over pure strategies
- Player randomizes to be unpredictable
- **Nash's Theorem:** Every finite game has at least one NE (possibly mixed)
- Example: Rock-Paper-Scissors → mixed NE = (⅓, ⅓, ⅓)

## Classic Games

### Ultimatum Game (Quiz 1)
- Proposer splits $10; Responder accepts or rejects
- Rational prediction: Proposer offers $1, Responder accepts (any amount > 0)
- **Empirical reality:** Modal offer ≈ $4-5; offers < 20% frequently rejected
- Shows: fairness norms, spite, reputation matter — agents aren't purely rational

### Public Goods Game (Quiz 2)
- Each player invests 0-5$ into public pool
- Pool doubled, divided equally among all players
- **Dominant strategy:** Free-ride (invest $0, benefit from others)
- **Empirical:** Initial cooperation, gradual decline
- Solutions: punishment, reputation, repeated interaction

### Prisoner's Dilemma
- Both cooperate → good outcome
- Temptation to defect → both worse off
- NE = both defect (but mutual cooperation is Pareto-optimal)

## Agent-Based Modeling

### What is it?
- Simulation of many agents following simple rules
- Emergent behavior from local interactions
- No central controller

### Relation to Game Theory
- Agents play games against neighbors
- Evolutionary dynamics: successful strategies spread
- Can study: emergence of cooperation, conventions, segregation (Schelling)

## Coalition Games

- **Splitting resources in groups**
- Shapley value: fair distribution based on marginal contributions
- Core: set of allocations where no subgroup can do better alone
- Application: modeling fairness in collective decisions

## Key Takeaways

- Game theory provides formal tools for modeling social/collective cognition
- Real humans deviate from pure rationality (fairness, emotions, bounded rationality)
- Agent-based models bridge game theory with complex adaptive systems
- Evolutionary game theory explains convention emergence without requiring rationality

## Literature
- Shoham & Leyton-Brown (2008). Multiagent Systems: Algorithmic, Game-Theoretic, and Logical Foundations.
