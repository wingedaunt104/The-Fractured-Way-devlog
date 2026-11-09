# The Path - Changelog

This file tracks development milestones, gameplay systems, improvements, and fixes made during the development of The Path.

**November 7, 2026**
### Added
- **Custom Protagonist:** Created and integrated a realistic main character featuring dreadlocks, a hoodie, cargo pants, and casual footwear.
- **Character Rigging & Physics:** Successfully implemented working animations, skeletal rigging, and physics for the new character.

### Improved
- **Game-Wide Performance:** Completed a major optimization pass across the game's levels, reducing rendering overhead and improving overall frame rates and gameplay responsiveness.
- **Storming Peaks Optimization:** Reduced unnecessary particle effects and performance-heavy moving objects, bringing frame times to approximately 14–16 ms in tested areas.
- **Forested Lands Optimization:** Optimized foliage density and environmental assets, achieving approximately 12–16 ms frame times in tested areas.
- **Rendering Efficiency:** Reduced unnecessary actors, draw calls, and environmental complexity while preserving each level's atmosphere.

### In Progress
- Further polishing character animations and movement transitions.
- Planning next levels.
- Continuing performance and stability testing across all levels.
  
## November 5, 2026

### Added / Updated
- **Engine Upgrade:** Migrated *The Path* from Unreal Engine 5.4 to Unreal Engine 5.8 to continue development on a newer engine version.

### Improved
- **Storming Peaks Performance:** Significantly optimized the level, reducing frame times from approximately 30 ms to 14–17 ms in tested areas, bringing performance close to a consistent 60 FPS.
- **Environmental Optimization:** Removed unnecessary fire effects, flame-based moving objects, and other performance-heavy environmental elements to reduce rendering overhead.
- **Rendering Efficiency:** Reduced draw calls and improved CPU rendering performance while preserving the level's stormy atmosphere.
- **General Level Optimization:** Continued optimizing environmental assets and effects across multiple levels to improve frame rates and gameplay responsiveness.

### In Progress
- **Forested Lands Optimization:** Began targeting 60 FPS, with current frame times ranging between approximately 17–22 ms (45–59 FPS).
- **Performance Testing:** Continuing to evaluate rendering performance and frame-time consistency across different environments.
- **Engine Compatibility Testing:** Verifying gameplay systems, materials, Niagara effects, and Blueprints following the upgrade to Unreal Engine 5.8.

### Next Steps
- Further optimize Forested Lands toward a consistent 60 FPS.
- Complete full-level performance testing across Storming Peaks and Forested Lands.
- Verify stability and functionality of existing gameplay systems following the engine migration.
## October 2026

- **Storming Peaks Completion:** Completed the main parkour course, including the final traversal sections and level completion trigger. Players can now play through and complete Storming Peaks. Expanded the route with moving rock platforms, ruins, environmental obstacles, and blue flame landmarks.

- **Environment & Visual Guidance:** Improved route readability and environmental composition using blue flames, rock formations, and ruins to guide players through the level. Refined storm lighting, cloud shadows, and ground visibility.

- **Projectile & Level Optimization:** Added distance-based activation for projectile spawners so hazards only fire when the player is within their configured range. Optimized Forested Lands by removing excess trees, grass instances, and redundant trigger boxes while preserving its appearance. Resolved the frame drops previously experienced during traversal and falling in testing.

- **Fixes & Audio:** Fixed moving platforms failing to reset correctly after player death, allowing them to return to their starting positions and be triggered again. Corrected outdoor rain audio playing indoors and added separate indoor rain ambience.

- **In Progress & Planned Improvements:** Continuing work on rain impacts on the player, ground splash effects, and preventing rain from passing through structures. Testing performance across levels and planning an animation overhaul to improve movement presentation and transitions.
## September 2026

- **Storming Peaks Environment:** Began and substantially developed the Storming Peaks parkour level with volumetric storm clouds, atmospheric lighting, lower cloud layers, floating rock formations, ruins, blue environmental flames, modular wall-running surfaces, and an expanded traversal route. Improved fog, lighting, cloud density, environmental composition, level readability, and the Blender-to-Unreal asset workflow.

- **Lightning & Hazards:** Built a dynamic lightning system using Niagara, including randomized background and parkour strikes, localized 3D warning audio, lethal blast zones, player-to-strike distance detection, directional knockback, lightning impact explosions, electric flashes, and outward energy streak effects.

- **Weather & Audio:** Added GPU-simulated player-following rain, automatic rain reattachment after respawn, looping rain ambience, randomized close and distant thunder sound pools, distance-based thunder selection, and realistic thunder delay. Improved storm pacing, spatial audio, thunder variety, and Niagara performance.

- **Death & Ragdoll Systems:** Integrated lightning hazards with the existing death and respawn systems, added physics-based directional ragdoll impulses, supported different impulses for individual hazards, preserved projectile death behavior through fallback logic, and improved overall death feedback.

- **Fixes & Respawn Behavior:** Fixed rain failing to reattach after respawn, projectile deaths breaking the normal respawn sequence, lightning ragdolls launching in the same world direction, and repeating Niagara impact effects. Added moving-platform reset and restart logic so parkour platforms return to their starting state and become usable again after player death.
