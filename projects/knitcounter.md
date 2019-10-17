---
title: The knit counter
description: Keep track of your rows with this smallish digital knit counter
date: 2018-06-24
tags:
  - arduino
  - attiny85
  - oled
  - broken
layout: layouts/post.njk
---

![Knitcounter with small battery](/img/knitcounter/sm-small_battery_square.jpg)

If you ever find yourself knitting a sweater you may notice that most knitting patterns has instructions like `repeat between * and * for 34 rows` or some such. And if you are like me your thoughts might wander,
and, what row was I on now again?

There are a lot of knit counters, and of course a lot apps. I wanted
mine to be small and light. The dream was to be able to use it as
the marker for start of round. This ways I couldn't possible miss
pressing the button, counting up a new round.

**CURRENT STATUS: broken**

## Build
![Circuit with attiny85](/img/knitcounter/sm-circuit.jpg)

You can obviously build this a lot smaller, but I wanted to use stuff
I already had at home.

  * A way to large proto board that I sawed to smaller size.
  * Large 12mm button
  * Small 6mm button
  * A AVR ATTiny85 micro controller
  * A capacitor over the power to smooth it out. I've read that
    it's a good thing to have.
  * 0.96 Inches OLED i2c display.
  * A Lithium-Polymer battery.

### The micro controller
The ATTiny85 is a nice little bugger. If you are fine running it at 1MHz
or 8MHz you don't need any external crystal, maybe just a capacitor. You
can fake USB with the
[V-USB](https://www.obdev.at/products/vusb/index.html) project, play sounds
with the high frequency PWM (at leas higher than a normal arduino). It
also happens to have a very nice low power mode. You can send it to sleep
and it will consume very little until an interrupt, triggered on one of
it's pins, wakes it up. This is the main reason I choose this particular
micro controller, more on that later in the "code" section!

There are also several Arduino "cores" you can use, so it's easy to program.

I had to build a small circuit so I could program it with my Atmel AVRRISP II.
![ISP Circuit](/img/knitcounter/sm-isp.jpg)

But you don't need to use a programmer! I just happen to have one,
but in this case an [Arduino will do just fine.](https://create.arduino.cc/projecthub/arjun/programming-attiny85-with-arduino-uno-afb829)

### The display
![Oled display](/img/knitcounter/sm-screen_and_circuit.jpg)

I had a smallish OLED display lying around, a gift from a friend. It is
rather small, but for displaying just some numbers its quite the overkill.

It's an i2c no-name display, but it has SSD1306 circuit on it like most other! I tried to get Adafruits [SSD1306](https://github.com/adafruit/Adafruit_SSD1306) library working with it, but failed.

After some googling I found another nice library: [tinusaur/ssd1306xled](https://bitbucket.org/tinusaur/ssd1306xled). With this I got
some progress!

For simplicity I used the font that came with the library, that gave
quite small numbers, but hey it was a very simple to code :)

### The code
The code can be found at [https://github.com/davidlgj/kniterator](https://github.com/davidlgj/kniterator)

I wanted the counter to a have a long battery life, preferably months.
It wouldn't do if it lost power during a project. Since most of the time
it just sits there, it's a perfect match for the deep sleep mode the
ATTiny85 has.

The code is simple, a one push of any of the buttons wakes it up. The
display lights up and presents the current count. Pressing the large button
increases the number, the smaller button decreases. After a couple of
seconds it turns off the display and powers itself down again.

There is lots of room for improvement, larger numbers for instance. You
could also have several counters, use the small button to cycle between
them. Large button to increase, long click to decrease.

I also had plans to save the number to the small EEPROM inside the
ATTiny85, so it never would loose count!

## But is it finished?
Well. No. It's broken.

When i started I only had a bit of a largeish battery. It added to the
weight stuck out at the bottom.
![with large battery](/img/knitcounter/sm-with_large_battery.jpg)

One nice thing with it thouhg was that it fitted nicely below the display.
For ease of use I didn't solder the display directly onto the proto board.
![with large battery](/img/knitcounter/sm-battery_between.jpg)

Later I got a new much much smaller battery. Yay! Soooo much lighter.
![Knitcounter with small battery](/img/knitcounter/sm-small_battery.jpg)

But know the display stuck out from the proto borard in an ugly way,
I couldn't have that could I? So off I went and soldered it directly
onto the board.

Unfortunately, I must have done something wrong. It broke the display,
its just black. Kaputt. Dead. Some testing leads me to believe the ATTiny85 is alive and kicking.

I bought a new, smaller display from Adafruit, but it doesn't have the
same pin count so it's not a drop in replacement.

And here, as always, I got stuck. I have managed to procure a new display
that looks to be of the same type as the old. One day I might try to
remove the broken one. One day...
