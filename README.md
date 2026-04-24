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
