---
layout: post
title: "Layout Changes and Completed Demo Mode"
date: 2020-04-01 1:00:00 -0500
categories: dev week11
unity_dir: week11
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3, 4, 5, 6, 7: Shortcuts to rooms
* esc: Shortcut to return to level select

## Development
A lot of miscellaneous fixes this week. I fixed the text prompts when you step on the tile to end the game so that they are always centered for different screen sizes. I also made the player face the correct direction when exiting a buildling, and I locked rooms once the player collected what was needed. The menu screens were redesigned -- I added some backgrounds and changed the size and layouts of the buttons to make them look nicer. I also finished the demo mode. When in demo mode, there is no world scene or UI showing progression. You don't need to collect anything. You also can't exit the rooms. Each room now has a back button that lets you return to the selection screen.

I've also been working on making some improvements to the puzzles. I made updates to the following rooms:
- Value (#4): I added a light source direction for this puzzle. Now, there is clearly a lightest and darkest side, and I changed how this puzzle checks for correctness. The top side always has to be the lightest and the right side always has to be the darkest, but it doesn't matter which exact shades you pick. I also rearranged the elements in this room. I wanted the value blocks to feel more like a conventional color picker.
- Texture (#6): I changed the idea for this entirely. Now, you can click on the targets to cycle through the different textures. Once all 3 match the pictures, you can click to collect your blocks. I changed some of the line drawings to more closely match the textures, and I might add more.
- Line (#1): Changed the layout of elements. Before, this room felt similar to the last room where you move around to find the correct location. I kept all the lines on the same plane, since I don't want to introduce 3D space yet. You can find the cube from any angle.
- Space (#7): I started added more stairs and platforms to give players more room to explore different perspectives.

## Next Steps
I will be working on much of the same things -- iterating on the puzzles and small polish things. There are also some things that needed to be added like more art, audio, and guidance.