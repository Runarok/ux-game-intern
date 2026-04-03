### 1. Lesson Focus



* Debugging = **process of identifying and fixing errors in logic**

* Mistakes are expected → value comes from **correction + understanding**

* Goal: build ability to **trace, isolate, and fix issues systematically**



---



### 2. Lesson Objectives



* Understand GDAU debugger interface

* Learn types of errors in programming

* Apply debugging techniques (print, test cases, debugger)



---



### 3. Debugger Interface (GDAU)



Located in bottom panel → multiple tabs:



#### Debugger Tab



* Core debugging tool

* Shows:



&#x20; * Stack frames (execution flow)

&#x20; * Variable states



#### Errors Tab



* Lists:



&#x20; * Errors (critical)

&#x20; * Warnings (non-critical)



#### Profiler



* Measures performance per node:



&#x20; * Time per frame

&#x20; * Frame %

&#x20; * Physics frame %



#### Monitors



* Tracks system metrics:



&#x20; * Time

&#x20; * Memory

&#x20; * Physics

&#x20; * Rendering

&#x20; * Audio



#### Video RAM



* Tracks GPU memory usage

* Important for optimization later



#### Misc



* Shows:



&#x20; * Clicked node

&#x20; * Node type during runtime



---



### 4. Warnings vs Errors



* **Warnings**



&#x20; * Code runs

&#x20; * Indicates inefficiency or unused elements

&#x20; * Example:



&#x20;   * Unused argument → prefix `_`

* **Errors**



&#x20; * Can break execution

&#x20; * Must be fixed



---



### 5. Breakpoints (Core Tool)



* Set by clicking left of line number

* Pauses execution at that line



**Use**



* Inspect variables at exact moment

* Step through logic line-by-line



---



### 6. Debug Controls



* **Continue** → resume execution

* **Break** → pause manually

* **Step Over** → next line

* **Step Into** → enter function

* **Skip** → ignore breakpoints



---



### 7. Types of Errors



#### 7.1 Syntax Errors



* Violation of language rules

* Detected before execution



**Examples**



* Wrong keyword (`bool` instead of `var`)

* Missing indentation

* Incorrect structure



---



#### 7.2 Runtime Errors



* Occur during execution

* Not caught beforehand



**Examples**



* Index out of bounds

* Wrong coordinate space (global vs local)



**Impact**



* Can crash game or break behavior



---



#### 7.3 Semantic (Logical) Errors



* Code runs but produces wrong result

* Hardest to detect



**Examples**



* Wrong condition (`<` vs `>`)

* Misunderstanding behavior (string + number → concatenation)



---



### 8. Casting (Quick Concept)



* Changing variable type:



&#x20; * `float(value)`

* Example:



&#x20; * `5 → 5.0 → 5.0 + 3.5 = 8.5`



---



### 9. Debugging Techniques



#### 9.1 Print Statements



* Place logs in code to track flow



**Strategy**



* Beforeafter functions

* Narrow down using:



&#x20; * Start → middle → end (binary search approach)



**Limitations**



* Manual, cluttered

* No automatic state tracking



---



#### 9.2 Test Cases



* Define:



&#x20; * Input → expected output



**Approach**



* Treat function as:



&#x20; * “guilty until proven correct”

* Validate:



&#x20; * Normal cases

&#x20; * Edge cases



**Rule**



* Expected results must be correct → no ambiguity



---



#### 9.3 Debugger (Advanced)



* Use when:



&#x20; * Problem is unclear

&#x20; * Print statements insufficient



**Focus**



* Track variable values step-by-step

* Observe unexpected changes



---



### 10. Debugging Workflow (Practical)



1. Identify symptom

2. Reproduce consistently

3. Use print → locate region

4. Use test cases → validate logic

5. Use debugger → inspect deeply

6. Fix → retest



---



### 11. Key Observations



* Syntax errors → easiest

* Runtime errors → visible during play

* Semantic errors → most dangerous (silent failures)



---



### 12. Performance Awareness



* Debug tools also help:



&#x20; * Identify lag sources

&#x20; * Optimize heavy nodes

* VRAM monitoring becomes critical once assets are added



---



### 13. What to Remember



* Debugging is not separate from coding → it *is* coding

* Most time in development is spent fixing, not writing

* Always isolate before fixing

* Never assume → verify with tests or prints

* Small logic errors scale into large system failures



---



### 14. What Matters Going Forward



* Ability to:



&#x20; * Trace execution flow

&#x20; * Read variable state changes

* Discipline to:



&#x20; * Test incrementally

&#x20; * Keep logic observable

* Awareness:



&#x20; * Bugs are rarely random → they follow your logic



---





