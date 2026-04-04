## 1. Completing 3D Model Import & Animation Setup

* Download a rigged humanoid model (e.g., Ybot from Mixamo) with animations: T-pose, idle, walk, run, jump, landing.
* Ensure animations are set to **“in place”** to avoid movement offsets.
* Export models as **FBX (with skin, FBX 7.4)**.
* Organize files into a permanent project folder (not Downloads).

## 2. Preparing Models in Blender

* Install Blender and the **GDAU Game Tools add-on**.
* Import T-pose first using **Initialize Character**, then add animations using **Join Animations**.
* Verify animations:

  * Model should remain in one position.
  * Re-import or change model if issues occur.
* Export as:

  * **.glb (binary)** preferred over .gltf (smaller size).
* Before export:

  * Delete camera and light.
  * Enable **animation loops** and **animation tree**.

## 3. Importing into GDAU Engine

* Place exported file into project folder → engine auto-imports.
* Create **inherited scene** (cannot open .glb directly).
* Rotate model **Y = -180°** to fix facing direction.
* Scale model appropriately (e.g., 2× if too small).

## 4. Player Scene Setup

* Add model under a spatial node.
* Enable **editable children**.
* Replace placeholder mesh with model.
* Configure collision:

  * Use **cylinder shape** for body and hitbox.
  * Adjust radius, height, and scale to match model.
* Adjust camera:

  * Example: Position (0, 5.2, 4.8), Rotation (-6.5, 0, 0).

## 5. Fixing Camera Detection Bug

* Add conditional checks in code to ensure camera node exists before applying transformations.
* Prevents random crashes due to inconsistent node detection.

## 6. Animation Tree Setup

* Add **AnimationTree node** and link to AnimationPlayer.
* Enable **Active** property.
* Create animation states:

  * Idle
  * Walk
  * Run
* Use **Blend3 node**:

  * -1 → Walk
  * 0 → Idle
  * +1 → Run
* Add **OneShot node** for jump:

  * Overrides other animations temporarily.

## 7. Animation Logic in Script

* Use a boolean (e.g., `movement_keys_pressed`) to track movement.
* Set animation via **blend amount**:

  * Idle = 0
  * Walk/Run = based on movement
* Always check if AnimationTree exists before using it.
* Jump handling:

  * Disable loop for jump animation.
  * Trigger OneShot for single execution.

## 8. Testing Animations

* Verify:

  * Walk → walking animation
  * Run → running animation
  * Idle → idle animation
  * Jump → plays once correctly
* Strafing may lack animation if not implemented.

---

## 9. Audio Editing Tool: Audacity

* Free, open-source audio editor.
* Supports formats: WAV, AIFF, FLAC, MP3, OGG (+ more with plugins).
* Key features:

  * Cut, copy, paste audio
  * Mix and splice tracks
  * Change pitch, speed, tempo
  * Apply effects
  * Plugin support (Nyquist)

## 10. Audio Synthesizers (Sound Creation)

* Used to generate sounds by modifying parameters.
* Learning curve is high.
* Examples:

  * Tyrell N6, Zebra (u-he)
  * Surge, Dexed, OB-Xd
  * TAL NoiseMaker, Odin 2, Voltage Modular
* Useful for:

  * Custom sound effects
  * Music creation

## 11. Blendwave (Beginner Sound Tool)

* Web-based sound editor for quick SFX creation.
* Features:

  * Sound library
  * Pitch, amplitude controls
  * Filters (high-pass/low-pass)
  * Effects (reverb, delay, distortion)
* Limitations:

  * No undo → track parameter values manually.

## 12. Digital Audio Workstations (DAWs)

* Used to manage, edit, and produce audio.
* Functions:

  * Multi-track editing
  * Plugin integration
  * Instrument simulation
* Free DAWs:

  * LMMS
  * Waveform Free
  * Cakewalk
  * BandLab
  * Reaper (trial)

## 13. Sound Libraries & Plugins

* Add instruments and presets to DAWs.
* Examples:

  * Native Instruments (Kontakt ecosystem)
  * Output (Arcade, Signal)
* Notes:

  * Some are expensive.
  * Compatibility varies by DAW.

## 14. Free & Paid Audio Asset Sources

### Free Sources:

* OpenGameArt
* FreeSound
* Bensound
* SoundCloud
* 99Sounds

### Paid / Mixed:

* Zapsplat (affordable)
* Fiverr (hire designers)
* Bandcamp (paid + Creative Commons)
* Unity Asset Store
* Boom Library (high-end)

## 15. DIY Sound Generators

* Tools for generating custom effects:

  * Bfxr
  * SFMaker
  * Blendwave

## 16. Additional Audio Options

* Kenney assets → public domain sounds.
* Chiptone → free chiptune generator.
* AI music tools (e.g., AIVA-like platforms):

  * Generate music by mood/scene/genre.
  * Free versions may include watermark.

## 17. Licensing Considerations

* Always check:

  * Attribution requirements
  * Commercial use rights
  * Licensing type (free, paid, public domain)

## 18. Key Takeaways

* Always verify animations stay in place before exporting.
* Use Blender add-ons to streamline animation workflows.
* AnimationTree + Blend3 + OneShot is core animation system.
* Always add null checks for nodes in scripts to prevent crashes.
* Audio pipeline:

  * Create (synth/tools) → Edit (Audacity/DAW) → Import.
* Choose between:

  * Creating custom sounds (flexible, time-consuming)
  * Using libraries (fast, limited uniqueness)
* Track licensing carefully when using external audio assets.

---