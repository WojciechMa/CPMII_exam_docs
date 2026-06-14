# Lecture 13: Modeling Language

## Two Approaches to Language

### 1. Formal Grammars
- Increasingly complex generative grammars
- Rules as primitive; language = rule system
- Language-specific computational mechanisms

### 2. Neural Network / Dynamical Approach
- Let multiple soft constraints act on performance
- Information on many levels simultaneously
- General learning processes explain "linguistic" effects
- Dynamical processes → emergence of structure (like reaction-diffusion models)

## Key Principle: Multiple Timescales
Language operates on:
- **Evolutionary** timescale (species development)
- **Cultural/learning** timescale (acquisition during lifetime)
- **Online/use** timescale (moment-to-moment processing)

## Example 1: Past Tense Acquisition (Rumelhart & McClelland, 1986)

### The Phenomenon
Children learning English show three stages:
1. Correct use of both regular and irregular (went, came)
2. **Overgeneralization** of regular form (goed, comed)
3. Re-establishment of correct irregular forms

### The Model
- Simple **pattern associator** (not even a hidden layer)
- Training:
  - Phase 1: 10 high-frequency verbs (2 regular, 8 irregular) — 100 updates
  - Phase 2: 410 medium-frequency verbs (334 regular, 76 irregular) — 190 presentations
- Testing: 86 lower-frequency verbs

### Results
- Faster learning for regular verbs
- Initial preservation of regular-irregular distinction
- **Overgeneralization emerges** (applies -ed to irregulars)
- Eventually recovers correct forms

### Achievement
- Complex, seemingly rule-based behavior emerges from **general learning mechanisms**
- No explicit rules encoded — behavior arises from network interactions
- Shows dependence of learning on **input structure** (frequency distribution)

## Introducing Dynamics: Recurrent Networks

### Jordan Net (1986)
- Associates static "plan" input with sequence of outputs
- Hidden units see their own previous output
- Subsequent output shaped by previous one
- Theoretical gain: sequence, process

### Elman Net: "Finding Structure in Time" (1990)

**Architecture:**
- Context units (hidden) preserve hidden layer activation from t-1
- Blend previous hidden state with current input at time t
- Provide "memory" of previous internal state
- Learning: backpropagation (recurrent connections not changed)

**Key difference from feedforward:**
- Can represent **temporal dependencies**
- Maintains internal state ("memory")
- Processes sequential data naturally

### What Elman Nets Discover

**Words (sub-regularities):**
- Trained to predict next letter/phoneme in continuous stream
- Network discovers word boundaries without spaces
- Prediction error spikes at word boundaries

**Lexical classes:**
- Hidden layer activations form clusters
- Clusters correspond to semantic/syntactic categories
- Hierarchical organization: nouns vs. verbs, then finer distinctions
- Discovered from sequential statistics, not labeled data

## Feedforward vs. Recurrent: Key Difference for Language

| | Feedforward (R&M) | Recurrent (Elman) |
|---|---|---|
| Input handling | Each input independent | Sequential, context-dependent |
| Memory | None | Previous hidden state |
| Temporal dependencies | Cannot capture | Core capability |
| Setup for language | Non-trivial encoding needed | Natural fit for sequences |

## Are All NNet Language Models Cognitively Plausible?

### Psychologically PLAUSIBLE:
- Elman net — biologically inspired architecture
- Hidden layer activations interpretable as representations
- Coupled interacting networks (modeling dialogue)
- Limited to what's inside human minds/bodies

### Psychologically IMPLAUSIBLE:
- **Transformers / LLMs** — "not particularly realistic cognitively or neuronally"
- Use "brute power" rather than mimicking human cognition
- "Most current models focus too closely on language itself" — neglect embodiment, interaction

## Properties of NNets for Language Modeling

### Advantages
- Learn from data (cultural transmission)
- Handle complex patterns through architecture
- Distributed representation (hidden layer imaging)
- Robustness and generalization (graceful degradation)
- Dynamic, context-sensitive processing (RNNs)
- "Soft constraints" — flexible adaptation

### Limitations
- Focus too closely on language itself (ignore embodiment)
- Lack "cognitive understanding" — no guarantee of matching human comprehension
- Hard to combine fast learning + gradual learning
- Must be tested against real situations, not just simulations
- "Biggest challenge": capture dynamic soft constraints AND seemingly rule-based functioning

## Experimental Semiotics (Bridge to Lecture 14)

Study communication as a form of joint action:
- Create novel communication systems in the lab
- Observe emergence of structure, conventions, compositionality
- Bridge between language modeling and language evolution

## Literature
- Elman, J. L. (1990). Finding Structure in Time. Cognitive Science, 14, 179-211.
- Rumelhart, D. & McClelland, J. (1986). On learning the past tenses of English verbs.
- Garrod & Galantucci (2011). Experimental Semiotics: A Review.
