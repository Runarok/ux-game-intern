# 1. Core Principle: Iterative Development

* Improvement comes from **repeated cycles**, not one-time design.

* Each iteration includes:

  * Modify mechanics
  * Update logic
  * Debug
  * Test

* Goal: **progressively refine behavior + experience**

---

# 2. Development Loop (Applied)

1. Translate mechanic changes → code
2. Implement new behavior
3. Debug (runtime + semantic)
4. Test (internal + user)
5. Refine again

→ This loop repeats continuously.

---

# 3. Programming Before Coding

* Don’t jump into code immediately.
* First:

  * Break down current behavior
  * Define desired behavior

### Example Structure:

* Current system → fixed movement (global axes)
* Desired system → camera-relative movement

---

# 4. Behavior Breakdown Method

## 4.1 Current State

* Movement tied to global axes
* Camera rotation independent
* Result: disorientation

---

## 4.2 Target State

* Movement tied to **local coordinate space**
* Camera controlled via mouse
* Player movement aligns with camera direction

---

## 4.3 Key Shift

* Global → Local transformation thinking

---

# 5. Core Implementation Concepts

## 5.1 Local vs Global Transform

* Global → fixed world directions
* Local → relative to object orientation

→ Fix: use `transform.basis` vectors

---

## 5.2 Velocity Handling

* Preserve:

  * Y-axis (gravity)

* Reset:

  * Horizontal components before recalculation

---

## 5.3 Camera Control

* Use mouse input
* Apply rotation on Y-axis
* Smooth movement using interpolation (lerp)

---

## 5.4 Input Handling

* Use unhandled input for mouse motion
* Capture + release mouse:

  * Capture → gameplay
  * Release → escape key

---

# 6. Debugging Strategy (Iteration 2)

## 6.1 Start with Runtime Errors

* Detected via engine debugger
* Example issue:

  * Assigning integer to vector → breaks later

### Insight:

* Error may appear **after actual cause**

---

## 6.2 Stack Understanding

* Stack = execution history (LIFO)

* Helps trace:

  * What happened before failure

* Doesn’t always show exact origin

---

## 6.3 Fix Pattern

* Identify incorrect data types
* Fix at **source of mutation**, not where it crashes

---

# 7. Semantic Errors (More Subtle)

## 7.1 Case 1: Run Speed Issue

* Code correct
* Problem = values too similar

### Insight:

* Semantics depend on:

  * logic + parameter values

---

## 7.2 Case 2: No Diagonal Movement

* Cause:

  * velocity overwritten instead of accumulated

### Fix:

* Replace:

  * `=`

* With:

  * `+=`

---

## 7.3 Debugging Without Tools

* Focus on:

  * recent changes

* Ask:

  * what changed that could cause this?

→ Often faster than debugger

---

# 8. Debugging Approach Hierarchy

1. Think (logic review)
2. Print statements
3. Value testing (sanity checks)
4. Debugger (if necessary)

---

# 9. Internal Testing Phase

## 9.1 Purpose

* Validate:

  * mechanics behavior
  * feel of movement

---

## 9.2 Testing Setup

* Create environment:

  * platforms at varied distances/heights

* Test:

  * movement
  * jump
  * speed
  * gravity

---

## 9.3 Key Focus

* Not difficulty
* Focus on:

  * balance
  * responsiveness

---

# 10. Parameter Tuning Strategy

* Use **binary search approach**:

  * Adjust → test → refine

* Tune:

  * walk/run speed
  * jump height/distance
  * gravity

---

# 11. Level Design for Testing

## 11.1 Initial Phase

* Rough layout
* Test mechanics limits

---

## 11.2 Later Phase

* Convert into obstacle course
* Introduce challenge intentionally

---

# 12. Visual Guidance (UX Layer)

* Use colors to guide player:

  * Start → green
  * End → distinct (e.g., blue)

* Avoid confusion:

  * Make important elements stand out

---

# 13. Modularity in Practice

* Mechanics implemented as functions
* Enables:

  * quick changes
  * easy debugging
  * isolated testing

---

# 14. Player Feedback Loop

* After internal testing:

  * bring external testers

* Collect:

  * observations
  * reactions

* Convert:

  * feedback → mechanics issues

---

# 15. Prototype Philosophy

* Prototype = experimentation zone
* Priorities:

  * remove flaws
  * validate mechanics

### Avoid:

* attachment
* premature polishing

---

# 16. Error Thinking Model

* Runtime error → system failure
* Semantic error → expectation mismatch

### Key Insight:

* Not all errors are code bugs
* Some are:

  * poor values
  * poor design decisions

---

# 17. Practical Workflow Summary

1. Identify mechanic issues
2. Define improved behavior
3. Update logic
4. Fix runtime errors
5. Detect semantic issues
6. Tune parameters
7. Test in controlled environment
8. Design test level
9. Gather feedback
10. Repeat

---

# 18. What to Always Remember

* Iteration > perfection

* Mechanics define experience

* Debugging is:

  * observation + reasoning

* Recent changes are prime suspects

* Values matter as much as logic

* Replace vs fix is a conscious decision

* Internal testing precedes user testing

* Prototype phase exists to fail safely

* Clarity in behavior design reduces debugging effort

---
