# The Fractured Way - Changelog

This file tracks development milestones, gameplay systems, improvements, and fixes made during the development of The Fractured Way.
## November 28, 2026

### Added

- **Complete Multi-Layer Rock Explosion VFX:** Expanded the original Niagara dust prototype into a comprehensive explosion effect combining multiple dust bursts, a radial shockwave, and smaller drifting dust particles.
- **Secondary Dust Burst:** Implemented `Dust_Burst_B`, introducing an additional animated dust layer to increase explosion volume and improve visual density.
- **Animated Shockwave Effect:** Developed a rapidly expanding shockwave using custom 4×4 flipbook textures, six-way lighting, and lifetime-based particle scaling.
- **Residual Dust Particles:** Added smaller dust puffs that expand and dissipate independently of the primary explosion, providing additional visual depth.
- **Additional VFX Materials:** Created specialized materials for secondary dust, shockwave, and smaller dust effects using the existing six-way lighting framework.
- **Projectile Explosion Integration:** Integrated the Niagara explosion system into `BP_ProjectileDestruction`, triggering the visual effects at the projectile's impact location alongside Chaos destruction.
- **Radial Player Knockback:** Implemented a sphere-overlap detection system that identifies players near the explosion and launches them away from the impact point without causing death.
- **Directional Knockback Calculation:** Added vector-based launch calculations using player position, explosion location, normalized direction, and upward velocity to produce more convincing explosive force.
- **Direct-Hit Death Impulse:** Added directional impulse calculations that allow projectile impacts to propel the player's ragdoll backward upon death.

### Improved

- **Explosion Visual Quality:** Refined particle sizes, outward velocities, expansion curves, and opacity fading to produce a larger, faster, more forceful rock explosion.
- **Dust Layering:** Combined primary and secondary dust bursts with smaller particles to create a more cohesive explosion rather than a single uniform dust cloud.
- **Shockwave Presentation:** Adjusted shockwave orientation, expansion, and fading to produce a more visible radial effect near the impact surface.
- **Ragdoll Knockback:** Improved the consistency of direct-hit death reactions through normalized impact-direction calculations and stronger physics impulses.
- **Projectile Gameplay Feedback:** Established distinct gameplay responses for direct projectile collisions and nearby explosions.
- **Projectile Scaling:** Further reduced the rock Geometry Collection scale to improve projectile proportions and visual consistency.
- **Niagara Particle Behavior:** Tuned particle lifetime, sprite scaling, velocity, and rotation independently across multiple explosion emitters.
- **Explosion Timing:** Coordinated the shockwave and dust layers to create a more pronounced initial impact followed by gradually dissipating dust.

### Fixed

- Fixed inconsistent direct-hit ragdoll reactions that sometimes caused the player to collapse without being propelled backward.
- Resolved the issue allowing the player to mantle onto explosive rock projectiles.
- Corrected shockwave visibility problems caused by sprite orientation and facing-vector configuration.
- Fixed the missing Sprite Renderer reference in Niagara's SubUV Animation module.
- Corrected shockwave animation configuration to use the full 4×4 texture atlas.
- Fixed secondary dust texture configuration to support its 8×8 flipbook animation.
- Prevented explosion-radius knockback from interfering with the existing direct-contact death behavior.
- Improved projectile collision and visual scaling consistency.

### Completed

- **Rock Explosion VFX:** Completed the primary dust burst, secondary dust burst, expanding shockwave, and drifting dust particles.
- **Direct-Hit Death:** Confirmed that direct projectile collisions trigger the player's death system.
- **Explosion-Radius Knockback:** Implemented and tested nonlethal knockback for players caught near the explosion.
- **Ragdoll Impact Response:** Improved and confirmed directional knockback on direct projectile contact.
- **Projectile Mantling Fix:** Resolved the unwanted interaction allowing the player to mantle onto explosive projectiles.
- **Niagara Integration:** Connected the explosion effects to the existing Chaos destruction Blueprint.

### In Progress

- **Distance-Based Camera Shake:** Preparing camera reactions that scale according to the player's proximity to the explosion.
- **Explosion Audio:** Planning realistic rock-impact and explosion sounds with distance attenuation and sound variation.
- **Projectile Performance Testing:** Preparing stress tests involving simultaneous explosions, particle overdraw, and Chaos fragment simulation.
- **Debris Cleanup:** Continuing verification of fragment lifetimes and cleanup behavior after destruction.
- **Projectile Variants:** Planning additional projectile effects and gameplay behavior for future environments.

### Next Development Milestone

