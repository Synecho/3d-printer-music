# StepperSong – 3D Printer Music

Make your 3D printer play music. Convert MIDI or audio to G-code in your browser.

**▶ [Open StepperSong](https://synecho.github.io/3d-printer-music/)** · free · no install · nothing is uploaded

## How to use

1. **Load** a MIDI or audio file (WAV, MP3, …)
2. **Listen & adjust:** tempo, pitch, range, one or two voices
3. **Pick your printer** from 40+ models
4. **Download** the G-code and print it

First time? Print the **test tone** and check it with a tuner app.

## Features

- MIDI and audio input with automatic note detection
- Two voices on CoreXY and bed slinger printers
- Shows which notes are too high and suggests a fix
- Ready-made G-code for Marlin, Klipper, Prusa and Bambu Lab
- Snippet mode to paste into your slicer's start G-code

## Supported printers

Prusa · Bambu Lab · Creality · Elegoo · Anycubic · Sovol · Qidi · Flashforge · Voron · Artillery · custom

## How it works

A stepper moving at *v* mm/s sounds at *f = v × full steps per mm*. StepperSong sets each move's speed so the motor hits the right note.

## Good to know

- No heating, no extrusion. Only the axes move.
- Turn off quiet/stealth mode for high notes.
- Clear the bed before starting. Use at your own risk.
- Only use files you have the rights to.
- Not affiliated with any printer manufacturer.

## License

[MIT](LICENSE)
