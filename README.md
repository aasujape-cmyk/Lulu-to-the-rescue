# GDD: Lulu to the Rescue

## 1. General Information
* **Title:** Lulu to the Rescue.
* **Genre:** Lane Defense.
* **Platform:** PC / Web (Godot Engine 4.x).
* **Concept:** Lulu must protect the house entrance from waves of intruders (humans and animals) using her barks and strategic "traps."

### 1.1 Project Goal
* **Academic Purpose:** Develop a functional prototype demonstrating mastery of State Machines, a lane-based combat system, and collision management.
* **User Experience:** Create an addictive and fun arcade game, prioritizing fluid animations and responsive controls.

## 2. Objective and Victory
* **Victory Condition:** Survive 3 waves of enemies without anyone reaching Lulu or the house.
* **Defeat Condition:** An enemy successfully reaches Lulu or the house.
* **Scoring:** Number of intruders scared away.

## 3. Gameplay Mechanics
### 3.1 Lane Movement
The stage is divided into 3 grass lanes. Lulu moves up/down between lanes using W/S or arrow keys. Lateral movement is limited within her defense zone.

### 3.2 Barking System
* **Action:** Pressing Space will make Lulu bark.
* **Effect:** Launches a shockwave in her lane that pushes enemies back by scaring them.
* **Cost:** Each bark consumes 10% stamina.

### 3.3 "Poop" Traps
* **Action:** Shift or E key. Lulu uses the "Poop" sprite.
* **Effect:** Leaves a mine in the lane. Any enemy that steps on it is stunned/blocked for 3 seconds.
* **Limitation:** Recharges every 3 barks that successfully scare enemies.

### 3.4 Stamina and Rest
If stamina reaches 0, Lulu becomes exhausted and stops to recover energy.
* **Recovery:** Stamina recovers slowly if Lulu stands still (Idle) or twice as fast if she sits (Sit), though sitting/standing up takes extra time.

### 3.5 Mechanic: The "Gift" Jump
* **How it works:** Lulu can jump forward to gain ground in the lanes and leave a poop mine so enemies step on it and lose time. She can only perform 1 or 2 jumps forward.

## 4. Enemies (Intruders)
* **Common Mailman:** Medium speed, withstands 2 barks before fleeing.
* **Fugitive Delivery Driver:** Very fast but flees after 1 single bark.
* **Stray Cat:** Moves in a zig-zag pattern between lanes.

## 5. User Interface (UI)
### 5.1 HUD
* Stamina Bar.
* "Intruders Scared" Counter.
* Clock showing remaining time for the waves.

## 6. Sound Design (SFX & Music)
* **Bark:** A dry, powerful "Woof" that varies slightly in pitch to avoid repetition.
* **Poop:** A comical "plop" sound when Lulu places it and when an enemy steps on it.
* **Jump:** A fast speed effect, similar to movie action scenes.
* **Alert:** A notification sound when a new wave appears.
* **Music:** A cheerful, upbeat melody.

## 7. Basic Technical Structure
* **Main Scene:** `jardin_defensa` (The root node containing everything).
* **Player Scene:** `lulu.tscn` (Including sounds, AnimatedSprite, and attack logic).
* **Enemy Scenes:** Humans and the Cat.
* **Ability/Trap Scenes:** Bark shockwave and Poop mine.
* **UI Scenes:** Start Menu, Victory, and Game Over screens.
* **Stamina System:** Consumption management per action and recovery via rest.

## 8. Technical Specifications
* **Nodes:**
    * `CharacterBody2D` (Lulu) with `AnimatedSprite2D`.
    * `Area2D` for bark projectiles and poop mines.
    * `Marker2D` in each lane for precise enemy spawning.

## 9. Dynamic Difficulty and Extra Features
### 9.1 "Power Bark"
If Lulu has 100% stamina, the first bark is a "Super Bark" that affects all 3 lanes simultaneously.

### 9.2 Nap Mode
At the 60-second mark, the owner appears in a window and cheers for Lulu, entering an infinite energy mode for a few seconds.
