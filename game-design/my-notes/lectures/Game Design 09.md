### 1. Lesson Objectives

* Complete download and setup of the GDAU engine
* Understand prototyping discipline (low-fidelity focus)
* Build first functional game prototype (basic scene + objects)

---

### 2. GDAU Engine Overview

* Open-source, lightweight, no installation (runs via executable)
* Strong support for:

  * 2D (optimized workflows)
  * 3D (modern graphics support)
  * Animation systems
* Multi-language scripting:

  * GDScript (Python-like)
  * C, C++ (GDNative)
  * Community-supported: Rust, Nim, D
* Cross-platform:

  * PC, consoles, VR/AR
* Node-based architecture (modular, Git-friendly file structure)
* Strong community ecosystem (forums, Discord, GitHub, tutorials)

---

### 3. Installation Key Points

* Download **stable version** (avoid experimental builds)
* Choose correct system architecture (32-bit / 64-bit)
* No installer:

  * Extract zip → run executable
* Portable:

  * Can run from USB
* Lightweight:

  * Fast download, low storage usage

---

### 4. Project Setup Workflow

* Open engine → Projects tab
* Create new project:

  * Use clear, descriptive naming
  * Maintain structured folders (e.g., `GDAU Projects/project_name`)
* Select rendering option (OpenGL ES 3.0)
* Create & edit project

---

### 5. Interface Structure (Core Panels)

* **Scene Dock** → Manage nodes (most important)
* **Main Workspace** → Visual editing (2D/3D)
* **Inspector** → Edit properties of selected node
* **File System** → Project file structure (`res:` root)
* **Node Dock** → Node relationships & signals
* **Import Dock** → Asset import settings

Bottom panel:

* Console, debugger, audio, animation tools

---

### 6. Workspace Controls

**3D Navigation**

* Right click + move → camera look
* WASD + right click → movement
* Scroll → zoom
* Middle click → orbit
* Shift + middle click → pan

**2D Navigation**

* Scroll → zoom
* Drag (various combinations) → pan
* Blue box = visible screen area

---

### 7. Core Architecture Concepts

#### Nodes

* Fundamental building blocks
* Properties:

  * Name
  * Editable parameters
  * Can process per frame
  * Can have parent-child relationships

#### Scenes

* Tree of nodes
* Must have:

  * Root node
  * Save/load capability
  * Instancing (reuse across project)

#### Game Structure

* Game = collection of scenes
* Scene = collection of nodes

---

### 8. Minimum Viable Game (MVG)

* Focus: **functionality over completeness**
* Remove all non-essential features
* Build smallest playable version first

**For 3D platformer prototype:**

* Player movement:

  * Walk
  * Run
  * Jump
* Environment:

  * Platforms
  * Ramps
* Game logic:

  * Win condition
  * Lose condition

---

### 9. Scene Creation Strategy

* Always modularize repeatable elements

  * Example: Platform → separate scene

* Benefits:

  * Reusability
  * Easy updates (change once → applies everywhere)
  * Cleaner structure

---

### 10. Building First Scene (Main Scene)

* Root node: Spatial (3D base)
* Save as: `main.tscn`
* Add:

  * Platform (instanced scene)
  * Camera
  * Box (physics test object)
  * Player (proxy)

---

### 11. Creating Game Objects

#### Platform (Static Object)

* Node: StaticBody
* Add:

  * CollisionShape → Box
  * MeshInstance → Cube
* Purpose: Floor / environment

---

#### Box (Physics Object)

* Node: RigidBody
* Affected by gravity
* Used for testing collisions

---

#### Player (Controlled Object)

* Node: KinematicBody
* Add:

  * CollisionShape
  * MeshInstance
* Not affected by physics automatically
* Movement controlled via scripts

---

### 12. Transform System (Important)

* Axes:

  * X, Z → horizontal
  * Y → vertical

* Transform properties:

  * Translate (position)
  * Rotate
  * Scale

Example:

* Platform scaled to (10, 1, 10)
* Player positioned based on center alignment logic

---

### 13. Camera Setup

* Add Camera node
* Position:

  * Above ground (Y axis)
  * Offset (Z axis)
* Rotate to face scene
* Use preview to test view

---

### 14. Physics Body Types (Critical Difference)

* **StaticBody**

  * Immovable
  * Used for environment

* **RigidBody**

  * Fully physics-driven
  * Affected by gravity, collisions, forces

* **KinematicBody**

  * Script-controlled movement
  * Not affected by physics automatically

---

### 15. Testing the Scene

* Use **Play Scene** (not full game yet)

* Validate:

  * Gravity (box falls)
  * Collision (box hits platform)
  * Player placement
  * Camera visibility

---

### 16. Key Principles to Remember

* Start low fidelity → iterate later
* Separate reusable components into scenes
* Nodes = smallest unit, scenes = structured grouping
* Always maintain clean project structure
* Use physics types correctly:

  * Static → environment
  * Rigid → simulation
  * Kinematic → player
* Test early, test often (even basic setups)

---

### 17. What Matters Going Forward

* Comfort with interface → reduces friction later
* Clear mental model:

  * Node → Scene → Game hierarchy
* Understanding transforms & positioning
* Grasp of physics object roles
* Discipline in keeping scope minimal

---
