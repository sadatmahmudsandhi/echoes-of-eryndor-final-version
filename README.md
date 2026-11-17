# Echoes of Eryndor

> **A first-person sci-fi survival experience aboard a failing orbital spacecraft, where every system decision matters.**

[![Godot](https://img.shields.io/badge/Engine-Godot%204.7-478CBF?logo=godot-engine&logoColor=white)](https://godotengine.org/)
[![Language](https://img.shields.io/badge/Language-GDScript-478CBF)](https://docs.godotengine.org/en/stable/)
[![Genre](https://img.shields.io/badge/Genre-Sci--Fi%20Survival-6C5CE7)](#)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview

**Echoes of Eryndor** is a 3D first-person science-fiction survival game built with Godot. The player explores an orbital spacecraft during a critical systems failure and must manage ship resources, interact with equipment, and complete emergency objectives before orbital decay becomes fatal.

The project combines spacecraft exploration, environmental interaction, system telemetry, and a time-sensitive reactor-stabilization objective.

## Features

- **First-person 3D exploration** of interconnected spacecraft areas, including corridors, crew spaces, a medbay, storage, a cockpit, and reactor facilities.
- **Player movement** with walking, sprinting, jumping, mouse-look, and step-climbing support.
- **Interactive spacecraft equipment** such as terminals, doors, pressure valves, holographic interfaces, and the reactor core.
- **Interaction prompts and visual feedback** to help identify usable objects.
- **Survival telemetry** tracking oxygen, cabin carbon-dioxide partial pressure, orbital velocity, and mission countdown.
- **Power-grid trade-offs** between Environmental Control and Life Support Systems (ECLSS), communications, and propulsion.
- **Mission progression and failure states**, including orbital re-entry and oxygen depletion.
- **Reactor stabilization objective** that requires the player to complete prerequisite actions before ignition.
- **Sci-fi interface styling** using a custom Godot UI theme and project assets.

## Tech Stack

| Technology | Purpose |
|---|---|
| [Godot Engine 4.7](https://godotengine.org/) | 3D game engine |
| GDScript | Gameplay logic and interaction systems |
| Godot 3D physics (Jolt) | Character and environment physics |
| Godot scenes (`.tscn`) | Levels, objects, UI, and reusable game components |
| Godot resources and imported assets | Materials, textures, audio, models, and visual effects |

## Prerequisites

Before running the project, install:

- **Godot Engine 4.7** or a compatible Godot 4.x build. The project configuration declares Godot 4.7 features.
- Git, if you plan to clone the repository from GitHub.
- A desktop environment capable of running Godot's Forward+ renderer.

> The project is configured for the **Forward+** renderer and a 1920 × 1080 viewport. Performance will depend on your hardware and the included 3D assets.

## Installation & Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/YOUR-USERNAME/echoes-of-eryndor.git
   ```

2. **Move into the project directory:**

   ```bash
   cd echoes-of-eryndor
   ```

3. **Open the project in Godot:**

   - Launch Godot Engine.
   - Choose **Import** or **Import Existing Project**.
   - Select the `project.godot` file inside the cloned folder.
   - Allow Godot to scan and import the project assets.

4. **Run the game:**

   - Open the project in the Godot editor.
   - Press **F6** to run the current scene, or **F5** to run the configured main scene.

   You can also launch the project from a terminal if the Godot executable is available on your system:

   ```bash
   godot --path . --editor
   ```

   To run the project without opening the editor:

   ```bash
   godot --path .
   ```

   If your executable is named `godot4`, replace `godot` with `godot4`.

## Usage

### Basic controls

The project defines input actions for movement, sprinting, interaction, and UI cancellation. The interaction action is also explicitly supported through the **E** key, and **Shift** is supported for sprinting.

| Action | Input |
|---|---|
| Move | Movement actions configured in **Project → Project Settings → Input Map** |
| Sprint | `Shift` |
| Interact with highlighted object | `E` |
| Toggle mouse capture | `Esc` |
| Jump | `Space` (`ui_accept`, according to the project input map) |

> **Note:** Review the Input Map in the Godot editor to confirm or customize the movement-key assignments for your preferred layout.

### Gameplay objective

1. Explore the spacecraft and locate the interactive systems needed for the emergency procedure.
2. Use the available terminals and equipment to progress through the ship.
3. Monitor oxygen, CO₂ partial pressure, orbital velocity, and the countdown displayed by the HUD.
4. Reroute power to bring communications and propulsion online when required.
5. Vent the air-terminal pressure before attempting reactor ignition.
6. Activate the reactor core after its prerequisites are satisfied.

The mission can fail if the orbital countdown expires or the oxygen supply is depleted. The current implementation also includes status messages for locked equipment and mission outcomes.

### Interaction system

Look at an interactive object to display its prompt. Press `E` to activate it. Depending on the object, interaction may play audio or an animation, update the HUD, highlight the object, or unlock a door.

## Project Structure

```text
echoes-of-eryndor/
├── addons/
│   └── pixel_ui_scifi/       # Sci-fi UI theme and interface assets
├── engine/                   # Additional engine/project resources
├── game assts/               # Game art and supporting assets
├── scene/                    # 3D levels and reusable scene files
│   ├── main.tscn
│   ├── cockpit.tscn
│   ├── control_center.tscn
│   ├── corridor.tscn
│   ├── Medbay.tscn
│   ├── reactor.tscn
│   └── ...
├── script/
│   ├── gamestate.gd          # Global mission state, telemetry, and signals
│   ├── character_body_3d.gd  # Player movement and interaction detection
│   ├── InteractableProp.gd   # Interactive object behavior
│   └── gate_door.gd          # Door locking and animation behavior
├── HUD.gd                    # HUD telemetry and mission messages
├── TAB RED.gd                # Animated status-screen behavior
├── fan.gd                    # Fan animation behavior
├── icon.svg                  # Project icon
└── project.godot             # Godot project configuration and main scene
```

*Folder names are shown as they appear in the project archive.*

## Contributing

Contributions, bug reports, and suggestions are welcome.

1. Fork the repository.
2. Create a feature branch:

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. Make your changes and test them in Godot.
4. Commit with a clear message:

   ```bash
   git commit -m "Add: describe your change"
   ```

5. Push your branch and open a Pull Request describing what changed and why.

For larger changes, open an issue first to discuss the proposed feature or approach. Please keep scene and script naming consistent with the existing project.

## License

This project is intended to use the **MIT License**. Add a `LICENSE` file containing the full MIT License text and update the badge above if a different license is selected.

---

**Project note:** This README is based on the project files provided. The archive does not include a separate release build or a confirmed test report, so the project status is marked as *In Development*.
