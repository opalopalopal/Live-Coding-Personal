I decided to import some of my own samples into strudel because I'm very picky about the sounds I use and it's easier for me to just focus on the code if I know the samples I'm pulling will be satisfying. I practiced all week using strudel but I kinda wanted to test my skills and come into Scratch today pretty blindsided, so that's what I did. During our 45 min work time I came up with some code and pasted it into a google doc for me to reference later if needed. Which I did need. When Siti Sarah came in, I let her listen to my patch and played her roughly what I waw planning on doing, and then we worked separately on our code until it was time. I got so nervous when it was time to perform that I lowkey forgot how to code for a minute. I think next time I'm going to write my code down on some paper to reference instead of switching tabs. That might calm my nerves. Overall, it was fun and I'm excited to perform for the class!!!

$: s("opal_pad").n(4).note("c3")
  .delay(0.5)
  .postgain(2)


$: s("[bd ~]!2")
  .duck(2)
  .duckattack(0.4)

$: s("~ sd [~ sd ] ~").slow(2)
  .delay(0.5)

$: s("[hh hh]!6 [hh ~]!2")
  .hpf(11000)

_$: s("opal_arp").n(2).note("<c3 c3 c#3 [c3, e3]>")

$: s("opal_bass").n(2).note("<c2 c2 c2 c2>")
  .distort("<0 1 2 <2.7 0.7>>")
   .orbit(2, 0.5)

$: note("64 64 64 64 | 64 64 64 [64 64 64 67]").s("saw")
  .bpf(2000)
  .room(0.5)
  .tremolosync("2")
  .postgain(0.5)

_$: s("opal_riser").note("< ~ ~ ~ c3>")
  .room(0.7)
  .delay(0.5)
  .postgain(1.5)




