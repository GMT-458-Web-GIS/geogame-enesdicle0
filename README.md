# GMT 458 - Assignment 2: GeoGame Design
## Project Title: "Geo-Dash" 🌍

This document outlines the design, features, and technical stack for the "Geo-Dash" game, fulfilling the "Design of the geo-game" requirement.

### 1. Game Concept & Requirements

"Geo-Dash" is a fast-paced geography game where players race against a 60-second clock to correctly identify as many countries as possible on an interactive world map.

**Core Features (Requirements):**
* **Time Limit:** The game must feature a 60-second countdown timer.
* **Core Mechanic:** Players will be given a country name and must click on that country on the map.
* **Scoring:** Each correct guess awards +1 point. The objective is to achieve the highest score possible before the time expires.
* **Data Source:** A GeoJSON file will be used for country borders and names.
* **Hosting:** The completed application will be hosted as a GitHub Pages site.

---

### 2. Frontend Layout & UI/UX Flow

The interface will be minimalist and clean to keep the player focused on the game, not on distracting UI elements.

**User Flow:**

1.  **Start Screen:**
    * The game title ("Geo-Dash") and a brief "How to Play" description.
    * A large "Start Game!" button to initiate the session.

2.  **Game Screen:**
    * **Header Bar:**
        * `Target: [COUNTRY NAME]` (The current objective).
        * `Time: 60` (A countdown timer that will turn red as it gets low).
        * `Score: 0` (The real-time score).
    * **Map Container:**
        * An interactive, clickable map container occupying ~80% of the screen.

3.  **End Screen:**
    * When the timer hits 0, a modal (pop-up) window will appear over the map.
    * It will display a "Time's Up!" title.
    * "Your Final Score: [SCORE]"
    * A "Play Again?" button to restart the game.

**Layout Sketch:**
*A simple wireframe for the main "Game Screen" is included below to visualize the layout.*

[YOUR SKETCH/DRAWING GOES HERE]
*(You need to add a simple drawing here. You can make it in Paint or draw it on paper and add a photo. Just show simple boxes for the Header, Map, etc.)*

---

### 3. Game Mechanics (Answers to Assignment Questions)

This section directly answers the specific questions from the assignment brief.

#### How the game will progress?
The game is a single 60-second "sprint". There is no difficulty level; the challenge comes from the player's own speed and geographic knowledge.
* When the game starts, a random country name is displayed (`Target: Brazil`).
* The player clicks the map.
* **On Correct Guess:** If the click is within that country's GeoJSON polygon:
    * `Score` is incremented by +1.
    * A brief visual confirmation (e.g., a green checkmark) appears.
    * A new random country is immediately selected (`Target: Australia`).
* **On Incorrect Guess:** If the click is on the wrong country:
    * `Score` does not change.
    * A brief visual error (e.g., a red "X") appears on the clicked spot.
    * The player must continue trying to find the **same target country**.

#### How many questions will there be?
There is an **unlimited** number of questions. The game continuously serves new random countries until the timer expires. Success is measured by how many correct answers can be "dashed" through in 60 seconds.

#### How many lives, if any?
There are **no lives**. The penalty for a wrong guess is not losing a life, but **losing time**. The player cannot advance to the next question (and next point) until they find the correct country, forcing them to spend precious seconds on their mistake.

---

### 4. JavaScript Library Selection

#### State which JS library you are planning to use.
* **Core Map Library: `Leaflet.js`**
    * **Reason:** Leaflet is a lightweight, easy-to-use, and well-documented library. It is perfect for this project's needs, which are primarily: loading a GeoJSON layer, styling it, and handling `on-click` events to identify features.
* **Bonus Library (Potential): `Chart.js`**
    * **Reason:** If the core game mechanics are completed with time to spare, I plan to use `Chart.js` as a bonus feature. On the "End Screen," it could display a simple donut chart summarizing the player's performance (e.g., "15 Correct Clicks" vs. "5 Incorrect Clicks"). This would demonstrate the use of an advanced data visualization package.[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/BhShQpq1)
