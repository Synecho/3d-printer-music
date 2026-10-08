# StepperSong – 3D Printer Music (MIDI & Audio to G-code)

Make your 3D printer play music: a free browser tool that converts MIDI or audio files into G-code so the printer's stepper motors play songs. One or two voices, preconfigured for 40+ printer models.

**Use it online:** https://synecho.github.io/3d-printer-music/

Everything runs locally in your browser. No files are uploaded and there is no server. To use it offline, download `index.html` and double-click it.

## Features

- **Load file:** MIDI directly, or audio (WAV, MP3, M4A, OGG, FLAC) via automatic pitch detection, with presets for vocals, whistling, guitar, bass and piano.
- **Listen & adjust:** note view with waveform, playback as printer sound or original, scrubbing, tempo, varispeed (tempo and pitch together), transpose, range selection with markers.
- **Two voices:** on CoreXY each of the two XY motors plays its own voice; on bed slingers X and Y do.
- **Printer selection:** kinematics, full steps per mm, build volume, speed and acceleration limits and firmware commands are stored per model.
- **Range check:** shows which notes are too high for the selected printer and suggests a transposition.
- **Export:** G-code with a firmware-specific header (Marlin, Prusa Buddy, Prusa MK3, Klipper, Bambu Lab), a calibration test tone, and the selected range as MIDI.

## Supported printers

Prusa (CORE One / One+ / INDX / L, MK4S, MK3S+, MINI+, XL), Bambu Lab (X1, P1, P2S, A1, A1 mini, H2D, H2S), Creality (Ender-3 V2 / S1 / V3 SE / V3 KE / V3, K1, K1C, K1 Max, K2 Plus), Elegoo (Neptune 4 / 4 Pro / 4 Max, Centauri Carbon), Anycubic (Kobra 3, Kobra S1), Sovol (SV06, SV06 Plus, SV08), Qidi (Q1 Pro, Plus4, X-Plus 3), Flashforge (Adventurer 5M / Pro), Voron (2.4 / Trident), Artillery (Sidewinder X3 / X4), plus custom values with a built-in calculator.

Each model shows where its values come from: firmware source code, official configuration, a community copy of the stock config, or an estimate. Bambu Lab publishes no motor data, so a 1.8° motor with a 20-tooth GT2 pulley is assumed. For estimated values, play the test tone first.

## How it works

A stepper motor moving at v mm/s produces the tone

    f = v · full steps per mm

Full steps per mm = steps per revolution ÷ (pulley teeth × belt pitch), e.g. 200 ÷ (20 × 2 mm) = 5.

On CoreXY, motor A runs at vx + vy and motor B at vx − vy. For two tones with belt speeds a and b, the head moves at vx = (a + b) / 2 and vy = (a − b) / 2. The axes move back and forth within a safe area around the bed center.

## Usage

1. Print the test tone G-code and measure it with a tuner app (A4 = 440 Hz, then A5 = 880 Hz). Enter any deviation as tuning offset under "Advanced settings".
2. Load a file, select a range, listen.
3. Download the G-code and start it as its own file on the printer. Do not paste it into the slicer's start G-code.

The G-code does not heat or extrude. It homes the axes, raises Z, and sets speed and acceleration limits for the current session only.

## Notes

- Quiet/stealth modes limit speed, so high notes get dropped. Turn them off for full range.
- With low acceleration, short notes don't fully reach their speed and sound slightly smeared.
- Use at your own risk. Make sure the travel path is clear before starting.
- Only use files you have the rights to or that are freely licensed.
- Not an official project of any printer manufacturer. All trademarks belong to their owners.

## License

MIT, see [LICENSE](LICENSE).
