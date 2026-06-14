# CPM II — Key Equations & Formulas Explained

A plain-language guide to every equation that appears in the course. No prior math beyond high school needed. **Every single letter is explained.**

---

## 1. Similarity & Categorization

### Distance between two stimuli (Minkowski)

$$d(x, y) = \left( \sum_{k=1}^{n} |x_k - y_k|^p \right)^{1/p}$$

| Symbol | What it is |
|--------|-----------|
| d(x,y) | The distance (dissimilarity) between stimulus x and stimulus y |
| x, y | Two stimuli (each is a list of numbers, one per dimension) |
| x_k | The value of stimulus x on dimension k (e.g., "redness" or "loudness") |
| y_k | The value of stimulus y on the same dimension k |
| \|x_k − y_k\| | How much x and y differ on dimension k (absolute value = always positive) |
| n | Number of dimensions in the perceptual space |
| k | Counter that runs through each dimension (1, 2, 3, ... n) |
| Σ | "Add up" all the dimension differences |
| p | Shape parameter: p=1 gives Manhattan distance; p=2 gives Euclidean |
| ^(1/p) | Take the p-th root of the sum (for p=2, this is a square root) |

**Plain English:** How "far apart" two stimuli are in perceptual space.
- When p=1: Manhattan distance (sum of absolute differences, like walking city blocks)
- When p=2: Euclidean distance (straight-line "as the crow flies")

---

### Similarity function (Shepard's Law)

$$S = e^{-c \cdot d^p}$$

| Symbol | What it is |
|--------|-----------|
| S | Similarity (a number between 0 and 1) |
| e | Euler's number ≈ 2.718 (base of natural exponential) |
| c | Sensitivity parameter — higher c means similarity drops off faster with distance |
| d | Distance between the two stimuli (from the formula above) |
| p | Usually same p as in distance (1 or 2) |
| −c·d^p | The exponent — always negative, so S is always between 0 and 1 |

**Plain English:** How similar two things *feel*. As distance grows, similarity drops exponentially.
- d=0 → S=1 (identical things = maximum similarity)
- d very large → S≈0 (very different = no similarity)

---

### MDS Stress (cost function)

$$\text{Stress} = \sqrt{\frac{\sum_{i<j}(d_{ij} - \hat{d}_{ij})^2}{\sum_{i<j} d_{ij}^2}}$$

| Symbol | What it is |
|--------|-----------|
| Stress | The "error score" — how badly the map disagrees with the original data (lower = better) |
| d_{ij} | Original dissimilarity between stimuli i and j (from experiment) |
| d̂_{ij} | Recovered distance between points i and j (in the MDS solution) |
| (d_{ij} − d̂_{ij})² | Squared error for one pair — how wrong the map is for this pair |
| Σ_{i<j} | Sum over all unique pairs of stimuli (avoid counting i,j and j,i twice) |
| √(...) | Square root — keeps Stress in same units as distances |

**Plain English:** MDS tries to place points on a map so that their distances match the original similarity data. Stress measures how bad the mismatch is. Stress = 0 means perfect recovery.

---

### GCM Classification Probability (Luce Choice Rule)

$$P(A|x) = \frac{b_A \cdot \sum_{i \in A} S(x, i)}{\sum_k b_k \cdot \sum_{j \in k} S(x, j)}$$

