+++
# Project title.
title = "Portrait Printing Typewriter"

# Date this page was created.
date = 2019-02-16T00:00:00

# Project summary to display on homepage.
summary = "Brother SX-4000 electric typewriter modified to print JPGs as ASCII text"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["electronics", "hardware hacks", "microcontrollers", "python", "hardware-software"]

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
Aug 2017 - Sept 2017

# Project Background
This project began when I picked up a sad typewriter with a broken keyboard set out for free in front of the university library. Since I have a soft spot for obsolete technology, I gave it a new home. Repurposing it became a recreational exercise in both hardware-microcontroller and microcontroller-computer interfaces.

# Project Description
Images are broken down into lines of text by a Python script on a laptop, which then sends lines of ASCII via a serial-USB interface to an Arduino-style microcontroller. The microcontroller then emulates typewriter keypresses using the transistor array to switch the typewriter’s keyboard matrix.

Mapping out the keyboard matrix was tedious, but the trickiest part was getting the computer and microcontroller to be patient. The microcontroller can switch the keyboard matrix much faster than the typewriter's daisy wheel can spin, and the typewriter's keyboard buffer only holds a few characters (presumably because fingers are usually slow). Without some way to make the system wait for the typewriter to finish typing, the typewriter tends to receive characters faster than it can type or remember them. I solved this problem by estimating an average typing time per character, and forcing the microcontroller to wait that interval before sending another character. Once the microcontroller has sent a complete line, it sends a message back to the Python script that it is ready to have its serial comms buffer filled with another line. 

 A Rasberry pi and webcam might be added eventually to integrate the whole system inside of the typewriter enclosure. This could be set up as a sort of photo-booth arrangement where one only has to push a button for a selfie to begin printing.
 
 If you decide to replicate this project, beware: you may find yourself searching for long-obsolete typewriter ribbons on ebay at 2 in the morning.
 Also beware: typewriters are always louder than you expect.


# Project Links
- Code, files and more pictures can be found at this [Github repo](https://github.com/KeiranCantilina/Typwriter-Portrait-Project)


# Acknowledgements
 Thanks to my lovely wife for putting up with CLACK-CLACK-CLACKCLACK-CLACK ad infinitum without becoming a voluntary widow.
 Thanks to the University of Minnesota librarians for putting old things out for free instead of just chucking them in the trash. 


# Project Photos
![photo1](https://github.com/KeiranCantilina/Typwriter-Portrait-Project/blob/master/FInal%20setup.jpg?raw=true)
![photo2](https://github.com/KeiranCantilina/Typwriter-Portrait-Project/blob/master/0826171633.jpg?raw=true)
![photo3](https://github.com/KeiranCantilina/Typwriter-Portrait-Project/blob/master/0825171817a.jpg?raw=true)
![photo4](https://github.com/KeiranCantilina/Typwriter-Portrait-Project/blob/master/0826171318.jpg?raw=true)
![photo5](https://github.com/KeiranCantilina/Typwriter-Portrait-Project/blob/master/0826171633c.jpg?raw=true)
![photo6](https://github.com/KeiranCantilina/Typwriter-Portrait-Project/blob/master/0825171817.jpg?raw=true)


