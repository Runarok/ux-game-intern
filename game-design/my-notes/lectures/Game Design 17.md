# 1. Purpose of AI in Games

* Automates behaviors in the game world

* Creates:

  * believable characters
  * dynamic gameplay

* Goal:

  * **immersion through controlled behavior**

---

# 2. Cost of AI

* High complexity:

  * subtle behavior details matter

* Poor tuning → breaks immersion immediately

* Tradeoff:

  * realism vs effort vs control

---

# 3. Academic AI vs Game AI

## 3.1 Academic AI

* Goal:

  * optimal, correct solutions

* Characteristics:

  * perfect memory
  * maximum efficiency
  * full information usage

---

## 3.2 Game AI

* Goal:

  * engaging experience, not correctness

* Characteristics:

  * intentionally limited
  * imperfect
  * controlled behavior

---

## 3.3 Key Insight

* Game AI is **designed illusion**, not intelligence

---

# 4. Core Requirements of Game AI

## 4.1 Balanced Cleverness

* Must be:

  * challenging enough
  * beatable

* Balance axes:

  * smart ↔ dumb
  * fast ↔ slow decision-making

---

## 4.2 Balanced Awareness

Components:

1. Detection (vision, hearing)
2. Spatial awareness
3. Memory

* Too high:

  * feels unfair

* Too low:

  * feels useless

---

## 4.3 Balanced Communication

* Applies to multiple agents

* Must avoid:

  * unrealistic coordination (e.g. telepathy)

* Should:

  * inform player indirectly

Examples:

* sound cues
* visual signals
* dialogue (“barks”)

---

# 5. Awareness Design Techniques

## 5.1 Detection

* Use:

  * line of sight
  * limited hearing

---

## 5.2 Spatial Awareness

* Local knowledge > global knowledge

* Forces:

  * exploration
  * uncertainty

---

## 5.3 Memory

* Controlled forgetting:

  * memory radius
  * decay over time

---

# 6. Key Design Principle

* AI should:

  * simulate intelligence
  * not achieve perfection

---

# 7. Why Academic AI Fails in Games

* Too optimal:

  * perfect pathfinding
  * full map awareness

* Breaks:

  * fairness
  * player agency

---

# 8. Use of Academic AI in Games

* Possible but:

  * requires modification
  * high effort

* Usually replaced by:

  * simpler approximations (“cheap hacks”)

---

# 9. Types of AI

## 9.1 Good Old-Fashioned AI (GOFAI)

* Symbol-based logic

* Examples:

  * Finite State Machines (FSM)
  * Minimax
  * Rule-based systems

---

## 9.2 New AI

* Emergent behavior from simple rules

* Examples:

  * Neural networks
  * Reinforcement learning
  * Evolutionary algorithms

---

# 10. Game AI Categories

## 10.1 Agent-Based AI

* Individual entities:

  * enemies
  * NPCs

* Behavior-driven

---

## 10.2 System-Based AI

* Controls game environment

* Adjusts:

  * difficulty
  * pacing
  * resources

Example:

* dynamic enemy spawning
* adaptive difficulty systems

---

# 11. Choosing AI for Your Game

## 11.1 Start with Design

* Ask:

  * what needs automation?

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

  * learn from experience

* Becomes:

  * complex quickly with scale

---

# 15. Implementation Strategy

## 15.1 Movement System

* Use:

  * velocity + direction (heading)

---

## 15.2 Patrol Logic

* Waypoints:

  * move between points

* Loop behavior

---

## 15.3 Collision Handling

* Detect collisions

* Apply:

  * damage
  * destruction logic

---

## 15.4 Chase Logic (Advanced)

* Detection zone
* Move toward player
* Return to patrol when lost

---

# 16. Optimization Mindset

* Optimize:

  * implementation effort

* Not:

  * theoretical correctness

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

  * expected vs actual movement

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

  * controlled imperfection

* Good AI:

  * feels human
  * not optimal

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
