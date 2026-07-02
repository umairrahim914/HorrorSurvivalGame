# 🔦 Procedural Horror Survival Game

A atmospheric, first-person horror survival game built in Unity (C#). Players are trapped in a procedurally generated environment with an intelligent enemy AI, relying on a flickering flashlight to navigate, survive, and locate the escape zone before being hunted down.

---

## 🎮 Game Overview & Mechanics
* **Survival Gameplay:** Navigate a dark environment to locate the **Finish Zone** while managing a failing flashlight.
* **Dynamic Environments:** Features an environment where obstacles (such as trees and blockades) spawn procedurally at runtime.
* **Intelligent Enemy AI:** A monster that dynamically hunts, tracks, and patrols using complex line-of-sight verification.
* **Dynamic Audio System:** Features an immersive audio layout where footstep pitches shift dynamically, and a horror heartbeat soundtrack automatically scales its volume up using mathematical interpolation as the monster closes in.

---

## 🛠️ Core Technical Features (Code Architecture)

### 🧠 Advanced NavMesh AI Architecture
* **Runtime Navigation Mesh Baking:** Uses Unity's modern `NavMeshSurface` to dynamically generate and rebuild the walkable map blueprint *at runtime* immediately after procedural map assets finish spawning.
* **Multi-State AI Engine:** Built a clean C# State Machine managing separate structural behaviors for **Baking**, **Patrol/Roaming** (using custom waypoint tolerance algorithms), **Chasing** (utilizing hardware stopping distances), and a lock-on **Jumpscare/Attack state**.
* **Raycast Verification:** Implemented 3D physics raycasting from the enemy’s eyes to handle true Line-of-Sight tracking and prevent the monster from seeing players through solid walls.

### 🏗️ Robust Systems Design
* **Singleton Pattern Architecture:** Implemented decoupled, global manager scripts (`GameManager`, `UiManager`, `AudioManager`) ensuring optimized global communication pathways across disparate scripts without relying on expensive runtime search operations.
* **Asynchronous Timing & Optimization:** Leveraged C# `IEnumerator` Coroutines to handle asynchronous execution blocks safely—such as non-blocking flashlight flicker variations, delayed jumpscare scene routing sequences, and background performance optimization structures.
* **Data Encapsulation:** Extensively utilized `[SerializeField]` attributes across components to isolate internal script state variables while maintaining full operational layout design flexibility directly within the Unity Editor Inspector.

---

## 💻 Tech Stack & Tools Used
* **Game Engine:** Unity (3D Object Architecture, Physics, Blend-Tree Animations)
* **Language:** C# (Object-Oriented Programming)
* **Camera System:** Unity Cinemachine (for smooth tracking, clamping head rotation, and atmospheric camera handling)
* **UI System:** Unity UI Framework + TextMeshPro
