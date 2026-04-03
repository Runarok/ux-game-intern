# 1. Lesson Focus



* Complete **leaderboard system integration**

* Introduce:



&#x20; * **3D assets (models)**

&#x20; * **Animation workflows**

* Shift:



&#x20; * from *functional prototype* → *visual + experiential layer*



---



# 2. Asset Philosophy



## 2.1 Core Principle



* Do not ship:



&#x20; * copied assets

&#x20; * placeholderproxy assets



## 2.2 Purpose of Assets



* Define:



&#x20; * visual identity

&#x20; * immersion

&#x20; * consistency



---



# 3. Leaderboard Completion (System Integration)



## 3.1 Scene Switching



* Leaderboard button:



&#x20; * loads leaderboard scene via script



---



## 3.2 Leaderboard Manager Script



### Key Variables



* file operator → file IO

* label array → UI references

* CSV line → raw file input

* original array → unsorted data

* sorted array → ranked data



---



## 3.3 Data Flow



### Step-by-step



1. Open score file

2. Read line-by-line

3. Parse into:



&#x20;  * `[name, score]` pairs

4. Store in array

5. Sort descending

6. Update UI labels

7. Rewrite sorted data to file



---



## 3.4 File Handling Rules



* Use:



&#x20; * **read mode** → retrieve data

&#x20; * **write mode** → overwrite data

* Always:



&#x20; * close file after operation

* Format constraint:



&#x20; * exactly **one space delimiter**



---



## 3.5 Sorting Logic



### Approach



* Manual selection-style sorting:



&#x20; * find max

&#x20; * move to output array

&#x20; * remove from input



### Characteristics



* Inefficient for large data

* Acceptable due to:



&#x20; * small dataset (top 10)



---



## 3.6 Optimization



* Only store:



&#x20; * **top 10 scores**

* Discard:



&#x20; * lower ranks



---



## 3.7 UI Update Logic



* Loop through labels (fixed 10)

* Handle:



&#x20; * fewer than 10 entries

* Format:



&#x20; * `"Name Score"`



---



# 4. Global State Management



## 4.1 Problem



* Player controller:



&#x20; * overloaded

&#x20; * unreliable across scenes



---



## 4.2 Solution



* Create **global singleton**



&#x20; * stores:



&#x20;   * player name

&#x20;   * score



---



## 4.3 Benefits



* Persistent data across scenes

* Cleaner separation of concerns



---



# 5. Submit Flow (Game Over → Leaderboard)



## 5.1 Input Handling



* Detect:



&#x20; * if player changed text

* Prevent:



&#x20; * empty submissions



---



## 5.2 Save Logic



1. Read existing file

2. Append new entry

3. Rewrite full file



---



## 5.3 Important Detail



* Writing overwrites file → must preserve old data manually



---



# 6. System Integration Fixes



* Set mouse mode visible in UI scenes

* Ensure:



&#x20; * UI accessible after transitions

* Validate:



&#x20; * full loop:



&#x20;   * play → score → submit → leaderboard



---



# 7. Asset Sources (3D Models)



## 7.1 Online Platforms



* Sketchfab

* itch.io

* CGTrader

* Kenney



---



## 7.2 Key Differences



* Quality varies

* Pricing varies

* Licensing varies



---



## 7.3 Critical Rule



* Always verify:



&#x20; * usage rights

&#x20; * commercial permissions



---



# 8. License Types (Must Know)



## 8.1 CC Attribution



* Free use (including commercial)

* Requires credit



---



## 8.2 CC0 (Public Domain)



* No restrictions

* No attribution required



---



## 8.3 Personal Use



* Not allowed in commercial release

* Only for:



&#x20; * prototyping



---



## 8.4 Educational Use



* Similar to personal

* allowed in teaching contexts



---



## 8.5 Royalty-Free



* Commercial use allowed

* Restrictions:



&#x20; * no resale

&#x20; * no standalone redistribution



---



## 8.6 Practical Insight



* Free ≠ usable in final product

* Fan art:



&#x20; * usually restricted



---



# 9. Asset Creation Tools



## 9.1 Core Tools



* Blender

* MakeHuman

* MB-Lab

* Asset Forge



---



## 9.2 Capabilities



* Modeling

* Rigging

* Texturing

* Animation

* Exporting



---



## 9.3 Workflow Insight



* Base mesh → customize → export → integrate



---



# 10. Rigging & Animation Basics



## 10.1 Rigging



* Add:



&#x20; * bones to model

* Purpose:



&#x20; * enable movement



---



## 10.2 Skinning



* Define:



&#x20; * which part moves with which bone



---



## 10.3 Weight Painting



* Controls:



&#x20; * influence intensity



---



## 10.4 Keyframe Animation



* Define poses at timestamps

* Engine interpolates between frames



---



# 11. Animation Tools



## 11.1 Mixamo



* Auto rigging

* Motion capture animations

* Fast pipeline



---



## 11.2 Blender (Animation)



* Manual control

* Keyframe-based



---



## 11.3 Cascadeur



* Physics-based interpolation

* Higher realism

* Paid



---



# 12. Asset Pipeline Strategy



## Basic Flow



1. Choose  create model

2. Check license

3. Rig (if needed)

4. Animate

5. Import to engine

6. Replace placeholder



---



# 13. Practical Constraints



* Asset quality vs uniqueness tradeoff

* Free assets:



&#x20; * often overused

* Custom assets:



&#x20; * time intensive



---



# 14. Development Insight



* Systems (leaderboard, scoring):



&#x20; * reusable across projects

* Asset pipelines:



&#x20; * iterative learning process



---



# 15. What to Remember



* Assets define perception, not just visuals

* Never ignore licensing—this is legal, not optional

* File IO requires strict control (read vs write)

* Sorting logic must match data constraints

* Keep only relevant data (top N optimization)

* Separate global state from gameplay logic

* UI + data systems must be fully integrated end-to-end

* Rigging is prerequisite for animation

* Mix automation (Mixamo) with control (Blender)

* Expect to experiment before finding a workflow that fits



---