| Symbol | What it is |
|--------|-----------|
| P(A\|x) | Probability that stimulus x belongs to category A |
| x | The new stimulus you're trying to classify |
| A | One specific category (e.g., "cats") |
| k | Counter that runs through ALL categories (cats, dogs, birds, ...) |
| i ∈ A | An exemplar (stored memory) from category A |
| j ∈ k | An exemplar from category k |
| S(x, i) | Similarity between new stimulus x and stored exemplar i (uses Shepard's formula) |
| Σ_{i∈A} S(x,i) | Total similarity of x to ALL exemplars in category A |
| b_A | Base rate (bias) for category A — how common/frequent that category is |
| b_k | Base rate for category k |
| Numerator | "Evidence for A" — how much x looks like things in A, weighted by A's frequency |
| Denominator | "Evidence for ALL categories" — normalizer to make probabilities sum to 1 |

**Plain English:** To classify x, compare it to every stored exemplar from every category. The category whose exemplars are most similar to x (weighted by frequency) wins. This is Luce's Choice Rule — it turns similarity scores into probabilities.

---

## 2. Hopfield Network

### Energy Function

$$E = -\frac{1}{2} \sum_{i,j} w_{ij} V_i V_j - \sum_i I_i V_i$$

| Symbol | What it is |
|--------|-----------|
| E | Energy of the network (lower = more stable/settled) |
| −½ | Constant to avoid double-counting (each pair counted once) |
| Σ_{i,j} | Sum over all pairs of neurons i and j |
| w_{ij} | Connection weight between neuron i and neuron j (how strongly they're linked) |
| V_i | Activity/output of neuron i (0 or 1, or continuous between 0-1) |
| V_j | Activity/output of neuron j |
| I_i | External input (bias) to neuron i — a "nudge" from outside |

**Plain English:** A single number representing how "settled" the network is. The network always moves toward lower energy. Think of a ball rolling downhill — it settles in valleys (= stored memories). When connected neurons are both active and have positive weights, energy goes down (stable). Mismatches increase energy (unstable).

---

### Continuous neuron output

$$V_i = \frac{1}{2}(1 + \tanh(\alpha U_i))$$

| Symbol | What it is |
|--------|-----------|
| V_i | Output of neuron i (a number between 0 and 1) |
| tanh | Hyperbolic tangent function — an S-shaped "squasher" (output between −1 and +1) |
| α | Steepness parameter — high α makes the neuron more like an on/off switch |
| U_i | Total input to neuron i (= Σⱼ w_ij V_j + I_i) |
| ½(1 + ...) | Shifts the tanh output from (−1, +1) range to (0, 1) range |

**Plain English:** Squashes the neuron's raw input into a value between 0 and 1. α controls how sharp: high α = almost binary (on/off); low α = gradual, analog response.

---

### TSP Cost Function (4 penalty terms)

$$E = \frac{A}{2}\sum_x\sum_{i\neq j} V_{xi}V_{xj} + \frac{B}{2}\sum_i\sum_{x\neq y} V_{xi}V_{yi} + \frac{C}{2}(\sum_x\sum_i V_{xi} - N)^2 + \frac{D}{2}\sum_x\sum_{y\neq x}\sum_i d_{xy}V_{xi}(V_{y,i+1}+V_{y,i-1})$$

| Symbol | What it is |
|--------|-----------|
| E | Total cost (the network tries to minimize this) |
| V_{xi} | Activity of neuron at position (x, i) — means "city x is visited at step i" |
| x, y | City indices (which city) |
| i, j | Step indices (which position in the route) |
| A, B, C, D | Penalty weights (how harshly each rule violation is punished) |
| N | Total number of cities |
| d_{xy} | Geographic distance between city x and city y |
| V_{y,i+1} | "City y is visited at step i+1" (the NEXT step) |
| V_{y,i−1} | "City y is visited at step i−1" (the PREVIOUS step) |

**Plain English — the four terms:**
- **Term A:** Punishes having the same city appear at two different steps (each city visited once)
- **Term B:** Punishes having two cities at the same step (one city per step)
- **Term C:** Punishes routes that don't visit exactly N cities (must visit all)
- **Term D:** Penalizes long distances between consecutive cities (prefer short routes)

---

## 3. Signal Detection & Decision Making

### Bienaymé Formula

$$\text{Var}(\bar{x}) = \frac{\sigma^2}{n}$$

| Symbol | What it is |
|--------|-----------|
| Var(x̄) | Variance (uncertainty/spread) of the group average |
| x̄ | The average (mean) of all individual guesses |
| σ² | Variance of a single individual's guess (how spread out one person's errors are) |
| n | Number of independent guesses/agents being averaged |

**Plain English:** When you average n independent guesses, the uncertainty shrinks by a factor of n. 10 people → 10× less variance. This is why crowds are wise — but ONLY if the guesses are independent (not copying each other).

---

### Bayes' Rule

$$P(\theta|D) = \frac{P(D|\theta) \cdot P(\theta)}{P(D)}$$

| Symbol | What it is |
|--------|-----------|
| θ (theta) | A hypothesis about the world (e.g., "there's a cat" or "the signal was on the left") |
| D | Data — the actual sensory evidence you received |
| P(θ\|D) | **Posterior** — probability of your hypothesis AFTER seeing the data |
| P(D\|θ) | **Likelihood** — probability of getting this data IF your hypothesis is true |
| P(θ) | **Prior** — probability of your hypothesis BEFORE seeing data (your expectation) |
| P(D) | **Marginal likelihood** — total probability of the data under all possible hypotheses (a normalizer to make everything add to 1) |
| \| | "Given" or "conditional on" — P(A\|B) = probability of A, assuming B is true |

**Everyday analogy:** You hear a noise at night. Prior: probably the cat (90%) or a burglar (10%). Likelihood: if burglar, loud crash is very likely; if cat, less so. After hearing a loud crash → posterior shifts toward burglar. That's Bayes.

---

### Psychometric Function (simplified)

$$P(\text{correct}) = \lambda + (1-2\lambda) \cdot \Phi\left(\frac{x - \alpha}{\beta}\right)$$

| Symbol | What it is |
|--------|-----------|
| P(correct) | Probability of giving the right answer (between 0 and 1) |
| x | Stimulus intensity (e.g., how big the difference between two circles is) |
| α (alpha) | **Threshold** — the stimulus level at which you're right 50% of the time (above chance) |
| β (beta) | **Slope/sensitivity** — how quickly your performance improves as stimulus gets stronger. Small β = very steep (sensitive); large β = gradual |
| λ (lambda) | **Lapse rate** — probability of random error even with a super-obvious stimulus (finger slip, blink) |
| Φ (Phi) | Cumulative normal distribution function — the mathematical shape that makes it S-curved |
| (x−α)/β | "How many steps above threshold is this stimulus?" — standardized distance |

---

## 4. Free Energy Principle

### Free Energy

$$F = -\log P(D) + D_{KL}(Q(\theta) \| P(\theta|D))$$

| Symbol | What it is |
|--------|-----------|
| F | Free Energy — a single number the brain tries to minimize |
| −log P(D) | **Surprise** — how unexpected the sensory data is under your model (high = "I didn't expect that!") |
| D_{KL}(...) | **KL Divergence** — how different your approximate beliefs are from the true answer |
| Q(θ) | Your brain's **approximate belief** about the world (a simplification it can actually compute) |
| P(θ\|D) | The **true posterior** — what you'd ideally believe (usually impossible to compute exactly) |
| D | Sensory data (what you see/hear/feel) |
| θ (theta) | Hidden causes of the data (what's actually out there in the world) |
| log | Logarithm (turns multiplication into addition; makes math tractable) |

**Plain English:** Free Energy = surprise + belief error. The brain minimizes both: (1) make better predictions so data isn't surprising, (2) make beliefs more accurate.

Equivalently:

$$F = \underbrace{E_Q[-\log P(D,\theta)]}_{\text{expected energy}} - \underbrace{H(Q(\theta))}_{\text{entropy}}$$

| Symbol | What it is |
|--------|-----------|
| E_Q[...] | Expected value (average) computed using distribution Q |
| −log P(D,θ) | "Energy" of a particular data+cause combination (how implausible it is) |
| H(Q(θ)) | Entropy of Q — how uncertain/spread-out your beliefs are (more spread = higher) |

---

### KL Divergence

$$D_{KL}(Q \| P) = \sum_\theta Q(\theta) \log \frac{Q(\theta)}{P(\theta)}$$

| Symbol | What it is |
|--------|-----------|
| D_{KL} | KL Divergence — a distance-like measure between two probability distributions |
| Q(θ) | First distribution (your approximate belief) |
| P(θ) | Second distribution (the "target" true distribution) |
| Σ_θ | Sum over all possible values of θ |
| log Q(θ)/P(θ) | How much Q and P disagree at each point θ |

**Plain English:** Measures how different two probability distributions are. Always ≥ 0. Equals zero only if Q = P exactly. The brain tries to make Q match P (reduce divergence = learn).

---

### ELBO (Evidence Lower Bound)

$$\text{ELBO} = -F = \log P(D) - D_{KL}(Q \| P)$$

| Symbol | What it is |
|--------|-----------|
| ELBO | Evidence Lower BOund — the quantity to MAXIMIZE |
| −F | Negative free energy (maximizing ELBO = minimizing free energy) |
| log P(D) | Log-evidence — how well your entire model explains the data |
| D_{KL}(Q‖P) | KL divergence penalty (always subtracted — penalizes bad approximations) |

**Plain English:** A quantity the brain (or a VAE) tries to MAXIMIZE. Higher ELBO = better model of the world. It's called a "lower bound" because ELBO ≤ log P(D) always (you can never exceed the true evidence).

---

## 5. Fractal Dimension & Noise

### Fractal Dimension

$$N = \varepsilon^{-D} \quad \Rightarrow \quad D = \frac{-\log N}{\log \varepsilon}$$

| Symbol | What it is |
|--------|-----------|
| N | Number of measurement units needed to cover the shape |
| ε (epsilon) | Length of the measurement ruler (smaller ruler = more detail) |
| D | Fractal dimension — how "crinkly" or complex the shape/signal is |
| log | Logarithm (any base — ratio stays the same) |

**Plain English:** If you measure a coastline with a ruler of length ε, you need N pieces. D tells you how "crinkly" it is:
- D = 1.0 → perfectly smooth line
- D = 1.5 → moderately crinkly (like a typical coastline)
- D = 2.0 → so crinkly it fills a whole area

---

### Power Spectrum Relationship

$$P(f) \sim \frac{1}{f^\beta}$$

| Symbol | What it is |
|--------|-----------|
| P(f) | Power (energy/strength) at frequency f |
| f | Frequency — how fast something oscillates (high f = fast changes) |
| β (beta) | Spectral slope — characterizes what TYPE of noise/signal this is |
| ~ | "Proportional to" (not exact equality, but the relationship holds) |

**Plain English:** How much "energy" is at each frequency in a signal:
- β=0: **white noise** — all frequencies equally strong → completely random, no memory
- β=1: **pink noise (1/f)** — slow changes dominate → found in natural/biological behavior
- β=2: **red/Brownian noise (1/f²)** → random walk, strong memory of previous state

---

### DFA Exponent (α)

| α value | Interpretation |
|---------|---------------|
| < 0.5 | Anti-correlated (when it goes up, next it tends to go down) |
| 0.5 | Uncorrelated (white noise — no memory) |
| 0.5–1.0 | Positively correlated (fractal — long-range memory) |
| 1.0 | Pink noise (1/f) — perfectly self-organized |
| 1.5 | Red noise (random walk — very strong memory) |

| Symbol | What it is |
|--------|-----------|
| α (alpha) | DFA exponent — summarizes the type of long-range correlation in a time series |
| DFA | Detrended Fluctuation Analysis — a method to estimate α from a time series |

**For gait:** Healthy young adults α ≈ 0.84 (nicely correlated); elderly α ≈ 0.69 (losing organization → more random → fall risk)

---

## 6. HKB Model (Motor Coordination)

### Potential Function

$$V(\phi) = -a\cos(\phi) - b\cos(2\phi)$$

| Symbol | What it is |
|--------|-----------|
| V(φ) | "Potential energy" at phase difference φ (valleys = stable patterns) |
| φ (phi) | Relative phase between two hands (0° = in-phase, 180° = anti-phase) |
| a | Strength of the first attractor mode (favors in-phase: φ=0°) |
| b | Strength of the second attractor mode (favors both in-phase AND anti-phase) |
| cos(φ) | Cosine — has a minimum (valley) at φ=0° |
| cos(2φ) | Cosine of double angle — has minima at φ=0° AND φ=180° |
| −a, −b | Negative signs make cosine valleys into potential valleys (lower = more stable) |

**Plain English:** An "energy landscape" for coordination. The hands naturally settle into valleys.
- When b is large relative to a: two valleys exist (both coordination modes stable)
- As speed increases: b shrinks → anti-phase valley vanishes → only in-phase remains
- This is the **phase transition** (bifurcation)

---

## 7. SOM (Self-Organizing Map)

### Weight Update Rule

$$\Delta w_j = \alpha(t) \cdot h(d_j, t) \cdot (x - w_j)$$

| Symbol | What it is |
|--------|-----------|
| Δw_j | Change in weights of neuron j (how much it learns this step) |
| α(t) | Learning rate at time t — starts large (big learning steps), shrinks over time (fine-tuning) |
| h(d_j, t) | Neighborhood function — how much neuron j participates in learning |
| d_j | Distance from neuron j to the BMU (Best Matching Unit) on the grid |
| t | Training iteration (time step) |
| x | Current input vector (the data point being presented) |
| w_j | Current weight vector of neuron j (what it "represents") |
| (x − w_j) | Direction to move — pulls neuron j's weights toward the input |

**Plain English:** The winning neuron (BMU) and its grid neighbors all move their weights toward the current input. Closer neighbors learn more. Over time, learning slows down and the neighborhood shrinks, giving fine-grained organization.

---

## Quick Symbol Reference

| Symbol | Meaning |
|--------|---------|
| Σ | Sum over all items |
| ∏ | Product of all items |
| e^x | Exponential (≈ 2.718^x) |
| log | Logarithm (inverse of exponential) |
| ∝ | "proportional to" |
| ≈ | "approximately equal" |
| δ_ij | Kronecker delta: 1 if i=j, 0 otherwise |
| ‖ | "given" in KL divergence notation |
| ∼ | "distributed as" or "proportional to" |
| φ | Relative phase (angle between 0° and 360°) |
| α | Learning rate, DFA exponent, or threshold (context-dependent) |
| σ² | Variance (spread of a distribution) |
| Φ | Cumulative normal distribution function |
