
# sito64

![pixelcat](assets/pixelotis.png)

stereo "tape" delay/looper thing for norns

join the conversation at - https://llllllll.co/t/22149

sito is an experimental fork of otis by @justmat, and a fork sito from @olt

Installation:

sito64 is not available from maiden. Open repl on norns.local and type the follwowing to install sito:

```
;install https://github.com/soulpixel/sito64.git
```

Changes to sito:

compatible with 64 grids

TODO:
- update documentation

# grid 


![otis](assets/otis21.png)

* L/R loops are laid out identically.
* touch a key inside the "loop position" area to jump to that point in the loop.
* holding the **grid alt** button and touching one of the speed up/down buttons will return speed to 1.
* holding the **grid alt** button and turning enc 2/3 will "slide" your L/R loops around the buffer. 

---

# lfo's

while holding an **lfo on** button you can edit lfo parameters with the norns encoders and keys:
* enc 1: lfo speed/frequency
* enc 2: lfo depth
* enc 3: lfo offset
* key 2/3: set lfo shape

to "patch" an lfo:

* hold an **lfo on** button
* adjust lfo settings
* touch a control

holding the grid alt button and pressing in the lfo section will "un-patch" the lfo.

---

# speed scales

speed scales are collections of 6 speeds that are playable via the grid. adding your own "tunings" is easy.

* connect norns to wifi and launch maiden
* open the ``dust/code/otis/lib`` folder
* open the file named ``spds.lua``

![spds](assets/spds.png)

to add your custom scale, simply:

* add the scale name to the ``spds.names`` table. (it's likely best to avoid spaces and special characters)

![names](assets/names.png)

* add a ``spds.YourNameGoesHere`` table containing six numbers 0-4.

![scales](assets/scales.png)

that's it! you're a musical hacker person now!
 
# parameter details

### l/r loops
* vol - loop volume
* speed - playback and recording speed
* speed slew - the time it takes for your speed to "settle" at its destination speed.
* loop start - start of your loop in seconds
* loop end - end of your loop in seconds
* feedback - how much of your overwritten material should stick around? 1 is all, 0 is none.
* rec - enable/disable recording
* pan - stereo posistion
* pan slew - time it takes for your pan position to "settle" at its destination position.

### engine
* sample rate
* bit depth
* saturation - tape style saturation amount
* crossover - crossover frequency for the effect filters
* tone
* noise - tape hiss amount

### config
* skip controls - whether skip jumps back to the start of your loop, or to a random position
* speed scale - set your speed scale/quantizing
* audio routing - set the signal flow. default is input + softcut -> engine.

### modulation
* lfo target - select parameter to modulate
* lfo shape - sine, square, or sample and hold
* lfo depth - amount of modulation
* offset - lfo offset amount
* lfo freq - lfo speed
* lfo - lfo on/off toggle
