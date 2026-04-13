I did the same thing with Hydra as I did with Strudel, where I messed around for the week finding code combinations I liked, and then saved them in a Google Doc to be able to refer to later. I listened to Siti Sarah's music vibe before we played, and fixed up my code a bit to fit her music better. I labeled all my code to be able to reference easier, and then made minimal changes as Siti Sarah played to smoothly transfer from one patch to the next when appropriate with her music.
Color shifting bouncing tie dye pixels
gradient(0.3,0.7,0.1) 
 .repeat(3, 3, 0)
  .pixelate(13)
  .diff(noise(3, 2, 1)).add(osc(1, 1, 5))
  .posterize(3,3,5)
  .modulateRotate(osc(5))

 .invert()
  .colorama(0.5, 0.1)
  .modulateScale(osc(4, -0.5, 0))

 .out()

velvet
gradient(0.3,0.7,0.1) 
  .pixelate(13)
  .diff(noise(3, 2, 1)).add(osc(1, 1, 5))
  .thresh(3,3,5)
  .modulateRotate(osc(5))
 .invert()
  .colorama(0.5, 0.1)
  .modulateRepeatY(osc(4, -0.5, 0))
 .out()


Tie dye
gradient(0.3, 0.7, 0.1).scale(1.5,[0.25,0.5,0.75,1].fast(0.25),[3,2,1])
  .invert([0,1].fast(0.1))
  .kaleid(5)
  .kaleid(9)
  .scale( ()=>Math.sin(time/5)*0.5 )
  .rotate(1, 1)
  .out(o0)

Black white and orange noise
osc(10, 2, 10).rotate( () => time%360 )
.rotate(2, 2)
 .layer(solid(0.2, 0.5, 0.8))
 .mask(shape(30, 0, 0.6))
 .add(noise(3, 0.5, 1)).diff(shape(1, 1, 5))
 .out(o0)

Pink square
osc(10, 2, 10) 
 .layer(solid(0.2, 2, 0.8))
 .mask(shape(30, 0, 0.6))
 .mult(voronoi(3, 2, 1)).diff(shape(1, 1, 5)).pixelate(3)
 .out()

.add(o1, () => (Math.sin(time/4) * 0.7 + 0.1)))

Classic kaleidescope
osc(12, 0.5, 0.5).scroll(5)
  .diff(shape(8, 0.3, 0.5))
  .mult(voronoi(10, 0.4, 0.2)).rotate(1, 0.5)
.add(shape(3, 0.2, 0.5)).invert().kaleid(4).out()


Rainbow pulsing noise
gradient(4, 0.4, 5)
.diff(noise(3, 10, 2))
.mult(shape(360, 0.4, 0.9))
.add(osc(20, 0.7, 0.7)).layer(solid(0.2, 0.4, 8))
  .mult(noise(3, 2,1)).add(gradient(1, 1, 5)).posterize(3, 3, 5)
.modulateRotate(osc(5))
.out()
