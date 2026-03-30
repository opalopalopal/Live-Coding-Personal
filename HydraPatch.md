s0.initImage("https://images.squarespace-cdn.com/content/v1/583b4d62d2b857c44d4d4c90/1596659266645-T8091JBBOB2QXR6S6FOV/e507e49ec05ef75d1b5dd118bafa3e76d06c7b24.jpeg")
src(s0)
.kaleid(10)
.add(osc(12)
  .color(0.7, 0.3, 0.9))
.diff(noise(10))
.layer(solid(2, 1, 2).mask(shape(30, 0, 0.6).add(voronoi(12))))
.brightness(0.1)
.out(o0)


I started out by finding a picture of a cuttlefish because I love them. And then I did the kaleid feature to fill my screen with a bunch of cuttlefish. I thought adding dark purple-ish oscillator feature on top would look cool, so I did. I added some noise on that whole image, as well as made it brighter, and then I lost everything. Oops. I started over, and redid exactly what I'm writing out now. I probably did some things differently the first time but I don't remember. I added a white highlight in the center using the shape feature and making the smoothing pretty blurred. I made all the RGB values high to make it white. I tried to put the voronoi over just the highlight but it was added on top of everything. I didn't mind it though, so It stayed. And that's what I did 
