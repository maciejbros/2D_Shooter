# 2D Shooter

2D Shooter is a top-down survival shooter developed in **C++** using the **Allegro 5** multimedia library.

The player controls a character, fights approaching zombies, manages ammunition and collects additional ammo packs. The game includes real-time movement, shooting, enemy AI, collision detection, health systems and audio effects.

## Features

* Top-down 2D gameplay
* Player movement
* Shooting system
* Zombie enemies
* Enemy health system
* Collision detection
* Ammunition management
* Ammo pickups
* Player and enemy health management
* Background music
* Shooting and reload sound effects
* 60 FPS game loop
* Sprite-based graphics
* Game-over handling

## Technologies

* C++
* Allegro 5
* Visual Studio
* vcpkg

The project uses Allegro 5 modules for graphics, images, fonts, audio and input handling. The game initializes the display, event queue and a timer running at 60 FPS.

## Gameplay

The objective is to survive while fighting zombies approaching the player.

The player can move around the game area and attack enemies using a firearm. Zombies have their own health points and are removed from the game after their health reaches zero.

Additional ammunition can be collected from ammo packs placed throughout the game area.

## Game Loop

The game is based on a real-time event loop running at approximately **60 frames per second**.

```text
Initialize Allegro
       │
       ▼
Load graphics and audio
       │
       ▼
Create game window
       │
       ▼
Initialize event queue
       │
       ▼
Start 60 FPS timer
       │
       ▼
┌─────────────────────┐
│     Game Loop       │
│                     │
│  Handle input       │
│  Move player        │
│  Move zombies       │
│  Update attacks     │
│  Check collisions   │
│  Update health      │
│  Draw game objects  │
│  Play audio         │
└──────────┬──────────┘
           │
           ▼
       Game Over
           │
           ▼
     Release resources
```

The main loop processes keyboard and timer events and updates the game state before rendering the next frame.

## Game Components

The project separates the main game entities into individual C++ classes.

### Player

Responsible for representing the player character, including its position, dimensions and interactions with other game objects.

### Zombie

Represents an enemy in the game.

Each zombie has:

* position,
* sprite,
* dimensions,
* health,
* health bar,
* movement logic,
* collision detection.

Zombies start with **3 health points** and move toward the player.

### Attack

Represents projectiles fired by the player and is responsible for handling projectile-related behaviour and collisions.

### Ammo

Represents ammunition pickups available on the map.

Ammo objects can be rendered on the screen and detect collisions with the player, allowing ammunition to be collected.

## Project Structure

```text
2D_Shooter/
│
├── assets/
│   ├── background.png
│   ├── background.wav
│   ├── ak_shot_sound.wav
│   ├── ak47_reload_sound.wav
│   ├── ammo_pickup_sound.flac
│   └── ...
│
├── Ammo.cpp
├── Ammo.h
├── Attack.cpp
├── Attack.h
├── Player.cpp
├── Player.h
├── Zombie.cpp
├── Zombie.h
│
├── strzelanka_2d.cpp
├── strzelanka_2d.sln
├── strzelanka_2d.vcxproj
├── strzelanka_2d.vcxproj.filters
├── packages.config
└── vcpkg.json
```

The main game entities are implemented as separate C++ classes, while `strzelanka_2d.cpp` contains the main application entry point and game loop.

## Resource Management

The project explicitly manages Allegro resources such as:

* displays,
* timers,
* event queues,
* bitmaps,
* fonts,
* audio samples.

Resources are released when the game ends to prevent memory and resource leaks.

## Getting Started

### Requirements

* Windows
* Visual Studio
* C++ compiler
* Allegro 5
* vcpkg

### 1. Clone the repository

```bash
git clone https://github.com/maciejbros/2D_Shooter.git
cd 2D_Shooter
```

### 2. Open the project

Open:

```text
strzelanka_2d.sln
```

in Visual Studio.

### 3. Configure Allegro 5

The project contains `vcpkg.json` and `packages.config` for managing project dependencies.

Make sure the required Allegro 5 libraries are available in the development environment.

### 4. Build and run

Build the solution in Visual Studio and run the application.

Make sure the `assets` directory is available relative to the executable, as the game loads its graphics and audio resources from this directory.

## Purpose of the Project

The project was created to practice:

* C++ programming,
* object-oriented programming,
* game development,
* real-time application loops,
* event-driven programming,
* collision detection,
* resource management,
* multimedia programming,
* working with external libraries,
* handling graphics and audio,
* designing interactions between multiple game entities.

## Author

**Maciej Bros**

GitHub: [@maciejbros](https://github.com/maciejbros)
