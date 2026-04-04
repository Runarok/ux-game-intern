# 1. Core Mindset About Mistakes

* Mistakes are **not losses**, even if they cost timeeffort.
* They are **feedback loops** that refine your logic.
* Debugging exists because mistakes are **expected, not exceptional**.
* The goal: **reduce repetition of the same mistake**, not avoid mistakes entirely.

---

# 2. Purpose of Debugging

* Identify and fix **runtime** and **logical (semantic)** errors.
* Understand how your program behaves **step-by-step**.
* Improve both:

  * Code correctness
  * Performance

---

# 3. GDAU Debugger Panel Overview

## 3.1 Debugger Tab

* Core debugging interface.
* Shows:

  * Stack frames (active processes)
  * Variable states
* Used with breakpoints to inspect execution.

## 3.2 Errors Tab

* Lists:

  * Errors (must fix)
  * Warnings (optional but important)
* Includes:

  * File name
  * Line number
  * Description
  * Suggested fixes

## 3.3 Profiler Tab

* Measures performance:

  * Time per frame
  * Frame %
  * Physics frame %
* Helps identify **performance bottlenecks**.

## 3.4 Network Profiler

* Tracks network-related performance.
* Not relevant unless using networking.

## 3.5 Monitors Tab

* Real-time system metrics:

  * Time
  * Memory
  * Physics
  * Rendering
* Useful for diagnosing **lag or inefficiency**.

## 3.6 Video RAM Tab

* Tracks VRAM usage.
* Important because:

  * VRAM is limited
  * Systems vary widely
* Helps optimize asset usage.

## 3.7 Misc Tab

* Shows:

  * Clicked node
  * Node type
  * Scene location

---

# 4. Breakpoints

* Pause execution at a specific line.
* Allows inspection of:

  * Variables
  * Flow of execution

### Key Controls:

* **Continue** → resume execution
* **Step Into** → enter function
* **Step Over** → skip function internals
* **Break** → pause manually

---

# 5. Types of Errors

## 5.1 Syntax Errors

* Violations of language rules.
* Examples:

  * Wrong keyword (`bool` instead of `var`)
  * Incorrect indentation
* Characteristics:

  * Easy to detect
  * Prevent program from running

---

## 5.2 Runtime Errors

* Occur during execution.
* Not caught before running.

### Causes:

* Unexpected inputs
* Invalid operations

### Examples:

* Index out of bounds
* Incorrect coordinate space

### Characteristics:

* Can crash program
* Harder to trace than syntax errors

---

## 5.3 Semantic (Logical) Errors

* Code runs, but behaves incorrectly.

### Causes:

* Wrong conditions
* Misunderstanding of logic
* Incorrect assumptions

### Examples:

* `<` vs `>` mismatch
* String concatenation instead of addition

### Characteristics:

* No error messages
* Most difficult to detect
* Dangerous in large systems

---

# 6. Debugging Techniques

## 6.1 Print Statements

* Quickest way to locate issues.

### Method:

* Add prints:

  * Before and after functions
  * Inside critical sections

### Binary Search Approach:

* Narrow down error location:

  * Start → Middle → End
  * Reduce search space step-by-step

### Limitations:

* Manual and messy
* No automatic state tracking

---

## 6.2 Test Cases

* Validate correctness using known inputsoutputs.

### Approach:

* Define expected outputs
* Compare actual vs expected

### Rule:

* Only one uncertainty at a time:

  * If test case is wrong → debugging fails

### Benefit:

* Builds confidence in correctness

---

## 6.3 Debugger (Advanced)

* Most powerful and detailed method.

### What to Track:

* Variable changes
* Execution flow
* Unexpected state transitions

### Key Insight:

* Debugging = **observing state changes over time**

---

# 7. Practical Debugging Strategy

1. Start with:

   * Error messages (if any)
2. Use:

   * Print statements for quick isolation
3. Validate:

   * With test cases
4. If unresolved:

   * Use debugger with breakpoints
5. Track:

   * Variable values line-by-line

---

# 8. Performance Awareness

* Use:

  * Profiler
  * Monitors
* Identify:

  * Heavy nodes
  * Frame drops
* Optimize only when needed.

---

# 9. Key Technical Concepts

## 9.1 Casting

* Converting data types:

  * Example: `float(5) → 5.0`

## 9.2 Indexing

* Arrays start at **0**
* Access beyond range → runtime error

## 9.3 Concatenation vs Addition

* Strings: `"7" + "3" → "73"`
* Numbers: `7 + 3 → 10`

---

# 10. Decision Framework for Debugging

Choose method based on problem size:

* Small issue → print statements
* Medium issue → test cases + prints
* Complex issue → debugger

---

# 11. What to Always Remember

* Syntax errors → visible and easy
* Runtime errors → appear during execution
* Semantic errors → silent and most dangerous
* Debugging is:

  * Not guessing
  * Not random trial
  * It is **systematic observation**
* Always:

  * Track variable state
  * Validate assumptions
  * Reduce uncertainty step-by-step
* Code is rarely wasted:

  * Even wrong implementations contain reusable insights

---
