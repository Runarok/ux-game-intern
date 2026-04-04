# 1. Lesson Objective

* Final phase of game development: **finalizing, polishing, and publishing**
* Goals:

  * Choose a **target platform**
  * Apply **final features and polish**
  * **Build and export** the game

---

# 2. Available Platforms

* Android
* iOS
* HTML5 (Web)
* Mac OSX
* Windows Desktop
* Linux (X11)

---

# 3. Platform Selection – Core Considerations

* Input methods differ per platform
* Hardware limitations (battery, performance)
* Player experience varies by device
* Optimize for **one platform at a time** (avoid generic design)

---

# 4. Mobile Platforms (Android & iOS)

## Advantages

* Touchscreen input (multi-touch, gestures)
* Built-in sensors:

  * Accelerometer (tilt controls)
  * GPS (location-based gameplay)

## Disadvantages

* Poor for precise controls (e.g., FPS games)
* Slow text input (on-screen keyboard)
* Battery constraints:

  * Avoid heavy computation
  * Avoid excessive lighting effects

## Key Use Cases

* Casual games
* Racing (tilt input)
* AR/location-based games (geocaching)

---

# 5. HTML5 (Web Platform)

## Advantages

* Runs on any device via browser
* Good for demos/promotions
* No installation required

## Disadvantages

* Requires internet (initially or fully)
* Limited by network performance

## Networking Concepts

* **Throughput**: data transfer rate (bits/sec)
* **Latency**: delay in communication

## Requirements for Good Performance

* High throughput
* Low latency

## Optimization Techniques

* Send only instructions (not assets)
* Minimize data size
* Avoid frequent/large data transfers
* Do not load assets during gameplay

---

# 6. PC Platforms (Windows & Mac)

## Input Flexibility

* Keyboard + mouse
* Controllers
* Joysticks
* VR/AR devices

## Hardware Variability

* Wide range (low-end → high-end PCs)
* Must support multiple configurations

## Optimization Strategy

* Use **Level of Detail (LOD)**:

  * Low → far objects
  * High → near objects

## Mac-Specific Notes

* Trackpad multi-touch gestures
* Webcam input possible
* Battery constraints (for laptops)

---

# 7. Linux Platform

## Similarities

* Same benefits as PC platforms

## Differences

* More technical setup
* No standard executable files
* Different launch mechanism

---

# 8. Console Considerations (General)

## Constraints

* Fixed hardware
* Controller-based input

## Design Considerations

* Map controls carefully
* Provide multiple control layouts
* Keep controls simple

## Limitations

* FPS and RTS less suitable due to control precision
* Controllers lack keyboard flexibility

## Unique Feature

* Analog input (joysticks/triggers → variable intensity)

---

# 9. Final Game Polish

## Visual Improvements

* Update materials and textures
* Fix texture distortion (UV issues)
* Use proper scene design (ideally external tools like Blender)

## Common Issue

* **Z-fighting**:

  * Caused by overlapping surfaces
  * Fix: slight rotation/offset

## Enhancements

* Add lighting (e.g., waypoint beacons)
* Adjust materials (transparency, scale)

---

# 10. Gameplay Logic Completion

## Required Additions

* End game when player falls
* Add respawn system
* Score system updates:

  * Reaching final platform → +points + respawn
  * Hitting AI → +points + respawn

## AI Behavior Change

* Do not delete AI on collision
* Keep AI active

---

# 11. Fall Detection System

## Implementation Steps

* Create **fall trigger area**
* Add collision shape
* Position below platforms
* Connect signal to player

## Result

* Player falls → game over screen triggered

---

# 12. Game Testing (Pre-Build)

## Must Verify

* Main menu navigation
* Gameplay loop
* Game over flow
* Leaderboard system
* All buttons and transitions

## Rule

* Test **all possible paths**

---

# 13. Build Process

## Steps

1. Set **starting scene** (main menu)
2. Save all scenes
3. Open **Export settings**
4. Choose platform (e.g., Windows)
5. Install export templates if missing
6. Select export path
7. Export project
8. Run executable to verify

---

# 14. Common Build Issues

* Game not launching → starting scene not set
* Missing templates → download required files
* Errors → recheck export steps

---

# 15. Key Takeaways

* Platform choice affects:

  * Controls
  * Performance
  * Game design
* Always optimize for **specific platform**
* Network constraints matter for web games
* Support multiple hardware levels on PC
* Keep controls simple and responsive
* Final polish + testing is essential before release
* Build process requires correct setup (scene + templates)

---


