# The Path - Changelog

This file tracks major development milestones, gameplay systems, improvements, and fixes made during the development of The Path.
## October 2026

### Added

- Completed the main Storming Peaks parkour course, including the final traversal sections and level completion trigger. Players can now play through and complete the level.
- Added distance-based activation for projectile spawners so hazards only fire when the player is within their configured range.
- Expanded Storming Peaks with moving rock platforms, ruins, environmental obstacles, and blue flame landmarks.

### Improved

- Improved Storming Peaks route readability and environmental composition using blue flames, rock formations, and ruins to guide players.
- Refined storm lighting, cloud shadows, and ground visibility.
- Optimized Forested Lands by removing excess trees, grass instances, and redundant trigger boxes while preserving the forest’s appearance.
- Reduced unnecessary projectile spawning across levels to improve gameplay performance.

### Fixed

- Resolved the frame drops previously experienced while traversing and falling through Forested Lands during testing.
- Fixed moving platforms failing to reset correctly after player death, allowing them to return to their starting positions and be triggered again.
- Rain audio playing indoors

### In Progress

- Finishing rain impact effects on the player and ground splash effects.
- Fix rain going through some structures
- Fix any performance issues between the levels.
- Thinking about how to execute an animation overhaul

## September 2026

- **Storming Peaks Environment:** Began and substantially developed the Storming Peaks parkour level with volumetric storm clouds, atmospheric lighting, lower cloud layers, floating rock formations, ruins, blue environmental flames, modular wall-running surfaces, and an expanded traversal route. Improved fog, lighting, cloud density, environmental composition, level readability, and the Blender-to-Unreal asset workflow.

- **Lightning & Hazards:** Built a dynamic lightning system using Niagara, including randomized background and parkour strikes, localized 3D warning audio, lethal blast zones, player-to-strike distance detection, directional knockback, lightning impact explosions, electric flashes, and outward energy streak effects.

- **Weather & Audio:** Added GPU-simulated player-following rain, automatic rain reattachment after respawn, looping rain ambience, randomized close and distant thunder sound pools, distance-based thunder selection, and realistic thunder delay. Improved storm pacing, spatial audio, thunder variety, and Niagara performance.

- **Death & Ragdoll Systems:** Integrated lightning hazards with the existing death and respawn systems, added physics-based directional ragdoll impulses, supported different impulses for individual hazards, preserved projectile death behavior through fallback logic, and improved overall death feedback.

- **Fixes & Respawn Behavior:** Fixed rain failing to reattach after respawn, projectile deaths breaking the normal respawn sequence, lightning ragdolls launching in the same world direction, and repeating Niagara impact effects. Added moving-platform reset and restart logic so parkour platforms return to their starting state and become usable again after player death.
