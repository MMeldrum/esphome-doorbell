# ESPHome Doorbell

A simple ESPHome-based doorbell project for a Wi-Fi-enabled smart home. This repository contains the configuration and supporting files needed to build, flash, and run a doorbell device with ESPHome.

I used an [ESP32-C3 SuperMini](https://www.espboards.dev/esp32/esp32-c3-super-mini/) but other boards can also be used.

## Features

- ESPHome configuration for a doorbell sensor and chime
- Wi-Fi connectivity
- MQTT or Home Assistant integration support
- Customizable automations and notifications

## Requirements

- ESP32/ESP8266 development board
- Doorbell button or sensor input
- Speaker or chime output (optional)
- ESPHome installed on your computer or Home Assistant instance

## Setup

1. Install ESPHome:
   - With Home Assistant: use the ESPHome add-on.
   - On a local machine: `pip install esphome`.
2. Connect your ESP device and configure the pin assignments in the YAML file.
3. Store sensitive values such as Wi-Fi credentials and API tokens in `secrets.yaml`.
   - ESPHome will read these values from the file in the same directory as your configuration.
   - Reference them in your YAML with `!secret <name>`.
   - Example:

```yaml
wifi:
  ssid: !secret your_wifi_ssid
  password: !secret your_wifi_password
```

4. Flash the firmware using ESPHome:

```bash
esphome run doorbell.yaml
```

5. Add the device to Home Assistant or connect it to your MQTT broker.

## Configuration

Edit `doorbell.yaml` to adjust the following settings:

- `wifi:` network name and password
- `api:` or `mqtt:` integration options
- `binary_sensor:` pin for the doorbell button
- `output:` or `switch:` settings for the chime or speaker

## Usage

Once flashed, the doorbell should report button presses and optionally trigger a chime or automation in Home Assistant.

## Contributing

Feel free to open issues or pull requests to improve the configuration, add features, or support additional hardware.

## License

This repository is provided as-is. Add your preferred license file if needed.
