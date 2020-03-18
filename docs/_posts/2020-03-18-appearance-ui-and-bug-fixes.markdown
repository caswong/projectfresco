---
layout: post
title: "Appearance, UI, and Bug Fixes"
date: 2020-03-18 1:00:00 -0500
categories: dev week9
unity_dir: week9
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3, 4, 5, 6, 7: Shortcuts to rooms

## Development
I added a quick UI to show progress and made all the boxes collectable. You can currently collect 8 out 9 pieces because room #3 (form) has yet to be implemented. I looked into some different ways to implement folding a net into a geometric shape, but I only found a few things about paper-folding physics that sounded too complex.

I did finish out room #4 (value). To get the piece from this room, you have to pick any 3 different values to correctly shade the box.

Last week, room #5 (texture) had quite a few bugs. You could generate multiple cubes from every texture rubbing and you could also sometimes generate a box before the texture rubbing appeared. These have been fixed this week.

When moving between scenes, the player now enters and exits near the doors so that you don't have to start over from the beginning. I used a persistent game controller script to keep track of the most recent scene.

Each room also has some visual updates. I added textures to walls and floors, and I also made many of the rooms smaller because you only need to interact with a small part of the room.

## Next Steps
Implement room #3 and create an end game state.