---
layout: post
title: "Color and Line Rooms"
date: 2020-02-26 1:00:00 -0500
categories: dev week7
unity_dir: week7
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3: Shortcuts to rooms

## Development

I added some cliffs to the game to make you feel like there is actual separation between the two sides. They aren't integrated into the game very well at the moment (you can walk over the gap and some objects don't sit quite right), but my main focus this week was on adding additional rooms.

I've added two more rooms -- one for color and one for line. Press 1, 2, or 3 to quickly access the rooms I have so far! I used ideas from my earlier color experimentation in this room. The idea is that you have to use your primary palette to match a target color. When the color is mostly correct, you can click on your mixed color, and your building material will materialize into a cube. The way the "color correctness" is measured is by ratios. If the ratio between red & green, red & blue, and green & blue in your mixed color and target color are within 0.5 for all values, this is considered close enough for this objective.

In the line room, this one is mostly displaying different types of lines and how they come together to form shapes. Clicking on the cube that is formed by the crossing lines will give you your building material. I'm not sure if this is what I want to stick with for this design principle.

## Next Steps
Next week, I will continue working on the prototypes for each of the rooms. I will also clean up my code and fix all the bugs I've introduced so far.
