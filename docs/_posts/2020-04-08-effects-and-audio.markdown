---
layout: post
title: "Audio and Puzzle Completion Effects"
date: 2020-04-08 1:00:00 -0500
categories: dev week12
unity_dir: week12
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3, 4, 5, 6, 7: Shortcuts to rooms
* esc: Shortcut to return to level select

## Development
This week, I changed up what happens when you solve puzzles. Instead of clicking on the area to create a cube, once you have the right configuration, the puzzle will just sparkle, pause for 3 seconds, and automatically give you your cube. Hopefully, this makes some of the puzzles less awkward because there were some cases where players weren't sure when they were done. I also added a shrinking effect so that all the blocks are more of a collectable size.

I also added all of the sounds I wanted in the game, which includes:
- City street ambience in world view
- Footstep sounds when the player is moving on grass, wood, and tile
- Sound effect for correctly solving a puzzle
- Sound effect for cube popping out
- Sound effect for collecting a cube
- Menu clicks
- Doors opening and closing
- Clicking sounds for puzzles
- Pencil/paint sounds for value & color

## Next Steps
I have a running list of some miscellaneous things I want to do:
- Victory sequence
- Player guidance (short text instructions)
- Add more assets and textures
- People artwork so they have some character
- Scene transitions
- Effects when you run into invisible barriers
- Optimization
