# smash-tv-no-music
SNES romhack to remove music from Smash TV

Apply to the Super Smash TV rom using https://www.romhacking.net/patch/ or another BPS patching tool of your choice.

The CRC32 of the base rom should be 2d0b20d0

### How it works. 
Only two edits were needed:

1: On the title screen the game plays track 2. Change the 2 to a 0.

2: At the start of each level the game does `LDA $0081cd,x` to look up what track number to start playing. That's `bf cd 81 00`. Change it to `a9 00 ea ea`, which is `LDA #0` followed by two bytes of noop padding.
