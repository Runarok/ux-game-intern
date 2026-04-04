## 1. Lesson Overview

* Focus: **Game Feel (juice + polish)**
* Structure:

  * Import **textures/materials into engine**
  * Define **game feel**
  * Explore **techniques to improve it**
  * Analyze **practical examples**

---

## 2. Importing Textures & Materials (GDO Engine)

### Setup

* Create `textures` folder in project
* Drag texture files → engine file system
* Import time depends on resolution

### Applying Textures to Models

1. Open scene (not just node)
2. Select mesh → Material → New Spatial Material
3. Assign maps:

   * Albedo → `_color`
   * Metallic → `_metalness`
   * Roughness → `_roughness`
   * Normal → `_normal`
   * Displacement → `_height`

### Displacement Settings

* Enable depth
* Use **deep parallax**
* Adjust scale (e.g., ~0.01)
* Enable **flip binormal** (avoid artifacts)

### Emission (Highlight Areas)

* Enable emission in material
* Assign bright color (e.g., red)

### Lighting

* Add **Directional Light**
* Adjust:

  * Position (e.g., Y ≈ 25)
  * Rotation
  * Energy (~0.6)
* Lighting affects realism significantly

---

## 3. Definition of Game Feel

* Coined by Steve Swink
* No strict definition (subjective)

### Core Idea

* Maximize **output for every player input**
* Goal: increase **engagement and immersion**

---

## 4. Four Core Aspects of Game Feel

### 4.1 Player Experience (UX)

* Understand what players like/dislike
* Guides design decisions

### 4.2 Player Feedback

* Every input → visible/audible/game response
* Minimum:

  * Visual
  * Audio
  * Gameplay effect

### 4.3 Player Metrics

* Track player behavior (performance, health, actions)
* Used for **adaptive difficulty**
* Example: AI adjusts difficulty dynamically

### 4.4 Player Connection

* Emotional / intellectual / adrenaline link
* Increases retention and immersion

---

## 5. Game Feel Goal

* Focus on **engagement → immersion → enjoyment**
* Avoid adding effects without purpose
* All features must contribute to **fun**

---

## 6. Three Characteristics of Game Feel

### 6.1 Real-Time Control

* Immediate response to input
* Minimal latency (even ~250ms feels bad)

**Effects:**

* Strong immersion
* Better control (important for fast gameplay)

---

### 6.2 Spatial Simulation

* Game exists in a **consistent world**
* Includes:

  * Position
  * Movement
  * Physics/logic rules

**Key:**

* Rules must be consistent
* Player actions must affect world

---

### 6.3 Polish (Juice)

* Extra effects to enhance feedback
* Examples:

  * Visual effects
  * Sound effects
  * Animation
  * Particles
  * Slow motion

**Rule:**

* Must enhance gameplay, not distract

---

## 7. Polishing Example (Projectile Iteration)

### Base Problem

* Projectile feels dull and weak

### Improvements (Step-by-step)

1. Add flashing colors → minor effect
2. Increase speed → better sense of danger
3. Add explosion → improves impact
4. Add shockwave → enhances perceived force
5. Add sound → major improvement

### Further Enhancements

* Launch sound (gun/magic)
* Travel sound (whoosh/whistle)
* Layered audio

---

## 8. Visual Techniques

* Primary feedback channel

### Methods

* Lighting
* Animation
* Colors & contrast
* Object size/shape
* Movement speed
* Facial expressions

**Goal:** highlight important gameplay info

---

## 9. Audio Techniques

### Principles

* Supports unseen events
* Sets mood and pacing

### Techniques

* Short sound effects (avoid fatigue)
* Multi-layered sounds (realism)
* Strong initial “kick” (attention grab)
* Ducking: reduce background audio during key sounds

---

## 10. Cinematic Techniques (Camera)

* Camera = player’s perspective

### Methods

* Camera shake → impact
* Letterboxing → cinematic scenes
* Zoom / focus → highlight importance
* Motion blur → speed
* Chromatic aberration → distortion/damage effects

---

## 11. Atmosphere Techniques

* Controls mood and immersion

### Methods

* Weather
* Ambient sounds
* Environmental animation
* World changes

---

## 12. Tactile (Haptic) Feedback

* Uses vibration/controllers

### Techniques

* Different vibration patterns = different meanings
* Consistency is critical
* Optional: feedback on button press

---

## 13. Case Studies

### Half-Life 2

* Strong atmosphere (oppression → empowerment)
* Gravity gun:

  * Visual recoil
  * Sound energy buildup
  * Increasing power progression

---

### Star Wars: The Force Unleashed

* Powerful force abilities (physics + sound)
* Large enemy groups → player feels strong
* Combo timing → skill satisfaction

---

### Blur

* Motion blur → speed sensation
* Power-ups → impactful visuals/physics
* Limited inventory → strategic pressure

---

## 14. Key Design Principles

* Immediate input response is critical
* Every action must generate feedback
* Combine multiple senses (visual + audio + haptic)
* Use metrics to refine experience
* Maintain consistency in rules and feedback
* Polish iteratively (test → improve → repeat)

---

## 15. Core Takeaways

* Game feel = **input → feedback → engagement loop**
* Real-time responsiveness directly impacts immersion
* PBR/visuals alone are not enough; feedback matters more
* Good game feel requires **layered effects**, not single changes
* Audio design is as important as visuals
* Camera and atmosphere strongly influence perception
* Polish is iterative and intentional, not random
* Player metrics enable smarter design decisions
* Strong game feel creates **immersion, clarity, and satisfaction**

---