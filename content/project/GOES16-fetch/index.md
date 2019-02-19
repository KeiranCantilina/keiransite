+++
# Project title.
title = "GOES-16 Image Fetcher and Desktop Background Utility"

# Date this page was created.
date = 2019-02-18T00:00:00

# Project summary to display on homepage.
summary = "Want a (nearly) real-time picture of the Earth from space as your desktop background? Look no further."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["R", "remote sensing", "image processing", "web scraping"]

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
Oct 2017


# Project Description
As an appreciator of both pretty pictures and ambitious radio projects, I wanted a real-time "Blue Marble"-style picture of the Earth as my deskop background. 

My first attempt at making this happen was to try to receive the downlink from the [GOES-16](https://en.wikipedia.org/wiki/GOES-16) geostationary weather satellite. GOES-16 is very far from the Earth, so a high-gain directional antenna is needed to listen in on it. Any reasonable person would have gotten a dish antenna, but given my time and budget constraints, I attempted to use an [RTL-SDR](https://www.rtl-sdr.com/about-rtl-sdr/) with an inconveniently-sized corner reflector antenna built out of cardboard and foil, sized for the required gain at ~1600 Mhz. I know I know, If you're familiar antennas, you're probably facepalming at my silliness. In my defense, I had to at least try.

Unsurprisingly, this didn't work. 

Surprisingly, the antenna itself did work very well; unfortunately, my location meant that the satellite was rather low on the horizon with a very electrically-noisy major city right smack-dab in the middle of my line of sight. The RTL-SDR has pretty terrible sensitivity and selectivity to begin with, so I decided to shelve this strategy for now.

Instead, I found that the images from GOES-16 are downloaded every 15 minutes and put on the web (in the form of a fancy app) by NOAA in collaboration with Colorado State University (RAMMB/CIRA-SLIDER, see http://rammb-slider.cira.colostate.edu). Yay! After some sleuthing to find the directory on their server where the pictures are stored, I wrote an R script that fetches the most recent full-disk images of the earth from the website, then formats the tiled image data to work as a desktop background. A batch file called by the Windows task scheduler runs the R script every 15 minutes, and the picture is dumped in a folder configured as a desktop background gallery.


# Project Links
- [Download the scripts at this Github repo](https://github.com/KeiranCantilina/GOES16-fetch)
- [RAMMB/CIRA - SLIDER](http://rammb-slider.cira.colostate.edu/)


# Acknowledgements
Thanks to the folks at NOAA and the Colorado State for making their science publicly available! 
Thanks to Hanna for letting me store that huge ill-fated corner reflector above her desk. 
Thanks to Paul Schuster for helping me improve the timestamp-parsing part of the script.


# Project Photos
{{< figure src="Capture.PNG" title="Purty desktop background (CIRA geocolor). It is also possible to configure the script to retrieve data from any of the other spectral bands GOES-16 can image. I've hidden my desktop icons because the disorganization is embarrassing." >}}
{{< figure src="Capture2.PNG" title="You can see the corner reflector antenna in the top right of this picture. Also visible is my desktop background as featured in this post, and the [Scanmera](https://keirancantilina.github.io/project/scanmera/)." >}}


