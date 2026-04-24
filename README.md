# SUBNET LIFT – Vertical Order

**SUBNET LIFT** is a high-fidelity, standalone elevator logistics simulation set in a corporate dystopia cyberpunk future. As the Master of Vertical Order, you are responsible for maintaining the flow of a 30-floor vertical mega-tower where social class determines survival.

## 🏗️ Core Game Mechanics
Manage a fleet of elevators across 30 floors. Passengers from three distinct social classes spawn with varying priorities:
- **EXECUTIVES (Magenta)**: Corporate elite. Extremely impatient (15s wait limit). High reward (20 CR) but heavy capacity impact (2.0 units).
- **WORKERS (Cyan)**: Middle class. Moderate patience (30s). Standard rewards (10 CR).
- **DRONES (Acid Green)**: Low-class service units. Patient (60s) but low reward (5 CR).

## 🎮 Dual Operation Modes
Choose your interface at startup:
- **🕹️ MANUAL_CONTROL**: Direct hands-on management. Use the floor strip to call elevators and the HUD to dispatch units. Features a `DISPATCH_ALL` protocol for automated nearest-call assignment.
- **💻 LOGISTICS_CODING**: Programmatic optimization. Write your own JavaScript automation scripts in the built-in terminal. Use the provided API to listen to elevator events (`on("idle", ...)`), pass floor boundaries, and set destinations.

## 💰 Scoring & Progression
- **Streak Multipliers**: Deliver units in rapid succession to build your delivery streak and multiply rewards.
- **Time Bonuses**: Rapid delivery (within 50% patience) yields a 1.5x credit bonus.
- **Infrastructure Shop**: Spend your hard-earned Credits (CR) on permanent upgrades:
  - **Elevator Speed**: Reduce floor-to-floor travel time.
  - **Max Capacity**: Increase the weight each car can handle.
  - **Fleet Expansion**: Deploy up to 4 elevators simultaneously.
  - **VIP Priority**: Grant Executives more patience via priority lanes.

## ⚠️ System Stability
- **Unserved Threshold**: If 20 passengers leave the system due to impatience, the vertical order collapses (Game Over).
- **Load Breach**: If more than 40 passengers are waiting simultaneously, the system overloads.

---
**MAINTAIN THE ORDER. EARN YOUR CREDITS.**

---
## 🌆 The Vertical Divide: Lore
The Tower is not just a building; it is a self-contained ecosystem.
- **Zones 0-5**: The Drone Recharge & Service Docks.
- **Zones 6-19**: The Proletariat Habitation Units.
- **Zones 20-29**: The Neon Penthouses (Executive Airspace).

Failure to maintain the flow of these zones results in "Resolution Breach"—a total shutdown of the sector's logistics.

## 🛠️ Technical Architecture
- **Sim-Render Decoupling**: The game uses a fixed-timestep simulation loop independent of the `requestAnimationFrame` render loop, ensuring consistency across high-refresh monitors.
- **Sandboxed Scripting**: Logic Mode utilizes a `new Function` constructor within an isolated world object, preventing accidental interference with the core UI.
- **Procedural HUD**: The UI is built using vanilla DOM elements with `backdrop-filter` for a modern, hardware-accelerated glass effect.
