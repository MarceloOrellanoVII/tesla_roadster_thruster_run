Act as an expert WebGL / Three.js game developer. Create a fully self-contained 3D browser mini-game in a SINGLE HTML file (including CSS and JavaScript).

### 🎯 Core Concept & Lore
The game features the new Tesla Roadster with its SpaceX cold-gas thruster package. The player drives along a endless 4-lane circular/oval highway track, avoiding traffic and signs while utilizing thruster flight to jump or fly over obstacles.

---

### 🕹️ Gameplay & Controls
1. **Movement Controls**:
   - `W` / `Up Arrow`: Accelerate forward.
   - `S` / `Down Arrow`: Brake / Reverse.
   - `A` / `Left Arrow` & `D` / `Right Arrow`: Steer left and right across the 4 lanes.
   - `Spacebar`: 
     - **Tap**: Jump off the ground.
     - **Hold**: Engage SpaceX thrusters to hover/fly upward into the air.

2. **Fuel / Thruster Meter Mechanics**:
   - Thruster gauge capacity lasts for **5 seconds** of continuous flight.
   - When the Spacebar is released or fuel hits 0%, the car gently glides back down to the road.
   - **Recharge**: Fuel fully replenishes automatically over **6 seconds** when not actively thrusting. Display a visible Thruster HUD gauge (color shifts from Cyan when ready to Red when empty).

3. **Track & Obstacles**:
   - A curved/circular 4-lane asphalt track with glowing lane dividers.
   - **Obstacles**:
     - Stationary / slow-moving traffic cars occupying random lanes.
     - Roadside / lane signs that crash the player if hit at low altitude.
   - **Collision Logic**:
     - Player can fly safely *over* obstacles if altitude is higher than the obstacle bounding box.
     - Colliding with a car or sign counts as a **Fail** (resets current run timer and speed).

4. **Win Condition & Goal**:
   - Objective: Overtake as many traffic cars as possible in **under 1 minute (60 seconds)**.
   - Display a live scoreboard showing: Time Remaining, Top Speed (MPH/KMH), Cars Overtaken, and Thruster Fuel %.

---

### 📷 End Game & Screenshot Feature
- When time expires or when the player finishes a 60-second run:
  - Freeze gameplay and display a stylized **Victory/Summary Screen**.
  - Show key stats: Total Overtakes, Peak Speed, and Overall Rank.
  - Include a working **"Share Speed Screenshot"** button (`<button>`).
  - Use HTML5 Canvas `.toDataURL('image/png')` or HTML2Canvas to capture the current screen and download a timestamped screenshot image (`Tesla_Roadster_Score.png`).

---

### 🎨 Visuals & Aesthetics
- **Graphics Framework**: Standard `Three.js` loaded via CDN (`https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js`).
- **Vehicle Model**: Construct a stylized procedural 3D Tesla Roadster using Three.js primitive geometries (low-poly sleek body, glowing taillights, translucent glass canopy, and underside thruster particle emitters).
- **Thruster Effect**: Emit continuous blue/white glowing flame particles underneath the car when the Spacebar is held.
- **Lighting**: Cyberpunk / futuristic night environment with neon road markings, street lights, and dynamic car headlights.

---

### 💻 Technical Rules
- Everything (HTML structure, CSS styles, canvas elements, and JS game logic) MUST be contained within one single `.html` file.
- Ensure the game starts automatically or via a simple overlay "START" button.
- Handle window resizing gracefully with responsive canvas scaling.
