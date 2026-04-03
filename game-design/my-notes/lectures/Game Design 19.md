# 1. Lesson Focus



* Complete unfinished AI behaviors

* Introduce:



&#x20; * **Menus (UI navigation)**

&#x20; * **Scoring systems (player feedback + motivation)**



---



# 2. Completing Agent Behaviors



## 2.1 Collision Design



* Separate collision logic:



&#x20; * **Player hitbox (body)**

&#x20; * **Agent head (top area)**



Purpose:



* Differentiate:



&#x20; * player hits agent → agent dies

&#x20; * agent hits player → player punished



---



## 2.2 Player → Agent Interaction



* Condition:



&#x20; * collision with agent head

* Result:



&#x20; * destroy agent



---



## 2.3 Agent → Player Interaction



* Condition:



&#x20; * collision with player hitbox

* Result:



&#x20; * reset player position

&#x20; * reset rotation



---



## 2.4 Respawn System



* Add:



&#x20; * respawn point node

* Logic:



&#x20; * reposition player to respawn coordinates



---



## 2.5 Common Failure Points



* Incorrect node paths

* Missing parent references (`..`)

* Naming mismatches

* Fix via:



&#x20; * print debugging

&#x20; * signal validation



---



# 3. Scene Consistency Issue



* After editing scenes:



&#x20; * must **re-instantiate nodes**

* Avoid:



&#x20; * “make local” misuse

* Ensure:



&#x20; * exported variables match script defaults



---



# 4. Menu System (Core UI)



## 4.1 Purpose



* Navigation between:



&#x20; * game

&#x20; * retry

&#x20; * exit

* Improves:



&#x20; * usability

&#x20; * structure



---



## 4.2 Main Menu Structure



* Root:



&#x20; * `Control node`

* Elements:



&#x20; * background (sprite)

&#x20; * title (label)

&#x20; * buttons:



&#x20;   * play

&#x20;   * exit



---



## 4.3 UI Design Details



* Fonts:



&#x20; * use TTFOTF

&#x20; * respect licensing

* Styling:



&#x20; * hover state

&#x20; * pressed state

&#x20; * normal state

* Polish:



&#x20; * filtering (anti-aliasing)



---



## 4.4 Button Logic



* Play button:



&#x20; * change scene → main game

* Exit button:



&#x20; * quit game



---



# 5. Game Over Menu



## 5.1 Structure



* Title label

* Buttons:



&#x20; * retry

&#x20; * leave game



---



## 5.2 Logic



* Retry:



&#x20; * reload main game

* Leave:



&#x20; * return to menu  exit



---



## 5.3 Integration



* On player death:



&#x20; * switch to game over scene

&#x20; * enable mouse visibility



---



# 6. Score Systems — Why They Matter



## 6.1 Core Role



* Feedback:



&#x20; * performance clarity

* Motivation:



&#x20; * progression

&#x20; * competition



---



## 6.2 Player Psychology (Bartle Types)



* **Achievers**



&#x20; * chase high scores, completion



* **Explorers**



&#x20; * gain advantage through knowledge



* **Socializers**



&#x20; * align with group goals



* **Killers**



&#x20; * dominate via ranking



👉 Score systems engage all types differently but consistently.



---



# 7. Types of Scoring Systems



## 7.1 Time-Based



* Measure:



&#x20; * time taken or remaining

* Complexity:



&#x20; * higher (custom timer logic)



---



## 7.2 Point-Based (Chosen)



* Reward:



&#x20; * actions (kills, progress)

* Advantages:



&#x20; * simple

&#x20; * flexible

&#x20; * easy to scale



---



## 7.3 Bonus-Oriented



* Optional objectives:



&#x20; * collectibles

&#x20; * side tasks

* Usually:



&#x20; * layered on top of main system



---



# 8. Choosing the Right System



* Decision factors:



&#x20; * implementation complexity

&#x20; * engine support

&#x20; * gameplay fit



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



&#x20; * exploit loops

* Maintain:



&#x20; * balance across playstyles



---



## 9.3 Negative Scoring



* Generally discouraged:



&#x20; * reduces player motivation

* If used:



&#x20; * must be clearly communicated



---



# 10. Linking Score to Gameplay



## Approach



* Attach score system:



&#x20; * as child of player



## Benefit



* Easier communication:



&#x20; * direct updates

&#x20; * fewer dependencies



---



# 11. Win  Loss Conditions



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



&#x20; * at the same point where events occur

&#x20; * (e.g., when enemy is destroyed)



---



# 13. System Design Tradeoffs



* Time-based:



&#x20; * more expressive

&#x20; * more complex



* Point-based:



&#x20; * less expressive

&#x20; * more practical



---



# 14. UI + Systems Integration



* Menus:



&#x20; * control flow

* Score:



&#x20; * feedback loop

* Together:



&#x20; * define player experience structure



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





