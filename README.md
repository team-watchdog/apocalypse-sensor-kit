# Apocalypse Sensor Kit User Manual

## Table of Contents
1. Introduction
2. System Overview
3. Hardware Setup
   - Sensor Module
   - Receiver Device
4. Software Installation
   - Arduino IDE Setup
   - Required Libraries
   - Firmware Upload
5. Deployment
   - Sensor Module Installation
   - Receiver Device Setup
6. Mobile Application
7. Maintenance and Troubleshooting
8. Appendix: Command Line Interface

---

## 1. Introduction

Welcome to the Apocalypse Sensor Kit user manual. This guide will walk you through the setup, deployment, and maintenance of your sensor network for monitoring environmental conditions in agricultural settings.

For detailed instructions, please refer to the full [documentation](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki).

## 2. System Overview

The system consists of three main components:
1. Sensor Modules: Battery-powered devices that collect environmental data.
2. Receiver Device: A central hub that receives and stores data from sensor modules.
3. Mobile Application: For visualizing and analyzing the collected data.

---

## 3. Hardware Setup

### Sensor Module

Components required:
- Arduino Pro Mini 3.3V 8MHz
- DHT11 temperature and humidity sensor
- BH1750FVI light intensity sensor
- Capacitive soil moisture sensor
- LoRa Ra-02 module
- LiPo battery (<1000mAh)
- CN3065 solar charger module
- 6V 1W mini solar panel
- Other components as listed in the full documentation

Assembly steps:
1. Remove the voltage regulator and power LED from the Arduino Pro Mini.
2. Connect sensors and LoRa module to the Arduino Pro Mini as per the [pin configuration](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki/Hardware-Setup#assembly-notes:~:text=in%20sleep%20mode.-,Assembly%20Notes,-The%20CN3065%20solar). (Refer the full documentation)
3. Set up the solar charging circuit with the CN3065 module.
4. Solder the components on a perforated board.
5. Prepare the PVC enclosure as described in the [full documentation](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki/Hardware-Setup#assembly-notes:~:text=Sensor%20Module%20Enclosure).
6. Mount the circuit board and components inside the enclosure.

### Receiver Device

Components required:
- ESP32 Dev Kit V1 (>4MB flash)
- LoRa Ra-02 module
- DS1307 RTC module
- Power adapter with MicroUSB cable

Assembly steps:
1. Connect the LoRa module to the ESP32 using the SPI pins.
2. Connect the RTC module to the ESP32 using the I2C pins.
3. Solder the components securely on a perforated board.

For detailed instructions, please refer the [Hardware Setup](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki/Hardware-Setup) section in the [Wiki](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki)

---

## 4. Software Installation

### Arduino IDE Setup

1. Download and install the Arduino IDE from [arduino.cc](https://www.arduino.cc/en/software).
2. Install the following board packages via the Board Manager:
   - Arduino AVR Boards
   - ESP32 by Espressif Systems

### Required Libraries

Install the following libraries via the Arduino Library Manager:
- DHT sensor library by Adafruit
- Adafruit Unified Sensor by Adafruit
- BH1750 by Christopher Laws
- LowPower by Rocket Scream Electronics
- LoRa by Sandeep Mistry
- RTCLib by Adafruit

### Firmware Upload

Sensor Module:
1. Open the sensor module code in the Arduino IDE.
2. Select "Arduino Pro or Pro Mini" as the board and "ATmega328P (3.3V, 8MHz)" as the processor.
3. Connect the TTL converter to the arduino and Set the correct port for your TTL converter on the Arduino IDE.
4. Upload the code to the Arduino Pro Mini.

Receiver Device:
1. Open the receiver device code in the Arduino IDE.
2. Select your ESP32 board from the boards list.
3. Set the correct port for your ESP32.
4. Upload the code to the ESP32.

Important: Ensure you modify the NETWORK_ID in both the sensor module and receiver device code to a unique identifier for your network.

For detailed instructions, please refer the [Sofware Development](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki/Software-Development) section in the [Wiki](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki)

---

## 5. Deployment

### Sensor Module Installation

1. Choose a location near your crops.
2. Dig a narrow hole approximately 1 foot deep.
3. Insert the PVC standpipe into the hole and secure it.
4. Install the soil moisture sensor next to the standpipe.
5. Route sensor wires through the pipe.
6. Attach the solar panel and route its wires.
7. Connect all wires to the circuit board.
8. Position the DHT11 sensor inside the standpipe.
9. Verify all connections and seal the enclosure.

### Receiver Device Setup

1. Place the receiver under shelter with access to constant power.
2. Connect the power adapter to the ESP32.
3. Ensure all peripherals are properly connected.
4. Place the receiver in a stable location for continuous operation.

For detailed instructions, please refer the [Installation and Deployment](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki/Installation-and-Deployment) section in the [Wiki](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki)

---

## 6. Mobile Application

1. Install the mobile application on your smartphone (provide link or instructions for obtaining the app).
2. Launch the app and navigate to the "Connect Receiver" section.
3. Scan for available Bluetooth devices and select your receiver.
4. Once connected, you can view sensor data, manage devices, and analyze readings.

Key features:
- Real-time sensor data viewing
- Historical data analysis with graphs
- Device management (add/edit/remove sensors and receivers)
- Custom time range selection for data viewing

---

## 7. Maintenance and Troubleshooting

Regular Maintenance:
- Review logs monthly
- Perform physical checks on sensor nodes every two months
- Check and clean solar panels as needed

Troubleshooting:
- If sensor module LED blinks rapidly, check sensor connections
- For receiver issues, use the Command Line Interface (CLI) to access logs and diagnose problems
- Refer to the "Maintenance and Troubleshooting" section in the full documentation for detailed guidance

Battery Life:
- Sensor modules can run on battery for about two months without solar charging
- If a module stops transmitting, check the battery and solar panel connections

---

## 8. Appendix: Command Line Interface

The receiver device provides a CLI for advanced troubleshooting and management. Connect to the receiver's serial port to access the following commands:

- `LS` : List all files and directories in the current directory
- `READ <file>` : Read the specified file
- `CD <dir>` : Change to the specified directory
- `DEL <file>`    : Delete the specified file
- `FLASHINFO` : Show total and used capacity of SPI flash
- `USAGE` : Show used capacity in bytes and as a percentage
- `SETTIME HH:MM:SS`: Set the RTC time
- `SETDATE YYYY-MM-DD`: Set the RTC date
- `DATETIME`: Display current date and time
- `HELP`: Show command catalog

Use these commands to manage data, check system status, and diagnose issues as needed.

For any additional support or questions, please refer to the full [documentation](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki).
