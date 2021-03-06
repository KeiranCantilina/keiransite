+++
# Project title.
title = "The Scanmera"

# Date this page was created.
date = 2019-02-15T00:00:00

# Project summary to display on homepage.
summary = "Microtek ScanMaker4900 flatbed scanner modified into a large-format VIS-NIR multispectral camera"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["sensors", "hardware hacks", "photography", "instrumentation", "electronics"]

# Optional external URL for project (replaces project detail page).
# external_link = "http://example.org"

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder.
[image]
# Caption (optional)
#  caption = "caption here"

# Focal point (optional)
# Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"

# Does the project detail page use math formatting? (old version of hugo site)
# math = false

+++

# Timeline
Nov 2017 - Current


# Project Background
This project began as a just-for-fun repurposing of an obsolete scanner, but I soon discovered that the linear CCD in this scanner is very sensitive to near-infrared (NIR) wavelengths. This sensitivity, along with the high resolution of images produced by the Scanmera, means that I can potentially use it to measure the health of crops in fields by measuring the Normalized Difference Vegetation Index (NDVI), which is based on relative Red/IR reflectivity of plants. 

# Project Description
<center>{{< figure src="test034_contrast_compressed.png" title="" >}}</center>

You can see how brightly vegetation shows up in the photo above. The weird vertical artifacts are actually passing pedestrians. Because the scanmera acquires images slowly from left to right, any moving objects get distorted along the horizontal axis.

The Scamera uses a 330mm doublet lens from an abandoned overhead projector. The scanner was heavily modified and none of the original optical assembly remains except for the imaging sensor. The sensor is so sensitive to IR that cardboard isn’t sufficiently opaque, hence the need to line the enclosure with foil. The only way to control exposure and depth of field is by using laser-cut cardboard apertures because there is no shutter. 

<center>{{< figure src="1109171424.jpg" title="Doublet lens" >}}</center>
<center>{{< figure src="1109171505.jpg" title="Modified imaging sensor assembly" >}}</center>	
<center>{{< figure src="1121171702.jpg" title="Cardboard apertures" >}}</center>

The scanner likes to eat 16V, and due to lack of resources the current power supply is a horrible assembly consisting of a 16V switching power supply plugged into an automobile DC-AC converter which is hooked up to a 12V SLA battery salvaged from a dead UPS. One day I will use a 12V-16V boost converter like a normal person. For pseudo-portability, the whole thing is set up on a cart from IKEA. It's juuuust short enough that I have to stoop when pushing it around.

<center>{{< figure src="1109171409.jpg" title="Sketchy power system" >}}</center>
<center>{{< figure src="Capture2.PNG" title="The system on its glorious IKEA cart" >}}</center>

Future work involves a chassis overhaul (for better portability), improved lightproofness (which should fix contrast issues), and a more stable/less noisy power supply (which should reduce the severe noise issue visible in pictures). 

# Project Links
- [Github repo](https://github.com/KeiranCantilina/Scanmera)
- [Full-resolution project images ](https://drive.google.com/open?id=11ls2AhE8IGYdJVQsz3RzfAySejQ5RCwX)(Note: Many images produced by the camera have a 1:5 pixel aspect ratio)



# Acknowledgements
 Thanks to Dr. Pete Marchetto for making acquisition of the scanner possible, and thanks to Dane Kouttron for help troubleshooting the noise issue.
 
 Much life-debt was owed to Hanna Lin for standing out in sub-0 temperatures with me while I carted around a silly contraption.


# Project Photos
![photo1](https://github.com/KeiranCantilina/Scanmera/blob/master/test_020_shrunk.png?raw=true)
![photo2](Capture.PNG)
![photo3](test035.png)
![photo4](test034_contrast_compressed.png)
![photo5](11_21_2017_1604_f022_002.png)
![photo6](1121171702.jpg)
![photo7](1115171600c.jpg)
![photo8](1109171409.jpg)


