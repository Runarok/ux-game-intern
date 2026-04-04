## 1. Lesson Overview

* Final lesson on **asset acquisition**, focused on **textures and materials**
* Structure:

  * Finish **audio asset import**
  * Explore **sources for textures/materials**
  * Compare **workflows (PBR, painting, scanning)**
  * Optional: apply textures to assets

---

## 2. Audio Asset Import (GDAU Engine)

### Sources & Selection

* Use free packs (e.g., **Kenney Assets**) for ready-to-use files
* Paid music possible (example used: *Ambient Background Corporate*)
* Choose assets based on game needs (UI sounds, background music)

### File Requirements

* Supported formats: **.ogg, .wav**
* Convert if needed using **Audacity** (MP3 → OGG/WAV)

### Conversion Steps (Audacity)

1. File → Import → Audio
2. File → Export → Export as OGG/WAV
3. Save → ignore metadata if not needed

### Project Organization

* Create folder: `audio_assets`

  * `music/`
  * `sounds/`
* Import gradually (avoid crashes)
* Extract zip files before importing

---

## 3. Audio Management in Engine

### Preview & Import Settings

* Preview audio in inspector
* Loop setting:

  * Default may be enabled
  * Must **reimport** to make changes permanent

### Audio Stream Player Node

Used to play audio during runtime

**Key properties:**

* Volume (dB): negative = quieter
* Pitch scale: controls pitch
* Playing: preview in editor
* Autoplay: plays on game start
* Stream paused: pause vs restart
* Mix target: output type (e.g., stereo)
* Bus: audio channel routing

---

## 4. Implementing Audio in UI

### Background Music

* Add `AudioStreamPlayer` node
* Assign music to stream
* Enable **autoplay**
* Adjust volume (~ -12 dB recommended)

### Button Sound Effects

* Use **multiple audio players** (avoid interrupting music)
* Example setup:

  * `button_down_player`
  * `button_up_player`

### Signals & Logic

* Use button signals:

  * `button_down` → play click
  * `button_up` → play release
* Always **check node exists before playing**

### Notes

* Exit button may cut sound early (acceptable)
* Multiple players prevent audio conflicts

---

## 5. Importance of Textures & Materials

* Primary visual component in games
* Define realism and appearance of assets

---

## 6. Texture & Material Sources

### CC0 Textures

* Free, no attribution required
* Large library, multiple formats/resolutions
* Includes **3D preview (Sketchfab)**

### Texture Haven

* Also CC0 licensed
* Up to **8K resolution**, PBR-ready
* Strong categorization + related suggestions
* No 3D preview

---

## 7. Creating Materials

### Materialize (Software)

* Converts images → materials
* Free, open-source (GPL3)
* Export usable maps

### Blender

* Create procedural textures using **PBR nodes**
* Fully customizable
* Suitable for commercial use

---

## 8. PBR (Physically Based Rendering)

### Definition

* Simulates real-world material behavior
* Includes: reflection, refraction, diffusion

### Key Concept

* Uses **multiple texture maps** (baked data)
* Reduces real-time calculations → improves performance

### Workflow (Blender Example)

* Use nodes like:

  * Noise Texture
  * Color Ramp
  * Bump Map
  * Principled BSDF

### Key Adjustments

* Scale, distortion → pattern control
* Color ramp → material colors
* Bump → surface depth
* Roughness/specular → realism

---

## 9. Texture Creation Techniques Comparison

### 9.1 Procedural (PBR)

**Pros:**

* Highly realistic
* Efficient rendering
* Fully customizable

**Cons:**

* Requires technical knowledge

---

### 9.2 Texture Painting

**Process:** paint directly on 3D models

**Pros:**

* High artistic control

**Cons:**

* Time-consuming
* Skill-dependent
* Requires graphics tablet

---

### 9.3 Texture Scanning

#### 3D Scanning

**Pros:**

* Extremely detailed
* Fast capture

**Cons:**

* Expensive equipment
* Large file sizes
* Needs post-processing

#### Photogrammetry

**Pros:**

* Cheaper (uses smartphone)
* Good realism

**Cons:**

* Requires precise image capture
* Slow processing
* Quality depends on photos

#### Photo-to-Material (e.g., Materialize)

**Pros:**

* Cheapest
* Easy to use

**Cons:**

* No real depth data
* Accuracy depends on image quality

---

## 10. Key Technical Practices

* Always organize assets properly
* Convert files to supported formats
* Use multiple audio players to avoid conflicts
* Reimport assets after changing import settings
* Check node existence before using in code

---

## 11. Assignment / Application

* Either:

  * **Find textures/materials** (libraries)
  * **Create your own** (PBR, painting, scanning)
* Prepare for import into engine in next lesson

---

## 12. Core Takeaways

* Audio pipeline: acquire → convert → organize → import → assign nodes
* GDAU requires **OGG/WAV formats only**
* Use **AudioStreamPlayer** nodes for runtime playback
* Textures/materials are critical for visual quality
* CC0 libraries provide free, high-quality assets
* PBR is the standard for realistic rendering
* Different workflows vary by cost, skill, and realism
* Efficiency comes from **preprocessing (baking)** rather than runtime computation

---