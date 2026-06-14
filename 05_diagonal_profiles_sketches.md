# Diagonal Profile Sketches (cRQA Exam Question)

## The Question

> Sketch a diagonal profile of two systems:
> 1. Tightly coupled, manifesting the same behaviour at approximately the same time
> 2. One system repeating the other system behavior with a delay (e.g. of 500ms)
> 3. One system avoiding the other system's behaviour at the same time

---

## Text-Art Diagrams

### (a) Tight coupling — simultaneous behavior

```
%RR
 |
 |         ***
 |       **   **
 |      *       *
 |     *         *
 |    *           *
 |...*.............*....... baseline
 |  *               *
 | *                 *
 |*                   *
 +-----------|----------→ Lag (ms)
         -1000  0  +1000
                ↑
          Peak at lag 0
         (synchrony)
```

**Interpretation:** Sharp, symmetric peak centered at lag 0. Systems do the same thing at the same time. Strong coupling, no leader/follower.

---

### (b) Following with 500ms delay

```
%RR
 |
 |                ***
 |              **   **
 |             *       *
 |            *         *
 |           *           *
 |..........*.............*.. baseline
 |         *               *
 |        *                 *
 |       *                   *
 +-----------|--------|-------→ Lag (ms)
         -1000  0   +500  +1000
                     ↑
              Peak at +500ms
         (B follows A with delay)
```

**Interpretation:** Peak shifted to +500ms. System B reproduces System A's behavior, but 500ms later. A leads, B follows. The peak height indicates coupling strength.

---

### (c) Avoidance — anti-coordination at same time

```
%RR
 |
 |***                     ***
 |   **                 **
 |     *               *
 |......*...............*...... baseline
 |       *           *
 |        **       **
 |          **   **
 |            ***
 +-----------|----------→ Lag (ms)
         -1000  0  +1000
                ↑
          Dip at lag 0
          (avoidance)
```

**Interpretation:** Trough/dip at lag 0, recurrence falls BELOW baseline. Systems actively produce DIFFERENT behaviors at the same time. They avoid matching each other. Recurrence may increase at other lags (they might match accidentally at non-zero delays).

---

## Visual Summary Table

| Scenario | Peak/Dip Location | Shape | Meaning |
|----------|-------------------|-------|---------|
| (a) Synchrony | Lag 0 | Sharp peak ↑ | Same behavior, same time |
| (b) Following | Lag +500ms | Shifted peak ↑ | B copies A with delay |
| (c) Avoidance | Lag 0 | Dip ↓ below baseline | Actively different at same time |

---

## PNG Version

See [05_diagonal_profiles.png](05_diagonal_profiles.png) for a proper matplotlib plot of the same three profiles.

---

## Bonus: Mother-Infant Diagonal Profile (Development)

### Early (~3 months):
```
%RR
 |
 |    ***********************
 |  **                       **
 |**                           **
 |.................................  baseline
 +-----------|----------→ Lag
          -2s   0   +2s
      (broad, no clear peak)
```

### Later (~6-8 months):
```
%RR
 |
 |           ***
 |         **   **
 |        *       *
 |.......*.........*...........  baseline
 |      *           *
 +-----------|----------→ Lag
          -1s   0   +1s
    (narrow peak at 0, tighter coupling)
```

**Development:** Profile narrows and sharpens — from diffuse coordination to focused synchrony. Turn-taking emerges in vocalizations.
