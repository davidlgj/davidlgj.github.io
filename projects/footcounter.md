---
title: The foot counter
description: No, not counting feet literally. Just a foot pedal to count rows while knitting
date: 2019-04-24
tags:
  - trinketm0
  - adafruit_trinket
  - keyboard
layout: layouts/post.njk
---


<video controls>
    <source src="/img/footcounter/example.mp4"
            type="video/mp4">

    Sorry, your browser doesn't support embedded videos.
</video>

After I broke my first [knitting counter](/projects/knittingcounter/) I had
an idea: We all have a screen with us all the time, the phone. I know,
not a new or a novel idea, and not the first time I thought of it.

(Tangent: I still think our phones are ridiculously underused for stuff.
And I don't understand why I can't just plug it into my laptop and use
the keyboard and screen?)

When you knit you usually use both hands. So why not use your feet!
So I built a simple two key keyboard (with A and B buttons) and a web app
to keep the count.

## Hardware
![knitting counter made for the foot](/img/footcounter/sm-assembled.jpg)


The Hardware is super simple:
  * [Adafruit Trinket m0](https://www.adafruit.com/product/3500) or [Adafruit Trinket](https://www.adafruit.com/product/1501). Both works,
  but the m0 starts up more quickly and is easier to program.
  * A proto bord
  * two push buttons
  * some wiring
  * some sort of box

You can use internal pull-ups in the trinket so you don't even need a resistor.

## Code
I've lost the source code, but it was just a copy paste of
[Adafruits keyboard example](https://learn.adafruit.com/adafruit-trinket-m0-circuitpython-arduino/circuitpython-hid-keyboard-and-mouse). The
only thing I changed was that i changed it to send "B" instead of
"Hello World\n" (row 18).

This means that I now have a two key keyboard, yay!

The second part of this is the a simple web app with two counters.
You can try it at [http://burningbroccoli.se/foot-counter/](http://burningbroccoli.se/foot-counter/)

The code for it is on [davidlgj/foot-counter](https://github.com/davidlgj/foot-counter)


## But is it finished?
We'll, that depends on your definition of finished. It doesn't really work.
So if that is a problem, then no, it's not finished.

What's wrong with it you might ask. Doesn't it up the counter when you press
the buttons? It does, but you now what else a smart phone does? It goes to
sleep when you're not using it! Which means you have to wake it up before
you can use your foot to press the buttons... kinda defeats the purpose.

The embarrassing thing is that I didn't figure this out until I had a beta
tester actually use it.
