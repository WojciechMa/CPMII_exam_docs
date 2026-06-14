# CPM II 2026 — Exam Preparation: Questions & Answers

> Synthesized from lecture slides, 2025 exam answers, cognitive_models_qa.pdf, and course materials.
> Organized by 2026 lecture numbering.

---

## Lecture 1: Introduction

### Q: Give several examples of research questions about psychological phenomena (e.g. memory, attention) that are inspired by information processing approaches and by interaction-dominant approaches.

**Information Processing approach** (cognition as staged computation):
- *Memory:* How is information encoded, stored, and retrieved? What is the capacity of working memory? (Atkinson-Shiffrin model)
- *Attention:* Where is the processing bottleneck — early or late? What determines filter criteria? (Broadbent's filter theory)
- *Perception:* How are features extracted and combined into object representations? (Feature Integration Theory)

**Interaction-Dominant approach** (cognition as adaptive coordination with environment):
- *Memory:* How does the history of an organism's coupling with its environment shape its current behavior? Is structured environment part of memory?
- *Attention:* How is attention selected for coherent action rather than filtering? How does it relate to ongoing goals and affordances?
- *Motor control:* How do perception-action cycles self-organize without a central controller? How does movement reveal knowledge about the world?
- *Coordination:* How do interacting agents mutually constrain each other's behavior? What coordination dynamics emerge in social interaction?

**Key distinction:** Information processing assumes start-stop cognition with stages (stimulus → processing → response). Interaction-dominant approaches assume continuous perception-action cycles, coupled to a structured environment, with no easily distinguished stages.

---

## Lecture 2: From Similarity to Categorization

### Q: What were Wittgenstein's objections against classical theory of concepts?

Wittgenstein objected that:
1. **No single common property** defines category membership — category members are linked by a "complicated network of similarities that overlap and criss-cross" (family resemblance).
2. **Category membership is graded**, not binary — some members are more typical/representative than others (prototype effects).
3. **Categories cannot be defined by necessary and sufficient conditions** — the classical approach (Aristotelian definition) fails for natural categories like "game."

### Q: What is a perceptual (psychological) space? How are stimuli represented in such a space?

A **perceptual space** is an abstract n-dimensional space representing the perceived dimensions of stimuli variability. Stimuli are represented as **points** (locations) in this space. The **distance** between points corresponds to perceived dissimilarity — closer points = more similar percepts.

Construction method: **Multidimensional Scaling (MDS)** — recovers the space from empirical data (e.g., confusion matrices, reaction times, similarity judgments) by minimizing a stress function (mismatch between experimental dissimilarities and recovered distances).

### Q: What kind of geometric relations are preserved through multidimensional scaling (MDS)? Do the lines parallel in the original space remain (approximately) parallel in the transformed space?

MDS preserves **distances** (or rank-order of distances) between points. It minimizes a cost function (Stress) representing the mismatch between original dissimilarities and recovered distances d_ij. 

**Parallel lines are NOT necessarily preserved** — MDS focuses on pairwise distance relationships, not linear/affine structure. The overall configuration may be rotated or reflected without affecting the solution.

### Q: What are the differences between prototype and exemplar models of categorization in terms of abstraction? How are exemplar models able to generalize to new stimuli?

| | Prototype Model | Exemplar Model (GCM) |
|---|---|---|
| **Abstraction** | Strong — category = single central tendency (mean) | None — all remembered instances stored |
| **Representation** | One prototype per category | All exemplars in memory |
| **Non-linear separability** | Cannot handle (e.g., XOR) | Can handle |

**Exemplar generalization mechanism (Nosofsky's GCM):**
- New stimulus classified by computing **weighted sum of similarities** to all stored exemplars per category
- Similarity function: S = e^{−c·d} (exponential decay with distance)
- Uses **Luce Choice Rule** (normalization) to compute classification probability
- Incorporates **base rate** (category frequency bias)

Key properties of the similarity function: identity (d=0 → S=1), non-negativity, rapid decay.

---

## Lecture 3: ART, Visual Attention

### Q: Explain the difference between the bottleneck theories of attention and selection-for-action theories of attention.

**Bottleneck theories:**
- Attention as a **filter** due to limited processing capacity
- Selection based on physical features (early: Broadbent) or semantic features (late: Deutsch & Deutsch)
- Main question: *where is the filter?* (early vs. late selection)
- Core assumption: we **cannot** process everything

**Selection-for-action theories** (Allport, 1989):
- Attention serves **action goals**, not just filtering
- Selection is for enabling **coherent action** in situations of unpredictability and multiple goals
- Rejects the "limitation/deficiency" framing
- Attention is divisible when actions don't require same effectors/channels
- "Having a body is to identify oneself with certain projects" (Merleau-Ponty)

**Key shift:** From "what gets filtered out" → "what enables effective action."

### Q: Are unattended stimuli processed at a semantic level or only the level of physical features? Support with empirical results.

**Yes, unattended stimuli ARE processed at semantic level** (though attenuated). Evidence:

1. **Cocktail party effect** — one's own name detected in unattended channel → semantic processing of "ignored" input
2. **Gray & Wedderburn** — participants integrate meaning across channels ("What the hell") despite attending to only one ear → semantic grouping overrides physical channel
3. **Von Wright** — Galvanic Skin Response to emotionally conditioned words in unattended channel → implicit semantic processing triggers emotional response

**Conclusion:** Unattended stimuli are processed semantically but in a weakened/attenuated form (Treisman's attenuation theory). Johnston proposed a flexible filter adapting to task demands.

### Q: What is the basic principle of Adaptive Resonance Theory?

ART (Grossberg, 1985) solves the **stability-plasticity dilemma:**
- **Plasticity:** ability to learn new patterns
- **Stability:** new learning must not destroy old knowledge (catastrophic forgetting)

**Solution:** Create new categories **on the fly** when top-down expectations **mismatch** bottom-up sensations. When expectations match input → "resonance" occurs → learning strengthens the match. When mismatch exceeds a threshold → new category is recruited.

Offers building blocks for modeling attention through top-down/bottom-up interaction.

### Q: How does categorization created by the ART1 model depend on the vigilance parameter?

The **vigilance parameter** controls category granularity:
- **High vigilance** → many fine-grained categories (requires close match between input and prototype) → used in Grossberg's model of **autism** (weak central coherence)
- **Low vigilance** → few broad categories (tolerates mismatch) → used in Grossberg's model of **schizophrenia**

Vigilance acts as a threshold: how similar must input be to an existing prototype before being assigned to that category vs. creating a new one.

---

## Lecture 4: Hopfield Network

### Q: What is a content-addressable memory? What phenomena can be modeled with this abstraction?

**Content-Addressable Memory (CAM):** Memory accessed by *content* (partial/degraded pattern) rather than by address. Given a noisy or incomplete input, the system retrieves the stored pattern most similar to it.

**Hopfield networks** implement CAM. The network converges to the nearest stored pattern (attractor) from any initial state.

**Modeled phenomena:**
- **Pattern completion** — reconstructing full memory from partial cue
- **Associative memory** — linking arbitrary stimuli (e.g., face → name)
- **Error correction** — noisy input → clean stored pattern
- **Memory retrieval** — emotional cue triggers full episodic memory
- Properties: fuzzy cue recall, time-to-recall, imperfect recall, false memories, limited capacity

### Q: How can Hopfield network be extended to model associations between arbitrary stimuli (for instance, a person's name and their face)?

1. **Represent** both stimuli as binary vectors (face pattern + name pattern)
2. **Concatenate** into a single combined vector [face | name]
3. **Store** this combined vector as a fundamental memory using Hebbian learning (weight update)
4. **Retrieval:** Present partial input (e.g., only the name portion, with face portion undefined/neutral) → let network iterate → it converges to the full stored pattern including the associated face

The key insight: the network treats the concatenated pattern as one memory, so activating any part can reconstruct the whole.

### Q: What is the role of energy potential function in Hopfield network? What are the local minima in the energy landscape?

**Energy function:** E = −½ Σᵢⱼ wᵢⱼVᵢVⱼ − Σᵢ IᵢVᵢ

**Role:** Guides network dynamics — every neuron update is guaranteed to **decrease or maintain** energy. The network evolves "downhill" in the energy landscape.

**Local minima** = stable states (attractors) where energy is lower than all neighboring states. These correspond to **stored memories**. When initialized with noisy input, the network flows to the nearest local minimum, retrieving the closest stored pattern.

---

## Lecture 5: Game Theory

### Q: What assumptions behind an agent are characteristic for game theory?

Game-theoretic agents are assumed to be:
1. **Rational** — they maximize their own utility/payoff
2. **Strategic** — they consider other agents' possible actions when choosing their own
3. **Self-interested** — motivated by individual payoff (not altruism)
4. **Fully informed** (in basic models) — know the rules, payoffs, and available strategies
5. **Simultaneous decision-making** — all players choose without knowing others' choices (in strategic/normal form games)

### Q: What is Nash equilibrium in game theory?

A **Nash Equilibrium** is a strategy profile (a*, a*₋ᵢ) where **no player can unilaterally improve their payoff** by changing their own strategy, given that all others keep theirs fixed.

Key properties:
- Every player is playing a **best response** to the others
- It's a **stable** state — no incentive to deviate
- A game may have zero, one, or multiple Nash equilibria
- It does NOT mean the outcome is optimal for everyone (cf. Prisoner's Dilemma)

### Q: What are mixed strategies in game theory?

A **mixed strategy** is a probability distribution over the set of pure (deterministic) strategies. Instead of choosing one action with certainty, a player randomizes according to specified probabilities.

**Why needed:** Some games have no pure-strategy Nash equilibrium (e.g., Rock-Paper-Scissors). A mixed-strategy NE always exists (Nash's theorem). Mixed strategies make a player unpredictable, preventing opponents from exploiting a deterministic pattern.

---

## Lecture 6: Decision Making 1 (Aggregation)

### Q: In a small group setting, what conditions impact the quality of group decisions?

Key conditions (from Bahrami et al., 2010 and SDT perspective):
1. **Individual competence variation** — if members' confidence levels vary visibly, the group can "reach for the truth" by weighting the most competent member
2. **Communication & feedback** — allowing communication leads to more accurate group decisions; members can share confidence, correct errors, coordinate
3. **Independence of observations** — if members' errors are correlated, averaging doesn't help (Bienaymé formula: Var(x̄) = σ²/n only when independent)
4. **Consensually incorrect stimuli** — if most members are biased the same way, the group converges on wrong answers
5. **Ability to communicate confidence** — what kind of information one participant can convey about their certainty

### Q: In the signal integration approach, how does the correlation between observing agents impact the distribution of group answers?

- **Independent agents** (zero correlation): Averaging is **statistically optimal** — variance reduces as σ²/n (Bienaymé formula). Errors cancel out.
- **Correlated agents:** Averaging is **suboptimal** because:
  - Errors are redundant (similar biases don't cancel)
  - Effective sample size is reduced
  - Common bias gets **amplified** rather than averaged out
  - In the limit of perfect correlation, averaging N agents is no better than one agent

Practical implication: Diversity of perspective matters more than group size.

### Q: Describe the 2-Alternative Forced Choice paradigm (2-AFC). What does the psychometric function describe? What is the meaning of its parameters?

**2-AFC task:** Participant is presented with two alternatives and must choose one (forced — no "I don't know" option). Example: "Which circle is larger?" or "Was the signal on the left or right?"

**Psychometric function:** S-shaped (sigmoid) curve relating stimulus intensity to probability of correct response.

**Parameters:**
- **Threshold (α):** Stimulus level at which performance = 50% (above chance) — the point of subjective equality
- **Slope (β / sensitivity):** Steepness of the curve — how quickly performance changes with stimulus intensity. Steeper = more sensitive discriminator
- **Bias (c):** Systematic preference for one response option when signal is ambiguous
- **Lapse rate (λ):** Upper asymptote < 1, reflecting inattention/motor errors

### Q: Give an example of how multisensory integration can lead to errors in perception.

**The McGurk Effect:**
- **Audio:** "ba" syllable is played
- **Visual:** video shows mouth articulating "ga"
- **Perceived:** "da" (neither audio nor visual!)

The brain integrates conflicting auditory and visual information into a "compromise" percept that doesn't correspond to either actual input. This demonstrates that perception is an active inference/integration process, not passive reception — and that this process can produce systematic errors when modalities conflict.

---

## Lecture 7: Decision Making 2 — Free Energy Principle & Bayesian Models

### Q: What is the forward and backward problem in Bayesian models of the brain?

**Forward problem (Generative model / Decoder):**
- Given causes θ, what sensory data D would they produce?
- Corresponds to the **likelihood** P(D|θ)
- Brain generates **top-down predictions** about expected sensory input
- "If there's a cat in front of me, what pattern should my retina show?"

**Backward problem (Inference / Encoder):**
- Given observed data D, what are the most probable causes θ?
- Corresponds to computing the **posterior** P(θ|D)
- Brain uses **bottom-up prediction errors** to update beliefs
- "Given this retinal pattern, what's probably out there?"

These interact continuously: brain predicts (forward), compares with actual input, computes error, updates model (backward).

### Q: What is the relation between FEP models and variational autoencoders?

Both share the framework of **variational inference:**

| | FEP (Brain) | VAE (Machine Learning) |
|---|---|---|
| Goal | Minimize surprise | Maximize ELBO |
| Encoder | Q(θ|D) ≈ P(θ|D) (recognition model) | Encoder network |
| Decoder | P(D|θ) (generative model) | Decoder network |
| Objective | Minimize Free Energy = −ELBO | Maximize ELBO |
| Actions | Active inference (change D through action) | N/A |

**Key link:** Free Energy = −ELBO = surprise + KL divergence. Both minimize the same quantity. FEP goes further by adding **action** (active inference: change the world to match predictions, not just update beliefs).

### Q: How are sensory experiences constructed from the activity of sensory receptors according to predictive processing theory?

According to **Predictive Processing:**

1. **Top-down predictions:** Higher cortical areas generate predictions about expected sensory input (based on generative model/priors)
2. **Bottom-up input:** Sensory receptors provide actual signals
3. **Prediction error:** At each hierarchical level, brain computes mismatch between prediction and actual input
4. **Model updating:** Prediction errors propagate upward, causing the internal model to update (Bayesian inference)
5. **Perception emerges** as the brain's "best guess" — the hypothesis that minimizes prediction error across all levels

**Key insight:** We don't perceive raw sensory data — we perceive the brain's best explanation of it. Perception = controlled hallucination constrained by sensory input.

---

## Lecture 8: Bottom-up Sensorimotor Learning

### Q: What kind of self-organization happens in Self Organizing Map (SOM)? What does it mean if two input patterns activate neurons which are neighbors in SOM topology?

**Self-organization in SOM (Kohonen network):**
- SOM learns to represent high-dimensional data in a low-dimensional grid (typically 2D) while **preserving topological relationships**
- Process: competitive learning — Best Matching Unit (BMU) and its neighbors update weights to become more similar to input
- Learning rate and neighborhood size decrease over time → convergence

**Neighboring neurons meaning:** If two input patterns activate neighboring neurons in the SOM grid, it means those patterns are **similar in the input space**. The SOM preserves topology — nearby points in input space map to nearby neurons on the grid. This is the key property: topological preservation.

### Q: Why cannot a movement mirroring task be realized through simple mapping of visual input to motor actuators? Why is there a need for predictive models?

Simple mapping fails because:
1. **Temporal delays** — there's a lag between observation and motor execution; direct mapping would always be late
2. **Motor noise** — actuators are imprecise, need correction
3. **Coordinate transformation** — visual space ≠ motor space (different reference frames, body morphology)
4. **Incomplete/noisy input** — visual information is often partial or degraded

**Predictive models are needed to:**
- **Anticipate** upcoming movements (compensate for delays)
- **Plan** sequences rather than just react
- **Correct** for motor noise using internal forward models
- **Infer** intended movement from incomplete visual information

### Q: Vanilla SOM model is used to realize unsupervised learning. How to modify it to perform prediction of future states?

Modifications for prediction:
1. **Time-windowed input:** Instead of feeding current state x(t), feed concatenated sequence [x(t), x(t-1), x(t-2),...] → SOM learns temporal patterns
2. **Growing When Required (GWR):** Architecture that adds nodes when existing ones don't match well — can learn dynamic sensorimotor maps
3. **Associative connections:** Link BMU at time t to BMU at time t+1 → learning transitions → predicting next state from current state

The key is incorporating **temporal information** into the SOM architecture so it learns sequential dynamics rather than just static clustering.

---

## Lecture 9: Motor Coordination and Fractal Dimension

### Q: What is self-organization? What kind of systems display self-organizing properties?

**Self-organization:** Process where a system spontaneously moves from disorder to order through internal interactions, without external control or blueprint.

Key insight: "We don't need structural similarity between effect and system producing it" — genetic material doesn't describe organism structure, brain doesn't generate detailed motor plans; instead they set boundary conditions for emergence.

**Systems displaying self-organization:**
- Physical: crystal growth, convection cells, snowflakes
- Biological: flocking, ant colonies, neural activity patterns
- Motor behavior: gait, coordination patterns
- Social: traffic patterns, language conventions

**Characteristic properties:** many interacting components, feedback, nonlinear dynamics, no central controller, emergence, energy flow, power-law structures.

### Q: How is white noise related to Brownian noise (red noise)?

| Property | White Noise | Brownian (Red) Noise |
|----------|-------------|---------------------|
| Definition | x(t) = ε, where ε ~ N(0,σ²) | x(t+1) = x(t) + ε |
| Independence | Samples completely independent | Each sample depends on previous |
| Spectrum | Flat: P(f) ~ 1 | Slope: P(f) ~ 1/f² |
| Fractal dimension | D = 2 | D = 1.5 |
| Correlation | None | Long-range correlations |

**Relationship:** Brownian noise is the **cumulative sum (integral)** of white noise. White noise = completely random; Brownian = random walk with memory.

**Between them:** Pink noise (1/f noise, β = −1, D' = 1) — found in human behavior (reaction times, gait, heart rate). This suggests self-organizing systems govern behavior.

### Q: What properties of gait dynamics make it a suitable phenomenon to be studied using fractal dimension?

1. **Complexity** — gait involves multiple interacting body systems; averaging statistics loses this
2. **Long-range dependencies** — stride-to-stride fluctuations show correlations across distant strides (DFA exponent 0.5 < α < 1.0) → fractal character
3. **Sensitivity to organization changes** — fractal dimension changes with:
   - Age (children α≈0.93 → elderly α≈0.69)
   - Disease (Parkinson's, neurodegeneration)
   - Walking speed conditions
4. **Predictive power** — fractal measures predict fall risk in elderly, detect neurodegenerative diseases
5. **Power-law structure** — suggests self-organizing underlying mechanism (not random, not purely deterministic)

---

## Lecture 10: Dynamical Systems — Models of Motor Coordination

### Q: Which approaches in the cognitive sciences assume the primacy of action in cognition and a crucial dependency of perception on action?

1. **Ecological Psychology** (Gibson) — organism tuned to and coupled with environmental structure; affordances
2. **Embodied Cognition** — cognitive processes rooted in body's interactions with environment
3. **Enactivism** (Varela, Thompson, Rosch) — cognition arises through dynamic interplay between organism and environment; perception is active exploration
4. **Sensorimotor Theory** (Noë) — perception = knowledge of sensorimotor contingencies
5. **Coordination Dynamics** (Kelso) — studying transitions between modes of coordination

Common thread: "World as its own model" (Brooks), continuous coupling, action-perception cycles, no start-stop cognition.

### Q: What is a synergy? Give some examples. How does it depend on compensatory processes?

**Synergy** (Bernstein): Functional, temporary binding of degrees of freedom into a coherent behavioral unit. Solves the **degrees of freedom problem** — every movement can be performed many ways, requiring flexible control over many DoF.

**Examples:**
- Speech production: jaw perturbation during /baeb/ → lips compensate within 20-30ms; during /baez/ → tongue compensates (Kelso et al., 1984)
- Grasping: if one finger slips, others increase grip force
- Walking: hip-knee-ankle coupling for stable gait

**Dependence on compensatory processes:**
- **Reciprocal compensation** = defining feature of synergies
- When one component is perturbed, others adjust to maintain the functional goal
- Compensation is **specific to the phase** of movement and to the task
- This reveals that the system is organized at the level of the goal, not individual components

### Q: Give two examples of predictions made by the model of bimanual coordination (Haken-Kelso-Bunz model).

**Prediction 1: Stability of coordination patterns**
- In-phase (φ = 0°) movements are **more stable** than anti-phase (φ = 180°) at all speeds
- Anti-phase shows increased variability (critical fluctuations) as speed increases

**Prediction 2: Speed-dependent phase transition**
- When movement frequency exceeds a critical value, anti-phase becomes unstable → spontaneous **bifurcation** to in-phase
- This transition shows **hysteresis** — switching point differs depending on direction of frequency change
- Predicted and confirmed: critical slowing down (increased relaxation time near transition), increased fluctuations before switch (Kelso et al., 1986; Scholz & Kelso, 1989)

---

## Lectures 11-12: Intrapersonal and Interpersonal Coordination

### Q: Guy van Orden et al., 2003 wrote: "Loosely speaking, whatever happens to one component happens to all components" – this is both a source of difficulty and hope. Why?

**Difficulty:**
- Cannot easily **isolate** cause-and-effect for individual components
- Confounding: manipulating one variable affects everything
- Hard to identify which component/interaction is critical
- Standard experimental logic (control one variable) breaks down

**Hope:**
- Studying **any one component** gives insight into the whole system
- System-level interventions can have **cascading effects**
- A single well-chosen measurement may reveal system-wide organization
- Holistic understanding becomes achievable through appropriate methods (like RQA)

### Q: What is cRQA? What is a diagonal profile?

**Cross-Recurrence Quantification Analysis (cRQA):**
- Method for examining coupling strength and nature between **two dynamical systems**
- Creates a cross-recurrence plot: marks a point whenever System A's behavior matches System B's behavior
- Reveals common constraints acting on both systems

**Diagonal profile (diagonal cross-recurrence profile):**
- Plots **recurrence rate as a function of time lag** along diagonals of the cross-recurrence plot
- Reveals **leading/lagging** relationships between systems
- Peak location → which system leads and by how much
- Peak height → strength of coupling

### Q: Sketch a diagonal profile of two systems: (a) tightly coupled, same behavior at same time; (b) one repeating other with 500ms delay; (c) one avoiding other's behavior at same time.

**(a) Tight coupling, simultaneous:** Sharp peak **centered at lag 0**, symmetric, high amplitude

**(b) Following with 500ms delay:** Peak **shifted to one side** (e.g., +500ms), indicating System B reproduces System A's behavior with a lag

**(c) Avoidance at same time:** **Dip/trough at lag 0** (below baseline), indicating systems actively produce *different* behaviors simultaneously

### Q: What is the nature of coupling of gaze and vocalizations in mother-infant interactions and how is this manifested on a diagonal profile?

**Early stages (~3 months):**
- Broader diagonal profile (influence spread across longer time window)
- No clear leader/follower
- Higher overall recurrence in gaze coordination

**Later stages (~6-8 months):**
- Higher concentration of recurrence **around lag-0** (tighter synchronization)
- Emerging **turn-taking** structure in vocalizations (decrease in overlapping vocalizations)
- More structured coordination patterns

**Developmental trajectory:** From diffuse, spread-out coordination → focused, synchronized, structured coupling. The diagonal profile narrows and peaks become sharper with development.

---

## Lecture 13: Evolution of Communication / Emergence of Signs

### Q: How are various features of communication systems dependent on interaction history? For example, arbitrariness of language symbols? Complexity of signs?

**Arbitrariness:**
- Signs typically start with some **iconicity** (resemblance to referent)
- Through repeated interaction, signs become **simplified and abstract** (Garrod et al., 2007: "pictionary" experiments)
- Alternating roles (both drawing) → faster convergence to arbitrary symbols
- Arbitrariness = product of **shared history and convention**, not design

**Complexity:**
- More complex environments → more structured signals
- "Learning by using" — signals that help predict partner's behavior are retained
- Compositionality emerges when the meaning space is complex enough to require it
- Interaction history creates dependencies on particular form-meaning mappings

### Q: Can an element of a communication system function well even though it has different meaning for each participant?

**Yes**, with caveats:
- Communication requires **sufficient coordination**, not perfect shared understanding
- "Learning by using" — a signal works if it helps A predict B's behavior (and vice versa), regardless of whether they represent the meaning identically internally
- Participants may have partially overlapping but non-identical interpretations and still coordinate successfully
- **Limit:** if divergence becomes too large and coordination breaks down, communication fails

### Q: What might be the sources of structuring of language systems? Why aren't languages simple?

**Sources of structure:**
1. **Interaction & coordination** — need to achieve shared goals drives structural conventions
2. **Cognitive constraints** — learnability, memorability, generalizability favor certain structures
3. **Communication pressures** — expressiveness, ambiguity resolution, efficiency
4. **Cultural evolution** — cumulative iterated learning selects for structures that survive transmission
5. **Historical contingency** — early choices constrain later development

**Why not simple:**
- **Expressiveness demands** — simple systems can't handle nuance or novel meanings
- **Compositionality** — structured signals are more learnable and generalizable than holistic ones
- **Robustness to noise** — redundancy in structure helps error correction
- **Multiple timescales** — evolution, development, and online interaction all shape structure simultaneously

### Q: Why is it difficult to study language emergence?

1. **Timescale** — evolution occurs over thousands/millions of years; inaccessible in real time
2. **Multiple interacting factors** — biological, cognitive, social, cultural all entangled
3. **No direct observation** — earliest stages of language lost to history
4. **Limited experimental control** — ethical constraints prevent radical manipulation of social environment
5. **Defining "emergence"** — unclear criteria for when a communication system counts as language
6. **Snowball effect** — once language exists, it's impossible to "restart" it experimentally

---

## Lecture 14: Lewis Signaling Game

### Q: In what sense are linguistic meanings conventional? What factors could cause a shift in an established system of meanings?

**Conventional means:** Meanings are established and maintained through **social agreement and shared usage**, not through inherent connection between form and meaning. The sound "dog" has no natural link to the animal — it's arbitrary convention.

**Factors causing shift:**
- **Social/cultural change** — new concepts need new terms; old terms adapt
- **Contact with other languages** — borrowing, influence
- **Prestige/influence** — language of powerful groups spreads
- **Ambiguity pressure** — consistently misunderstood words drift to resolve confusion
- **Semantic processes** — bleaching (loss of content), metaphorical extension
- **Lewis signaling dynamics** — evolutionary reinforcement can establish and shift conventions even without social reasoning

### Q: What are the limitations of Lewis' signaling game model? Can it be extended to work with structured signals?

**Limitations:**
1. Small discrete sets of states/signals/actions (oversimplified)
2. No **compositionality** — signals are holistic, not structured
3. No **syntax** or grammar
4. Agents are perfectly rational with complete information
5. No noise/errors in transmission
6. Objects assumed equally important (no frequency effects)
7. Fixed vocabulary size

**Extensions for structured signals:**
- Add syntax rules for combining signals
- Introduce hierarchical structure
- Add vocabulary constraints (finite budget)
- Allow compositional meaning (parts of signals carry partial meaning)
- These extensions make it a more powerful framework for studying language evolution

---

## Lecture 15: Towards Humane Cognitive Science

### Q: Two senses of the term "social cognition"

1. **Cognition OF social objects** — studying how we perceive, represent, and reason about other people, their mental states, emotions, intentions (Theory of Mind, face recognition, etc.)

2. **Cognition IS social** — cognition itself is fundamentally shaped by social interaction; "action first" in the social world (Vygotsky). Cognitive development is a product of social collaboration, not just individual information processing.

### Q: How is human cognition of other humans special (according to engaged epistemology)?

According to De Jaegher's **engaged epistemology:**

- Most of our knowledge about humans IS **second-person knowledge** (gained through direct engagement, not detached observation)
- Human knowing is "living, loving knowing" — requires **letting the other be** (not overdetermining or underdetermining)
- This knowing is **mutually transforming** — both knower and known are changed
- Traditional science relies only on 3rd-person (objective, disengaged) perspective, which may **destroy** or lose precisely what matters about human cognition
- Call for **engaged epistemology:** bring felt understanding back into science
- We are "extraordinary sensitive" to others' attention toward us — bodily modifications occur just from being noticed (William James, 1884)
- Implication: studying cognition requires studying coordination and interaction, not just isolated individuals

---

## ⚠️ Concerns & Notes

1. **Lecture 8 (Sensorimotor/SOM):** No lecture text was extractable — answers synthesized from 2025 exam answers + lab notebooks. The descriptions of SOM, predictive models, and GWR come from secondary sources. If the lecturer emphasized something specific beyond what's here, it won't be captured.

2. **Lecture 6 required reading** (Bahrami et al., 2010): The exam question explicitly says "see the required reading." The answers above cover the main points from the lecture, but the paper itself may contain additional conditions for group decision quality that aren't in the slides.

3. **FEP lecture (Lecture 7):** The extracted text was only 3K chars (mostly equations). Answers supplemented heavily from 2025 exam prep. If the 2026 lecturer added new material beyond the slides, it's not captured.

4. **Lecture 9 vs. 2026 ordering:** In 2025, fractal dimension was Lecture 2; in 2026 it's Lecture 9. Content appears the same but context may differ.

5. **Categorization PDF** had binary encoding issues in extraction — key content covered via `cognitive_models_qa.txt` instead.

6. **Missing diagrams:** Several questions (HKB phase portraits, diagonal profiles, cRQA plots) benefit from visual diagrams that can't be reproduced here. Recommend reviewing the original slides for these.
