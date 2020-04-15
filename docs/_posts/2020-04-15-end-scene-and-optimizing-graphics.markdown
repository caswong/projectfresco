---
layout: post
title: "Ending Scene and Optimizing Graphics"
date: 2020-04-15 1:00:00 -0500
categories: dev week13
unity_dir: week13
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials
* 1, 2, 3, 4, 5, 6, 7: Shortcuts to rooms
* esc: Shortcut to return to level select

## Development
I made another iteration to the texture room. Based on suggestions, you're marked as correct if you leave the correct texture on for 2 seconds, so you can't just spam and click through all of them. I also added more options, so there are 8 pictures to cycle through. I also made a quick fix in the last room and expanded the area that is considered the correct position to see the cube.

I spent quite a lot of time looking into optimization this week because the lag in the world scene was really starting to bother me. This was mostly due to the rendering effects from one of the cameras. I didn't know a whole lot about graphics in Unity, so it took me some time to understand and get it right. One solution I found that worked was using OnPreRender and OnPostRender functions to supply a target texture to the camera. Previously, I was using OnRenderImage, which triggers a CPU ReadPixel and stalls the GPU until it finishes. I measured the frame rate before and after this change. Before, the frame rate was anywhere between 37-44 fps. After the change, the frame rate was 42-50 fps. The frame rate was at 50 when the scene first loaded and would reduce over time. This change did help, but wasn't super noticeable to me. There are definitely other places in my code that I can optimize.

After the switch to using OnPostRender, there was now half a second where the sketch effect wouldn't be applied yet. This ruined the illusion, so I also added scene transitions to try to hide some of that. These are just simple fade-to-black transitions. They happen going in and out of doors and when you first enter the game through play mode.

Finally, I added a cutscene for the end of the game. When the player has collected all 9 blocks and steps on the green tile outside, they will be locked in place. A bridge will appear, and the player will move across it automatically. Then the congratulations message will appear, and there will be a restart button that takes you back to the title screen. I also added two new sound effects as a part of this sequence.

While making the ending cutscene, I found some serious bugs that no one had encountered before. I had some objects that had DontDestroyOnLoad added to them because they needed to persist between rooms (like the UI and any game managers). These weren't being deleted when you restarted the game, so your progress would actually be saved. This means that in some of the older builds, you can probably solve a puzzle and never go back into the room, even if you restart the game.


## Next Steps
- Player guidance (short text instructions)
- Add more assets or artwork
- Effects when you run into invisible barriers
- More optimization
- Consider being able to go back into solved rooms but without the collectable
