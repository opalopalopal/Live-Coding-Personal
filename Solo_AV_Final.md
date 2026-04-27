I found the "numbers" sample pack in strudel and decided immediately that I wanted to use it. I then started out how I always do, by making a drum beat I like, and then finding a bass line to match. This time I started out with the descending piano line, and then added a filtered supersaw underneath for beat-drop purposes. Then I just went aheaad and added little flourishes and pads as I saw fit to fill space. I also added the number sample bank pitched up and down because I thought it was funny. With visuals, I love showing my face. I think it's cool. I added colorama and posterize because I also thinkg it's cool. The noise exposing and covering my face was also cool. Honestly, the way I approach visuals is just by throwing random stuff in and keeping what I like. So that's what I did. Thanks for the wonderful semester, I am definietly going to keep coding after this class :).

//STRUDEL CODE
_$: s("rolandtr909_bd ~ rolandtr909_bd ~")
  .duck(2)
  .duckdepth(0.7)
  .duckattack(0.4)

_$: s("~ rolandtr909_sd").delay("<0.5:0.25 1.3:0.75 0 >")
  .pan(0.4)
  .postgain(0.6)

_$: s("[hh hh [oh ~] hh]!2")
  .bpf(13000)


_$: s("steinway").n(1).note("<f2 e2 d2 ~>")
  .room(1.2)
  .postgain(0.3)

_$: n(rand.range(0,7).segment(8))
  .scale(chooseCycles("F:pentatonic", "C:Major"))
  .s("balafon_soft")
  .postgain(3)
  .degradeBy(0.2)

_$: note("<~ [ ~ ~ ~ f3] d4 ~>").s("harp")
  .room(2)
  .distort(1.5)

$: s("gm_fx_echoes").note(choose("E3, F4", "F4, E4"))
  .room(0.8)
  .bpf(2000)
  .orbit(2)

_$: note("<~ ~ ~ [~ ~ ~ ~ d3 e3 f3 g3]>").s("gm_agogo")
  .room(0.5)

_$: s("numbers").n("<1 2 3 4> | <5 6 7 8 9> | <0 0 1 0> | <9 8 7 6>").note("c2 | b2")
  .sometimesBy(0.5, p => p.fast(2))
  .degradeBy(0.2)
  .distort(2)
  .postgain(0.2)
  .pan("<1 0 1 0>")

_$: s("numbers").n("<8 7 6 5 4 3 2 1>").note("c2")
  .clip(1)
  .distort(2)
  .postgain(0.2)
  .pan("<1 0 1 0>")

_$: s(" ~ ~ [bongo ~ bongo] ~")
  .distort(3)
  .pan(1)

_$: note("<[f1 a1] [e1 a1] d1 g1>").s("supersaw")
  .room(1.2)
  .orbit(2)
  .lpf(800)
  .postgain(1.3)

_$: s("shaker_small!4").fast(2)
  .postgain(4)

_$: note("<[[c4 d4 f4 g4 a4 F5]!2]>").palindrome().s("gm_pad_bowed")
  .room(1)
  .hpf(5000)
  .postgain(1)
  .pan(sine)



//HYDRA CODE

s0.initCam()
src(s0).add(solid(0.2, 0.3, 0.8))
 .mult(noise(1.2, 1, 1))
  .posterize(4)
  .colorama(3)
  .hue(() => Math.sin(time))
  .brightness(0.5)
  .modulate(noise(5),()=>a.fft[0])
  .saturate( () => Math.sin(time))
 .out()
