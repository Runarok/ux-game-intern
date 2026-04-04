# 1. Core Problem: Refinement Without Structure

* Improving blindly can:

  * Drift away from original design intent
  * Introduce new problems while fixing old ones

* Solution: **Structured refinement process**

---

# 2. Root vs Symptom Thinking

* Don’t fix surface issues.
* Focus on **mechanics (root cause)**.

### Principle:

* Bad experience ≠ random issue
* It is a result of **underlying mechanics**

---

# 3. Game Interaction Model (Foundation Layer)

## 3.1 Core Loop

* Player → Input
* System → Processes input
* Game state updates
* UI → Displays output
* Loop repeats

---

## 3.2 Three Core Entities

### Player

* Provides input
* Reacts to output

### User Interface (UI)

* Translates:

  * Player input → system
  * System output → player

* Must be:

  * Clear
  * Non-intrusive

### Core Mechanics

* Backend logic
* Produces game state
* Defines challenge + behavior

---

## 3.3 Gameplay Definition

* Gameplay = **UI ↔ Mechanics interaction**

---

# 4. Interaction Models (How Player Engages)

## 4.1 Avatar-Based

* Player controls a character
* Limitations = avatar capabilities
* Example constraints:

  * Movement
  * Reach
  * Abilities

---

## 4.2 Multi-Present (Strategy Style)

* No avatar

* Player controls multiple entities

* Key traits:

  * Zoomed-out control
  * Task delegation
  * Limited by visibility + control device

---

## 4.3 Party-Based

* Multiple avatars controlled together

* Hybrid:

  * Strategy + immersion

* Flexible camera → affects experience

---

## 4.4 Contestant Model

* Player chooses from predefined options

* Limited control

* Often used in:

  * Story systems
  * Mini-games (e.g., lockpicking)

---

## 4.5 Gameplay Modes

* Different interaction models can coexist

* Example:

  * Exploration → Avatar
  * Dialogue → Contestant

---

# 5. Evaluating Mechanics (Good vs Bad)

## 5.1 Use Player Feedback Properly

* Don’t take feedback at face value
* Translate feedback → **mechanics problem**

### Example Insight:

* “Players want more hero units” ≠ quantity issue
* It signals:

  * Imbalance
  * Preference bias
  * Engagement flaw

---

## 5.2 Key Questions

* Which interaction model is used?
* How does it affect experience?
* Why does player prefer one element over another?

---

## 5.3 Goal at This Stage

* Only:

  * Identify
  * Categorize

* NOT fix yet

---

# 6. Ranking Bad Mechanics (Prioritization)

## 6.1 Based on Player Reaction

* Ratings
* Feedback intensity

---

## 6.2 Based on Impact

### Highest Priority:

* Crashes → breaks game

### Next:

* Performance issues
* Poor responsiveness
* Friction in gameplay

---

## 6.3 Measurement Techniques

### Timing

* Measure execution speed
* Stress test mechanics

### Isolated Testing

* Test one mechanic independently

### Focused Ratings

* Evaluate:

  * Responsiveness
  * Usability
  * Performance impact

---

# 7. Fix vs Replace Decision

## 7.1 When to Replace

* Mechanic is:

  * Fundamentally broken
  * Too costly to fix
  * Harming core experience

---

## 7.2 Replacement Cost Reality

* Slowest solution
* Requires:

  * Redesign
  * Implementation
  * Testing

---

## 7.3 Extreme Case

* Too many broken mechanics →
  → **Reconsider entire design direction**

---

# 8. Decision Framework for Mechanics

Ask:

1. Why does this mechanic exist?
2. What happens if we remove it?
3. Is there a better way to achieve the same effect?

---

# 9. Modularity (Critical Design Principle)

## 9.1 Definition

* System built as interchangeable components

---

## 9.2 Benefits

* Easy to:

  * Disable
  * Replace
  * Test

---

## 9.3 Structure of a Module

* Input
* Process
* Output

---

## 9.4 Practical Use

* Comment out a function → test necessity
* Replace function → test alternative

---

## 9.5 Anti-Pattern

* Monolithic code:

  * Hard to modify
  * Hard to debug
  * Hard to replace parts

---

# 10. Foundational vs Non-Foundational Mechanics

## 10.1 Foundational

* Game breaks without it
* Must:

  * Refine or replace carefully

---

## 10.2 Non-Foundational

* Game still works without it
* Can:

  * Remove or redesign freely

---

# 11. Replacing Mechanics (Practical Thinking)

## 11.1 Diagnose Precisely

* Don’t assume obvious issue

### Example:

* Jump feels bad ≠ jump physics issue
  Could be:

  * Camera discomfort
  * Overuse
  * Poor level design

---

## 11.2 Alternative Thinking

Instead of:

* Fixing → question design

### Examples:

* Double jump → glide
* Jump → wind lift
* Jump → ladder
* Platform height → adjust

---

# 12. Prototype Phase Philosophy

* This phase is for:

  * Experimentation
  * Iteration
  * Failure

* Avoid:

  * Attachment to ideas
  * Over-polishing early

---

# 13. Hidden Insight (Important)

* Feedback is often:

  * Indirect
  * Incomplete

→ You must **interpret**, not just implement

---

# 14. Practical Workflow

1. Collect feedback
2. Map feedback → mechanics
3. Categorize (good/bad)
4. Rank by:

   * Severity
   * Impact
5. Decide:

   * Fix or replace
6. Use modularity to test
7. Iterate in prototype phase

---

# 15. What to Always Remember

* Mechanics = root cause of experience
* Player feedback is a signal, not a solution
* Ranking prevents wasted effort
* Modularity enables fast iteration
* Foundational mechanics require deeper thinking
* Replacement is costly → use carefully
* Prototype phase = safe zone for change
* Lack of structure → design drift

---
