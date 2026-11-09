# Storming Peaks Completion & Level Optimization


## Overview

Storming Peaks is now playable from start to finish, including its final traversal sections and level completion trigger.

This month’s work focused on finishing the parkour course, improving visual guidance, fixing moving-platform behavior, and reducing performance issues across Storming Peaks and Forested Lands.

## Completing Storming Peaks
<img width="1025" height="549" alt="image" src="https://github.com/user-attachments/assets/8a00176f-4b11-487e-b1c8-60635bc14b15" />

The course was expanded with additional ruins, floating rock formations, moving platforms, and environmental obstacles.

Blue flame landmarks help guide players toward upcoming traversal sections. Integrating these effects into rock formations and ruins helped make the route easier to follow while maintaining the level’s storm atmosphere.

Lighting and cloud shadows were also adjusted to improve ground visibility during traversal.

## Distance-Based Projectile Spawning

As the levels grew, projectile launchers were firing even when the player was far away. This created unnecessary activity across areas the player was not currently traversing.

I updated the C++ projectile spawner to use a configurable activation radius.


https://github.com/user-attachments/assets/c6b23369-0d28-44ea-8592-fbcd87c44b0e


The system periodically checks the distance between the player and each spawner:

- Entering the activation radius starts the projectile spawn timer.
- Leaving the radius stops the timer.
- Returning to the area allows the spawner to activate again.

The radius can be adjusted in the Details panel so launchers can support different firing distances and parkour layouts.

## Optimizing Forested Lands

<img width="1052" height="577" alt="image" src="https://github.com/user-attachments/assets/294ce896-3689-492d-8146-f97186049a89" />

Forested Lands was experiencing noticeable frame drops during traversal, particularly when the player fell and more of the environment became visible.

I cleaned up excess environmental content, removing approximately 2,500 trees, hundreds of thousands of grass instances, and around 30 redundant trigger boxes.

The goal was to preserve the forest’s appearance while reducing unnecessary density. The remaining trees, fog, and lighting still maintain the forest atmosphere from the playable route.

Following the cleanup and projectile changes, the frame drops I had previously encountered were no longer occurring during my playtests. Further testing across levels is still planned.

## Moving-Platform Fixes

Moving platforms sometimes failed to return to a usable state after player death. Some continued moving or restarted immediately after the player respawned.

I refined the reset behavior so platforms return to their starting positions and can be triggered again. This allows players to retry traversal sections without platforms remaining out of reach or out of sequence.

## Rain Audio

Added separate outdoor and indoor rain ambience to support changes in sound when moving between exposed and sheltered areas.

Work also addressed overlapping rain audio from multiple rain-volume instances by restricting audio control to a designated instance.

## Current Status

Completed:

- Storming Peaks course playable from start to finish
- Final traversal sections and level completion trigger
- Distance-based projectile spawner activation
- Forested Lands foliage and trigger-box cleanup
- Moving-platform reset fixes
- Route guidance and storm-lighting improvements
- Separate indoor and outdoor rain ambience

## Next Steps

- Finish rain impact effects on the player and refine ground splashes.
- Prevent rain from passing through some structures.
- Continue performance testing across levels.
- Plan an animation overhaul to improve movement presentation and transitions.
