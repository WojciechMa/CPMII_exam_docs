# CPM II 2026 — Quick Reference (Cheat Sheet)

## Lecture 1: Introduction
- **Info-processing:** stages, stimuli → response, closed systems, start-stop cognition
- **Interaction-dominant:** perception-action cycles, continuous coupling, open systems, self-organization
- Key figures: Gibson (ecological), Kelso (coordination dynamics), Varela (enactivism)

## Lecture 2: Categorization
- **Wittgenstein:** family resemblance, no necessary+sufficient conditions, graded membership
- **MDS:** recovers perceptual space from similarity data; minimizes Stress; preserves distances
- **Prototype model:** strong abstraction, single mean per category, fails on XOR
- **Exemplar model (GCM):** no abstraction, stores all instances, similarity S = e^{−c·d}, Luce choice rule
- Distance: Euclidean (p=2) or Manhattan (p=1); Shepard's universal law of generalization

## Lecture 3: ART & Attention
- **Bottleneck theories:** limited capacity → filter (early: physical; late: semantic)
- **Selection-for-action:** attention enables coherent action, tied to goals, not "deficiency"
- Evidence for semantic processing of unattended: cocktail party, Gray & Wedderburn, Von Wright GSR
- **ART principle:** stability-plasticity dilemma → new category when top-down ≠ bottom-up
- **Vigilance:** high → many categories (autism model); low → few categories (schizophrenia model)
- **ARTSCAN:** attentional shrouds, surface-based attention, view-invariant object recognition

## Lecture 4: Hopfield Network
- **CAM:** access memory by content (partial cue → complete pattern)
- Energy: E = −½ΣᵢⱼwᵢⱼVᵢVⱼ − ΣᵢIᵢVᵢ; local minima = stored memories
- Arbitrary associations: concatenate [stimulus A | stimulus B], store as one pattern
- **TSP encoding:** 2D neuron grid, Vₓᵢ=1 means city x at step i; 4 penalty terms (A,B,C,D)
- D-Wave: physical Hopfield implementation (quantum annealing)

## Lecture 5: Game Theory
- **Nash Equilibrium:** no player gains by unilateral deviation
- **Mixed strategy:** probability distribution over pure strategies; always exists (Nash theorem)
- Ultimatum game: rational = accept any >0; empirical ≈ 40-50% offers, reject <20%
- Public goods game: rational = free-ride; cooperation sustained by punishment/reputation
- Agent assumptions: rational, strategic, self-interested, informed

## Lecture 6: Decision Making 1 (Aggregation)
- **Bienaymé:** Var(x̄) = σ²/n (only if independent, equal variance, no bias)
- **SDT:** signal + noise distributions; d' = sensitivity, c = criterion/bias
- **2-AFC:** forced binary choice; psychometric curve (threshold, slope, bias, lapse)
- **Wisdom of crowds:** works when independent + diverse; fails when correlated/biased
- **McGurk effect:** audio "ba" + visual "ga" → perceived "da" (multisensory integration error)

## Lecture 7: FEP & Bayesian Models
- **Bayes:** P(θ|D) = P(D|θ)P(θ) / P(D)
- **Forward problem:** causes → data (generative model, decoder, top-down)
- **Backward problem:** data → causes (inference, encoder, bottom-up)
- **Predictive Processing:** brain generates predictions, computes prediction error, updates model
- **Free Energy:** F = −ELBO = surprise + KL(Q‖P); minimized by perception AND action
- **Active Inference:** minimize FE by changing beliefs OR changing sensory input through action
- **VAE connection:** encoder = Q(θ|D), decoder = P(D|θ), objective = maximize ELBO

## Lecture 8: Sensorimotor Learning (SOM)
- **SOM:** competitive learning, BMU + neighborhood update, preserves topology
- Neighbors in SOM grid → similar in input space
- **Why not simple mapping for mirroring:** delays, motor noise, coordinate transform, noise
- **Prediction:** time-windowed input, GWR (Growing When Required), associative transitions
- Lab: color quantization, Iris clustering, TSP with 1D SOM, hand gesture recognition

## Lecture 9: Fractal Dimension & Gait
- **Self-organization:** chaos → order without external control; power-law structures
- **Fractal dimension:** N = ε^{−D}; D = −log(N)/log(ε)
- **White noise:** independent, flat spectrum, D=2
- **Brownian (red):** x(t+1)=x(t)+ε, P(f)~1/f², D=1.5
- **Pink noise (1/f):** between white and red, found in human RT and gait, D'=1
- **DFA exponent α:** 0.5=uncorrelated, 1=pink, 1.5=red; gait: 0.5<α<1.0
- **Gait:** long-range correlations, sensitive to age (0.93→0.69), predicts falls & Parkinson's

