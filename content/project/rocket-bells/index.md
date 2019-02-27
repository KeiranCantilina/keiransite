+++
# Project title.
title = "Musical Rocket Bells"

# Date this page was created.
date = 2019-02-19T00:00:00

# Project summary to display on homepage.
summary = "What would rocket nozzle bells sound like if they were played like musical bells?"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["CAD", "finite element analysis", "R", "music", "audio synthesis", "fourier synthesis"]

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
July 2017


# Project Background
My friend Dane emailed me one day to tell me about a dream he had. It was a long and convoluted (as dreams often are), but the part that stuck out to me was a scene he described where I ran around a space rocket nozzle factory playing the nozzles like bells. 

As a person that plays real non-dream bells semi-professionally, I became intensely curious: how exactly _would_ it sound if I was in a rocket nozzle factory playing the nozzles like bells? 

This project was an attempt to find out (using every conceivably relevant tool available to me, just for fun).

# Project Description
The first step to figuring out how rocket bells would sound is to make a model of a typical rocket bell nozzle.

Since I had recently read that modern rocket bells use Inconel 718, I chose that to be the material for our nozzles. For dimensions, I found a simple drawing [here](http://isaacperrin.com/designing-and-simulating-a-liquid-bipropellant-aerospike-rocket-engine). 
<center>{{< figure src="template.png" title="Rocket bell drawing" >}}</center>

I was too excited to sit down and trace the drawing by hand, so I imported it into Inkscape and used the bitmap trace function to generate a DXF.
This made a bit of a mess, but mostly everything was there. I imported the DXF into AutoCAD and cleaned it up a bit to make a profile (with an eyeballed thickness).
<center>{{< figure src="autocad.PNG" title="Nice and clean.">}}</center>

With a profile to import into AutoDesk Inventor, it was easy to generate a solid by revolving the profile. I set the material properties to that of Inconel 718.
<center>{{< figure src="rocketbell.png" title="Tada, pretty solid!">}}</center>

Now that I had a model, it was time to figure out how it would sound. To figure out where to start, let's look at some basic campanology!
***
___
### Campanology 101 detour

In a normal musical cup-shaped bell, the bell is usually hung from its crown and struck at the rim (called the soundbow) with a clapper. When struck, a bell vibrates in many modes all at the same time, with each vibrational mode producing its own signature pitch. These pitches (known as "overtones") are not harmonically related, which is why bells sound kinda weird |compared to other musical instruments.

<center>{{< figure src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Erfurt_Bell.png/440px-Erfurt_Bell.png" title="First several bell overtones (picture from Wikipedia)" >}}</center>

The perceived pitch of the bell (called the "strike tone") is actually a psychoacoustic phenomenon. The brain hears the lowest 6-ish overtones of the bell, and (due to currently not fully understood reasons) tries to interpret those overtones as if the bell was an instrument with harmonically related overtones. This results in the brain fabricating a strike tone which is then perceived as the pitch of the bell. For more information, see [this Wikipedia article](https://en.wikipedia.org/wiki/Strike_tone) or [this excellent site](http://www.hibberts.co.uk/index.htm).
***
___
So now with that explanation out of the way, it's clear that I had to figure out the vibrational modes of our rocket bell.
To make things simpler, I decided to assume our rocket bell was hung by the waist between the bell and the little portion on the other side.
With a constraint set to the waist of the nozzle, I then performed a free-space modal analysis using Inventor's built-in FEA tools. This told me the vibrational modes of the the nozzle and their frequencies.

<center>{{< figure src="fundamental.PNG" title="Fundamental mode of the rocket bell (Hum tone)">}}</center>
With this data in hand, I pushed it through my [Bell synthesizer R script](https://github.com/KeiranCantilina/FEA-Bell-simulation/blob/master/Bell%20sound%20simulation%20FINAL.R). Since Inventor's FEA doesn't give me relative amplitude of each mode, I chose to assume that the relative amplitudes and decay curves for each mode would match that of a true musical bell of approximately the same size.

Here's what came out of the script:
<iframe width="100%" height="100" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/334401793&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe>

Fantastic! Sounds believable. 

I couldn't help but to try to "play" a song with rocket bells. I made a soundfont (available [here](https://github.com/KeiranCantilina/Rocket-Bells/blob/master/Rocket%20Bells.sf2)) and pitch-shifted the original sample up and down to make a nice playable range. This isn't really realistic (bells usually change timbre nonlinearly with pitch, due to material property limitations) but it's fun. :P With a royalty-free MIDI file and 5 minutes spent fiddling in MuseScore, I generated the monstrosity below.

Here's Auld Lang Syne played with Rocket Nozzle Bells:
<iframe width="100%" height="100" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/334404425&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe>




# Project Links
- [Audio](https://soundcloud.com/keiran-cantilina/rocket-bell-1)
- [Audio](https://soundcloud.com/keiran-cantilina/auld-lang-syne-played-by-extrapolated-rocket-bells)
- [Github Repo](https://github.com/KeiranCantilina/Rocket-Bells)
- [Bell synthesizer code](https://github.com/KeiranCantilina/FEA-Bell-simulation/blob/master/Bell%20sound%20simulation%20FINAL.R)
- [Rocket Bell Soundfont](https://github.com/KeiranCantilina/Rocket-Bells/blob/master/Rocket%20Bells.sf2)


# Acknowledgements
Thanks to Dane Kouttron for sharing his dreams! 


# Misc Project Photos
<center>
{{< figure src="rocket bell mode_1543Hz.png">}}
{{< figure src="featured.png" >}}
{{< figure src="Capture.PNG" title="Inventor FEA tool" >}}



