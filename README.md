# SkyTrack Mission Studio (Desktop)

> **Part of SkyTrack** - The Operating System for Autonomous Missions.
> *Design Logic Once, Validate Virtually, Fly Anywhere.*

## ⚡ What is this?
The centralized command interface for SkyTrack. It serves as the **Application Plane** where engineers design **Hybrid Missions** (Visual + Code), validate reliability via **Digital Twin**, orchestrate mixed fleets, and **generate post-mission intelligence** (Reports/Maps).

## 🎯 Who this is for
Built for **Mission Builders** & **Robotics Engineers** who need to:
- **Stop rewriting code:** Abstract away hardware differences (PX4/DJI).
- **Code with context:** Inject custom scripts into visual flows without rebuilding firmware.
- **Close the Data Loop:** Automate the generation of inspection reports and maps immediately after flight.

## 🛠 Key Capabilities
Matches the Core Platform Capabilities defined in SkyTrack Architecture:
- **Hybrid Mission Architecture:** The best of both worlds. Design mission flow using **Visual Logic Blocks** for speed, OR inject **Custom Python/C++ Nodes** for complex algorithmic logic.
- **Digital Twin & Environmental Intelligence:** A unified 3D environment for **Instant Sim2Real Validation**. Visualize **3D Reality Layers** (LiDAR/Maps) to plan missions with context-aware precision.
- **Universal Hardware Abstraction:** The "Write Once, Fly Anywhere" layer. Deploy the same mission logic to custom Pixhawk drones or legacy DJI fleets via the unified control plane.
- **Automated Reporting & Analytics:** Turn telemetry into value. Automatically generate **Compliance Reports**, **Crop Health Maps**, or **Inspection Logs** immediately upon mission completion.

## 🔄 The Sim-to-Real Workflow
1. **Design:** Define intent using Visual Blocks or **inject custom code** via the embedded IDE.
2. **Validate:** Trigger **Instant Sim2Real Validation** to test edge cases (e.g., "What if battery < 20%?") in the Digital Twin.
3. **Deploy:** Push to the **Universal Hardware Abstraction** layer on the physical fleet.
4. **Operate & Analyze:** Monitor secure live telemetry and receive **Automated Mission Reports** post-flight.


## 🧩 Architecture Context
How this component fits into the SkyTrack Ecosystem:

```mermaid
graph TD
    %% Define Nodes
    Studio["Mission Studio (Application Plane)"]
    Core["Core Orchestration (Orchestration Plane)"]
    HAL["Universal Hardware Abstraction (Execution Plane)"]
    
    subgraph Targets [Deployment Targets]
        Real["Physical Hardware"]
        Sim["Digital Twin Engine"]
    end

    %% Define Relationships
    Studio <-->|Intent & Logs| Core
    Core <-->|Signed Commands| HAL
    HAL -->|Real Control| Real
    HAL -.->|Simulated Physics| Sim

    %% Styling (Optional - for better visibility in dark mode)
    classDef plain fill:#fff,stroke:#333,stroke-width:2px,color:#000;
    class Studio,Core,HAL plain;
