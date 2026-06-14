# Lectures 11-12: RQA, cRQA & Interpersonal Coordination

## Recurrence Quantification Analysis (RQA)

### Core Idea
A dynamical system **recurs** — it returns to regions of state space it has visited before. RQA quantifies the patterns of these recurrences.

### Process
1. Record time series of behavior
2. Reconstruct system trajectory in state space (using time-delayed copies)
3. Create **recurrence plot:** mark a point whenever the system is "close" to a state it previously visited
4. Compute statistics from the recurrence plot

### Key RQA Measures
| Measure | Meaning |
|---------|---------|
| **RR (Recurrence Rate)** | % of plot that is recurrent; overall coupling/predictability |
| **DET (Determinism)** | % of recurrent points forming diagonal lines; predictability/structure |
| **MaxLine** | Longest diagonal line; longest period of similar behavior |
| **Entropy** | Shannon entropy of line length distribution; complexity |

### Why Use RQA?
- Works for **non-linear, non-stationary** systems
- No assumptions about distribution or stationarity
- Reveals structure invisible to standard linear methods (correlation, spectral analysis)
- Appropriate for studying complex dynamical systems (behavior, physiology)

## Cross-Recurrence Quantification Analysis (cRQA)

### Purpose
Examine the **coupling between TWO dynamical systems**.

### How It Differs from RQA
- RQA: one system's recurrence with itself
- cRQA: marks when System A's behavior matches System B's behavior
- Reveals common constraints acting on both systems

### Process
1. Two time series (one per system)
2. Same reconstruction parameters for both
3. Cross-recurrence plot: point whenever one system's state is "close" to the other's state
4. Compute diagonal profile

### Interpretation
- High cRQA measures → strong coupling between systems
- Can reveal: subsystems of a larger system, or one system following the other

## Diagonal Cross-Recurrence Profile

### What It Shows
**Recurrence Rate as a function of time lag** along the diagonals of the cross-recurrence plot.

### How to Read It
- **Peak at lag 0:** Systems do the same thing at the same time (tight synchrony)
- **Peak shifted to positive lag:** System B follows System A with a delay
- **Peak shifted to negative lag:** System A follows System B
- **Dip at lag 0:** Systems actively avoid doing the same thing simultaneously
- **Peak height:** Strength of coupling
- **Peak width:** Time window of influence

### Three Canonical Profiles

1. **Tightly coupled, simultaneous:** Sharp symmetric peak at lag 0
2. **One following other (e.g., 500ms delay):** Peak shifted to one side by 500ms
3. **Avoidance/anti-coordination:** Trough at lag 0 (below baseline)

## Example: Postural Coordination in Conversation (Shockley et al., 2003)

- Measured front-back sway during conversation
- **Finding:** More recurrence for conversing pairs than non-conversing pairs
- Trajectories more similar for longer (higher MaxLine)
- **Verbal communication was enough** to couple movements
- Movements coupled to conversational partner, NOT to visible person!
- Mechanism: rate of speech? breathing? guiding attention?

## Example: Speaker-Listener Gaze Coupling (Richardson & Dale, 2005)

- Speaker tells story; listener's eye movements tracked
- cRQA of gaze positions
- **Finding:** Listener's gaze follows speaker's gaze with ~2 second lag
- Coupling strength predicts comprehension
- Shows information flow from speaker to listener through coordinated attention

## Mother-Infant Interaction Development

### Early Stages (~3 months)
- Broader diagonal profile (influence spread over longer time window)
- No clear leader/follower in gaze organization
- Higher overall recurrence in gaze coordination

### Later Stages (~6-8 months)
- Higher concentration of recurrence **around lag 0** (tighter synchrony)
- Decrease in overlapping vocalizations → emerging **turn-taking** structure
- More structured, more focused coordination patterns

### Developmental Trajectory
From diffuse, spread-out coupling → focused, synchronized, structured coordination.

## Van Orden's Quote (2003)

> "Loosely speaking, whatever happens to one component [of a system] happens to all components"

### Source of DIFFICULTY:
- Cannot isolate variables in an interconnected system
- Manipulation of one component affects everything
- Standard experimental logic (control one variable) breaks down
- Hard to identify which specific interaction is critical

### Source of HOPE:
- Studying any one component gives insight into the whole system
- System-level interventions can cascade
- A single measurement may reveal system-wide organization
- Supports holistic understanding through appropriate methods

## Literature
- Pellecchia & Shockley (2005). Application of RQA: Influence of Cognitive Activity on Postural Fluctuations.
- Shockley, Santana & Fowler (2003). Mutual interpersonal postural constraints in cooperative conversation.
- Richardson & Dale (2005). Looking to Understand: Speaker-Listener Eye Movements and Discourse Comprehension.
- Nomikou et al. (2016). Constructing Interaction: The Development of Gaze Dynamics.
