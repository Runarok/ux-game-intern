# 1. Purpose of AI in Games



* Automates behaviors in the game world

* Creates:



&#x20; * believable characters

&#x20; * dynamic gameplay

* Goal:



&#x20; * **immersion through controlled behavior**



---



# 2. Cost of AI



* High complexity:



&#x20; * subtle behavior details matter

* Poor tuning → breaks immersion immediately

* Tradeoff:



&#x20; * realism vs effort vs control



---



# 3. Academic AI vs Game AI



## 3.1 Academic AI



* Goal:



&#x20; * optimal, correct solutions

* Characteristics:



&#x20; * perfect memory

&#x20; * maximum efficiency

&#x20; * full information usage



---



## 3.2 Game AI



* Goal:



&#x20; * engaging experience, not correctness

* Characteristics:



&#x20; * intentionally limited

&#x20; * imperfect

&#x20; * controlled behavior



---



## 3.3 Key Insight



* Game AI is **designed illusion**, not intelligence



---



# 4. Core Requirements of Game AI



## 4.1 Balanced Cleverness



* Must be:



&#x20; * challenging enough

&#x20; * beatable

* Balance axes:



&#x20; * smart ↔ dumb

&#x20; * fast ↔ slow decision-making



---



## 4.2 Balanced Awareness



Components:



1. Detection (vision, hearing)

2. Spatial awareness

3. Memory



* Too high:



&#x20; * feels unfair

* Too low:



&#x20; * feels useless



---



## 4.3 Balanced Communication



* Applies to multiple agents

* Must avoid:



&#x20; * unrealistic coordination (e.g. telepathy)

* Should:



&#x20; * inform player indirectly



Examples:



* sound cues

* visual signals

* dialogue (“barks”)



---



# 5. Awareness Design Techniques



## 5.1 Detection



* Use:



&#x20; * line of sight

&#x20; * limited hearing



---



## 5.2 Spatial Awareness



* Local knowledge > global knowledge

* Forces:



&#x20; * exploration

&#x20; * uncertainty



---



## 5.3 Memory



* Controlled forgetting:



&#x20; * memory radius

&#x20; * decay over time



---



# 6. Key Design Principle



* AI should:



&#x20; * simulate intelligence

&#x20; * not achieve perfection



---



# 7. Why Academic AI Fails in Games



* Too optimal:



&#x20; * perfect pathfinding

&#x20; * full map awareness

* Breaks:



&#x20; * fairness

&#x20; * player agency



---



# 8. Use of Academic AI in Games



* Possible but:



&#x20; * requires modification

&#x20; * high effort

* Usually replaced by:



&#x20; * simpler approximations (“cheap hacks”)



---



# 9. Types of AI



## 9.1 Good Old-Fashioned AI (GOFAI)



* Symbol-based logic

* Examples:



&#x20; * Finite State Machines (FSM)

&#x20; * Minimax

&#x20; * Rule-based systems



---



## 9.2 New AI



* Emergent behavior from simple rules

* Examples:



&#x20; * Neural networks

&#x20; * Reinforcement learning

&#x20; * Evolutionary algorithms



---



# 10. Game AI Categories



## 10.1 Agent-Based AI



* Individual entities:



&#x20; * enemies

&#x20; * NPCs

* Behavior-driven



---



## 10.2 System-Based AI



* Controls game environment

* Adjusts:



&#x20; * difficulty

&#x20; * pacing

&#x20; * resources



Example:



* dynamic enemy spawning

* adaptive difficulty systems



---



# 11. Choosing AI for Your Game



## 11.1 Start with Design



* Ask:



&#x20; * what needs automation?



---



## 11.2 Evaluate Each Task



* Does AI help?

* Is it worth the effort?



---



## 11.3 Avoid Overbuilding



* Start minimal

* Expand only if needed



---



# 12. Practical AI Scope (For This Project)



Agent behaviors:



1. Damage player on collision

2. Take damage from player

3. Patrol between points

4. (Optional) Chase player



---



# 13. Chosen Approach: Finite State Machine (FSM)



## 13.1 Concept



* States = behaviors

* Transitions = conditions



---



## 13.2 Example States



* Patrol

* Chase

* Hurt



---



## 13.3 Why FSM



* Simple

* controllable

* sufficient for small systems



---



# 14. Limits of FSM



* Cannot:



&#x20; * learn from experience

* Becomes:



&#x20; * complex quickly with scale



---



# 15. Implementation Strategy



## 15.1 Movement System



* Use:



&#x20; * velocity + direction (heading)



---



## 15.2 Patrol Logic



* Waypoints:



&#x20; * move between points

* Loop behavior



---



## 15.3 Collision Handling



* Detect collisions

* Apply:



&#x20; * damage

&#x20; * destruction logic



---



## 15.4 Chase Logic (Advanced)



* Detection zone

* Move toward player

* Return to patrol when lost



---



# 16. Optimization Mindset



* Optimize:



&#x20; * implementation effort

* Not:



&#x20; * theoretical correctness



Use:



* engine features (signals, nodes)

* simple logic over complex systems



---



# 17. Debugging Strategy



## 17.1 Use Print Statements



Track:



* state transitions

* target selection

* velocity values



---



## 17.2 Validate Behavior



* Compare:



&#x20; * expected vs actual movement



---



## 17.3 Key Checks



* Correct waypoint targeting

* Proper order of logic execution



---



# 18. Development Discipline



* Plan before coding

* Define behaviors clearly

* Avoid impulsive implementation



---



# 19. Core Design Philosophy



* AI is:



&#x20; * controlled imperfection

* Good AI:



&#x20; * feels human

&#x20; * not optimal



---



# 20. What to Always Remember



* AI exists to enhance gameplay, not solve problems perfectly

* Balance is more important than intelligence

* Awareness must be limited intentionally

* Simplicity scales better than complexity

* FSM is enough for most early systems

* Don’t over-engineer early

* Use engine tools instead of reinventing systems

* Debug through observation, not assumption

* Plan logic before implementation

* Player perception matters more than system accuracy



---





