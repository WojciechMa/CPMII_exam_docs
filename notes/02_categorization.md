# Lecture 2: From Similarity to Categorization

## The Task of Categorization

**Categorization = discrimination + abstraction** (Harnad, 2003)

> "To Cognize is to Categorize: Cognition is Categorization"  
> "All of our categories consist in ways we behave differently toward different kinds of things"

## Classical Theory of Concepts

- Categories defined by **necessary and sufficient conditions**
- Membership is binary (in or out)
- All members are equally representative

## Wittgenstein's Critique: Family Resemblance

- No single property shared by all members of a category (e.g., "games")
- Categories held together by a "complicated network of similarities overlapping and criss-crossing"
- **Graded membership** — some members more typical than others (prototype effects)
- Category boundaries are fuzzy, not sharp

## Perceptual (Psychological) Space

- Abstract n-dimensional space representing perceived dimensions of stimuli variability
- Stimuli = **points** in this space
- **Distance** between points = perceived dissimilarity
- Closer points → more similar percepts

### Multidimensional Scaling (MDS)

**Purpose:** Recover perceptual space from empirical similarity data (confusion matrices, reaction times, similarity judgments)

**Method:** Minimize Stress function:
- Stress = mismatch between original dissimilarities and recovered distances d_ij
- Iterative optimization to find point configuration

**What's preserved:** Pairwise distances (or rank-order of distances)  
**What's NOT preserved:** Parallel lines, absolute orientation (solution can be rotated/reflected)

### Distance Functions

- Manhattan distance: p = 1 (city-block)
- Euclidean distance: p = 2

### Similarity Function (Shepard's Universal Law)

S = e^{−c·d^p}

Properties:
- Identity: d=0 → S=1
- Non-negativity: S approaches 0 but never negative
- Rapid decay: small differences → large similarity drop

## Prototype Model

- **Strong abstraction:** category = single central tendency (mean of exemplars)
- New item classified by distance to prototype
- Simple, efficient
- **Limitation:** Cannot handle non-linearly separable categories (e.g., XOR problem)
- Single point cannot represent categories with multiple clusters

## Exemplar Model: Generalized Context Model (GCM, Nosofsky)

- **No abstraction:** stores ALL remembered instances (exemplars)
- Classification by **weighted sum of similarities** to all stored exemplars per category

### GCM Formula

P(category A | stimulus x) = (b_A · Σ S(x, exemplar_i∈A)) / (Σ_all_categories b_k · Σ S(x, exemplar_j∈k))

Where:
- b_k = base rate (category frequency bias)
- S = similarity function (exponential decay)
- Normalization via **Luce Choice Rule**

### Advantages over Prototype

- Can handle XOR / non-linearly separable problems
- Captures within-category structure
- Accounts for frequency effects
- More parameters but better fits to human data

## Key Comparison

| Feature | Prototype | Exemplar (GCM) |
|---------|-----------|----------------|
| Abstraction | Strong (one mean) | None (all instances) |
| Storage | Minimal | All exemplars |
| Non-linear categories | Fails | Succeeds |
| Computational cost | Low | Higher |
| Psychological reality | Less supported | Well-supported |

## Literature

- Harnad, S. (2017). To cognize is to categorize. In Handbook of Categorization in Cognitive Science.
