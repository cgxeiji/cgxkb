# The Space Between You and Me - Build Guide

Thank you for deciding to build your own **The Space Between You and Me**
keyboard! This keyboard uses a reversible PCB design and can be configured to
add a trackball and/or a rotary encoder to each side. Below you will find a
detailed assembly guide with the trackball on the right side and the rotary
encoder on the left side. Feel free to customize these addons however you like!

## Bill of Materials (BOM)

First, let's make sure we have all the components necessary to build the
keyboard.

[insert table]

## Preparing the PCB

![Picture of both PCB](./img/pcbs.jpg)

Each side of the keyboard uses 1 PCB. Make sure that the orientation is
correct. The bottom part of the PCB has a label that says `CGxKB v0.1.0 L-TOP`
for the **left side** and `CGxKB v0.1.0 R-TOP` for the **right side**. This
guide will show you a step by step guide of how to build the **right side** of
the keyboard. Take a look at the pictures below as a reference.

#### PCB for the left side
![left side](./img/pcb-left.jpg)

#### PCB for the right side
![right side](./img/pcb-right.jpg)

### Trackball Module

Each side includes a PCB module for the `trackball` on the bottom corner.
**CAREFULLY** break away the module and use a file to smooth the border of the
PCB.

![break trackball module](./img/break-module.jpg)
![sand down the PCB](./img/file.jpg)

## Soldering the Diodes

We are going to add the `diodes` on the `BACK SIDE` of the PCB. Because we are
building the **right side** first, we need to flip the PCB and attach the
diodes on the side that says `CGxKB v0.1.0 L-TOP`. Here, you can use through
hole diodes or SMD diodes.

![SMD diodes](./img/diodes.jpg)

Make sure that the **mark** of the diode is on the same side as the line on the
PCB. In the picture below, there is a line and a triangle pointing to the left
side. The diode has a line on the left side of `T4`. This is the correct
orientation.

![diode orientation](./img/diode-orientation.jpg)

I recommend that you put a little bit of solder to one side of the pad of the
diode. Put this on the same side for all the diodes, so you have a visual
reminder of the correct orientation of the diode.

![diode solder side](./img/diode-solder1.jpg)

Use a pair of tweezers to hold the diode and reheat the little bit of solder
that you put before. Make sure to do this quickly, long exposure to heat could
`DAMAGE` the component.

![diode solder tweezers](./img/diode-solder2.jpg)

Make sure that the diode is flat on the PCB. You can reheat the solder point to
fix the position of the diode if necessary. Do this `BEFORE SOLDERING THE
OTHER SIDE`. It will save you some headaches.

![diode flat on the PCB](./img/diode-flat.jpg)

If the diode is correctly soldered, it should look something like this.

![diode solder finish](./img/diode-solder3.jpg)

### Special diodes

Double check the orientation of the diodes marked in `red`. Attach the diode
marked in `blue` if you want to use a `knob` on that side of the keyboard.

![special diodes](./img/diode-warning.jpg)

Once you soldered all the diodes, your PCB should look like this.

![all diodes](./img/diode-all.jpg)

## Building Bridges

If you want to use the `OLED display`, `trackball`, or `knob`, we need to
connect a few bridges on the `BACK SIDE` of the PCB. The bridges are marked
in `red` in the picture below. Here, I am connecting the `trackball` and the
`OLED display`.

![bridges](./img/bridges.jpg)

## More Components

Now, we need to attach the `TRRS jack`, and `RESET button`. If you are
adding a `trackball`, add two extra `female pins`. If you are adding an `OLED
display`, add an extra `male and female pin`. If you are adding a `knob`, add an
extra `rotary encoder` (marked in `green`). As a recommendation, solder shorter
components first and taller components last: `pin` > `TRRS jack` > `RESET
button`.

![more components](./img/more-stuff.jpg)

These components are place on the `TOP SIDE` of the PCB and soldered on the
bottom side.

![more components on top](./img/more-stuff-top.jpg)

### <a name="section-ofa"></a>One-Flat-All

When soldering the `pins` to the `OLED display` and the PCB, I recommend that
you solder only `one` pin, like the picture below.

![oled-one](./img/oled-one.jpg)
![pin-one](./img/pin-one.jpg)

Then, check that the pins are `flat` to the surface. You can reheat the solder
point to fix the alignment of each component. It is easier to reheat only one
pin than trying to fix it when you have soldered all the pins.

![oled-flat](./img/oled-flat.jpg)
![pin-flat](./img/pin-flat.jpg)

If everything is aligned, the `OLED display` and the PCB should be parallel
when connected.

![oled-pin](./img/oled-pin.jpg)

Use the same process for the `TRRS jack` and the `RESET button`.

