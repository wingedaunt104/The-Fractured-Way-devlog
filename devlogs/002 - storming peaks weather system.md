# Storming Peaks Weather System

## Overview

This update completed the core dynamic weather system for Storming Peaks.

The system combines GPU-based rain, randomized lightning, distance-aware thunder, environmental audio, and respawn-safe weather behavior while keeping performance stable during gameplay.

## Rain System

- Added Niagara-based rain throughout Storming Peaks
- Moved the primary rain emitter to GPU Compute Simulation for improved performance
- Attached the rain system to the player so the effect remains consistent throughout traversal
- Added level-specific rain logic so the system only activates in Storming Peaks
- Added automatic rain reattachment after player death and respawn
- Added looping rain ambience to reinforce the storm environment
- Adjusted Niagara settings after testing CPU and GPU particle performance

## Lightning System

- Added randomized background lightning strikes
- Added randomized parkour lightning strike locations
- Added localized warning audio before hazardous strikes
- Added lethal strike-radius detection using player-to-strike distance
- Integrated lightning deaths with the existing ragdoll and respawn system
- Increased random spacing between strikes for more natural storm pacing

## Thunder System

- Added separate close and distant thunder sound pools
- Added randomized thunder sound selection to reduce repetition
- Added distance-based selection between sharp close thunder and distant rolling thunder
- Added distance-based thunder delays to simulate sound travel time
- Added spatialized thunder playback at lightning strike locations

## Performance Optimization

The original rain setup relied more heavily on CPU particle simulation and collision-event processing, which caused performance to degrade during longer play sessions.

The system was reworked to:

- Use GPU Compute Simulation for the primary rain emitter
- Reduce unnecessary Niagara collision-event processing
- Remove expensive splash-event behavior from the main rain emitter
- Preserve the large-scale storm effect while improving runtime stability
- Prioritize reliable gameplay performance over unnecessary particle complexity

## Gameplay Integration

Weather behavior is integrated with the existing respawn system.

When the player respawns in Storming Peaks:

- The current level is checked
- The newly spawned player character is referenced directly
- The rain system is attached to the new character
- Weather effects remain isolated from other levels

## Completed

- Dynamic GPU rain
- Rain ambience
- Player-following rain
- Respawn-safe rain attachment
- Level-specific weather activation
- Randomized lightning
- Parkour lightning hazards
- Warning audio
- Distance-aware thunder
- Randomized thunder variation
- Storm performance optimization

## In Progress

- Adding lightning impact explosion effects
- Continuing development of the Storming Peaks parkour course
- Expanding ruins and traversal sections
- Final lighting and atmosphere polish