Implement distance-based camera shake and explosion audio for normal rock projectiles, followed by final gameplay and performance testing.

**Development Status:** The normal rock projectile's destruction VFX, direct-hit death behavior, explosion-radius knockback, and ragdoll reactions are functional. Camera shake, audio, and final validation remain before the complete rock projectile system is considered finished.

## November 26, 2026

### Added

- **Custom Rock Impact VFX:** Developed a new dust explosion effect for rock projectiles using Blender-generated visual assets and Unreal Engine 5 Niagara.
- **Six-Way Dust Lighting Material:** Created `MM_RockDust`, a custom translucent material supporting six-direction lighting, normal reconstruction, sunlight response, and configurable dust coloration.
- **Dynamic Sunlight and Backscatter:** Implemented directional sunlight calculations and adjustable backscatter controls to give dust a more natural appearance across different lighting conditions.
- **Animated Dust Flipbooks:** Imported and configured 11 custom dust textures, including packed six-way lighting maps and motion-vector textures, using BC7 compression.
- **Niagara Rock Impact Prototype:** Created `NS_RockImpact_Dust_Test`, featuring instantaneous particle spawning, outward velocity, randomized lifetimes, variable sprite sizes, and animated dust clouds.
- **Custom VFX Organization:** Established a dedicated rock-impact asset structure for textures, materials, and Niagara effects to support future projectile variations.

### Improved

- **Rock Fragment Scaling:** Reduced the size of Chaos Geometry Collection fragments to better match the projectile's proportions and prevent overly large debris from dominating impacts.
- **Explosion Force:** Adjusted radial explosion velocity to produce more controlled fragment scattering while preserving the force of the initial impact.
- **Dust Explosion Presentation:** Refined the dust effect into a shorter, more compact burst that better complements the game's visual style and fast-paced parkour gameplay.
- **Particle Movement:** Adjusted Niagara particle velocity and distribution to produce a more cohesive dust cloud rather than widely separated particles.
- **Dust Transparency:** Improved particle opacity and depth fading to soften visible intersections and reduce harsh edges.
- **Projectile VFX Direction:** Established a reusable approach for future destruction effects, including flaming rocks, golden projectiles, environmental hazards, and organic projectiles.

### Fixed

- Corrected excessive Chaos fragment rotation by disabling unwanted torque behavior.
- Reduced unnatural fragment movement and excessive launching through adjustments to explosion forces.
- Fixed incorrect Niagara flipbook sampling caused by configuring an 8×8 texture atlas as a 4×4 grid.
- Fixed dust particles displaying entire texture sheets instead of individual animation frames.
- Corrected inverted dust sprites caused by unwanted particle rotation.
- Improved the appearance of hard, cut-off edges around dust particles.
- Corrected Niagara SubUV texture sampling and synchronized the two packed lighting textures used by the dust material.

### In Progress

- **Rock Impact VFX Refinement:** Configuring sprite expansion and lifetime-based scaling to make the dust burst grow and dissipate more naturally.
- **Niagara System Completion:** Preparing additional dust layers, shockwave particles, and fine debris effects using the generated VFX assets.
- **Projectile Destruction Integration:** Planning to connect the Niagara explosion to `BP_ProjectileDestruction` while preserving the existing C++ collision and Chaos destruction systems.
- **Chaos Physics Polish:** Investigating occasional fragment drifting and physics instability during destruction.
- **Projectile VFX Variations:** Planning additional effects for different projectile types, including fire, metallic impacts, and organic hazards.
- **VFX Performance Testing:** Preparing to evaluate particle performance, transparency overdraw, and simultaneous projectile impacts in gameplay.
## November 17, 2026

### Added

- **Custom Protagonist Overhaul:** Integrated an upgraded protagonist model featuring improved facial anatomy, realistic skin textures, refined clothing geometry, detailed hands, and enhanced facial features.
- **Physics-Based Dreadlocks:** Implemented a separate skeletal hair system with 30 simulated hair bones, individual physics bodies, and configurable constraints, allowing dreadlocks to react dynamically to player movement.
- **Advanced Hair Materials:** Introduced redesigned dreadlocks featuring improved strand geometry, realistic surface textures, natural thickness variation, frizz, and detailed hairline elements.
- **Hair Animation Blueprint:** Developed a dedicated Animation Blueprint using Copy Pose From Mesh and RigidBody simulation, allowing the dreadlocks to follow the character's animations while maintaining independent physics.
- **Character Reveal Renders:** Created multiple cinematic character poses and renders for the game's upcoming official social media reveal.

