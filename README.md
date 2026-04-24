# SUBNET LIFT – Vertical Order

**SUBNET LIFT** is a high-stakes, cyberpunk-themed elevator management simulator. In a vertical mega-tower where social class determines your survival, you operate the lift systems that keep the gears of the city turning.

## 🏙️ The Setting
The tower is divided into distinct zones:
- **0-5**: The Private Ground Exit / Executive Entry.
- **6-19**: The Worker Hubs (Habitation Units).
- **20-29**: The Penthouse Executive Suites.

## 🛂 Social Stratification
Passengers are divided into three classes:
- **EXECUTIVES (Magenta Diamond)**: High weight (2.0), extremely impatient (15s), high rewards + speed bonuses.
- **WORKERS (Cyan Rectangle)**: Standard weight (1.0), moderate patience (30s).
- **DRONES (Lime Green Drone)**: Low weight (0.5), high patience (60s), low rewards.

## 🎮 Game Modes
- **MANUAL PLAY**: Direct intervention using on-screen control panels and floor-click dispatching.
- **CODING MODE**: A programmatic interface (inspired by Elevator Saga) where you write JavaScript to automate the tower's logistics.

## 🛠️ Upgrade System
Earn credits by delivering passengers and spend them in the **Point Shop**:
- **Elevator Speed**: Reduce floor-to-floor travel time.
- **Capacity**: Increase the total weight each car can handle.
- **Acceleration**: Boost door opening and closing speeds.
- **Fleet Expansion**: Unlock up to 4 elevators total.
- **VIP Priority**: Increase Executive patience.
- **Drone Replicator**: Increase credit yield from service drones.

## 📜 Coding API
In **Coding Mode**, you have access to:
- `elevators`: Array of `Elevator` objects.
  - `goToFloor(n)`: Queue a floor.
  - `stop()`: Clear queue and idle.
  - `on("idle", callback)`: Triggered when queue is empty.
  - `on("floor_reached", callback)`: Triggered when car arrives.
- `floors`: Array of `Floor` objects.
  - `on("button_pressed", callback)`: Triggered when a call is made.
  - `waitingPassengers()`: Metadata about current lobby.

## 🚀 Getting Started
1. Open `index.html` in any modern browser.
2. Select your interface.
3. Keep **System Load** low and **Corporate Compliance** high to avoid an **Order Breach**.

---
*Created by Antigravity AI for the SOUMILCHANDRA Mega-Tower.*
