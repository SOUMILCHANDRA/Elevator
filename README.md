# SUBNET LIFT – Vertical Order

**SUBNET LIFT** is a high-fidelity, standalone elevator logistics simulation set in a corporate dystopia cyberpunk future. As the Master of Vertical Order, you are responsible for maintaining the flow of a 30-floor vertical mega-tower where social class determines survival.

## 🏙️ The Lore: A Divided Tower
The tower is the heart of the city, but it is deeply stratified:
- **PENTHOUSE (Floors 25-29):** The domain of the Corporate Executives. High stakes, high impatient, high rewards.
- **WORKER HUB (Floors 6-19):** The mid-tier residential and industrial units for the corporate middle class.
- **SERVICE SLUMS (Floors 0-5):** The service layers and drone recharge stations for the lower class.

## 🎮 Dual Control Interfaces
Players can choose their operational protocol at initialization:

### MODE A: MANUAL_CONTROL
- **Direct Dispatch**: Use the **CALL** buttons on the floor strip or the elevator HUD to manually assign floors.
- **Strategic Intervention**: Prioritize high-value Executives during peak load times to maintain compliance.
- **Tactical Overrides**: Command elevators to go to the nearest call or idle at strategic floor intervals.

### MODE B: LOGISTICS_CODING
- **Programmatic Optimization**: Inject JavaScript protocols into the tower's infrastructure.
- **Custom Logic**: Write your own `init` and `update` functions to automate the fleet.
- **Developer Terminal**: A built-in terminal console provides real-time logs and error reporting for your optimization scripts.

## 🧬 Social Stratification System
The simulation handles three distinct classes with unique behaviors:

1. **EXECUTIVES (#ff00c8)**
   - **Patience**: 15s (Extremely Impatient).
   - **Weight**: 2.0 units (Heavy).
   - **Reward**: 20 CR + Speed Bonuses.
   - **Zones**: Spawn at 0-5 or 25-29. Targets 0-5 or 20-29.

2. **WORKERS (#00f0ff)**
   - **Patience**: 30s.
   - **Weight**: 1.0 unit.
   - **Reward**: 10 CR.
   - **Zones**: Spawn at 6-19. Targets any floor.

3. **DRONES (#39ff14)**
   - **Patience**: 60s.
   - **Weight**: 0.5 units.
   - **Reward**: 5 CR.
   - **Zones**: Spawn anywhere 0-24. Targets lower floors.

## 💰 Economic Efficiency & Scoring
Your performance is measured in **Corporate Compliance** and **Credits (CR)**:
- **Time Bonuses**: Delivering a passenger in less than 50% of their patience limit yields a **+50% Credit Bonus**.
- **Wait Penalties**: Delaying a passenger past their 50% threshold incurs a **-1 CR/sec penalty**.
- **Streak Multipliers**: Delivering units within 5s of each other builds a streak (e.g., 1.1x, 1.2x). Batch deliveries are the key to high scores.

## ⚡ Infrastructure Shop (Persistent Upgrades)
Earn credits to permanently upgrade your mega-tower's infrastructure. All purchases persist across browser sessions:
- **Elevator Speed (5 Levels)**: Reduce travel time from 1.0s to 0.15s per floor.
- **Max Capacity (5 Levels)**: Increase car weight limit from 8 to 16 units.
- **Fleet Expansion**: Unlock a **3rd and 4th lift unit** to handle extreme loads.
- **Door Boost**: Reduce door open/close cycles by 30%.
- **VIP Priority**: Grant Executives an extra **+5s patience**.
- **Drone Replicator**: Increase drone delivery value by **+1 CR**.

## ⚠️ Termination Protocols (Loss Conditions)
The system will fail if vertical order collapses:
- **Load Breach**: More than **40 units** are waiting simultaneously.
- **Service Failure**: More than **20 units** are left unserved (departure due to patience timeout).
- **Warning State**: The system enters a warning pulse when the load exceeds 25 units.

## ⚙️ Technical Specifications
- **Standalone Engine**: Pure Vanilla JS, CSS, and HTML5. Zero external dependencies.
- **Fixed-Timestep Physics**: Simulation logic is decoupled from framerate for deterministic behavior.
- **Web Audio API**: Procedural sound generation for UI events and warnings.
- **Secure Sandbox**: User scripts in Coding Mode use isolated scope evaluation with a built-in debug terminal.
- **Persistence**: All logic, upgrades, and high scores are managed via `localStorage`.

## 🛠️ Logistics Coding API
In **LOGISTICS_CODING** mode, your script must be an object with `init` and `update` methods:

```javascript
{
    init: function(elevators, floors) {
        // Initial protocol setup
        elevators.forEach(e => {
            e.on("idle", () => { e.goToFloor(0); });
        });
    },
    update: function(dt, elevators, floors) {
        // Real-time optimization logic
    }
}
```

### Elevator Object API:
- `elevator.goToFloor(num)`: Command to target floor.
- `elevator.currentFloor`: (Float) Current vertical position.
- `elevator.state`: "idle", "moving_up", "moving_down", "open".
- `elevator.loadFactor()`: (Float 0-1) Weight usage.
- `elevator.on(event, callback)`: Events like "idle", "passing_floor", "floor_button_pressed".

### Floor Object API:
- `floor.level`: Floor number (0-29).
- `floor.waitingPassengers()`: List of passengers and their target floors.
- `floor.on("button_pressed", callback)`: Triggered when a call is made.

---
**AUTHORIZATION GRANTED. MAINTAIN THE VERTICAL ORDER.**
