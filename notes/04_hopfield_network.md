# Lecture 4: Hopfield Network

## What is Memory?

Types: sensory, short-term/working, long-term (episodic, semantic, procedural)

### Associative Memory
- Associations between inherently unrelated items
- Learned through conditioning or deliberate learning
- Can involve complex objects and properties
- Neurally: "associative memory cells" (Wang & Cui, 2018)

### Properties of Human Memory
- Recall based on fuzzy cues (emotion, aroma, context)
- Recall takes time (not instantaneous)
- Imperfect recall, false memories
- Limited capacity; overtaxing → degradation

## Hopfield Network

### Origin
- John Hopfield (1982) — simultaneously a model of **spin glass** phenomenon and neural activity
- Nobel Prize in Physics 2024

### Architecture
- **Recurrent** neural network with dense connections (all-to-all)
- Binary or continuous neuron outputs
- Symmetric weights: w_ij = w_ji
- No self-connections: w_ii = 0

## Content-Addressable Memory (CAM)

**Traditional memory:** access by address (street number)  
**Content-addressable:** access by content (partial/degraded pattern → retrieve closest match)

### How it works:
1. Store patterns by setting weights (Hebbian learning)
2. Present noisy/partial input as initial state
3. Network iterates (asynchronous neuron updates)
4. Converges to nearest stored pattern (attractor)

### Modeled Phenomena
- Pattern completion (partial cue → full memory)
- Error correction (noisy → clean)
- Associative memory (one stimulus triggers associated stimulus)
- Memory retrieval from emotional/contextual cues

## Energy Function

### Definition
E = −½ Σᵢⱼ wᵢⱼVᵢVⱼ − Σᵢ IᵢVᵢ

### Role
- Every neuron update **decreases or maintains** energy
- Network dynamics = "rolling downhill" in energy landscape
- Guarantees convergence to a stable state

### Local Minima = Stored Memories
- Local minima in energy landscape correspond to stable attractors
- These are the stored patterns
- Initialization with partial input → flow to nearest minimum → recall

### Capacity
- Can store approximately 0.14N patterns (N = number of neurons)
- Exceeding capacity → spurious attractors (false memories!)

## Extending to Arbitrary Associations

To associate face with name:
1. Encode face as binary vector, name as binary vector
2. **Concatenate:** [face_vector | name_vector]
3. Store this combined vector as a fundamental memory
4. **Retrieval:** Present name only (face portion = neutral) → iterate → network fills in associated face

## Hopfield Network for Combinatorial Optimization

### Travelling Salesman Problem (TSP)

Hopfield & Tank (1985): use continuous Hopfield network to solve TSP

### Continuous Model
- Output: V_i = ½(1 + tanh(αU_i))
- Input: U_i = Σⱼ w_ij V_j + I_i
- Network dynamics IS the optimization process

### TSP Encoding
- Neurons organized in 2D grid: V_{xi} = 1 means "city x is i-th stop"
- Cost function with 4 terms:

| Term | Ensures |
|------|---------|
| A | Each city visited at most once |
| B | Each step contains at most one city |
| C | Route consists of N cities total |
| D | Shorter routes are preferred (uses distance matrix) |

### Deriving Weights
From cost function, derive:
- w_{xi,yj} = −Aδ_xy(1−δ_ij) − Bδ_ij(1−δ_xy) − C − Dd_xy(δ_{j,i+1} + δ_{j,i−1})
- I_{xi} = C(N + σ)

### D-Wave Quantum Computer
- Physical implementation of Hopfield-like network (analog computer)
- Quantum annealing for combinatorial optimization
- Theoretically faster for some NP-hard problems

## Literature
- Hopfield, J.J. (1982). Neural networks and physical systems with emergent collective computational abilities.
- Hopfield & Tank (1985). Neural computation of decisions in optimization problems.
