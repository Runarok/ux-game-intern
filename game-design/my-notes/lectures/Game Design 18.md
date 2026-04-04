# 1. Development Priority Shift

* First phase complete:

  * **Minimum Viable Game (MVG)**

* Next phase:

  * shift from **function → form**

    * visuals
    * theme
    * narrative

---

# 2. Why MVG Comes First

* Ensures:

  * core mechanics work
  * game is playable

* Prevents:

  * wasted effort on aesthetics before validation

* Foundation:

  * everything else builds on stable mechanics

---

# 3. Score System Implementation

## 3.1 UI Setup

* Add:

  * `Control node` → score manager
  * `Label node` → score display

* Position:

  * top of screen (non-intrusive)

---

## 3.2 Core Logic

* Variable:

  * `player_score = 0`

* Update triggers:

  * enemy defeated → +100
  * reaching goal → +200

---

## 3.3 Display Update

* Convert score to string before rendering
* Update label dynamically during runtime

---

## 3.4 Edge Case

* Repeated scoring exploit:

  * fix using:

    * boolean flag
    * or scene transition immediately

---

# 4. Win Condition System

* Add:

  * `Area node` (win box) on final platform

* Detect:

  * player entry

* Actions:

  * award points
  * trigger win state

---

# 5. Leaderboard System Design

## 5.1 Data Handling

* Store:

  * username + score

* Use:

  * file system (persistent storage)
  * dictionary array for processing

---

## 5.2 Workflow

1. Opencreate score file
2. Append new score
3. Read all entries
4. Sort descending
5. Display top scores
6. Rewrite file (keep top N only, e.g. 10)

---

## 5.3 Persistence

* Use:

  * **autoload (singleton)**

* Purpose:

  * share data across scenes

---

## 5.4 Input Handling

* Capture username via:

  * `LineEdit node`

* Validate:

  * prevent empty submissions

* Use:

  * boolean flag (`text_changed`)

---

# 6. UI Flow Structure

* Game Over Scene:

  * input username
  * submit → save score

* Navigation:

  * leaderboard button
  * return to main menu

---

# 7. Genre vs Theme

## 7.1 Genre

* Defines:

  * gameplay structure
  * mechanics
  * player interaction

Examples:

* platformer, RTS, puzzle

---

## 7.2 Theme

* Defines:

  * setting
  * visual coherence
  * narrative tone

---

## 7.3 Relationship

* Genre:

  * mechanical classification

* Theme:

  * aesthetic + conceptual layer

* Independent but overlapping

---

# 8. Theme Design Principle

* Theme must:

  * **emerge from mechanics**

* Not:

  * imposed arbitrarily

---

# 9. Mechanics → Theme Mapping

## Current Mechanics

* move (walkrun)
* jump
* avoid defeat enemy
* reach goal

---

## Interpretation

* Supports:

  * humanoid or robotic entities

* Enemy:

  * patrolling obstacle

* Example fit:

  * robotic sci-fi environment

---

# 10. Narrative Design

## 10.1 Types of Narrative

1. Text-based

   * direct indirect

2. Cutscenes

3. Dialogue

4. Voice-over

5. Emergent gameplay narrative

---

## 10.2 Most Relevant Here

* Emergent narrative:

  * story through player actions

* Supported by:

  * theme
  * assets
  * feedback

---

# 11. Narrative Through Mechanics

* Meaning comes from:

  * player interpretation

* Examples:

  * jumping → skill
  * near miss → tension

* No explicit story needed if:

  * mechanics + theme align

---

# 12. Theme Exploration Examples

## 12.1 Valid Theme

* Robot training simulation:

  * player = robot
  * enemies = obstacles
  * goal = training objective

---

## 12.2 Alternative Theme

* Cat vs robot vacuum

* Shows:

  * same mechanics → different interpretation

---

## 12.3 Rejection Criteria

* If assets don’t logically align with mechanics
* If narrative feels disconnected

---

# 13. Post-Theme Design Updates

## 13.1 Game Design Document

* Update:

  * theme
  * narrative
  * visual direction

---

## 13.2 Mood Board

* Define:

  * colors
  * textures
  * atmosphere

---

## 13.3 Storyboard

* Decide:

  * level-based vs endless

* Based on:

  * narrative logic

---

# 14. Technical Design Documentation

* Record:

  * mechanics
  * AI behavior
  * UI systems

* Maintain:

  * chronological updates

---

# 15. Risk Analysis (New Layer)

* Asset compatibility
* Theme consistency
* Narrative clarity
* Engine limitations

---

# 16. Scaling Considerations

* Single level → expand to:

  * multiple levels
  * or endless mode

* Based on:

  * gameplay loop

---

# 17. Development Discipline

* Do not:

  * modify mechanics during theming

* Only change:

  * assets
  * visuals
  * presentation

---

# 18. Key Design Constraint

* Mechanics are fixed
* Everything else adapts around them

---

# 19. What to Always Remember

* Finish functionality before aesthetics
* Theme must justify mechanics, not contradict them
* Narrative can be implicit through gameplay
* Keep systems simple before scaling
* Validate input and edge cases early
* Persistent systems (like leaderboard) need structure, not hacks
* Documentation saves time later
* Every new layer (theme, UI, narrative) introduces new risks
* Avoid changing core mechanics after MVG
* Design decisions should reduce future complexity, not increase it

---
