---
title: The clock
description: A smart clock with spoilers about todays weather.
date: 2019-07-24
tags:
  - neopixel
  - clock
  - raspberrypi
  - weather
layout: layouts/post.njk
---

<video controls>
    <source src="/img/clock/test.mp4"
            type="video/mp4">

    Sorry, your browser doesn't support embedded videos.
</video>

This is a work in progress. I got the idea from a "smart" clock I saw. It was quite nice.
Looked like a brick with large colorful pixels. Can't find it anymore though. Anyway
it could show the weather, mail etc. I liked it, but it was expensive (>€100) and closed
to their app for control.

A bit later i saw [this nice IKEA hack](https://hackaday.com/2019/06/12/ikea-cloud-lamp-displays-the-weather-with-esp8266/).
Its a IKEA cloud lamp that changes color depending on the weather and even flashes for
lightning storms! Very nice.

## The plan
The plan is to build a smart clock for my sons room, it would be super cool if it could
be the hub for some kind of voice control, but first off I want it to tell what the
weather will be for the upcoming day. I asked my son, and he'd rather have an analog
clock instead of a digital, so I bought a cheap ordinary wall clock. It had no numbering,
I guess to look clean, so that is something I will need to fix in the future.

I wanted to line the clock with RGB leds so I could mark out the weather approximately
where the hour mark is. This means the clock can tell the weather for the upcoming 12
hours.

I'm planning to use a Raspberry Pi Zero W for the brains of it.

## The build so far

![clock in my workspace](/img/clock/sm-workspace.jpg)

Any sane person would here go and buy a nice Adafruit led
strip and just line the edge of the clock with it. But I
like to use what I already have in my stash, and one of the
things I have are several
[Flora Neopixels](https://www.adafruit.com/product/1260)
(I bought two 20 packs that where on a ridiculous sale).

I decided to use 8 of them, to make it a bit easier to solder
and to not overwhelm the Raspberry Pi Zero.

The neopixel needs 3 wires, power and a signal, and that
sinal needs to be chained to the next pixel. That means
three wires between each of them.

Looking around my workspace for some wire I happened to see
some copper tape that I bought to experiment with. The tape
is supposed to be used in the garden to create a barrier
for slugs. It has a copper foil over a paper/plastic back.
So you can't tape a circuit together, but you *can* solder
to it!

![copper tape as wires](/img/clock/sm-threelanes.jpg)

The middle lane of tape is the signal, and since it needs
to chain the neopixels together I took a flat screwdriver
and just scraped away a spot where the neopixel should be.

![copper tape as wires](/img/clock/sm-soldered.jpg)

Works like a charm! I also soldered three wires to it. The plan
is to drill a hole through the backplate and place the raspberry
pi zero on the back.

So now it's time for the software... and that's where it's
hanging in limbo right now.

![copper tape as wires](/img/clock/sm-soldered.jpg)


Future plans involve speakers or buzzer for alarm, camera for
keeping track of intruders (or waving to turn of alarm!)

