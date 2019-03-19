+++
# Project title.
title = "Long-Distance Relationship Light"

# Date this page was created.
date = 2019-02-19T00:00:00

# Project summary to display on homepage.
summary = "A pair of networked RGB LED widgets that synchronously change color when one of them is activated"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["internet of things", "electronics", "microcontrollers", "C++", "ESP8266", "Arduino", "hardware hacks", "coding"]

# Optional external URL for project (replaces project detail page).
# external_link = "http://example.org"

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder.
[image]
# Caption (optional)
#  caption = "caption here"

# Focal point (optional)
# Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Center"

# Does the project detail page use math formatting? (old version of hugo site)
# math = false

+++

# Timeline
May 2018

# Project Background
A few weeks before my wife and I were to be apart for the summer (due to me studying abroad and her only able to join me there in the fall), my wife stumbled upon [these](https://www.thedailybeast.com/sync-with-long-distance-loved-ones-using-lamps) "Long Distance Friendship Lamps." I loved the idea, but I was less enthusiastic about the fact that the operation of the lamps depended on the continuous operation of the company servers. Also they were $150 for a pair, which was a bit much.

I decided to make a weekend project out of creating my own set! A brief bit of googling revealed that there are similar things out there, but I'm intentionally forging forward without looking at other implementations for the learning opportunity. I also set a $5 budget for myself, beyond which any parts would have to come from scrap or stuff I already had. 

# Project Description
The current design uses a pair of Wildfires (an Arduino-flavor board made by [WickedDevice](https://shop.wickeddevice.com/product/wildfire/)) with RGB LEDS inside of a pair of very cheap button lights from Amazon. The Wildfire is not super well-suited to this project, but it has an integrated ESP8266 wifi chip and a microSD thingy and also I had like 5 of them from work, so that's what I used.

{{< figure src="Capture4.PNG" title="Wildfire board in situ with RGB LED module resting on top" >}}</center>

The software side of things was supposed to be pretty simple. The Wildfire randomly generates 3 values (for RGB) when a button press is detected. These values are published via MQTT to a feed on io.adafruit.com. The device is also subscribed to the same feed, and will collect both values it publishes and values from other devices on the feed. When data is received through the subscription, the device parses the data and uses the RGB values to change its own color.

This was complicated by very buggy firmware on the Wildfire board which made it randomly stop talking to the ESP8266. In addition, for some reason, comments in certain parts of the code would completely prevent the board from subscribing to the MQTT feed. This makes no sense but I was able to work around it. This project would probably have been massively easier if I was able to buy a pair of Adafruit Feathers or even just two normal Arduino pro minis paired with two ESP8266 modules.

I managed to finish the project in time before my departure, and my wife and I were able to use the devices between Ohio and Belgium all summer long.

Future improvements include a migration to more stable hardware, and also custom prettier enclosures.


# Project Links
- [Github repo](https://github.com/KeiranCantilina/IOT-Long-Distance-Relationship-Colorcube)


# Acknowledgements
Thanks to my wife for the idea, and for being patient as I cursed at vaguely defined compile errors. 


# Project Photos
<center>{{< figure src="0422180032.jpg" title="Most recent version" >}}
{{< figure src="0422180012.jpg" title="Enclosure-less prototype next to the most recent version" >}}
{{< figure src="Capture2.PNG" title="Ugly undersides" >}}
{{< figure src="Capture3.PNG" title="Progress picture" >}}
{{< figure src="Capture4.PNG" title="It's a tight fit..." >}}</center>


