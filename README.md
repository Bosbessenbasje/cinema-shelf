# Cinema Shelf

Cinema Shelf is a project to help you find and return a DVD case in a dark home cinema. The idea is simple: select a film from the catalogue and light up its place on the shelf.

## First prototype

Start with one shelf, a short strip of addressable LEDs and a handful of cases. Map each case to a position on the strip. Selecting a title should illuminate the corresponding spine, so you can pick it out without turning on the room lights. The first practical test is whether the light clearly distinguishes two adjacent cases in the dark.

## Ideas to explore

- **Detect a pickup or return.** There is room behind the cases for a sensor on each shelf. A presence sensor, possibly radar, could detect activity while a pickup or return is expected. The system would assume the user handled the indicated case. Whether a sensor can distinguish that action from someone walking past needs testing.
- **Flag unexpected activity.** If a shelf detects movement when no pickup or return is pending, its LEDs could briefly blink red. This would flag the shelf for a check without guessing which case moved.
- **Scan a case to find its home.** An RFID tag on each case and a reader near the rack could simplify returns. Hold the case up to the reader and the LEDs show where to put it back.

Camera-based detection, potentially with infrared illumination, is parked for later. The LED locator can be tested on its own first.

## License

[CC0 1.0 Universal](LICENSE)
