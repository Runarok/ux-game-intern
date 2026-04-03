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



&#x20; * Code correctness

&#x20; * Performance



---



# 3. GDAU Debugger Panel Overview



## 3.1 Debugger Tab



* Core debugging interface.

* Shows:



&#x20; * Stack frames (active processes)

&#x20; * Variable states

* Used with breakpoints to inspect execution.



## 3.2 Errors Tab



* Lists:



&#x20; * Errors (must fix)

&#x20; * Warnings (optional but important)

* Includes:



&#x20; * File name

&#x20; * Line number

&#x20; * Description

&#x20; * Suggested fixes



## 3.3 Profiler Tab



* Measures performance:



&#x20; * Time per frame

&#x20; * Frame %

&#x20; * Physics frame %

* Helps identify **performance bottlenecks**.



## 3.4 Network Profiler



* Tracks network-related performance.

* Not relevant unless using networking.



## 3.5 Monitors Tab



* Real-time system metrics:



&#x20; * Time

&#x20; * Memory

&#x20; * Physics

&#x20; * Rendering

* Useful for diagnosing **lag or inefficiency**.



## 3.6 Video RAM Tab



* Tracks VRAM usage.

* Important because:



&#x20; * VRAM is limited

&#x20; * Systems vary widely

* Helps optimize asset usage.



## 3.7 Misc Tab



* Shows:



&#x20; * Clicked node

&#x20; * Node type

&#x20; * Scene location



---



# 4. Breakpoints



* Pause execution at a specific line.

* Allows inspection of:



&#x20; * Variables

&#x20; * Flow of execution



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



&#x20; * Wrong keyword (`bool` instead of `var`)

&#x20; * Incorrect indentation

* Characteristics:



&#x20; * Easy to detect

&#x20; * Prevent program from running



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



&#x20; * Before and after functions

&#x20; * Inside critical sections



### Binary Search Approach:



* Narrow down error location:



&#x20; * Start → Middle → End

&#x20; * Reduce search space step-by-step



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



&#x20; * If test case is wrong → debugging fails



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



&#x20;  * Error messages (if any)

2. Use:



&#x20;  * Print statements for quick isolation

3. Validate:



&#x20;  * With test cases

4. If unresolved:



&#x20;  * Use debugger with breakpoints

5. Track:



&#x20;  * Variable values line-by-line



---



# 8. Performance Awareness



* Use:



&#x20; * Profiler

&#x20; * Monitors

* Identify:



&#x20; * Heavy nodes

&#x20; * Frame drops

* Optimize only when needed.



---



# 9. Key Technical Concepts



## 9.1 Casting



* Converting data types:



&#x20; * Example: `float(5) → 5.0`



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



&#x20; * Not guessing

&#x20; * Not random trial

&#x20; * It is **systematic observation**



* Always:



&#x20; * Track variable state

&#x20; * Validate assumptions

&#x20; * Reduce uncertainty step-by-step



* Code is rarely wasted:



&#x20; * Even wrong implementations contain reusable insights



---





