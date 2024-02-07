# Seizure Detection Device

This repository contains the Arduino code for a seizure detection device. The device monitors for seizure-like activity using an accelerometer and alerts caregivers or medical personnel through an SMS message sent via ThingSpeak's ThingHTTP app when seizure-like motions are detected.

## Features

- **Seizure Detection:** Utilizes an accelerometer to detect seizure-like movements based on specific frequency patterns.
- **SMS Notifications:** Sends an SMS to a predefined number when a seizure is detected, using ThingSpeak's ThingHTTP API.
- **Wi-Fi Connectivity:** Connects to a local Wi-Fi network to send data and notifications.
- **False Alarm Handling:** Allows for a false alarm to be dismissed within a specified timeframe.

## Hardware Requirements

- Arduino-compatible microcontroller with Wi-Fi capabilities (such as the Adafruit Feather M0 Wi-Fi).
- Adafruit LSM303 Accelerometer.
- General IoT connectivity components (wires, breadboard, etc.).

## Setup

1. Assemble your circuit with the microcontroller and accelerometer according to the provided schematics.
2. Replace `ssid` and `pass` with your Wi-Fi network's SSID and password.
3. Replace `apiKey` with your ThingSpeak ThingHTTP API key.
4. Update the `number` variable in `sendSMS()` function to the phone number where you want to send the SMS.
5. Load the code onto your Arduino-compatible microcontroller.

## Operation

- The device will start sampling movement data at a specified frequency.
- If it detects movement patterns that fall within the seizure-characteristic frequency band, it will increment a counter.
- If the counter exceeds a threshold within a given time interval, the device will consider it a seizure event.
- It will then try to send an SMS message. If the button is pressed, it will reset the detection and abort the message sending.

## Configuration

- The sampling frequency and the threshold values are set at the beginning of the code and may be adjusted to match the specific requirements of the user or the environment.

## Usage

- The device should be placed securely on the subject.
- In the event of a seizure, ensure that the device is not accidentally reset by the person assisting the subject.
- After a seizure event, the device needs to be manually reset to continue monitoring.

## Contributing

Contributions to this project are welcome. If you have suggestions for improvements or have developed enhancements, please open an issue or a pull request.

## License

This project is licensed under the MIT License. See `LICENSE` for more information.
