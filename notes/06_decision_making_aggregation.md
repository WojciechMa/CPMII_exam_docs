# Lecture 6: Decision Making 1 — Information Aggregation

## Wisdom of the Crowds

**Classic demonstration:** Averaging many independent guesses → surprisingly accurate group estimate.

Example from class:
- "How heavy is the heaviest liger?" → group average ≈ 395-420 kg; correct = 418 kg
- "How many lakes in Poland?" → group average ≈ 10,000

### Why it works: Bienaymé Formula

If x = (x₁, ..., xₙ) are independent random variables with variance σ²:

**Var(x̄) = σ²/n**

Conditions for optimality of averaging:
- Equal variance among agents
- **No systematic bias**
- **Independence** of observations

When these fail (correlation, shared bias), wisdom of crowds breaks down.

## Signal Detection Theory (SDT)

### Origin
- Started by radar researchers (detecting signal in noise)
- Adopted by psychologists for studying perceptual sensitivity

### Framework
- Observer must decide: signal present or absent?
- Two overlapping distributions: noise-only vs. signal+noise
- Decision = set a criterion (threshold)

### Key Measures
- **d' (sensitivity):** distance between distribution means (ability to discriminate)
- **c (criterion/bias):** location of decision threshold (liberal vs. conservative)

### Hit, Miss, False Alarm, Correct Rejection
|  | Signal Present | Signal Absent |
|--|--|--|
| Respond "yes" | Hit | False Alarm |
| Respond "no" | Miss | Correct Rejection |

## 2-Alternative Forced Choice (2-AFC)

### Task Structure
- Participant presented with two alternatives → must choose one
- No "I don't know" option (forced choice)
- Examples: "Which circle is larger?", "Was signal on left or right?"

### Psychometric Function
- S-shaped (sigmoid) curve: stimulus level → P(correct)
- Fitted to behavioral data

### Parameters
| Parameter | Meaning |
|-----------|---------|
| **Threshold (α)** | Stimulus level at 50% correct (above chance) |
| **Slope (β)** | Steepness — how quickly performance changes with intensity |
| **Bias (c)** | Systematic preference for one response |
| **Lapse rate (λ)** | Upper asymptote < 1 (inattention, motor errors) |

## Bayesian Signal Integration

### Problem
How to combine signals from multiple sources (senses, agents)?

### Bayesian Solution
P(S|r₁, r₂) = P(r₁, r₂|S) · P(S) / P(r₁, r₂)

- S = source signal, r₁, r₂ = cues from different sources
- **Weak interpretation:** Mathematical model of universal principle, realized limitedly by specific mechanisms
- **Strong interpretation:** Useful metaphor for actual perception process

### Optimal Integration
- Weight each cue by its **reliability** (inverse variance)
- More reliable cues weighted more heavily
- Combined estimate has lower variance than any single cue

## Group Decision Making

### Conditions Impacting Quality (Bahrami et al., 2010)

1. **Variation in individual confidence** — if visible, group can weight the best member
2. **Communication & feedback** — enables error correction, information sharing
3. **Independence** — correlated errors reduce benefit of aggregation
4. **Consensually incorrect stimuli** — shared bias → group converges on wrong answer
5. **Ability to communicate confidence** — metacognitive access matters

### Effect of Correlation Between Agents

- **Independent:** Var(x̄) = σ²/n → averaging reduces error linearly with group size
- **Correlated:** Effective sample size reduced; shared bias amplified; averaging less beneficial
- In limit of perfect correlation: N agents = 1 agent
- **Implication:** Diversity of perspective > group size

## Multisensory Integration Errors

### The McGurk Effect
- **Audio:** "ba" + **Visual:** mouth saying "ga" → **Perceived:** "da"
- Brain creates a "compromise" percept that matches neither input
- Demonstrates: perception = active inference, not passive reception
- Integration isn't always "optimal" — can produce systematic errors

### When Integration Fails
- Conflicting modalities → illusory percept
- Large conflict → may ignore one modality ("capture")
- Need to detect inconsistency: P(r₁, r₂|S) requires independence assumption

## Literature
- Bahrami, B., et al. (2010). Optimally interacting minds. Science, 329(5995), 1081-1085.
