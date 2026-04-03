### 1. Lesson Objectives



* Install and set up the game engine

* Understand disciplined prototyping practices

* Build first **software prototype (hands-on)**



---



### 2. Engine Selection Context



* Using **Godot Engine (referred as GDAU)**

* Reasons (implied from walkthrough):



&#x20; * Free & open-source

&#x20; * Strong 2D + good 3D support

&#x20; * Lightweight and portable

&#x20; * Active community + plugins



---



### 3. Installation & Setup



* Download **stable version** (avoid experimental builds)

* No traditional install → just unzip and run executable

* Benefits:



&#x20; * Portable (USB runnable)

&#x20; * Small size

&#x20; * Fast setup



---



### 4. Website Structure (What Matters)



* **Features tab** → engine capabilities

* **News  Dev blog** → updates

* **Community tab** → forums, Discord, GitHub

* **Download tab** → engine versions

* **Assets  Learn (important later)**



---



### 5. Project Initialization



* Create new project:



&#x20; * Use **clear naming + structured folders**

* Choose rendering option (OpenGL ES3)

* Result → first working project environment



---



### 6. Core Mental Model



#### 6.1 Hierarchy



* Game = collection of **scenes**

* Scene = collection of **nodes**



#### 6.2 Node Properties



Every node has:



* Name

* Editable properties

* Per-frame processing capability

* Can be parentchild

* Modular role



#### 6.3 Scene Properties



* Has a **root node**

* Can be savedloaded

* Can be instanced (reused)



---



### 7. Editor Interface (Essential Docks)



* **Scene Dock** → node hierarchy

* **Inspector** → properties editing

* **File System** → project structure

* **Import** → external asset settings

* **Node Dock** → relationships & scripts

* **Main Workspace** → 2D3D editing



**Bottom Panel:** console, debugger, audio, animation



---



### 8. Navigation Controls



#### 3D



* Right-click + move → camera view

* WASD + mouse → movement

* Scroll → zoom

* Middle click → orbit  pan



#### 2D



* Mostly pan + zoom

* Blue box = visible screen area



---



### 9. Asset Library



* Provides plugins and tools

* Not used initially (avoid complexity early)



---



### 10. Minimum Viable Game (MVG) Concept



* Build **smallest playable version**

* Remove all non-essential features



#### Example (3D Platformer Prototype):



* Movement: walking, running, jumping

* Environment: platforms, ramps

* Game logic: winlose conditions



**Key idea:**



* Validate gameplay first, expand later



---



### 11. Scene Construction Strategy



* Use **modular scenes**

* Separate reusable objects (e.g., platforms)



#### Why



* Edit once → update everywhere

* Cleaner structure

* Scalable design



---



### 12. Scene Setup (Practical Flow)



#### 12.1 Main Scene



* Root node (Spatial)

* Acts as game world



#### 12.2 Platform Scene



* StaticBody (immovable)

* CollisionShape (physics boundary)

* MeshInstance (visual cube)



#### 12.3 Box Scene



* RigidBody (affected by physics)

* Falls and collides → used for testing



#### 12.4 Player Scene



* KinematicBody

* Controlled via scripting (no physics forces)



---



### 13. Physics Object Types



#### Static Body



* Immovable

* Used for environment (floors, walls)



#### Rigid Body



* Fully physics-driven

* Affected by gravity, forces



#### Kinematic Body



* Manually controlled

* Not affected by physics automatically

* Used for player



---



### 14. Transform System



Each object has:



* Translate (position)

* Rotate

* Scale



Axes:



* X (red), Y (vertical), Z



---



### 15. Collision System Basics



* Requires **collision shape**

* Must align with visual mesh

* Defines interaction boundaries



---



### 16. Testing the Scene



* Use **Play Scene (not full game yet)**

* Validate:



&#x20; * Physics (box falling)

&#x20; * Camera view

&#x20; * Object placement



---



### 17. Camera Setup



* Add camera node

* Position + rotate manually

* Use preview to validate framing



---



### 18. Grid & Position Logic



* Engine uses **center-based positioning**

* Example:



&#x20; * Platform height → centered → top at +1

&#x20; * Player must align exactly → precise placement



---



### 19. Modularity Principle



* Everything reusable → separate scene

* Avoid hardcoding objects inside main scene



---



### 20. Prototyping Discipline Applied



* Keep prototype:



&#x20; * Low fidelity

&#x20; * Minimal features

&#x20; * Functional over polished



* Focus:



&#x20; * Mechanics working

&#x20; * Not visuals



---



### 21. Key Development Habits



* Name everything clearly

* Save scenes frequently

* Keep structure organized

* Test continuously (not at end)



---



### 22. Constraints & Expectations



* Even “small” prototype = complex

* Debugging will consume time

* Errors are expected



---



### 23. What You Achieved



* Installed engine

* Created structured project

* Built modular scenes

* Implemented:



&#x20; * Floor

&#x20; * Physics object

&#x20; * Player placeholder

* Ran first simulation



---



### 24. What Comes Next



* Scripting (movement, logic)

* Turning static setup → interactive system



---



### 25. Key Takeaways (All Things to Remember)



* Think in **nodes → scenes → game hierarchy**

* Always build **minimum viable version first**

* Separate reusable components into scenes

* Choose correct physics body type based on behavior

* Align collision + visuals properly

* Test early using isolated scenes

* Keep prototype functional, not polished

* Structure and modularity save time later

* Understanding engine fundamentals > rushing features



---

