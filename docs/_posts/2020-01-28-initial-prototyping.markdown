---
layout: post
title: "Initial Prototyping: Color Spaces"
date: 2020-01-28 11:00:00 -0500
categories: dev week3
---

## Development

Since art is a broad subject, I started by experimenting with a fundamental concept -- color mixing. This is actually non-trivial because computer color schemes are additive, and combining all colors gives you white. Unity uses the RGB color space, which is additive. Color mixing in the physical world is subtractive, and combining all colors gives you black. Painting uses the RYB color space, the 3 primary colors. My goal was to match real world color mixing as closely as possible.

I first tried to use Unity's Color.Lerp, which just averaged the red, green, and blue pixels of 2 colors. I found that RGB color mixing works well for orange and purple, but mixing blue and yellow makes gray instead of green. This implementation also reached each primarily color too quickly.

![rgb color space experiment 1](/assets/v1.gif)

In the next approach, I found a better way to average RGB colors. Here, I squared the colors, added them together, and then took the square root. There are more intermediate steps between colors, but still no green.

![rgb color space experiment 2](/assets/v2.gif)

Next, I tried to convert the colors to the CMYK color space because it's subtractive and used by popular creative programs like Photoshop. I averaged the colors in CMYK and then converted back to RGB. The purple looks a lot nicer, but some colors still aren't right.

![cmyk color space experiment 1](/assets/v3.gif)

I tried the different averaging method from before in CMYK.

![cmyk color space experiment 2](/assets/v4.gif)

So...

It's impossible to get green from pure RYB. I adjusted the the blue to have some green pixels. Now we have the whole range of colors!

![cmyk color space experiment 3](/assets/v5.gif)

The final code:
{% highlight ruby %}
void OnMouseDown()
{
    targetColor = target.GetComponent<Renderer>().material.color;
    if (targetColor == Color.white)
    {
        target.GetComponent<Renderer>().material.color = addColor;
    }
    else
    {
        float k1 = 1 - Mathf.Max(targetColor.r, targetColor.g, targetColor.b);
        float c1 = (1 - targetColor.r - k1) / (1 - k1);
        float m1 = (1 - targetColor.g - k1) / (1 - k1);
        float y1 = (1 - targetColor.b - k1) / (1 - k1);

        float k2 = 1 - Mathf.Max(addColor.r, addColor.g, addColor.b);
        float c2 = (1 - addColor.r - k2) / (1 - k2);
        float m2 = (1 - addColor.g - k2) / (1 - k2);
        float y2 = (1 - addColor.b - k2) / (1 - k2);

        float k3 = (k1 + k2) / 2;
        float c3 = (c1 + c2) / 2;
        float m3 = (m1 + m2) / 2;
        float y3 = (y1 + y2) / 2;

        float r = (1 - c3) * (1 - k3);
        float g = (1 - m3) * (1 - k3);
        float b = (1 - y3) * (1 - k3);
        target.GetComponent<Renderer>().material.color = new Color(r, g, b);
    }
}
{% endhighlight %}

Color mixing could be one mechanic in a game. I made a quick 3D environment and moved the objects into the UI.

![color mixing in the ui of a 3d world](/assets/proto1.png)

## Next Steps

It might be interesting to explore how we can affect more complex objects in the world. Perhaps the game should be more story-driven and requires more world building. Once I get to do some interviews, I'll have more of an idea of what features would be useful for art educators.
