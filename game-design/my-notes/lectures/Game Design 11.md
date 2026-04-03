### 1. Lesson Focus



* Camera = **player’s perception layer**

* Goal: design + implement camera behavior aligned with gameplay

* Combines:



&#x20; * Design thinking (feel, clarity)

&#x20; * Technical execution (scripting, transforms)



---



### 2. Lesson Objectives



* Compare camera types and control techniques

* Choose suitable camera setup for the game

* Implement camera behaviors via scripting



---



### 3. Documentation Access (Workflow Tool)



* Sources:



&#x20; * Official website → Learn tab

&#x20; * Script editor:



&#x20;   * **Online Docs**

&#x20;   * **Search Help**

&#x20; * Shortcut:



&#x20;   * `Ctrl + Click` on functionclass



**Use case**



* Fast lookup of functions (e.g., input, camera)



---



### 4. Improved Player Script (From Previous Lesson)



#### Structural Change



* Input logic moved to:



&#x20; * `handle_input()` function

* Benefits:



&#x20; * Cleaner structure

&#x20; * Reusable logic



#### New Additions



* Constants:



&#x20; * `GRAV = 9.8`

&#x20; * `JUMP = 5`

* Features:



&#x20; * Prevent opposite inputs (left + right → no movement)

&#x20; * Run (Shift modifier)

&#x20; * Jump (Space key)

&#x20; * Manual gravity (for KinematicBody)



---



### 5. Input Handling Logic Structure



* Split into 2 axes:



&#x20; * X-axis → leftright

&#x20; * Z-axis → forwardbackward



**Key Logic Pattern**



* Check conflicting inputs first

* Then specific inputs

* Use nested conditions for modifiers (e.g., Shift → run)



---



### 6. Emergent Behavior



* Diagonal movement occurs naturally:



&#x20; * Combining X + Z movement

* Not explicitly programmed

* Result of system design



---



### 7. Camera Fundamentals



* Camera defines:



&#x20; * What player sees

&#x20; * How gameplay feels

* Influenced by:



&#x20; * Film & photography principles (composition, framing)



---



### 8. Camera Types



#### Perspective Camera



* Default for 3D games

* Provides depth perception (via view frustum)

* Used in:



&#x20; * First-person

&#x20; * Third-person



#### Orthographic Camera



* No depth scaling

* Best for:



&#x20; * 2D games

&#x20; * Precision alignment tasks

* Objects retain size regardless of distance



#### Isometric Camera



* Angled top-down (~30° up, 45° side)

* Shows multiple sides simultaneously

* Used in:



&#x20; * Strategy  simulation games

* Hard to configure correctly



---



### 9. Camera Perspectives



#### First Person



* Camera = player’s eyes

* Pros:



&#x20; * High immersion

* Cons:



&#x20; * Limited awareness (no rear view)



#### Third Person



* Camera follows player externally

* Pros:



&#x20; * Better spatial awareness

&#x20; * Shows character animations

* Cons:



&#x20; * Camera collision complexity

&#x20; * Less immersion



---



### 10. Camera Models



#### Static Camera



* Fixed position

* Pros:



&#x20; * Stable view

&#x20; * Simpler implementation

* Cons:



&#x20; * Limited perspective

&#x20; * Requires multiple cameras



#### Dynamic Camera



* Moves with player

* Pros:



&#x20; * High engagement

&#x20; * Flexible viewing

* Cons:



&#x20; * Complex to implement

&#x20; * Requires collision handling



---



### 11. Camera Behaviors



#### Follow Camera



* Tracks player movement

* Key factors:



&#x20; * Player speed

&#x20; * Environment complexity

&#x20; * Smoothness vs responsiveness



#### Orbit Camera



* Rotates around player

* Requires:



&#x20; * Player as center reference

&#x20; * Relative positioning

* Complexity:



&#x20; * Collision handling

&#x20; * Maintaining visibility



#### Zoom Behavior



* Adjusts camera distance

* Needs:



&#x20; * Collision awareness

&#x20; * Restore original position after obstruction



---



### 12. Chosen Setup (For This Game)



* Third-person

* Dynamic camera

* Behaviors:



&#x20; * Follow (primary)

&#x20; * Orbit (basic)

&#x20; * Zoom (manual)



**Reason**



* Matches platformer gameplay (movement + visibility)



---



### 13. Follow Camera Implementation (Key Insight)



* No scripting needed

* Method:



&#x20; * Make camera a **child of player node**



**Effect**



* Camera inherits:



&#x20; * Position

&#x20; * Rotation

* Automatically follows player



---



### 14. Camera Positioning



* Offset from player:



&#x20; * Y (height): ~5

&#x20; * Z (distance): ~10

* Rotation:



&#x20; * Tilt down (~ -15° on X)



---



### 15. Orbit Implementation



#### Structure



* Add intermediate node (Spatial)



&#x20; * Player → Spatial → Camera



#### Logic



* Rotate Spatial node:



&#x20; * Q → rotate left

&#x20; * E → rotate right



**Key Concept**



* `$NodeName` = reference shortcut



**Rotation**



* Use radians (`deg2rad()`)



---



### 16. Zoom Implementation



#### Input Mapping



* Mouse wheel:



&#x20; * Scroll up

&#x20; * Scroll down



#### Logic



* Move camera:



&#x20; * Forwardbackward (Z)

&#x20; * Slight vertical adjustment (Y)



**Important**



* Simplified version (no collision handling)



---



### 17. Global vs Local Coordinates



* **Global**



&#x20; * Relative to entire scene

* **Local**



&#x20; * Relative to parent node



**Implication**



* Current movement uses global axes:



&#x20; * Independent of camera direction



---



### 18. Current Limitation



* Player movement:



&#x20; * Not camera-relative

* Result:



&#x20; * “Forward” doesn’t change with camera angle



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



&#x20; * Input handling

&#x20; * Movement

&#x20; * Camera control

* Always handle:



&#x20; * Edge cases (collisions, clipping)

* Keep early systems simple → complexity grows fast



---



### 21. What Matters Going Forward



* Understand:



&#x20; * Transform hierarchy (parent-child)

&#x20; * Coordinate systems

* Be able to:



&#x20; * Addremove camera behaviors safely

&#x20; * Debug movement vs camera inconsistencies

* Awareness:



&#x20; * Camera design = both technical + psychological



---





