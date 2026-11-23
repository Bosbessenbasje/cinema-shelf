# Cinema Shelf

Cinema Shelf helps you find and return a DVD or Blu-ray case in a dark home cinema. Select a film on the tablet and an addressable LED strip lights up its place on the shelf.

The collection contains roughly 1,500 titles. CLZ already records the cabinet and shelf for each title, using codes such as `A1`. Cinema Shelf would extend that mapping to the position of each case.

## First prototype

Start with one shelf, a short strip of addressable LEDs and a handful of cases. Map each case to a position on the strip. With the room lights off, select two adjacent titles in turn and check whether you can pick out the correct spine each time. Then remove a case, select the title again and check whether the light clearly marks the gap where it belongs.

## Shelf lighting and control

- Try a WS2812B or SK6812 strip with one LED per case position. The prototype will show how well the LED spacing matches the case widths.
- Map each case to a cabinet, shelf and LED index. If different racks use separate controllers, include the controller in the mapping. A barcode could provide another way to look up a case.
- An ESP32 or Arduino could control the strips. WLED on an ESP32 is one option, with a segment for each shelf and commands sent over HTTP/JSON or MQTT.

## Ideas to explore

- **Scan a case to find its home.** An NFC/RFID tag on each case and a single reader near the tablet or rack could simplify returns. Hold the case up to the reader and the LEDs show where to put it back. The tag identifies the case, while the database holds its location. This allows cases to move and tags to be added gradually.
- **Detect a pickup or return.** There is room behind the cases for a sensor on each shelf. A presence sensor, possibly radar, could detect activity while a pickup or return is expected. The system would assume the user handled the indicated case. Test whether the sensor can distinguish that action from someone walking past. Locating an individual case with radar would also require testing the mounting angle and range resolution.
- **Flag unexpected activity.** If a shelf detects movement when no pickup or return is pending, its LEDs could briefly blink red. This would flag the shelf for a check without guessing which case moved.

## Camera detection for later

One fixed camera per cabinet could watch for changes near the selected title during a pickup or return. Infrared illumination could help in the dark. A phone recording of a few pickups and returns would show how gaps and leaning cases affect position estimates. The LED locator can be tested on its own first.

## License

[CC0 1.0 Universal](LICENSE)
