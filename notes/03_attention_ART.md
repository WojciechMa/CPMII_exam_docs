# Lecture 3: ART & Visual Attention

## Attention: The Phenomenon

> "Every one knows what attention is. It is the taking possession by the mind, in clear and vivid form, of one out of what seem several simultaneously possible objects or trains of thought." — William James, 1890

## Two Frameworks for Attention

### 1. Bottleneck / Filter Theories

**Core assumption:** Human processing capabilities are limited → need a filter

#### Early Selection (Broadbent)
- Filter operates on **physical features** (location, intensity, pitch)
- Technique: dichotic listening (shadowing)
- Unattended channel: only physical features processed

#### Challenges to Early Selection
- **Cocktail party effect** — own name detected in unattended channel
- **Gray & Wedderburn** — semantic grouping across channels ("What the hell")
- **Von Wright** — Galvanic Skin Response to conditioned words in unattended channel

#### Resolution
- **Treisman:** Attenuation theory — unattended stimuli weakened, not blocked
- **Deutsch & Deutsch:** Late selection — all stimuli processed semantically
- **Johnston:** Flexible filter — adapts to task demands

### 2. Selection-for-Action Theories (Allport, 1989)

**Core assumption:** We don't NEED to process everything — attention serves action

**Rejects:**
- That early selection = spatial/physical, late = semantic
- That selection stems from system "limitations"

**Proposes:**
- Attention selects information for **coherent action**
- Serves evolutionarily important goals
- Functions in situations of: unpredictability (fast reactions) and multiple goals (hierarchy)
- Attention divisible when actions don't require same effectors/channels

> "Having a body is to identify oneself with certain projects and to be continually committed to them" — Merleau-Ponty

### Internal vs External Attention

- William James: "objects and trains of thought" — both internal and external reasons
- Bottom-up: noticing relevant novelty (unpredictability)
- Top-down: forming expectations based on goals (multiple goals)

## Adaptive Resonance Theory (ART)

### The Stability-Plasticity Dilemma

- **Plasticity:** System must learn new patterns
- **Stability:** New learning must not destroy old knowledge (catastrophic forgetting)
- Most neural networks suffer catastrophic forgetting

### ART Solution

Create **new categories on the fly** when top-down expectations mismatch bottom-up sensations.

### ART1 Architecture

- **Bottom-up layer (F1):** Receives input features
- **Top-down layer (F2):** Stores category prototypes
- **Matching:** Input compared to top-down expectation
- **Resonance:** If match is good enough → learn/strengthen
- **Reset:** If mismatch exceeds vigilance threshold → recruit new category node

### Vigilance Parameter

Controls category granularity:
- **High vigilance** → many fine-grained categories → used in model of **autism** (weak central coherence)
- **Low vigilance** → few broad categories → used in model of **schizophrenia**

### ART1 Properties

- Each category has a prototype (contains only central features)
- Prototypes are refined over time
- Attention in ART1: selecting particular features based on stimulus itself

## ARTSCAN Model (Fazl, Grossberg, Mingolla, 2009)

### Problem: Feature Integration

Which features belong to which objects? Need to bind features to spatial locations.

### What and Where Pathways
- **Ventral (What):** Object identity
- **Dorsal (Where):** Spatial location

### ARTSCAN Concepts

1. **Preattentive mechanisms** recognize surfaces/boundaries → build **attentional shroud**
2. **Attentional shroud** ensures exploration limited to single object
3. **Eye saccades** generate multiple views of same object
4. **View-invariant representations** formed across saccades

### Key Features
- Based on ART architecture
- Biologically plausible (models real-time neural groups)
- Predicts human reaction times
- Distinguishes spatial vs. object attention
- Saliency directs gaze; volitional spotlight directs object attention

## Literature

- Lindsay, G. W. (2020). Attention in psychology, neuroscience, and machine learning. Frontiers in Computational Neuroscience, 14, 29.
- Fazl, Grossberg, Mingolla (2009). View-invariant object category learning, recognition, and search.
