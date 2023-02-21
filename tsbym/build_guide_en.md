# The Space Between You and Me - Build Guide

Thank you for deciding to build your own **The Space Between You and Me**
keyboard! This keyboard uses a reversible PCB design and can be configured to
add a trackball and/or a rotary encoder to each side. Below you will find a
detailed assembly guide with the trackball on the right side and the rotary
encoder on the left side. Feel free to customize these addons however you like!

## Bill of Materials (BOM)

First, let's make sure we have all the components necessary to build the
keyboard.

| Component                        | Quantity | Comment                                                   | Reference                                                                       |
|----------------------------------|----------|-----------------------------------------------------------|---------------------------------------------------------------------------------|
| Kailh Switch Socket (MX or Choc) | 38       | You can combine or add both MX and Choc.                  | https://shop.yushakobo.jp/en/products/4291?variant=43246483374311               |
| SMD Diode 1N4148W                | 38-40    | Add an extra diode if using a rotary encoder with switch. | https://shop.yushakobo.jp/en/products/a0800di-02-100?variant=37665574420641     |
| Pro-micro based MCU              | 2        | As long as it has the same pinout as a pro-micro.         | https://shop.yushakobo.jp/en/products/elite-c?_pos=2&_sid=359c0fb16&_ss=r       |
| 2 Pin 3.5x6x4.3mm Tactile Switch | 2        | For the reset button.                                     | https://shop.yushakobo.jp/en/products/a0800ts-01-1?_pos=16&_sid=87bea47f3&_ss=r |
| TRRS Jack                        | 2        |                                                           | https://shop.yushakobo.jp/en/products/a0800tr-01-1?_pos=1&_sid=73467339c&_ss=r  |
| TRRS Cable                       | 1        | To connect each side.                                     | https://shop.yushakobo.jp/en/products/trrs_cable?_pos=1&_sid=b895f0379&_ss=r    |
| USB Cable                        | 1        | To connect with you device. Choose depending on your MCU. | https://shop.yushakobo.jp/en/products/usb_type_a_to_c_cable                     |
| Switch (MX or Choc)              | 38       | Choose and combine your favourite switches!               |                                                                                 |
| Keycaps                          | 38       | Choose and combine your favourite keycaps!                |                                                                                 |

| Optional Parts                   |          |                                                           |                                                                                 |
|----------------------------------|----------|-----------------------------------------------------------|---------------------------------------------------------------------------------|
| Rotary Encoder                   | 0-2      | Optional rotary encoder per side.                         | https://shop.yushakobo.jp/en/products/3762?_pos=1&_sid=9b1a10619&_ss=r          |
| PMW3360DM-T2QU + Lense           | 0-2      | Optional mouse sensor per side.                           | https://www.aliexpress.com/item/32834829893.html                                |
| 34mm Trackball                   | 0-2      | Optional mouse trackball per side.                        | https://www.amazon.co.jp/dp/B08JZ97N31/                                         |
| OLED 128x32 SSD1306              | 0-2      | Optional if you want to add a display per side.           | https://shop.yushakobo.jp/en/products/oled?_pos=3&_sid=a4b10dd5d&_ss=r          |

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

### LEFT AND RIGHT SIDES ARE SLIGHTLY SHIFTED!!!

When you place the `Elite-C` on the PCB, make sure that you align the markings
on the `TOP SIDE` of the PCB with its pins.

![Elite-C Align](./img/elite-c-align.jpg)

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

![trakball](./img/trackball.jpg)

The trackball controls the mouse on your computer. The position of the
trackball lets you use the mouse with your thumb or index finger.

Unfortunately, I made a mistake when designing this beta version, so we need to
fix the board using external components.

![trackball components](./img/tb-components.jpg)

You will need:

|Components|Value|Quantity|
|---|---|---|
|Capacitor|4.7uF|1|
|Resistor|10k|1|
|Resistor|39|1|
|PMW3360DM||1|
|Lens||1|
|PCB||1|
|1x4 Pin Header||2|

