# Lecture 9: Fractal Dimension & Gait Dynamics

## Self-Organization

Systems that spontaneously move from **chaos to order** without external control.

Key insight: "We don't need to look for structural similarity between the effect and the system producing it!"
- Genetic material doesn't describe detailed organism structure → sets boundary conditions for emergence
- Brain doesn't generate detailed motor plan → modifies attractor landscape

### How to Study Self-Organizing Systems
1. Look for mathematical models producing qualitatively similar structures
2. Measure quantitative outcomes, group systems with similar statistics
3. Characteristic property: **power-law structures**

## Fractals

### Definition
Structures conforming to power law; self-similar at multiple scales.

**Coastline paradox:** Length depends on measurement stick length.

### Fractal Dimension Formula
N = ε^{−D}

D = −log(N) / log(ε)

Where: N = number of units, ε = scaling factor, D = fractal dimension

Example: Koch curve → D = 1.2619

### Statistical Self-Similarity
Not structural similarity but **similarity of statistical properties** across scales. Applied to time series:
- Larger D → larger variability

## Types of Noise

### White Noise
- x(t) = ε, where ε ~ N(0, σ²)
- Independent samples
- Flat spectrum: P(f) ~ 1
- Fractal dimension: **D = 2**
- No memory

### Brownian Noise (Red Noise)
- x(t+1) = x(t) + ε — random walk
- Each sample depends on previous
- Spectrum slope: P(f) ~ 1/f²
- Fractal dimension: **D = 1.5**
- Strong memory

### Pink Noise (1/f Noise)
- Between white and red
- P(f) ~ 1/f^β where β ≈ 1
- Fractal dimension: **D' = 1** (of integrated signal)
- Found in: ocean tides, heart rate, neuron activations, speech, music, **reaction times**, **motor behavior**

### Relationship Between β and D
Power spectrum slope β connects to fractal dimension:
- When β ∈ (−3, −1): D = 1 + (β+3)/2
- When β ∈ [−1, 1]: D = 2; then D' = 1 + (β+1)/2

| Noise Type | β | D | Character |
|------------|---|---|-----------|
| White | 0 | 2 | No correlation |
| Pink | −1 | 2 (D'=1) | Long-range correlation |
| Red/Brown | −2 | 1.5 | Strong correlation (random walk) |

## Estimating Fractal Dimension: DFA

**Detrended Fluctuation Analysis (DFA):**

DFA exponent α interpretation:
- α < 0.5 → anti-correlated
- α ≈ 0.5 → uncorrelated (white noise)
- α > 0.5 → positively correlated
- α ≈ 1.0 → 1/f noise (pink)
- α > 1.0 → non-stationary, unbounded
- α ≈ 1.5 → red noise (Brownian motion)

## Natural Noise in Human Behavior

Experiment (Gilden, Thornton & Mallon, 1995):
- Participants press button when they think 1 second has passed
- Reaction times form a time series
- Spectrum: P(f) ~ 1/f^{0.59} → pink noise!
- Neither purely random nor purely deterministic

**Implication:** Human behavior governed by self-organizing processes producing power-law (fractal) structures.

## Research Strategy

1. Power-law structures → suggest self-organizing systems
2. Measure fractal dimension of structures in space and time
3. This measures **system complexity**
4. Similar fractal dimensions across phenomena → similar underlying rules

## Gait Mechanics

### Why Study Gait?
- Uniquely human locomotion pattern
- Requires long learning (developmental stages, cultural)
- Visibly rhythmic but maintaining rhythm is complex:
  - Upper body = reverse pendulum with multiple masses
  - Phases of instability (falling)
  - Movement in 3D requiring compensation
  - Variable terrain

### Traditional vs. Fractal Approach
- **Traditional:** Averaged statistics (mean stride length, time) → ignores complexity
- **Fractal:** Study fluctuations in stride-to-stride variability → captures macro properties (long-range dependencies)

### What Generates Stride Variability?

Three hypotheses:
1. Random, uncorrelated noise → would show D ≈ 2 (white)
2. Local correlations (recovering after misstep) → short-range
3. **Long-distance dependencies (fractal)** → 0.5 < α < 1.0

Measured data support hypothesis 3: **fractal character** of gait dynamics.

### Fractal Dimension and Aging

| Group | DFA exponent α |
|-------|---------------|
| Children 3-4 years | 0.93 |
| Children 6-7 years | 0.93 |
| Children 11-14 years | 0.88 |
| Young adults | 0.84 |
| Elderly | 0.69 |

Trend: stride fluctuations become **less correlated** with age (moving toward white noise = loss of long-range organization).

### Clinical Applications
- **Sensitive to aging** — progressive decorrelation
- **Predictive for fall risk** among elderly
- **Predictive for neurodegenerative diseases** (Parkinson's)
- Robust across different walking conditions
- Hypothesis: fluctuation variability connected with neuron connectivity

## Literature
- Holden, J.G. (2005). Gauging the Fractal Dimension of Response Times from Cognitive Tasks.
- Hausdorff, J.M. (2007). Gait dynamics, fractals and falls.
