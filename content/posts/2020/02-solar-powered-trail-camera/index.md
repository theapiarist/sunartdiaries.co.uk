---
categories: 
    - geekery
date: 2020-02-29
draft: 'false'
tags:
  - rhododendron
  - trailcam
  - fauna
title: 'Solar powered trail camera'
---

Storms Ciara, Dennis and now Jorge have rather interrupted my early spring tasks and I've been trapped indoors as the wind howls and the rain hammers down. In between the weather I've been [tree planting](/2019/12/trees-for-bees/) and [rhododendron bashing](/2019/05/dont-forget-your-roots/) but I've also had ample time to complete a solar powered supply for my [trail cameras](/2019/11/trail-cameras/).

These trail cameras require a 12V supply. Standard alkaline batteries - eight 1.5V AA cells - are drained very quickly. It is strongly recommended that you use 1.5V lithium batteries. These deliver the higher power necessary to drive the LED flash and IR detector for much longer - for 9-12 months in my experience. Not only do these last a lot longer, they also work much better at low temperatures. However, this is not an inexpensive option. Non-rechargeable AA lithium cells cost a little under £1.50 each when purchased in reasonable numbers.

Which, at about £12.00 per camera, soon adds up.

And they still run out :disappointed:

## Here comes the sun

I'm a big fan of solar power. It heats most of the hot water in the house and I use it on my '[bee shed](https://theapiarist.org/let-there-be-light/)' for trickle-charging a 100Ah 'leisure' battery, providing power for the lighting.

Solar panels are improving all the time and prices are dropping significantly. It seemed logical that the combination of a small sealed lead acid battery coupled with a small solar panel would be able to provide year-round power for my trail cameras (which have an AUX port for a power supply).

I needed a solution that would be reasonably portable, waterproof and with sufficient power to drive the camera(s) even if the sun doesn't appear for days.

{{< figure src="images/200225-043.jpg" caption="If the sun doesn't appear for days ..." alt="If the sun doesn't appear for days ..." >}}

My amateur back-of-an-envelope calculations suggested a 7Ah battery would be sufficient, coupled with a 5W or 10W panel. These calculations were based on the [measured power consumption of my trail cameras](https://www.trailcampro.com/collections/browning-trail-cameras/products/browning-recon-force-advantage#battery).

All of my trail cams are made by Browning, and any details provided below _e.g._ the size/type of connectors used, may be specific to these models (Recon Force Advantage, Spec Ops Advantage and the new Recon Force Edge). In particular note that these Browning models are 12V cameras, whereas many other makes need only a 6V supply.

## Parts list

See notes section at the end of the page for an update to the parts list

**Solar panel** kit - 10W 12V monocrystalline solar panel, charge controller and connectors from [Photonic Universe](https://www.photonicuniverse.com/en/). They also sell through Amazon [^554]. You can buy the parts individually for about the same price.
[^554]: Take care if buying through eBay as there are some ~~crooks~~ resellers there who hike identical kit prices by 50%.

{{< figure src="images/200207-020.jpg" caption="Charge controller" alt="Charge controller" >}}

**Sealed lead acid rechargeable battery** - 7Ah 12V. These are readily available new but you might be able to scrounge one from a defunct computer uninterruptible power supply, a mobility scooter or kid's electric toy car.

MTM waterproof 'ammo' **storage box** - I used what I had available (50 calibre model), but the smaller model 30 calibre model would have been sufficient. Any waterproof box would do, but these have a convenient carry handle and are pretty robust.

**Cable glands** - these are available in a variety of sizes and most are too large for the relatively thin cables that connect the solar panel and the trail cam. I used PG7's which are about the smallest I could easily find on Amazon.

{{< figure src="images/71QkFGBsj5L._AC_SL1500_.jpg" caption="Waterproof cable glands" alt="Waterproof cable glands" >}}

Trail cam **power supply cable** - for Browning cameras you need a **5.5mm x 2.1mm male connector**. Other cameras may well be different. You can buy the connectors separately for a few pence from electronic component shops, or pre-wired with male/female ends as extension leads in various lengths from eBay for a couple of pounds.

{{< figure src="images/s-l1600.jpg" caption="Male (top) and female (bottom) 5.5 mm x 2.1 mm DC connectors, pre-wired" alt="Male (top) and female (bottom) 5.5 mm x 2.1 mm DC connectors, pre-wired" >}}

Miscellaneous items - a few bits of scrounged closed cell foam, a couple of spade end connectors and some small zip ties.

Tools - soldering iron (not strictly necessary, but it helps to secure the spade end connectors and to tidy up the ends of wires), pliers, small screwdriver and a sharp knife. You may also need a multimeter to be certain of not frying your camera - see below.

{{< figure src="images/200207-021.jpg" caption="Cable glands fitted and tightened down" alt="Cable glands fitted and tightened down" >}}

In addition, you will need a drill bit of a size suitable for the cable glands. For the PG7's I used this was a 12mm bit and a small amount of widening with a fine file. 

## Assembly

- Securely fit the battery in the box. I used closed cell foam to pack it in tightly, preventing any lateral movement, but still leaving ample space above the battery for the wiring and charge controller.
- Drill the side or end wall of the box for the cable glands. You'll need at least two - one for the solar panel wire and one for the trail cam power cable. Make sure the fitted cable glands do not prevent securely locating the battery. Also ensure that the lid of the box does not foul the cable glands when opening/closing.
- Make up a short battery cable with spade end connectors at one end and bare wire tails at the other. Connect the battery to the charge controller using the labelled connections (and consult the instructions if necessary). Positive to positive and negative to negative. _It is important to connect the battery to the charge controller **before** you connect the solar panel._ The battery should be protected with an inline fuse (1.25 - 2 times the rated current of the charge controller). The Photonic Universe kits include this.
- Run the solar panel cable through a cable gland and connect to the input connectors on the charge controller. Ensure there's sufficient slack cable inside the box to pack everything down neatly in due course. Tighten up the cable gland.
- Run the power cable through a cable gland and attach to the power output connectors on the charge controller. _Note **carefully** the positive and negative connections - see below._ Tighten up the cable gland.
- Check all connections are secure, tidy away the wiring - using zip ties where necessary - and place the solar panel outdoors in the sun. The PV (photovoltaic) charging and load (the battery in this case) lights should illuminate.
- Close the lid securely, connect the camera and enjoy years of savings on battery replacements :smile:

{{< figure src="images/200207-019.jpg" caption="All ready to go" alt="All ready to go" >}}

As the photo above shows, there's ample space in the 50 calibre MTM box and a smaller box would have been sufficient.

## Be positive

The Browning cameras need the centre pin of the power cable to be **positively** charged.

{{< figure src="images/200207-015.jpg" caption="Browning trail cam AUX power input showing positive centre pin." alt="Browning trail cam AUX power input showing positive centre pin." >}}

**Don't mess this up** or there's a chance of frying the camera. If there's any doubt, hook the ends of the power cable up to a small multimeter and confirm that the centre pin is positive. This is what I did. Better safe than sorry :anguished: .

When the camera is running from the internal batteries the remaining charge is shown in the bottom left of the screen.

{{< figure src="images/200207-016.jpg" caption="Battery power - £12 of AA's installed" alt="Battery power - £12 of AA's installed" >}}

When you plug in the external power cable this changes to indicate the presence of an AUX power supply.

{{< figure src="images/200207-017.jpg" caption="External battery" alt="External battery" >}}

The camera does not need any internal batteries to run, so these can be removed and used for a camera in heavy woodland or deep shade.

{{< figure src="images/200207-018.jpg" caption="Batteries and battery cage" alt="Batteries and battery cage" >}}

Replace the empty battery cage to help ensure the camera remains watertight.

## In use

I built the first of these external solar powered batteries with long cables for both the solar panel and the camera power supply. In practice I usually co-locate the battery box and the solar panel a metre or two away from the camera in a location that gets a reasonable amount of light.

The solar panel needs to have a good 'view' of the sky, ideally directly south facing. With a sufficiently long power cable it is usually possible to secure the camera facing north (to avoid glare) to a tree with the power supply tucked away out of sight (to anything but the sky) nearby [^100].
[^100]: I'll post more details on optimal solar panel orientation when I discuss my shed lighting sometime in the future.

{{< figure src="images/200207-014.jpg" caption="Solar powered trail camera in use" alt="Solar powered trail camera in use" >}}

The panel's aluminium frame could perhaps be usefully camouflaged but it's surprising how quickly the passing wildlife learn to ignore it.

After just a few days in the field - in pretty terrible weather - the charge controller showed that the battery was fully topped up and the system has continued to work flawlessly ever since.

## Safety notes

There are several posts online describing solar powered trail cameras which do not use a charge controller. These are generally 6V systems and smaller panels. Whatever the voltage, if a charge controller is not used it is important that there is a diode preventing battery drain at night when the panel is not working. Inexpensive charge controllers are about a tenner. They stop overcharging of the battery.

The charge controllers I use have one or more USB outputs which sometimes come in handy ... but that's for a future post.

{{< figure src="images/200226-061.jpg" caption="Here's something I found earlier ... and a solar powered trail cam (top right)." alt="Here's something I found earlier ... and a solar powered trail cam (top right)." >}}

---

## Notes

After several months of faultless operation of the first of these battery boxes I've now built more and they now power all my trailcams. I've made several minor changes to the design:

{{< figure src="images/200607-31.jpg" caption="5W solar panel and MTM Mini AC15 waterproof box" alt="5W solar panel and MTM Mini AC15 waterproof box" >}}

1. I now use a [5W 12V solar panel](https://www.photonicuniverse.com/en/catalog/full/117-5W-12V-solar-trickle-charging-kit-with-5A-solar-controller-and-battery-cable-with-crocodile-clips.html). It's half the size of the 10W panel but appears more than sufficient to charge a 7Ah battery on a camera taking up to 40 x 20 second videos per night. Note that I've yet to have one of these smaller panels running over a full winter.
2. I've switched to a [MTM Case-Gard Ammo Can Mini AC15](https://smile.amazon.co.uk/gp/product/B07NDKBNTT) box. This is a much smaller waterproof case but still has room to house the battery and charge controller. You need to be careful in choosing the position for the cable gland.
3. I now use a single cable gland to take all the wiring bundled together. It needs to be larger than the PG7 specified above. I use PG11 cable glands. To avoid water ingress I wrap the bundled cables with Nescofilm or parafilm before tightening it closed. There are probably better ways to achieve this.
4. I now use a very short cable from the solar panel to the battery box and a 5m power cable to the camera. I zip-tie the solar panel loosely to the handle of the battery box which keeps it in place. There is now only one trailing cable to coil up and it's rare I cannot find a sky-exposed location within 5 metres of the camera.

{{< figure src="images/200607-35.jpg" caption="Small but perfectly formed" alt="Small but perfectly formed" >}}

These work very well and power three different Browning trailcams including the new [Recon Force Edge](https://shop.naturespy.org/product/browning-recon-force-edge-wildlife-camera-btc-7e/) which has the useful ability to be set on a timer _e.g._ to only run from 8pm to 7am.