Let's start by sanding the PCB. Be careful not to damage the pre-soldered
components on the PCB.

![PCB Sanding](./img/tb-sanding.jpg)
![PCB Sanded](./img/tb-sanded.jpg)

Next, let's solder the `PMW3360DM` sensor. Here, the square-shaped hole on the
PCB should match `pin 1` of the sensor. There is a small white mark on the
sensor that indicates which one is `pin 1`. Use the
[one-flat-all](#section-ofa) technique to make sure that the sensor is flat on
the PCB. Use the picture below as reference.

![Sensor Pin 1](./img/tb-pin1.jpg)

Once all pins are soldered, the bottom part should look like this:

![Sensor Soldered](./img/tb-sensor.jpg)

`DO NOT REMOVE THE PROTECTIVE COVERS` yet. These will protect the sensor until
we finish attaching all the components.

Now, we need to bend the resistors and capacitors in a special way. Make sure
to check all the pictures before you start bending the components to get an
idea of the shape you should aim for.

![Bending Components](./img/tb-bend.jpg)

The first component we need to attach is the `10k resistor`. The straight leg
should go to `pin 5`, while the bent leg should go to `pin 7`. The resistor
doesn't have direction (polarity) so you are free to choose which leg to bend.

![10k Resistor](./img/tb-10k.jpg)

It should look something like this:

![10k Resistor Front](./img/tb-10k-front.jpg)

You can slightly bend the resistor towards the sensor like this:

![10k Resistor Side](./img/tb-10k-side.jpg)

The next component is the `39 resistor`. The `S` bent leg should go to `pin 15`
and the `L` bent leg should go to `pin 4`.

![39 Resistor](./img/tb-39.jpg)

It should look something like this:

![39 Resistor Side](./img/tb-39-side.jpg)

The final component is the `4.7uF capacitor`. The straight leg should go to
`pin 3`, while the bent leg should go to `pin 8`. The capacitor doesn't have
direction (polarity) so you are free to choose which leg to bend.

![4.7uF Capacitor](./img/tb-cap.jpg)

It should look something like this:

![4.7uF Capacitor Front](./img/tb-cap-front.jpg)
![4.7uF Capacitor Side](./img/tb-cap-side.jpg)
![4.7uF Capacitor Top](./img/tb-cap-top.jpg)

`MAKE SURE THAT THE CAPACITOR IS CENTERED!` The capacitor should fit inside the
hole on the PCB when you place it on top. If it doesn't fit, try to move the
capacitor a little until it fits comfortably. When bending the legs, make sure
that the `LEGS DO NOT TOUCH EACH OTHER`. This might break the PCB.

![4.7uF Capacitor Hole Side](./img/tb-cap-hole-side.jpg)
![4.7uF Capacitor Hole Bottom](./img/tb-cap-hole-bot.jpg)

Once everything fits nicely, remove the protective film from the sensor.

![Remove the protective film](./img/tb-film.jpg)

Then, put the lens over the sensor. `MAKE SURE IT IS IN THE CORRECT
ORIENTATION!` The lens only fits one way, do not try to force the lens over the
sensor. Use the picture below as reference.

![Lens](./img/tb-lens.jpg)
![Lens Placed](./img/tb-lens2.jpg)

Finally, place the PCB on the keyboard. Make sure that the `SPI` pins and the
`POWER` pins are aligned.

![Done!](./img/tb-done.jpg)

Congratulations!!! You are done installing the trackball!


### Knob

![knob](./img/knob-top.jpg)

When you solder the knob, use the same
[one-flat-all](#section-ofa) technique to attach
the knob. Make sure that it rests flat on the PCB.

![knob flat](./img/knob-flat.jpg)

The bottom of the PCB should look something like this.

![knob bottom](./img/knob-bottom.jpg)

Congratulations!!! You are done installing the knob!

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

Congratulations! Now, let's have fun programming it! Go to the [FIRMWARE
GUIDE](./firmware_guide_en.md#section-mck) and program the layout you want!
