# BASIC

These binaries are derived from Tim's cassette tape:
https://www.youtube.com/watch?v=fedhosTZD_g&t=1s

The process to generate them is:

1. Trim the WAV files to start and end with a clean "carrier" signal.
2. Down-sample to mono, `sox swtpc4kbasic.wav -r 11025 -c 1 -b 16 4k.wav` (and similarly for 8k)
3. Decode with `minimodem --rx --ascii -S 1200 -M 2400 300 -f 4k.wav > 4k.bin` (and similarly for 8k).

Untested!!  I need more RAM, and a way to load them (maybe Teletype punched tape).


