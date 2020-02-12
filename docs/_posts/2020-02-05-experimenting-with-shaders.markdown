---
layout: post
title: "Experimenting with Shaders"
date: 2020-02-04 11:00:00 -0500
categories: dev interview week4
---

## Development

This week, I experimented with different artistic shaders.

The first shader I tried using was a [watercolor shader](https://www.bruteforce-games.com/post/watercolor-shader-devblog-13).

Using the code from the blog post, I applied the shader to a scene with buildings.

![scene view](/assets/shader1.png)
![game view](/assets/shader2.gif)

This did not look the same as what is described in the blog post. Below is an image from the blog post of the final effects.

![correct appearance for watercolor shader](/assets/tutorial.gif)

The objects in my scene seemed to be missing colored shadows and fog. I messed around with some of the settings, but still didn't get it to look as elegant as the example in the end. I moved on since I wasn't sure whether or not this shader would be useful to me later.

The next shader I experimented with was a [pencil effect](http://www.shaderslab.com/demo-99---pencil-effect-1.html) shader. This one didn't come with explanations for what anything meant. I first tried applying this shader directly onto the material of the buildings like the watercolor shader, but this didn't produce the effect. After some searching, I learned that this was a post-processing effect.

I needed to add this code, attach it to the camera, and create a new material for the shader, so that the pencil effect would render over everything:

{% highlight ruby %}
using UnityEngine;
 
[ExecuteInEditMode]
public class CameraRenderTexture : MonoBehaviour
{
    public Material Mat;
 
    public void OnRenderImage(RenderTexture source, RenderTexture destination)
    {
        Graphics.Blit(source, destination, Mat);
    }
}
{% endhighlight %}

The scene vs. the game view

![scene view](/assets/shader1.png)
![game view](/assets/shader1-f.gif)

This shader also allows you to change the gradient threshold and the color threshold.

![inspector](/assets/shader1-ins.png)

The gradient threshold seems to change the amount of shading/hatching in the effect, and the color changes how much of the original color is preserved. The full range of gradient and color are shown below.

![gradient spectrum](/assets/shader1-gradient.gif)
![color spectrum](/assets/shader1-color.gif)

The last shader I experimented with was an [oil paint shader](http://www.shaderslab.com/demo-63---oil-painting.html).

This one worked very similarly to the pencil effect shader. I applied the shader to a material, and the camera post-rendered the effects.

![oil paint shader](/assets/shader3.gif)

## Interview
I had the opportunity to interview an MFA student at the Stamps School of Art & Design. He has taught a number of classes about media art, including creative programming and digital fabrication. He is interested in using technology for aesthetics and considers the art he does as "not very mainstream," so it can be challenging to teach students this field in classrooms. One of the key takeaways from my conversation with him is that anyone can eventually learn technical skills -- it's more important for art students to become skilled at communication, to be able to share a message and provide a "method to their madness."

From this interview, it's clear that I should eventually incorporate story-based elements in the game to help students practice communication.

## Next Steps

Next week, I have set up interviews with two high school art teachers. I will continue experimenting with different mechanics/tools I could use or possibly mimicking an existing art-based game until I have a better direction.
