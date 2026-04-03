### 1. Core Principle: Mechanics as “Atoms” of Systems



* Complex game behavior = combination of **simple, low-level components (mechanics)**

* Break systems into smallest units → recombine to design complex gameplay

* Understanding fundamentals → easier system design and debugging



---



### 2. Rules vs Mechanics (Critical Distinction)



* **Rules**



&#x20; * High-level descriptions

&#x20; * Visible to players (instructions, objectives, tutorials)

&#x20; * Define *what* the player should do



* **Mechanics**



&#x20; * Low-level implementations of rules

&#x20; * Often hidden from players

&#x20; * Define *how* the game actually works



* Key relation:



&#x20; * All mechanics are rules

&#x20; * Not all rules are mechanics



---



### 3. Nature of Game Mechanics



* Govern:



&#x20; * Behaviors

&#x20; * Limitations

&#x20; * Interactions

* Can be embedded systems (physics, AI, UI interactions)

* **Media-independent** → transferable across platformsengines



---



### 4. Core Mechanics



* Most important mechanics in a game



* Characteristics:



&#x20; * Used frequently

&#x20; * Affect multiple systems

&#x20; * Essential for progressioncompletion



* Examples:



&#x20; * Portal → portals + physics

&#x20; * FPS → aiming, shooting, movement systems

&#x20; * Strategy systems → decision-making mechanics



---



### 5. Continuous vs Discrete Mechanics



#### 5.1 Continuous Mechanics



* Operate on **floating-point values**

* Smooth, real-time interactions

* Examples:



&#x20; * Movement, physics, racing systems

* More realistic but computationally heavier



#### 5.2 Discrete Mechanics



* Operate on **integers  states**

* Grid-based or step-based systems

* Examples:



&#x20; * Turn-based games, inventories, economies

* More efficient and predictable



---



### 6. Physics Mechanics



* Simulate real-world behavior using algorithms

* Usually handled by game engines

* Trade-off:



&#x20; * Realism vs performance



#### Optimization Strategy:



* **Baking**



&#x20; * Precompute simulations → store as animations

&#x20; * Pros: performance efficiency

&#x20; * Cons: reduced variationrealism



#### Practical Insight:



* Games often **approximate physics**, not fully simulate

* “Believable” > “Realistic”



---



### 7. Progression Mechanics



* Control **player advancement speed**

* Prevent skipping content or unintended shortcuts



#### Common Forms:



* Level systems (stats, XP)

* Item restrictions (levelclass requirements)

* Locked gates (keys, puzzles, conditions)

* Ability gating (skills required to proceed)



#### Purpose:



* Maintain pacing

* Ensure content engagement

* Prevent design bypass



---



### 8. Tactical Mechanics



* Enable **strategic decision-making**

* Common in strategy and competitive games



#### Design Considerations:



* Must maintain **balance**

* Avoid dominant strategies

* Introduce trade-offs



#### Examples:



* Terrain effects

* Unit strengthsweaknesses

* Environmental modifiers



---



### 9. Social Interaction Mechanics



* Govern **player-to-player interaction**



#### Includes:



* Chat systems (textvoice)

* Trading systems

* Reportingmoderation tools

* Emoteslimited communication



#### Key Insight:



* Modern games enforce structure → reduce toxicity

* Earlier systems relied on unwritten player rules



---



### 10. Internal Economy (Most Critical System)



#### 10.1 Resources



* Anything that can be:



&#x20; * Collected, used, produced, or consumed

* Examples:



&#x20; * Money, time, ammo, health, items



#### Types:



* **Tangible** → physical presence (inventory items)

* **Intangible** → numerical values (health, currency)



---



#### 10.2 Entities



* Containers of resources



* **Simple Entity** → holds one value (e.g., weapon ammo)



* **Compound Entity** → holds multiple (e.g., player inventory)



---



### 11. Economic Functions



#### 11.1 Sources (Increase resources)



* Time-based (income per second)

* Condition-based (unlock rewards)

* Trigger-based (activate event)



#### 11.2 Drains (Remove resources)



* Permanent loss (ammo usage, health loss)



#### 11.3 Converters (Transform resources)



* Crafting systems (materials → item)



#### 11.4 Traders (Exchange resources)



* Buyingselling, item transfers



---



### 12. Combining Economic Systems



* Systems can mix:



&#x20; * Time + condition + trigger

* Creates layered and dynamic economies

* Example:



&#x20; * Resource node that generates over time, upgrades with level, releases on interaction



---



### 13. Economy Design Patterns (Shapes)



* Design economy using **resource flow over time**



#### Example Pattern:



* High resources → gradual depletion → scarcity

* Leads to:



&#x20; * Strategic gameplay

&#x20; * Resource tension



#### Case Insight:



* Chess-like systems:



&#x20; * No sources

&#x20; * Only drains + conversions

&#x20; * Forces precision and planning



---



### 14. Design Insight: Illusion vs Reality



* Full realism is often unnecessary

* Players respond to:



&#x20; * Consistency

&#x20; * Feedback

&#x20; * Believability

* Cheap approximations often outperform heavy simulations



---



### 15. System Interaction Insight



* Mechanics don’t exist in isolation

* Interaction of mechanics → creates dynamics → defines experience

* Poor interaction → broken gameplay

* Strong interaction → emergent complexity



---



### 16. Key Takeaways (All Things to Remember)



* Complex systems are built from simple mechanics

* Mechanics are low-level implementations; rules are high-level descriptions

* Core mechanics define the identity of the game

* Continuous vs discrete impacts realism and performance

* Physics should be optimized; realism is optional

* Progression mechanics control pacing and player flow

* Strategy mechanics must be balanced to avoid dominant playstyles

* Social mechanics must be controlled to prevent negative behavior

* Every game has an internal economy governing resources

* Resources + entities + functions form the economic system

* Sources, drains, converters, and traders shape gameplay flow

* Economy design can be planned using resource flow patterns

* Mechanics interacting together create the actual player experience



---

