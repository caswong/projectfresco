---
layout: post
title: "Putting Demos Together"
date: 2020-02-19 1:00:00 -0500
categories: dev week6
unity_dir: week6
---

## Controls
* Up: Move forward
* Left/Right: Rotate
* Click: Interact with materials

## Development

I've made a lot of different demos so far that showcase different artistic concepts. This week, I thought about how to put them together into one game.

In this prototype, the initial idea is that the city is divided, with the people on one side having the means to get across to the other side. These people have more resources and are from the more affluent part of the city. You begin as a player on the other side that does not have access. Your goal is to build a bridge to give yourself and your community access to the other side.

On your half of the city, you can enter different buildings to collect building materials. Each room will exemplify a different design principle in art education. In the first room, I took the perspective shift demo from last week. I added rotation movement to the player, since this is the the only way this demo works with a first-person point of view. As you climb the stairs, the 3D cube projected onto 2D surfaces will start to form the correct shape. Once you're at the right location, you can click the outline to materialize the object into a collectable. Collectables/inventory haven't been implemented yet.

Last week, I couldn't get the skybox on the left side to not be rendered under the post-processing shader. I looked into this some more. The way this is currently implemented is that the objects without the sketch effects are put on a NoShader layer, with Camera2's culling mask set to the NoShader layer. Camera 2 also has the Don't Clear flag, so that these objects look like they sit within the same scene, which means that Camera2 has no skybox. Below are the camera previews of both cameras.

![camera 1](/assets/camera1.png)

![camera 2](/assets/camera2.png)

I also tried having the cameras each render one half of the screen. This required an additional script because modifying the viewport rect repeated and squished the scene on each half. The script I wrote was a scissor rect, which just clipped anything outside of the camera's half.

![initial view with scissor rect](/assets/scissorrect1.png)

Standing at the center, you do get split environments.

![moving off center with scissor rect](/assets/scissorrect2.png)

But when you move off center, the split rendering continues to follow the player. Doing this also made me realize that a split skybox looked pretty jarring anyway, so I decided to do no more work trying to fix this.

## Next Steps
Next week, I will work on getting prototypes of the design concepts that will be presented in the other rooms. These will be the remaining six design principles or any other interesting experiments I can think of. I will also work on making the first room more dynamic.
