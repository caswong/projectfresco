---
layout: post
title: "All Prototypes"
date: 2020-03-11 1:00:00 -0500
categories: dev week8
unity_dir: week8
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3, 4, 5, 6, 7: Shortcuts to rooms

## Development
This week, I worked on building out the remaining rooms. There are 7 elements of design in total: line, shape, form, value, color, texture, and space. I ordered the rooms in this way because this is the natural way you would learn these concepts in the classroom, since they increase in complexity.

One aspect of shape is positive and negative spaces. For shape (room #2), the cube is created in the negative space. You can click on each of the circles in the room to rotate them, and when they are in the correct orientation, the lines of the cube will be formed in the background.

Form is all about using 2D shapes to create a 3D shape. For form (room #3), I wanted to have an interactive net of a cube that folds into the 3D shape by clicking on each piece. This hasn't been fully implemented yet because I had difficulty coming up with a good implementation. Each square piece can pivot in a different direction, and pieces that are touching should be able to rotate together for certain folds. For example, one piece could be adjacent to 2 other squares, and rotating that piece would have to rotate all of them together along that fold. Once folded, the number of adjacent pieces then changes.

For value (room #4), I did something similar to a common shading exercise. This room is also similar to the color room. By clicking on the different shades, you can then paint the color onto the cube pieces. The goal is to get an accurate shading of a cube, although I haven't determined how I will measure this accuracy yet.

For texture (room #6), I also did something similar to an exercise in real life, which involves creating a pencil rubbing to get a texture from a real surface. In this room, there will be white squares on different surfaces, and clicking on them will show a "drawing" of the implied texture. Clicking on the squares again will make a cube of that material.

Some of these ideas still need to be improved, but the main point was to get some idea down for each element of design.

## Next Steps
If I can figure out how to implement my idea for room #3, I will finish that room for next week. Otherwise, I will work on improving the current concepts I have. This will involve making the rooms more interesting and engaging and fixing bugs. Another thing to work on is making the items collectable and adding a UI and inventory.
