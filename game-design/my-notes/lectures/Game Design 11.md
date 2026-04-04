### 1. Lesson Focus

* Camera = **player’s perception layer**
* Goal: design + implement camera behavior aligned with gameplay
* Combines:

  * Design thinking (feel, clarity)
  * Technical execution (scripting, transforms)

---

### 2. Lesson Objectives

* Compare camera types and control techniques
* Choose suitable camera setup for the game
* Implement camera behaviors via scripting

---

### 3. Documentation Access (Workflow Tool)

* Sources:

  * Official website → Learn tab
  * Script editor:

    * **Online Docs**
    * **Search Help**
  * Shortcut:

    * `Ctrl + Click` on function/class

**Use case**

* Fast lookup of functions (e.g., input, camera)

---

### 4. Improved Player Script (From Previous Lesson)

#### Structural Change

* Input logic moved to:

  * `handle_input()` function

* Benefits:

  * Cleaner structure
  * Reusable logic

#### New Additions

* Constants:

  * `GRAV = 9.8`
  * `JUMP = 5`

* Features:

  * Prevent opposite inputs (left + right → no movement)
  * Run (Shift modifier)
  * Jump (Space key)
  * Manual gravity (for KinematicBody)

---

### 5. Input Handling Logic Structure

* Split into 2 axes:

  * X-axis → left/right
  * Z-axis → forward/backward

**Key Logic Pattern**

* Check conflicting inputs first
* Then specific inputs
* Use nested conditions for modifiers (e.g., Shift → run)

---

### 6. Emergent Behavior

* Diagonal movement occurs naturally:

  * Combining X + Z movement

* Not explicitly programmed

* Result of system design

---

### 7. Camera Fundamentals

* Camera defines:

  * What player sees
  * How gameplay feels

* Influenced by:

  * Film & photography principles (composition, framing)

---

### 8. Camera Types

#### Perspective Camera

* Default for 3D games

* Provides depth perception (via view frustum)

* Used in:

  * First-person
  * Third-person

---

#### Orthographic Camera

* No depth scaling

* Best for:

  * 2D games
  * Precision alignment tasks

* Objects retain size regardless of distance

---

#### Isometric Camera

* Angled top-down (~30° up, 45° side)

* Shows multiple sides simultaneously

* Used in:

  * Strategy / simulation games

* Hard to configure correctly

---

### 9. Camera Perspectives

#### First Person

* Camera = player’s eyes

* Pros:

  * High immersion

* Cons:

  * Limited awareness (no rear view)

---

#### Third Person

* Camera follows player externally

* Pros:

  * Better spatial awareness
  * Shows character animations

* Cons:

  * Camera collision complexity
  * Less immersion

---

### 10. Camera Models

#### Static Camera

* Fixed position

* Pros:

  * Stable view
  * Simpler implementation

* Cons:

  * Limited perspective
  * Requires multiple cameras

---

#### Dynamic Camera

* Moves with player

* Pros:

  * High engagement
  * Flexible viewing

* Cons:

  * Complex to implement
  * Requires collision handling

---

### 11. Camera Behaviors

#### Follow Camera

* Tracks player movement

* Key factors:

  * Player speed
  * Environment complexity
  * Smoothness vs responsiveness

---

#### Orbit Camera

* Rotates around player

* Requires:

  * Player as center reference
  * Relative positioning

* Complexity:

  * Collision handling
  * Maintaining visibility

---

#### Zoom Behavior

* Adjusts camera distance

* Needs:

  * Collision awareness
  * Restore original position after obstruction

---

### 12. Chosen Setup (For This Game)

* Third-person

* Dynamic camera

* Behaviors:

  * Follow (primary)
  * Orbit (basic)
  * Zoom (manual)

**Reason**

* Matches platformer gameplay (movement + visibility)

---

### 13. Follow Camera Implementation (Key Insight)

* No scripting needed

* Method:

  * Make camera a **child of player node**

**Effect**

* Camera inherits:

  * Position
  * Rotation

* Automatically follows player

---

### 14. Camera Positioning

* Offset from player:

  * Y (height): ~5
  * Z (distance): ~10

* Rotation:

  * Tilt down (~ -15° on X)

---

### 15. Orbit Implementation

#### Structure

* Add intermediate node (Spatial)

  * Player → Spatial → Camera

#### Logic

* Rotate Spatial node:

  * Q → rotate left
  * E → rotate right

**Key Concept**

* `$NodeName` = reference shortcut

**Rotation**

* Use radians (`deg2rad()`)

---

### 16. Zoom Implementation

#### Input Mapping

* Mouse wheel:

  * Scroll up
  * Scroll down

#### Logic

* Move camera:

  * Forward/backward (Z)
  * Slight vertical adjustment (Y)

**Important**

* Simplified version (no collision handling)

---

### 17. Global vs Local Coordinates

* **Global**

  * Relative to entire scene

* **Local**

  * Relative to parent node

**Implication**

* Current movement uses global axes:

  * Independent of camera direction

---

### 18. Current Limitation

* Player movement:

  * Not camera-relative

* Result:

  * “Forward” doesn’t change with camera angle

---

### 19. Key Design Trade-offs

* Simplicity vs realism
* Control vs automation
* Stability vs immersion

---

### 20. What to Remember (Core Layer)

* Camera is not visual only → it affects gameplay

* Parenting = powerful shortcut for follow behavior

* Separate logic:

  * Input handling
  * Movement
  * Camera control

* Always handle:

  * Edge cases (collisions, clipping)

* Keep early systems simple → complexity grows fast

---

### 21. What Matters Going Forward

* Understand:

  * Transform hierarchy (parent-child)
  * Coordinate systems

* Be able to:

  * Add/remove camera behaviors safely
  * Debug movement vs camera inconsistencies

* Awareness:

  * Camera design = both technical + psychological

---
