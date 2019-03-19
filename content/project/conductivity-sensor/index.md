+++
# Project title.
title = "Contactless Water Conductivity Sensor"

# Date this page was created.
date = 2019-03-15T00:00:00

# Project summary to display on homepage.
summary = "Corrosion-immune and biofouling-resistant sensor for measuring conductivity in natural or urban freshwater systems"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["sensors", "hydrology", "electronics", "electrical engineering", "instrumentation", "microcontrollers", "coding"]

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
Jan 2017 - Jun 2018

# Project Description
This project was for my Masters thesis at the University of Minnesota. The objective of this project was to develop a cheap and more rugged alternative to conventional water conductivity sensors, which are often susceptible to corrosion and fouling despite being quite expensive. This flaw exists because water conductivity is conventionally inferred by measuring the electrical resistivity of the water, which requires the direct contact of metallic electrodes with the water under test. I have avoided this problem in my design by measuring electrical impedance instead of electrical resistance. Thus, the sensor can use electrodes insulated from the water in an arrangement similar to a parallel-plate capacitor.

After coming up with the operating principle of the sensor, I designed, simulated, built, and characterized various prototypes. Prototypes were calibrated by comparison with a commercial conductivity sensor in saline solutions of various concentrations. The final prototype I presented at my thesis defense was paired with a commercial microcontroller/DDS board and was capable of processing the raw signal from the sensor and logging data in real units.

# Project Links
- [Github repo](https://github.com/KeiranCantilina/Contactless_Conductivity_Sensor)
- [Full text of my thesis](https://conservancy.umn.edu/handle/11299/200148)

# Acknowledgements
 Thanks to Dan Furuta for help with testing and troubleshooting during the iterative design process, and for lending me his vintage impedance analyzer.
 Thanks to Hanna Lin for moral support, without which this project would have been impossible.


# Project Photos
<center>{{< figure src="0215181346.jpg" title="The testing and characterization setup" >}}</center>
<center>{{< figure src="0215181346b.jpg" title="Tsunami DDS/ucontroller board" >}}</center>
<center>{{< figure src="1121171239a.jpg" title="Top view of sensor before potting in epoxy" >}}</center>