### Improved

- **Hair Physics Responsiveness:** Adjusted angular damping, spring strength, constraint limits, and velocity response to produce more natural hair movement during running, jumping, falling, and landing.
- **Dreadlock Settling Behavior:** Refined the hair's return-to-rest motion by adjusting base constraint stiffness and damping, reducing slow or unnatural movement while preserving flexibility in the individual strands.
- **Character Appearance:** Improved shoulder positioning, neck proportions, facial likeness, eye materials, facial hair, hoodie geometry, and clothing textures.
- **Character Movement Rotation:** Updated player rotation settings so the camera can rotate independently while the character remains stationary, without requiring turn-in-place animations.
- **Character Animation Integration:** Maintained compatibility between the upgraded skeletal meshes and existing locomotion and parkour animation systems.
- **Character Presentation:** Refined cinematic lighting, posing, hand anatomy, camera framing, and render quality for promotional character screenshots.

### Fixed

- Fixed the character rotating unnecessarily when moving the camera while standing still.
- Fixed the longstanding checkpoint respawn orientation issue that caused the character to consistently face the wrong direction after respawning.
- Corrected unnatural dreadlock movement caused by incorrect physics settings on supporting skeleton bodies.
- Fixed excessively stiff hair movement by refining physics damping and constraint spring settings.
- Resolved initial animation compatibility issues encountered while testing upgraded character meshes in duplicated Blueprints.
- Corrected visual issues in character renders, including awkward arm positioning, unnatural finger poses, and excessive rendering noise.

### In Progress

- **Projectile Explosion Polish:** Continuing development of the Chaos-based projectile destruction system, including more consistent impacts, fragment scattering, and explosive visual effects.
- **Explosion Effects:** Planning improved dust clouds, debris particles, impact audio, radial player damage, and camera shake.
- **Hair Performance Optimization:** Evaluating the performance impact of the redesigned high-detail dreadlocks.
- **Level Progression:** Planning a revised eight-level structure with a more deliberate difficulty curve and stronger integration of the game's narrative.
- **Social Media Reveal:** Preparing the first official character reveal for The Fractured Way.

## November 10, 2026

### Added

- **Chaos Projectile Destruction:** Implemented a physics-based destruction system using Unreal Engine's Chaos Geometry Collections, allowing rock projectiles to fracture into individual pieces upon impact.
- **Explosive Fragment Physics:** Integrated a custom Chaos Master Field that applies radial and angular velocity to shattered projectiles, launching fragments outward with explosive force and realistic tumbling.
- **Reusable Destruction Framework:** Developed a C++ and Blueprint interface system that spawns destructible Geometry Collections when projectiles collide with environmental objects, supporting future projectile variations.
- **Debris Lifetime Management:** Added automatic cleanup for shattered projectile fragments, removing debris after a short lifespan to prevent unnecessary physics simulation.

### Improved

- **Projectile Collision Detection:** Refined collision handling using a dedicated collision sphere, improving projectile interactions with walls, terrain, and other physical objects.
- **Projectile Spawning Reliability:** Resolved issues involving projectiles colliding with their own launchers or other projectiles, preventing premature destruction.
- **Impact Responsiveness:** Improved the transition between projectile collision and Chaos destruction, allowing rocks to fracture and scatter at the point of impact rather than relying on subsequent environmental collisions.
- **Destruction Visuals:** Adjusted fracture strain, radial velocity, and angular physics settings to produce more impactful rock explosions.
- **C++ and Blueprint Integration:** Improved communication between projectile impact events and destruction Blueprints, resolving issues where the destruction interface failed to execute.

### Fixed

- Fixed projectiles passing through walls due to incorrect collision settings.
- Fixed projectile meshes appearing offset from their collision components.
- Fixed projectiles disappearing immediately after spawning due to unintended collisions.
- Fixed Chaos destruction events failing to trigger through the Blueprint interface.
- Corrected C++ projectile spawner implementation and restored distance-based spawning functionality.

### In Progress

- Refining Chaos destruction consistency across different collision surfaces and environmental objects.
- Planning explosion damage radius and physics-based ragdoll knockback for nearby players.
- Adding Niagara dust, debris particles, and impact audio to enhance destruction effects.
- Continuing performance testing to ensure Chaos physics remains efficient during repeated projectile impacts.
  
## November 7, 2026
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
- **Engine Upgrade:** Migrated *The Fractured Way* from Unreal Engine 5.4 to Unreal Engine 5.8 to continue development on a newer engine version.

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
