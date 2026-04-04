### 1. Lesson Focus

* Shift from **engine usage → scripting logic**
* Core goal: make the game respond to **player input**
* Introduces programming fundamentals within game context

---

### 2. Lesson Objectives

* Understand basic programming concepts
* Create and attach scripts to game objects
* Write and test simple logic in GDScript
* Modify scripts to add player movement functionality

---

### 3. Script Creation & Attachment

* Create folder: `res:scripts`
* Select correct node (Player → KinematicBody)
* Create script:

  * Language: GDScript
  * Inherits from selected node
  * Example name: `player_controller.gd`
* Script attaches to node (visible via icon)

**Important**

* Wrong script → delete file + detach from node
* Script remains cached until engine restart

---

### 4. Script Editor Structure

* Built-in editor (no external IDE needed)
* Panels:

  * Top → script tabs
  * Bottom → function list
* Key menus:

  * File → manage scripts
  * Edit → modify code
  * Search → findreplace
  * Go To → navigate large scripts
  * Debug → error handling

---

### 5. GDScript Fundamentals

* Python-like syntax (easy learning curve)
* Dynamically typed:

  * No need to define types explicitly
* Uses `var` for variables

**Key Difference from Python**

* Designed for node-based architecture
* Includes built-in types for 2D3D (vectors, transforms)

---

### 6. Variables & Constants

* Variables:

  * Store values (numbers, objects, booleans, etc.)
  * Declared using `var`
* Constants:

  * Declared using `const`
  * Uppercase naming convention
  * Used for fixed values (e.g., speeds)

**Best Practice**

* Define variablesconstants at top of script

---

### 7. Boolean Logic

* Boolean values: `true`  `false`

**Operators**

* Comparison:

  * `<`, `>`, `==`
* Logical:

  * `and` → both must be true
  * `or` → at least one true
  * `not` → inverts result

---

### 8. Conditional Statements

* `if` → primary condition
* `elif` → additional conditions
* `else` → fallback (no condition)

**Usage**

* Control game behavior based on inputstate
* Must follow structure:

  * One `if`
  * Multiple `elif`
  * One optional `else`

---

### 9. Loops

* **for loop**

  * Fixed number of iterations
* **while loop**

  * Runs until condition is met
  * Risk of infinite loop

**Use Case**

* Avoid repeating code manually

---

### 10. Functions (Core Concept)

* Defined using `func`
* Structure:

  * Input (parameters)
  * Processing
  * Output (return)

**Purpose**

* Reuse logic
* Keep code modular and readable

---

### 11. Game Loop Concept

* Game runs continuously via loop:

  1. Wait for input
  2. Process input
  3. Update game state
  4. Render output
* Runs multiple times per second (frame-based)

**Key Insight**

* Everything in gameplay ties to this loop

---

### 12. Event Handling & Input System

* Input handled via:

  * **Events** → actions (key presses)
  * **Listeners** → detect events
* Engine maps inputs (e.g., `ui_up`, `ui_down`)

---

### 13. Core Movement Implementation

#### Function Used

* `_physics_process(delta)`

  * Runs every frame
  * Handles physics-related updates

#### Input Detection

* `Input.is_action_pressed("ui_up")`

  * Returns boolean

---

### 14. Movement Logic Structure

#### Step 1: Velocity Variable

* `var velocity = Vector3()`
* Represents movement in 3D (X, Y, Z)

#### Step 2: Speed Constants

* `const WALK = 5`
* `const RUN = 20`

#### Step 3: Direction Mapping

* Z-axis → forwardbackward
* X-axis → leftright
* Sign (+-) controls direction

---

### 15. Applying Movement

* Modify velocity based on input
* Apply movement:

  * `move_and_slide(velocity, Vector3.UP)`

**Important**

* Setting velocity alone ≠ movement
* Must apply via movement function

---

### 16. Input Mapping Setup

* Project Settings → Input Map
* Add keys (e.g., W → `ui_up`)
* Allows multiple keys for same action

---

### 17. Fixing Direction Issues

* Movement depends on camera orientation
* If reversed:

  * Invert sign of velocity

---

### 18. Stopping Movement

* Use `else` branch:

  * Reset velocity when no input
* Replace multiple `if` with `elif`

  * Prevent conflicting inputs

---

### 19. Edge Case Handling (Important)

* Problem:

  * Opposite inputs (e.g., left + right)
* Result:

  * Unstable or priority-based movement

**Expected Fix**

* Cancel movement when both pressed

---

### 20. Running Mechanic

* Add condition:

  * If `shift` + direction → use RUN
  * Else → use WALK

---

### 21. Key Structural Rules

* Indentation defines code blocks
* Variables must be defined before use
* One execution flow:

  * if → elif(s) → else
* Movement logic runs every frame

---

### 22. What Actually Changed in This Lesson

* Game is no longer static
* Transition:

  * Scene → interactive system
* Player input now drives game behavior

---

### 23. What Matters Going Forward

* Clear understanding of:

  * Input handling
  * Frame-based updates
  * Velocity-based movement
* Ability to:

  * Read logic flow
  * Modify behavior safely
* Awareness of edge cases (conflicting inputs)

---
