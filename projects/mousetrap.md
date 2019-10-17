---
title: The mouse trap
description: To trap a smart mouse you need... a long tube. And an arduino.
date: 2019-10-05
tags:
  - arduino
  - servo
layout: layouts/post.njk
---


![rigged trap](/img/mousetrap/sm-rigged.jpeg)

We had a a problem. It was small furry and super cute. And it pooped
everywhere. The mouse had already foiled a couple of traditional traps
we set for it so I knew I had to take matters into my own hands.

This is actually not an unfinished project. Its not nice looking,
well built or good code. **But it caught the mouse!**

## Hardware

 * PVC pipe
 * Two metal plates
 * Arduino
 * Small servo (small enough to be driven directly by the arduino)
 * Small metal pin, the kind use to fasten knitting needles
 * Duct tape
 * Popsicle sticks
 * Copper tape (I used the one used for keeping slugs out of your garden)
 * Some wooden planks
 * Some screws


## Build

The build is quite simple. A trigger at the end of a PVC pipe triggers a
closing mechanism on the other side. The trick is that the pipe is so long
the mouse doesn't have a chance to bolt.

![trigger with peanut butter](/img/mousetrap/sm-pressure_plate.jpg)

The "pressure plate" is to popsicle sticks with copper tape on them.
A bit of a broken popsicle stick in the middle keeps them from touching
until the weight of the mouse is on it. Btw peanut butter is great for
mouse traps.

The arduino code just polls with a `digitalRead` and sweeps the servo
at the first hint of any critters.


### The guillotine

<video controls>
    <source src="/img/mousetrap/test.mp4"
            type="video/mp4">

    Sorry, your browser doesn't support embedded videos.
</video>

The closing mechanism is super simple, the metal plate is a bit heavy and
when the servo removes the pin it falls down. Sawing a bit down into the
wood makes sure the mouse can't push get a hold and push it up.
