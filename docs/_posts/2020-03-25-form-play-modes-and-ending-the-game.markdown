---
layout: post
title: "Form, Play Modes, and Ending the Game"
date: 2020-03-25 1:00:00 -0500
categories: dev week10
unity_dir: week10
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3, 4, 5, 6, 7: Shortcuts to rooms
* esc: Shortcut to return to level select

## Development
I finally finished room #3! In this room, you fold the squares together by clicking on each one to create your building block. You can fold the pieces in any order, and certain pieces are connected and will fold together. I implemented this by using Unity's RotateAround function, and this required quite a bit of fiddling. Each piece rotates on a different axis, and I also had to set different target positions. I also created pivot groups, so these axes and target positions also changed for individual pieces.

There is now a basic title screen that shows you two modes of play -- regular play mode or demo mode. Demo mode allows you to select an individual concept to display, which might be useful to some educators who just want to demonstrate one thing. In demo mode, there won't be any progression or collectables, and you won't be able to enter the world view. Eventually, there will just be a back button that lets you select another concept.

In play mode, there is now a complete feedback loop. You end the game by stepping on the green tile (your soon-to-be building site). If you have all 9 blocks, you'll be redirected to the title screen. Eventually, this will be some kind of cutscene that shows your finished bridge.

I also started experimenting with particle systems this week. I added some sparks when the cubes are instantiated to make them stand out more. I made my own emission map in Photoshop for these.

## Next Steps
I'd like to focus on player guidance next. Right now, it's unclear what you can interact with and what you need to do. There needs to be at least some text to explain the story. I'll also work on adding more juice. :)