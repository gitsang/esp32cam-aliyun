# esp32cam-aliyun

## Prerequisite

Arduino IDE:

- https://www.arduino.cc/en/software
- Tested Version: 2.3.3

Additional boards manager URLs:

- https://dl.espressif.com/dl/package_esp32_index.json
- Or use local version: [package_esp32_index.json](./resources/package_esp32_index.json)

Borad Module:

- ESP32 Wrover Module

Libraries:

- `ArduinoJson.h`:
  - Tested Version: 7.2.0
  - Install:
    - Search `ArduinoJson - by Benoit Blanchon` from `Library Manager` then install.
  - Message:
    - https://arduinojson.org/?utm_source=meta&utm_medium=library.properties
- `PubSubClient.h`:
  - Tested Version: 2.8.0
  - Install:
    - Download zip from https://docs.arduino.cc/libraries/pubsubclient/#Releases
    - Download zip and load by `Add .ZIP Library...`
  - Message:
    - https://pubsubclient.knolleary.net/
- `SHA256.h`:
  - Tested Version: b4b722e
  - Install:
    - Download zip from https://github.com/simonratner/Arduino-SHA-256
    - Download zip and load by `Add .ZIP Library...`

## Configure

Copy `config.h.example` to `config.h` and fill in the values.
