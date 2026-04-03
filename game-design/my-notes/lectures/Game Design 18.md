# 1. Development Priority Shift



* First phase complete:



&#x20; * **Minimum Viable Game (MVG)**

* Next phase:



&#x20; * shift from **function → form**



&#x20;   * visuals

&#x20;   * theme

&#x20;   * narrative



---



# 2. Why MVG Comes First



* Ensures:



&#x20; * core mechanics work

&#x20; * game is playable

* Prevents:



&#x20; * wasted effort on aesthetics before validation

* Foundation:



&#x20; * everything else builds on stable mechanics



---



# 3. Score System Implementation



## 3.1 UI Setup



* Add:



&#x20; * `Control node` → score manager

&#x20; * `Label node` → score display

* Position:



&#x20; * top of screen (non-intrusive)



---



## 3.2 Core Logic



* Variable:



&#x20; * `player_score = 0`

* Update triggers:



&#x20; * enemy defeated → +100

&#x20; * reaching goal → +200



---



## 3.3 Display Update



* Convert score to string before rendering

* Update label dynamically during runtime



---



## 3.4 Edge Case



* Repeated scoring exploit:



&#x20; * fix using:



&#x20;   * boolean flag

&#x20;   * or scene transition immediately



---



# 4. Win Condition System



* Add:



&#x20; * `Area node` (win box) on final platform

* Detect:



&#x20; * player entry

* Actions:



&#x20; * award points

&#x20; * trigger win state



---



# 5. Leaderboard System Design



## 5.1 Data Handling



* Store:



&#x20; * username + score

* Use:



&#x20; * file system (persistent storage)

&#x20; * dictionary  array for processing



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



&#x20; * **autoload (singleton)**

* Purpose:



&#x20; * share data across scenes



---



## 5.4 Input Handling



* Capture username via:



&#x20; * `LineEdit node`

* Validate:



&#x20; * prevent empty submissions

* Use:



&#x20; * boolean flag (`text_changed`)



---



# 6. UI Flow Structure



* Game Over Scene:



&#x20; * input username

&#x20; * submit → save score

* Navigation:



&#x20; * leaderboard button

&#x20; * return to main menu



---



# 7. Genre vs Theme



## 7.1 Genre



* Defines:



&#x20; * gameplay structure

&#x20; * mechanics

&#x20; * player interaction



Examples:



* platformer, RTS, puzzle



---



## 7.2 Theme



* Defines:



&#x20; * setting

&#x20; * visual coherence

&#x20; * narrative tone



---



## 7.3 Relationship



* Genre:



&#x20; * mechanical classification

* Theme:



&#x20; * aesthetic + conceptual layer

* Independent but overlapping



---



# 8. Theme Design Principle



* Theme must:



&#x20; * **emerge from mechanics**

* Not:



&#x20; * imposed arbitrarily



---



# 9. Mechanics → Theme Mapping



## Current Mechanics



* move (walkrun)

* jump

* avoid  defeat enemy

* reach goal



---



## Interpretation



* Supports:



&#x20; * humanoid or robotic entities

* Enemy:



&#x20; * patrolling obstacle

* Example fit:



&#x20; * robotic  sci-fi environment



---



# 10. Narrative Design



## 10.1 Types of Narrative



1. Text-based



&#x20;  * direct  indirect

2. Cutscenes

3. Dialogue

4. Voice-over

5. Emergent gameplay narrative



---



## 10.2 Most Relevant Here



* Emergent narrative:



&#x20; * story through player actions

* Supported by:



&#x20; * theme

&#x20; * assets

&#x20; * feedback



---



# 11. Narrative Through Mechanics



* Meaning comes from:



&#x20; * player interpretation

* Examples:



&#x20; * jumping → skill

&#x20; * near miss → tension

* No explicit story needed if:



&#x20; * mechanics + theme align



---



# 12. Theme Exploration Examples



## 12.1 Valid Theme



* Robot training simulation:



&#x20; * player = robot

&#x20; * enemies = obstacles

&#x20; * goal = training objective



---



## 12.2 Alternative Theme



* Cat vs robot vacuum

* Shows:



&#x20; * same mechanics → different interpretation



---



## 12.3 Rejection Criteria



* If assets don’t logically align with mechanics

* If narrative feels disconnected



---



# 13. Post-Theme Design Updates



## 13.1 Game Design Document



* Update:



&#x20; * theme

&#x20; * narrative

&#x20; * visual direction



---



## 13.2 Mood Board



* Define:



&#x20; * colors

&#x20; * textures

&#x20; * atmosphere



---



## 13.3 Storyboard



* Decide:



&#x20; * level-based vs endless

* Based on:



&#x20; * narrative logic



---



# 14. Technical Design Documentation



* Record:



&#x20; * mechanics

&#x20; * AI behavior

&#x20; * UI systems

* Maintain:



&#x20; * chronological updates



---



# 15. Risk Analysis (New Layer)



* Asset compatibility

* Theme consistency

* Narrative clarity

* Engine limitations



---



# 16. Scaling Considerations



* Single level → expand to:



&#x20; * multiple levels

&#x20; * or endless mode

* Based on:



&#x20; * gameplay loop



---



# 17. Development Discipline



* Do not:



&#x20; * modify mechanics during theming

* Only change:



&#x20; * assets

&#x20; * visuals

&#x20; * presentation



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





