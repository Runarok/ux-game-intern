# 1. Lesson Focus

* Complete unfinished AI behaviors

* Introduce:

  * **Menus (UI navigation)**
  * **Scoring systems (player feedback + motivation)**

---

# 2. Completing Agent Behaviors

## 2.1 Collision Design

* Separate collision logic:

  * **Player hitbox (body)**
  * **Agent head (top area)**

Purpose:

* Differentiate:

  * player hits agent → agent dies
  * agent hits player → player punished

---

## 2.2 Player → Agent Interaction

* Condition:

  * collision with agent head

* Result:

  * destroy agent

---

## 2.3 Agent → Player Interaction

* Condition:

  * collision with player hitbox

* Result:

  * reset player position
  * reset rotation

---

## 2.4 Respawn System

* Add:

  * respawn point node

* Logic:

  * reposition player to respawn coordinates

---

## 2.5 Common Failure Points

* Incorrect node paths

* Missing parent references (`..`)

* Naming mismatches

* Fix via:

  * print debugging
  * signal validation

---

# 3. Scene Consistency Issue

* After editing scenes:

  * must **re-instantiate nodes**

* Avoid:

  * “make local” misuse

* Ensure:

  * exported variables match script defaults

---

# 4. Menu System (Core UI)

## 4.1 Purpose

* Navigation between:

  * game
  * retry
  * exit

* Improves:

  * usability
  * structure

---

## 4.2 Main Menu Structure

* Root:

  * `Control node`

* Elements:

  * background (sprite)
  * title (label)
  * buttons:

    * play
    * exit

---

## 4.3 UI Design Details

* Fonts:

  * use TTFOTF
  * respect licensing

* Styling:

  * hover state
  * pressed state
  * normal state

* Polish:

  * filtering (anti-aliasing)

---

## 4.4 Button Logic

* Play button:

  * change scene → main game

* Exit button:

  * quit game

---

# 5. Game Over Menu

## 5.1 Structure

* Title label

* Buttons:

  * retry
  * leave game

---

## 5.2 Logic

* Retry:

  * reload main game

* Leave:

  * return to menu exit

---

## 5.3 Integration

* On player death:

  * switch to game over scene
  * enable mouse visibility

---

# 6. Score Systems — Why They Matter

## 6.1 Core Role

* Feedback:

  * performance clarity

* Motivation:

  * progression
  * competition

---

## 6.2 Player Psychology (Bartle Types)

* **Achievers**

  * chase high scores, completion

* **Explorers**

  * gain advantage through knowledge

* **Socializers**

  * align with group goals

* **Killers**

  * dominate via ranking

👉 Score systems engage all types differently but consistently.

---

# 7. Types of Scoring Systems

## 7.1 Time-Based

* Measure:

  * time taken or remaining

* Complexity:

  * higher (custom timer logic)

---

## 7.2 Point-Based (Chosen)

* Reward:

  * actions (kills, progress)

* Advantages:

  * simple
  * flexible
  * easy to scale

---

## 7.3 Bonus-Oriented

* Optional objectives:

  * collectibles
  * side tasks

* Usually:

  * layered on top of main system

---

# 8. Choosing the Right System

* Decision factors:

  * implementation complexity
  * engine support
  * gameplay fit

→ For this project:

* **Point-based is optimal**

---

# 9. Designing Point Logic

## 9.1 Sources of Points

* Enemy defeat
* Progress milestones
* (optional) collectibles

---

## 9.2 Design Constraints

* Avoid:

  * exploit loops

* Maintain:

  * balance across playstyles

---

## 9.3 Negative Scoring

* Generally discouraged:

  * reduces player motivation

* If used:

  * must be clearly communicated

---

# 10. Linking Score to Gameplay

## Approach

* Attach score system:

  * as child of player

## Benefit

* Easier communication:

  * direct updates
  * fewer dependencies

---

# 11. Win Loss Conditions

## Loss

* agent collision
* falling off map
* failure states

---

## Win

* reaching final platform

---

# 12. Implementation Strategy

## Key Idea

* Update score:

  * at the same point where events occur
  * (e.g., when enemy is destroyed)

---

# 13. System Design Tradeoffs

* Time-based:

  * more expressive
  * more complex

* Point-based:

  * less expressive
  * more practical

---

# 14. UI + Systems Integration

* Menus:

  * control flow

* Score:

  * feedback loop

* Together:

  * define player experience structure

---

# 15. What to Remember

* Separate collision logic → enables clean behavior design
* Signals are core to interaction flow
* Scene consistency matters after edits
* UI is not optional — it defines usability
* Score systems are psychological tools, not just numbers
* Simpler systems scale better early
* Avoid punishing players unless intentional
* Always tie scoring to meaningful actions
* Update score where the event happens
* Keep systems close to where they’re used (player-centric design)
* Debugging is part of system design, not an afterthought

---
