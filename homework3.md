So I started by sorting through all the samples Strudel provided, I was looking for a sound with a medium-ish amount of audible harmonics and legato in nature. I figured a sample like this would be easy to turn into percussion. I started with the kick by finding the lowest note Strudel could produce with the sample provided. I wasn't able to code notes below c1, so I transposed that note by two octaves to get it in the range I wanted. Then I added a LPF, a pitch bend, and some distortion to turn the pitch into a more rhythmic element.  
I copy and pasted my kick drum code for the snare and hihat and changed the filters to make them sound less like a kick. I took away the pitch bend element and changed the LPF to a HPF for both the snare and hihat. I heard the rhythm that I wanted in my head, so I just had to do some finessing and trial and error to make it happen.
I decided to make the bass note D because I like that note. I also copy and pasted from the kick for the sample name and effecs. I changed the LPF, crush, gain, and room accordingly and then worked on the rhythym. I like glitchy kinds of noises, so I decided to have the bass play a quarter note, and then glitch out. I played around with the frquency number in the quarter note duration until landed on 3 16 notes and the 1 16th rest.
For the bass chord type thing I had originally wanted to have a separate bass lines above the glitchy bass drone, but then accidentally layered the 55 and 59 note values instead of playing them after one another and really enjoyed it. So I ran with that.
The drone was mainly for ambience. I wanted a long strung out note so I used the euclidLegato function. I played around with different values and liked how the 4, 8 values sounded like side chain compression, so I stuck with it.
The melody was really difficult, I couldn't find anything that I liked. The sound was really beautiful, I think mmy ADSR and room values are perfect. But none of my rhythmic or pitch values sounded good to me. I played around with chord progressions and various chord arpeggiations and landed on this. 
For the performance itself, I'm gonna do the classic and start with the bass and then introduce kick snare and hihat. Then I'll add the bass chords and dip out the hihat to add the drone. Then I'll take out the bass chords and snare and add melody so its just kick, drone, and the melody. Then I'll add back in the snare, hihat, bass, and bass chords to finish off.

//kick
_$: note("[c1 ~!10] [~!10 c1 ~]")
.transpose("-12")
.s("gm_pad_bowed")
.lpf("200")
.penv(1, 0.1, 0.5, 0.1, -12)
.crush(10)
.gain(10)
.room(0.5)

//snare
_$: note("~ [d4 ~!12]")
.s("gm_pad_bowed")
.hpf("500")
.adsr(0, 0, 0.5, 0.3)
.crush(4)
.gain(6)
.room(0.3)

//hihat
_$: note("g5!4")
.s("gm_pad_bowed")
.hpf("200")
.adsr(0, 0, 1, 0)
.crush(4)
.noise(100)
.gain(0.4)

//bass
_$: n("1 [1!3 ~]").note("62")
.transpose("-36")
.s("gm_pad_bowed")
.lpf(180)
.adsr(0, 0.1, 0.5, 0.1)
.crush(10)
.gain(3)
.room(0.3)

//bass chord?
_$: n("1 [1!5] 1").note("~ [55, 59] 69")
.transpose("-36")
.s("gm_pad_bowed")
.lpf(300)
.adsr(0, 0.1, 0.5, 0.1)
.crush(10)
.gain(2)
.room(0.3)

//drone
_$: n("50, 65").sustain(0.5).euclidLegato(4, 8)
.s("gm_pad_bowed")
.lpf(180)
.adsr(0, 0.1, 0.5, 0.1)
.crush(10)
.gain(2)
.room(0.5)
.pan(saw)

//melody
_$: note("[[62 60 58]!4 | [[56 62 60]!4]]")
.s("gm_pad_bowed")
.hpf("7000")
.room(2)
.adsr(0.1, 0, 0, 0.2)
.gain(1)


