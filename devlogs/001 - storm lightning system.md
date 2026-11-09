# Storm Lightning System

## Overview

Storming Peaks uses a dynamic lightning system built with Unreal Engine 5 Blueprints and Niagara.

The system randomly selects predefined strike locations throughout the environment and synchronizes lightning bolts with rapid exposure flashes.

## How It Works

The storm controller waits for a random amount of time before triggering a lightning strike.

Each strike:

1. Chooses a random strike location
2. Moves the Niagara lightning effect to that location
3. Activates the lightning bolt
4. Triggers a rapid double-flash using Post Process exposure
5. Deactivates the lightning effect
6. Plays thunder
7. Waits a randomized amount of time before triggering another strike

## Random Strike Locations

Target Points are placed throughout the level and stored inside an array.

A random array item is selected whenever lightning is triggered.

This allows lightning to appear at different locations instead of repeatedly striking the same position.

## Background and Parkour Lightning

The system is being designed with two types of strikes:

### Background Strikes
Used primarily for atmosphere and environmental effects.

### Parkour Strikes
Planned gameplay hazards that will strike playable areas and kill the player if within range.

The system can randomly choose between background and parkour locations.

## Niagara

The visible lightning bolt was created using Niagara's Dynamic Beam system.

The effect uses:

- Beam rendering
- Position jitter
- Custom beam width
- Blue-white coloring
- Short activation duration

## Lightning Flash

A Post Process Volume is temporarily modified during each strike.

The exposure sequence creates a double-flash effect:

2.8 → 1.78 → 2.5 → 1.78

Short delays between each exposure change within the Pos Process Volume simulate the irregular flickering of lightning.

## Current Status

Implemented:

- Randomized lightning timing
- Random background strike locations
- Niagara lightning bolt
- Double exposure flash
- Repeating storm cycle
- Parkour course strike locations
-  Player death by lightning
  
In Progress:
- Thunder audio
