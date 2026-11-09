# Unreal Engine 5.8 Migration, Performance Optimization & New Protagonist

## Overview

Over the past few weeks, development on *The Path* has shifted toward improving performance, updating the game's technical foundation, and establishing a more distinct identity for its main character.

The project has been migrated from Unreal Engine 5.4 to Unreal Engine 5.8. I also completed a major optimization pass across the game's levels, with particularly noticeable improvements in Storming Peaks and Forested Lands.

One of the biggest additions is a new custom protagonist model, replacing the generic appearance previously used during development. The character now has working animations and physics, with further visual and movement polish planned.

## Migrating to Unreal Engine 5.8

I migrated *The Path* from Unreal Engine 5.4 to 5.8 to continue development using a newer engine version.

This required moving the project into the updated environment and continuing to evaluate existing gameplay systems, assets, materials, and rendering behavior.

The migration also provided an opportunity to revisit performance issues that had become increasingly noticeable as the game's environments expanded.

**[IMAGE 1: Screenshot of The Path running inside Unreal Engine 5.8]**

## Game-Wide Performance Optimization

One of my main priorities was reducing rendering overhead and improving frame-time consistency throughout the game.

As levels became larger and more detailed, unnecessary actors, visual effects, foliage, and environmental objects contributed to increasingly expensive rendering workloads.

I used Unreal Engine's profiling tools to examine frame times, draw calls, and CPU/GPU performance.

The optimization work focused on reducing unnecessary rendering activity while preserving the atmosphere and visual identity of each environment.

### Optimizing Storming Peaks

Storming Peaks was initially one of the most demanding levels, with frame times reaching approximately 27–30 milliseconds during earlier tests.

Profiling revealed that the CPU rendering thread was a major bottleneck. Some of the largest improvements came from removing unnecessary blue fire effects and flame-covered moving objects.

I reduced expensive environmental elements while preserving important visual landmarks and the level's dark, stormy atmosphere.

Following these changes, tested sections of Storming Peaks began running at approximately 14–17 milliseconds per frame, approaching or exceeding the 60 FPS target as seen in the image below.

<img width="1278" height="714" alt="Screenshot 2026-11-08 205150" src="https://github.com/user-attachments/assets/d2a12dc3-4963-4bd9-a5de-31c065b0696b" />


### Optimizing Forested Lands

Forested Lands also underwent additional optimization because of its dense environmental design and large number of placed actors.

At one point, the level contained approximately 6,125 actors, many of which were individually placed trees and environmental objects.

I continued reducing unnecessary foliage and environmental complexity, prioritizing objects that contributed little to the player's immediate surroundings.

The goal was to preserve the forest's atmosphere without maintaining excessive rendering overhead.

Earlier tests showed frame times of approximately 17–22 milliseconds. Following further optimization, tested areas began reaching approximately 12–16 milliseconds, bringing performance much closer to a consistent 60 FPS.

<img width="1280" height="719" alt="Screenshot 2026-11-08 205858" src="https://github.com/user-attachments/assets/24ba16b0-de90-40ab-8293-af0193259b60" />

## Introducing the New Main Character

Another major development milestone was the creation of a custom protagonist for *The Path*.

The game's story follows an ordinary person who is unexpectedly pulled into a strange dimension and must escape by navigating increasingly dangerous environments through parkour.

Unknown to him, a malevolent presence watches his progress throughout the journey.

I wanted the main character's appearance to reinforce the idea that he is an ordinary person caught in an extraordinary situation, rather than a traditional fantasy hero or soldier.

The new model features a realistic human appearance, long dreadlocks, a dark hoodie, cargo pants, and casual footwear.

<img width="679" height="545" alt="Screenshot 2026-11-08 201721" src="https://github.com/user-attachments/assets/b51737e8-9738-4a1d-93d0-1f3e22525c86" />

### Character Rigging, Animation & Physics

Following the model's creation, I worked on making the character functional with the game's existing movement systems.

The new protagonist now supports working skeletal animations and physics, allowing the character to participate in the parkour gameplay rather than remaining a static model.

This is an important step toward giving *The Path* its own recognizable character and visual identity.


https://github.com/user-attachments/assets/9d62d284-9248-4671-89ce-c20fecc323d7



### Future Character Customization

I also plan to introduce unlockable character skins that allow players to customize the protagonist's appearance.

These outfits will provide visual variety while maintaining a consistent character identity.

Keeping compatible skeletal structures across different outfits will help support the existing movement animations and reduce unnecessary animation work.

## Current Status

Completed or implemented:

- Migration from Unreal Engine 5.4 to 5.8.
- Major performance optimization work across the game's environments.
- Storming Peaks improvements, reaching approximately 14–17 ms in tested areas.
- Forested Lands improvements, reaching approximately 12–16 ms in tested areas.
- Custom main character model.
- Functional character animations, rigging, and physics.

## Next Steps

- Continue testing performance throughout every level, especially during active gameplay and environmental hazards.
- Polish the protagonist's movement animations and transitions.
- Continue improving gameplay stability and preparing the game for future testing
- Plan the next levels
- Overhaul animations

