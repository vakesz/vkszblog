---
layout: post
title:  "Automotive Hacking and Know-How"
date:   2023-02-08 12:11:30 +0200
categories: vakesz vksz who automotive hacking hack
share-title: "Automotive Hacking and Know-How | vksz.io"
cover-img: "/assets/img/hacking_cover.webp"
---

I’ve been listening to [Hack es Langos Podcast](https://hackeslangos.show/) for quite a while now, and lately, they started to talk about how networks in cars behave function, what can you see or modify in a car and was an interesting topic. First of all, I can highly recommend to anyone interested in IT Security and understands Hungarian to listen to it as well.

Let’s start with the protocols themselves.

 - **FlexRay**\
    FlexRay is a communication bus designed to ensure high data rates, and fault tolerance, operating on a time cycle, split into static and dynamic segments for event-triggered and time-triggered communications. But it’s much more expensive compared to other options.
 - **CAN**\
    It is a message-based protocol, designed originally for multiplex electrical wiring within automobiles to save on copper. For each device, the data in a frame is transmitted serially. Frames are received by all devices, including by the transmitting device.
 - **Automotive Ethernet**\
    What drives for in-vehicle Ethernet are the upcoming ADAS functions for automated and autonomous driving as well as infotainment use cases. Ethernet is cheap, but not very widely used yet.

>There are many other protocols that are being used in the Automotive area, but these are the ones that I’m mostly familiar with and seen being used. Sure, there’s LIN, and CAN-FD as well, but I’d like to just provide a starting point here for you to decide yourself if you’d like to dig deeper into it.

<p align="center">
<img src="/assets/img/network.webp"><br>
<font size="1px">Automotive Networks and their connections.</font>
</p>

# So, how do you start?

All cars have some kind of OBD port for which you can purchase either an ELM module or an Arduino Uno board with a CAN breakout board. The information that you can get through these ports could be very limited since usually it’s only a gateway module and only forwards a small percentage of all the messages of the car and you might not see everything. If you want to get deeper, you have to somehow connect to the harness itself and then you’ll be able to see everything.

In the Automotive world, we’re using Vector CANalyzer/CANoe for this, but these are paid software and probably you can’t get access to it. If you do it in whatever way, use it happily. For others, Wireshark could be a great option as well. But, even if you have the best tools available to do this you’ll need a database for the frames so that you can understand what’s on the network. There’s a so-called OpenDBC on GitHub which contains some cars database file, which most likely has been reverse-engineered or leaked.

# What next?

You can find many interesting projects on GitHub. Such as adding a reverse cam to your car that used to be a paid option during the purchase or so, or just trying some things out. But whatever you do, you have to understand it’s your own responsibility. I highly recommend having an OBD tool so any mistakes you make during your adventure, you can at least send out a ClearDTC to your car and recover the ‘damages’ you’ve made.

I tried to collect many useful pages here where you can find a lot of information about how these systems work or how to go even further. Such as what protection algorithms are mostly used which you can find on the AUTOSAR page, and how OBD is defined, or if you’re just interested in a few videos of either development showcased by LTT, or a replay attack done by Donut Media you can check those below.

# Important links
 - [Awesome Automotive](https://github.com/Marcin214/awesome-automotive) – GitHub
 - [OpenDBC](https://github.com/commaai/opendbc) – GitHub
 - [AUTOSAR](https://www.autosar.org/) – Offical Page
 - [Replay attack example](https://www.youtube.com/watch?v=myW2cxyOHEQ) – Donut Media
 - [BMW’s Billion Euro R&D Facility](https://www.youtube.com/watch?v=3In3u2QpSUE) – LTT
 - [BMW – Concept Autonomous Cars & Motorbike!](https://www.youtube.com/watch?v=PhSooO33Eus) – LTT