## Lecture 10: Motor Coordination (HKB)
- **Ecological psych:** primacy of action, affordances, coupling to environment
- **Bernstein's problem:** degrees of freedom → synergies (functional binding)
- **Synergy features:** dimensionality reduction + reciprocal compensation
- **HKB model predictions:** (1) in-phase more stable than anti-phase; (2) speed-dependent transition (bifurcation) from anti-phase → in-phase
- Evidence: critical slowing down, critical fluctuations before transition, hysteresis
- Kelso et al. 1984: jaw perturbation → lip/tongue compensation in 20-30ms

## Lectures 11-12: RQA & Interpersonal Coordination
- **RQA:** recurrence in state space of ONE system; measures: RR, DET, MaxLine, entropy
- **cRQA:** cross-recurrence between TWO systems; reveals coupling strength
- **Diagonal profile:** RR as function of lag → shows lead/lag and coupling strength
- Shockley et al. 2003: postural coupling in conversation (even without seeing partner)
- Richardson & Dale 2005: speaker-listener gaze coupling with ~2s listener lag
- **Mother-infant development:** broad→narrow profile, diffuse→focused coordination

## Lecture 13: Language Modeling
- **Elman net (SRN):** hidden units + context units (copy of previous hidden state); finds structure in time
- **Past tense model (R&M 1986):** simple pattern associator → overgeneralization effect emerges
- **Word superiority effect, word boundaries** — discovered by network without explicit rules
- **Lexical classes:** Elman net discovers them via hidden-layer clustering (semantic hierarchy)
- **Psychologically plausible** (Elman) vs **implausible** (Transformers: brute force, no cognitive realism)
- NNet advantages: learns from data, distributed representation, robust to noise
- NNet limits: "focus too closely on language itself", lack embodiment, no fast learning

## Lecture 14: Evolution of Communication
- **Garrod et al. 2007 "pictionary":** signs become arbitrary through interaction; alternating roles → faster
- **Galantucci 2005:** communication emerges for coordination (not just reference)
- Communication systems: (a) numeration-based, (b) icon-based, (c) layout-based
- **Lewis signaling game:** evolutionary dynamics → stable conventions without reasoning
- Limitations: no compositionality, no syntax, no noise, simplified agents
- Extensions: add structure, hierarchy, vocabulary limits → compositionality emerges

## Lecture 15: Humane Cognitive Science
- **Social cognition (sense 1):** cognition OF social objects (ToM, face recognition)
- **Social cognition (sense 2):** cognition IS social (Vygotsky: product of collaboration)
- **Engaged epistemology (De Jaegher):** 2nd-person knowledge, "loving knowing," letting be
- Translating 1st/2nd person → 3rd person = double work or destruction
- William James 1884: extraordinary sensitivity to others' attention
- Example: dementia care — emotion connection is last to go

---

## Key Models → One-Line Summary

| Model | Does what |
|-------|-----------|
| MDS | Recovers perceptual space from similarity judgments |
| GCM (Nosofsky) | Exemplar categorization via weighted similarity |
| ART1 (Grossberg) | Online categorization solving stability-plasticity |
| Hopfield Network | Content-addressable memory via energy minimization |
| HKB (Haken-Kelso-Bunz) | Bimanual coordination, predicts phase transitions |
| SOM (Kohonen) | Topology-preserving dimensionality reduction |
| Elman SRN | Finds sequential structure in language |
| Lewis Signaling Game | Convention emergence through evolutionary dynamics |
| Free Energy / PP | Perception as prediction error minimization |
| DFA | Estimates fractal dimension / long-range correlations |
| cRQA | Measures coupling between two dynamical systems |

---

## Key People

| Person | Associated with |
|--------|----------------|
| Grossberg | ART, ARTSCAN |
| Nosofsky | GCM (exemplar model) |
| Hopfield | Content-addressable memory, energy function |
| Kelso | HKB model, coordination dynamics |
| Bernstein | Degrees of freedom, synergies |
| Kohonen | Self-organizing maps |
| Elman | Simple Recurrent Network |
| Friston | Free Energy Principle |
| Gibson | Ecological psychology, affordances |
| Wittgenstein | Family resemblance |
| Bahrami | Optimal interacting minds |
| De Jaegher | Engaged epistemology |
| Garrod/Galantucci | Experimental semiotics |
| Lewis | Signaling game / conventions |
| Richardson & Dale | Speaker-listener gaze coupling |
