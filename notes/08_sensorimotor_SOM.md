# Lecture 8: Bottom-up Sensorimotor Learning

## Self-Organizing Map (SOM / Kohonen Network)

### What is SOM?
A neural network architecture that performs **unsupervised learning** while preserving the **topological structure** of the input data in a lower-dimensional representation (typically 2D grid).

### Self-Organization Process

1. **Initialize** nodes with random weight vectors (same dimensionality as input)
2. **Present** a random input vector x
3. **Competition:** Find Best Matching Unit (BMU) — node whose weights are closest to input (Euclidean distance)
4. **Cooperation:** Define neighborhood around BMU (decreases over time)
5. **Adaptation:** Update BMU and neighbors' weights to become more similar to input:
   - Δw = α(t) · h(d, t) · (x − w)
   - α(t) = learning rate (decreases over time)
   - h(d, t) = neighborhood function (decreases with distance d from BMU and over time)
6. **Repeat** until convergence

### Key Properties
- **Topology preservation:** Similar inputs → neighboring neurons on grid
- **Dimensionality reduction:** High-D input → low-D map
- **Vector quantization:** Discretizes continuous input space
- **Unsupervised:** No labels needed

### What "neighbors in SOM topology" means
If two input patterns activate neighboring neurons, those patterns are **similar in the original high-dimensional input space**. The SOM preserves topological relationships.

## Applications (from Lab)

### 1. Color Vector Quantization
- 15 colors (3D RGB vectors) mapped to 2×2 SOM grid
- Similar colors → neighboring grid cells
- Grid size vs. data: more neurons than colors → some empty; fewer → loss of distinction

### 2. Clustering (Iris data)
- 4D flower measurements → 2D SOM
- Categories emerge in grid topology without supervision

### 3. Solving TSP
- 1D SOM (ring) fitted to 2D city coordinates
- SOM self-organizes to approximate optimal tour
- Grid size > cities needed for good solutions

### 4. Hand Gesture Recognition
- SOM extracts shape features from images
- Outline angles computed from SOM grid → classify gestures

## Movement Mirroring: Why Simple Mapping Fails

**Problem:** Map visual observation of movement directly to motor commands.

**Why it fails:**
1. **Temporal delays** — processing and motor execution lag behind observation
2. **Motor noise** — actuators are imprecise
3. **Coordinate transformation** — visual space ≠ motor/body space (different reference frames, morphology)
4. **Incomplete/noisy visual input** — occlusion, low resolution, ambiguity

## Need for Predictive Models

Predictive models are necessary to:
- **Anticipate** upcoming movements (compensate for sensory-motor delays)
- **Plan** movement sequences (not just react frame-by-frame)
- **Correct** for motor noise using internal forward models
- **Infer** intended movement from partial visual information

## Modifying SOM for Prediction

### Approach 1: Time-Windowed Input
- Feed concatenated sequence [x(t), x(t-1), x(t-2), ...] instead of single state
- SOM learns temporal patterns / trajectories

### Approach 2: Growing When Required (GWR)
- Dynamically adds nodes when existing ones don't match well
- Adapts network size to complexity
- Can build incremental sensorimotor maps

### Approach 3: Associative Transitions
- Link BMU at time t to BMU at time t+1
- Learn transition probabilities between states
- Enable prediction of next state from current state

### Key Principle
Incorporate **temporal information** into the SOM architecture to learn sequential dynamics rather than just static clustering.

## Literature
- Mici, L., Parisi, G., Wermter, S. (2018). An incremental self-organizing architecture for sensorimotor learning and prediction.
- Butz, M. V., et al. (2010). Self-Organizing Sensorimotor Maps Plus Internal Motivations Yield Animal-Like Behavior.
