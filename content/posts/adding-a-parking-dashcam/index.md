---
title: "Adding a Parking Dashcam to a 2nd-Gen Mazda CX-5"
summary: "How I spent far too long trying to squeeze every last drop of functionality from my parking dashcam."
date: 2025-01-27
tags: ["DIY", "automotive"]
---

## Initial Installation

Earlier this month, I decided that I wanted a more sophisticated dashcam setup for my second-generation Mazda CX-5. Mostly, I wanted the parking mode feature, which is basically a cheaper version of Tesla's [Sentry Mode](https://www.notateslaapp.com/tesla-reference/1303/tesla-sentry-mode-what-it-is-how-to-use-it-and-battery-drain), to record any incidents that occur when the vehicle's engine is off, such as when parked on the street or in a parking garage. I opted for a [Rove R2-4K Dual](https://www.amazon.com/ROVE-R2-4K-DUAL-STARVIS-Included/dp/B0D6J5B98H)[^1], and the installation went pretty smoothly. I followed this video pretty closely for the install:

{{< youtube VZDuZvfIwlo >}}

[^1]: I won’t speak to the quality of this dashcam just yet since I haven't had the time to fully utilize all its features. I will mention, though, that there was a minor software annoyance that caused the rear dashcam to show up mirrored on the display. The playback of both cameras works well, and the Rove support team was pretty helpful in sending me a replacement. It did not solve the issue, but it's good to know their customer support is at least responsive and helpful.

At this point, you're pretty much good to go with a working dual dashcam setup. However, since this dashcam had the parking mode feature I was looking for, I needed to go a step further and install a hardwire kit.

## Hardwire Kit

The point of the hardwire kit is to "tap" directly into a vehicle's fuse box for power even when the car is off. There are accessories and components in every modern vehicle that stay on even when the engine's power is cut, with the dashcam's parking mode being one of them. The hardwire kit comes with various-sized "add-a-circuit" fuse taps, so the idea is basically to identify the type of fuse that's currently plugged in, replace it with the add-a-circuit tap, and add the existing fuse back into the add-a-circuit. Here are the four most common fuse shapes (for fuse tapping) found in almost all cars:

![Common Fuse Taps](common-fuse-taps.jpg)

It turns out that the CX-5 uses low-profile mini fuses (second from the bottom), so we'd simply use the low-profile mini add-a-circuit from the kit. When installing the fuse tap, however, I realized that it didn’t fit properly. The tap would jut out because there were a couple of small plastic hooks protruding from the sides of each slot, which I assume are there to act as extra security for the existing fuse. This would cause the tap to fall out with even the slightest nudge. The solution here is simply to use the normal mini tap that also came with the kit (pictured last). Alternatively, one can be shortsighted and use a pair of pliers to twist off the pieces of plastic in the fuse box (please don't be like me).

![Fuse Taps Installed](red-wire-fuse-taps.jpg)
*Fuse taps installed. If your model is anything like mine: the yellow (ACC) is installed on Fuse 9 (15A) labeled F.OUTLET [Accessory sockets]. The red (constant) is installed on Fuse 16 (20A) labeled PLG [Power liftgate]. And of course, black is grounded to the chassis with the bolt on the left.*

## Parking Mode

The [hardwire kit](https://www.amazon.com/dp/B0B7235VLX) has different voltage cutoffs, ranging from 11.8V to 12.4V. The idea here is that if the car battery gets below the set voltage, the kit will automatically cut the power to the dashcam so that it doesn't consume any more power, and one would still be able to start the car. This detail is important to know for later. The kit has three colored wires, and this is how each of them should be wired to change the behavior of the dashcam:

![Hardwire Installation Guide](rove-hwk-instructions.jpg)

In non-parking mode (pictured at the bottom), both the yellow and red wires are connected to the ACC fuse so that when the vehicle is off, the wires stop receiving power and the dashcam shuts off.

In parking mode (pictured at the top), the red wire is attached to a constant power source, allowing power to be supplied even when the vehicle is off. The dashcam detects the presence/absence of the yellow ACC wire to determine the vehicle state and toggle parking mode accordingly.

## Manual Toggling

Normally, the parking mode configuration works well and would be the finish line for those looking to enable parking mode on their dashcam. But there are some drawbacks to keeping parking mode on constantly:

- **Battery drain**: Parking mode can drain the car battery over extended periods.
- **False recordings**: Wind, small vibrations, or passing shadows can trigger unnecessary recordings.
- **Unnecessary use**: If the vehicle is in a secure garage, parking mode is redundant.

That last point is the one that resonates with me the most—my personal situation calls for the ability to toggle parking mode on and off easily since my vehicle stays in a garage approximately 80% of the time (*wildly non-verifiable estimate*). In order for this toggling to happen, we'd have to be able to switch between an ACC source and a constant source, both feeding into the hardwire kit's red wire (but ensuring power delivery is mutually exclusive).

### The "My Car Battery Is Not Swole Enough" Problem

At this point in the project, I was pretty proud of myself. I'd gotten all the electronics down, the dashcam was working flawlessly, and I was able to effortlessly toggle between the non-parking and parking modes without the camera rebooting. Now, I just had to put it to the test. After a long drive to have dinner with family for Chinese New Year, I parked the car in the garage and turned on parking mode to see how long it would actually record. I'd set it to timelapse mode, and at 1 FPS, my conservative estimates put it in the range of recording for a couple of hours to about 6 hours worth of footage condensed into (at a minimum) a 4-minute video that I would be able to play back. Imagine my surprise when I came back the next day and there was only an 11-second clip, which equates to parking mode running for only 5.5 minutes. Actually, I wasn't surprised—mainly just disappointed.

To solve this issue, I purchased an external battery pack ([BlackVue B-112](https://www.amazon.com/dp/B01HFRH34Q?ref=ppx_yo2ov_dt_b_fed_asin_title)) specifically made for dashcams with parking modes, so it now becomes the sole source of power when the engine is off, instead of the actual battery of the vehicle. I also decided to purchase a cheapo voltage meter I could hook up to check on how much voltage the dashcam was pulling at any given time, just to provide extra transparency about battery behavior. The wiring diagram now looks like this:

![Wiring Diagram Part 2](cx5-wiring-part-2.jpg)
*Notice how the constant fuse tap is completely gone, and we solely rely on the B-112 to be the source of 12V constant.*

### Prettifying it all

Now all that's left to do is wire management and to 3D print a nice little container for the toggle switch and voltmeter. Here's how those came out:

![3D Printed Case](3d-printed-case.jpg)
*Switch downward to activate parking mode. Switch upward to return to non-parking mode.*

