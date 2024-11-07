# Gishushu Traffic Lights System

## Overview
The Gishushu Traffic Lights system manages the flow of vehicles and pedestrians at a cross intersection with four main directions: North, South, East, and West. Each direction is equipped with standard traffic lights (red, yellow, green) for vehicles and pedestrian lights (red, green). The system is designed to alternate the green, yellow, and red lights in a cycle to ensure smooth traffic flow while prioritizing pedestrian safety.

![Gishushu Traffic Lights Diagram](traffic\state\diagram.png)
## Objects
- **Routes (Directions)**: North, South, East, West
- **Traffic Lights**:
  - **Vehicle Lights**: Red, Yellow, Green for each direction (North, South, East, West)
  - **Pedestrian Lights**: Red, Green (synchronized with each direction)

## Traffic Light States and Cycle
The traffic light cycle operates as follows for each direction:

1. **Green (Vehicles)**:
   - The active direction allows vehicles to move with a **green** light.
   - Pedestrian light for the active direction is **red** (no pedestrian crossing).
2. **Yellow (Transition)**:
   - The active direction's light changes from green to **yellow**, signaling vehicles to prepare to stop.
   - Pedestrian light for the active direction changes to **green**, allowing pedestrians to cross.
3. **Red (Stop)**:
   - The active direction's light transitions to **red** after the yellow state.
   - Pedestrian light for the active direction also turns **red**.
   - A new direction then gets the **green** light, continuing the cycle.

## Detailed State Cycle
1. **North Green (Active)**:
   - **North** has the green light for vehicles; pedestrians wait (red light).
   - **South, East, and West** have red lights for vehicles and green pedestrian lights.
2. **North Yellow (Transition)**:
   - North changes to yellow; pedestrians can cross with a green pedestrian light.
   - South, East, and West remain red for vehicles.
3. **North Red (Stop)**:
   - North changes to red for both vehicles and pedestrians.
   - **South** gets the green light, beginning a new cycle for the South direction.
4. This cycle continues similarly for **South**, **East**, and **West** directions, each following the sequence of green, yellow, and red lights with synchronized pedestrian signals.

## Pedestrian Signals
Pedestrian signals are synchronized with vehicle lights to ensure safety:
- When a direction is green for vehicles, the pedestrian light is red.
- When a direction changes to yellow (vehicles slowing down), the pedestrian light turns green to allow safe crossing.
- When the vehicle light turns red, the pedestrian light also turns red.

## System Flow Summary
The system continuously cycles through the following order:
1. **North Green → North Yellow → North Red**
2. **South Green → South Yellow → South Red**
3. **East Green → East Yellow → East Red**
4. **West Green → West Yellow → West Red**

This structured flow manages vehicle movement and pedestrian crossing at the Gishushu intersection, providing a safe and efficient experience for all road users.