![TRRS jack and reset button](./img/jack-rst.jpg)

The `top side` of the PCB of the `right side` of the keyboard with a
`trackball` should look something like this. If you want to use a `knob`
instead, `DO NOT ATTACH` it yet. First, we need to test the connections.

![stuff on top](./img/top-stuff.jpg)

## Micro-Controller

Let's prepare the `Elite-C` and two `conthrough` pins. You can use other
equivalent micro-controllers like the Pro Micro instead of the Elite-C. I am
using the Elite-C because it has an USB-C port.

The `conthrough` pins have one side with small holes. Make sure that this side
is facing the same direction. The holes should be closer to the `Elite-C`.
Also, the pins should be placed on the side with the electronic components.
Check the pictures below.

![Elite-C](./img/elite-c-pin.jpg)
![Elite-C Flip](./img/elite-c-flip.jpg)

You can place the `Elite-C` with the pins on the PCB to help you keep it
aligned when soldering. Make sure that the `Elite-C` fits flat on the PCB
before soldering.

![Elite-C PCB](./img/elite-c-pcb.jpg)

### ONLY SOLDER THE PIN TO THE ELITE-C!!!

Don't solder these pins to the PCB.  The idea behind using `conthrough` pins is
to make the micro-controller easily replaceable in case something happens.

![Elite-C Soldering](./img/elite-c-solder.jpg)
![Elite-C Bottom](./img/elite-c-bottom.jpg)

## Checking the PCB

![almost here](./img/almost-there.jpg)

Your PCB should be looking something like the picture above. The next step is
to install the firmware and check that the `OLED display` and the `diodes`
work before attaching the hot-swappable connections. If something doesn't work,
we can easily fix it at this stage.

Follow the [FIRMWARE GUIDE](./firmware_guide_en.md) and install the firmware.
After that, use a pair of metal tweezers to check each switch. If it works, the
`OLED display` should show you some nice messages!

`MAKE SURE TO ONLY CONNECT THE SAME SWITCH`. There is a chance that a
short-circuit happens if the tweezers accidentally touch something they
shouldn't have while the PCB is powered.

![it works!](./img/its-alive.jpg)

If you plan to use the `knob`, don't forget to test its switch as well.

![it also works!](./img/its-alive-knob.jpg)

## Hot-Swappable

Once everything is working, it's time to attach the `hot-swappable` connectors.
First, remove the `OLED display` and flip the PCB. We need to put the
connectors on the `BACK SIDE` of the PCB.

![hot-swappable](./img/hot.jpg)

Place the `hot-swappable` on the PCB.

![hot-pcb](./img/hot1.jpg)

Solder only one side of the connector. Make sure that the connector is `flat on
the PCB` and reheat the solder if necessary to adjust the position.

![hot-one](./img/hot2.jpg)

Then, solder the other side. This might be a little bit difficult because of
the diode (I might change the position of the diode in the final version of
this keyboard). I suggest that you put the soldering iron perpendicular to the
PCB and solder this point from above, like in the picture below.

![hot-aid](./img/hot-aid.jpg)
![hot-all](./img/hot3.jpg)

Once you soldered all the hot-swappable connectors, your PCB should look like this.

![hot-finished](./img/hot-all.jpg)
![hot-finished-left](./img/hot-all-left.jpg)

## Add-ons

The following add-ons should be attached once you soldered all the previous
components in this guide.

### Trackball

### Knob

![knob](./img/knob-top.jpg)

When you solder the knob, use the same
[one-flat-all](#section-ofa) technique to attach
the knob. Make sure that it rests flat on the PCB.

![knob flat](./img/knob-flat.jpg)

The bottom of the PCB should look something like this.

![knob bottom](./img/knob-bottom.jpg)

## Finishing the Keyboard

Now, it is time for the fun part! Place your favourite switches and keycaps and
make sure that the keyboard is working correctly.

You can laser cut or 3D print the `top plate` for the switches and carefully
insert each switch.

![switches](./img/switches.jpg)

Make sure that all the pins are facing the `south part` of the keyboard!

![switches south](./img/switches-south.jpg)

Once you have placed all your favourite switches, carefully place them on top
of the PCB.

![switches pcb](./img/switches-pcb.jpg)

Gently press them until you have a nice switch sandwitch (*wink *wink).

![switch sandwitch](./img/switches-sandwitches.jpg)

Test that all the switches are working correctly.

![key test](./img/key-test.jpg)

The final PCB should look something like this.

![switches all](./img/switches-all.jpg)

Do the same for the other side and place your favourite keycaps on top!

![keycaps](./img/keycaps.jpg)

Your keyboard is finished!

Congratulations! Now, let's have fun programming it!
