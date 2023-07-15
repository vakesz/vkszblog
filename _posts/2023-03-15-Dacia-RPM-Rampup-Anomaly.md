---
layout: post
title:  "Dacia RPM Rampup Anomaly"
date:   2023-03-15 18:11:30 +0200
categories: vakesz vksz who dacia anomaly
share-title: "Dacia RPM Rampup Anomaly | vksz.io"
cover-img: "/assets/img/dokker_cover.webp"
css: "/assets/css/video-embed.css"
---

I had a discussion with my father a few weeks ago during the family day of Continental, and he has a car namely Dacia which has issues with holding a stable rpm during driving. (We do not live together for quite a while.) Since there were multiple presentations held about how each of the systems works in the car this problem just came up.

Since I don’t have a complete understanding of how a car altogether works completely, I tried to talk with some of my colleagues whether they have some ideas on how to diagnose this behavior, but mostly the suspicion was about the throttle pedal itself that it might not provide a linear signal to the motor control unit, or simply the connection of it has contact failure. But sadly, this was not the case. We took the car to the service, where they measured the pedal travel to see if it reflects its values correctly. Everything seemed fine.

> He’s the first owner of the car and it has been malfunctioning ever since it was taken out of the shop. Also the car received many firmware updates, for each related ECU but still didn’t resolve this issue.

<p align="center">
<img src="/assets/img/Prague_2017_Dacia_Dokker_1.webp"><br>
<font size="1px">Dacia Dokker 2017 1.6</font>
</p>

Last weekend, I choose to stay at my dad’s place for the weekend, had some breakfast, and went down to the garden and it came into my mind that, hmm. The car is here and we still couldn’t figure out the root cause of the issue. I opened it up, unplugged the pedal connectors, and checked them if they have any issues by look or not, but couldn’t spot anything so just reseated them.

Then I noticed that there was an ELM327 module in the car, so I got curious and connected it to the car’s OBD connector and started downloading some apps for it on my iPhone. After trying for at least an hour I concluded that it’s not supported on iOS for some reason to use these modules and only Wifi ones work, I grabbed some old Samsung tablet that I had around and downloaded the first app that came in front of me in the Google Play Store and voila! It worked right away. OK, so then the fun begins. 🙂

<p align="center">
<img src="/assets/img/elm327.webp"><br>
<font size="1px">ELM327 BT LE</font>
</p>

I tried to hold the pedal myself in a stable position while looking at the OBD outputs, but couldn’t focus on it, although it was already weird for me that the car just revs up, while just holding at around 15-20%. Then I asked my father to try to hold the pedal in a fixed position so I could make a video about the diagnostic output.

{% include youtubePlayer.html id="8EJ7jPH_4eE" %}

We currently only have a few suspicions about it, but it’s highly likely that maybe there’s a very small vacuum leak, which is not setting any DTC on the ECUs and while the car draws in more air due to the leak the RPM ramps up. (More air = more fuel) It can also be observed that the car has a bit higher than reasonable gasoline consumption.

If we succeed to find or prove this theory then I’ll share my findings. Until then, take care and have a nice day!