# archive

### 2.23.26
#### naomi's side
```setcpm(143)
samples('github:mikeoat/RIFLES-SAMPLES/refs/heads/main')

_$: s("rg-hi2").scrub(0.15)//.struct("[x x x x]")
  //.struct("[x - - - x - - x - - x - x - x -]")
  //.struct("[x - - x - - x - - - x - - - - -]")
  .struct("[x x - x - - x - - x - - x - - x]")
  //.struct("[x x x x x - x x - x x - x - x x]")
  .decay(.9)
  .slow(4)
  .orbit(2)
  .gain(0.6)


_$: s("gran-sn_hi")
  .struct("[- - x -]")
  .slow(4)
  .room(1)
  .delay(0.5)
  .gain(2)

_$: s("cp")
  .struct("[- x]")
  .slow(2)

_$: n("[7 2 5 9 0 1 4 8 6 3 7 1 0 5 2 9]").scale("c5:minor").s("saw")//.rev()
.decay(0.1)
.delay(.1)
.room(0.2)
.gain(1)
.slow(8)

_$: n("[4 8 0 2 9 1 5 7 3 6 8 0 4 1 9 2]").scale("c6:minor").s("triangle")//.rev()
.decay(0.3)
.gain(.6)
.slow(16)

_$: n("[0 0 0 2 5 1 5 7 3 6 8 0 4 1 9 2]").scale("c1:minor").s("supersaw")
.distort(2)
.decay(2)
.slow(8)
.gain(0.3)
.orbit(2)

_$: n("[0 0 0 0]").scale("c1:minor").s("supersaw")
.distort(2)
.decay(2)
.slow(16)
.gain(0.5)
.orbit(2)

_$:s("gesic_bd-noise")
//.struct("[x x]*2")
.struct("[x - - - x - - x - - x - x - x -]")
.slow(4)
  .distort(4)
.gain(0.05)
.duckorbit(2).duckattack(0.2)
```

#### mike's side
```_$: n(run("<4 5 2>/4"))
  .scale("C4:minor").s("kalimba3")
  .room(3)
  .lpf(1000)
  .gain(0.5)
.orbit(2)

$: s("gesic_bd-noise")
  .struct(

  )
  //.struct("<[x x] [x x] [x x] [x <[x x] [- x x]> ]>")
  //.struct("[x - - - x - x -]")
  //.struct("[x x - x - - x - - x - - x - - x]")
  .slow(2)
  .duckorbit(2).duckattack(0.2).duckdepth(0.8)

$: s("gran_misc-deep")
  //.scrub(0.1)
  //.end(0.1)
  //.struct("[- - - x - - x -]")
  //.struct("[x x - x - - x - - x - - x - - x]")
  //.struct("[x - - [- x -] - x - -]")
  .struct("<x - ->*4")
  //.struct("[- - x -]/2")
  .slow(2)
  .room(1)
  //.gain(0.4)
  .orbit(2)

_$: n("[[4 8 0] 2 9 [1 5 7] 3 6 [8 0 4] 1 9 2]/8").scale("C3:minor").s("psaltery_pluck")
  .room(1)
  .orbit(2)
  .gain(0.5)

$: note("<c2>*4")
  //chord("[Cm Gm Eb Do]").voicing()
  .sometimes(x=>x.transpose("<12 -12 24 -24>/5"))
  .s("sawtooth").slow(2)
  .lpf("<523 1046 1569 2092 2615 3138 3661 4184>*2")
  .lpq(40)
  .gain(0.4)
  .orbit(2)
  ```