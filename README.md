# The Apocalypse Sensor Kit Manual
 developed by Sahan Panditharathne

[සිංහලෙන් කියවන්න](https://github.com/team-watchdog/apocalypse-sensor-kit/blob/main/README-Sinhala.md)

[தமிழில் படியுங்கள்](https://github.com/team-watchdog/apocalypse-sensor-kit/blob/main/README-Tamil.md)


The Apocalypse Sensor Kit is a cheap, DIY suite of hardware and software that you can put together yourself, plant in the ground, and get readings for light intensity, soil moisture, humidity, and temperature - useful stuff when you're trying to learn what happened to your potato plants. It's essentially most of the same functions as most state of the art farm monitoring equipment, but a lot cheaper. It comes with a mobile app, which you can [download from this link](https://github.com/team-watchdog/apocalypse-sensor-kit/releases/tag/v1.0.0). This is a companion to our records of 70 growable plants at [Lanka.wiki](https://lanka.wiki). 

![image](https://github.com/user-attachments/assets/cfc0591f-ce04-4ae8-a2c1-cbe2be183927)

These sensors have solar cells for charging and can average up to two months without solar charging. They connect to a reciever (LKR 3850) over LoRA, a long-range wireless communications method that gives them a maximum range of kilometers (which means you can stick them on far-off bits of a farm). The reciever communicates to a mobile app (Android) that visualizes the data for you and allows you to name and monitor clusters of sensors. 

![image](https://github.com/user-attachments/assets/72c6c55a-3db3-462f-a3ab-a04a5d2e6a49)

Here's what each sensor node looks like when fully assembled and deployed. If it's a little ugly, that's by design. We wanted to build something that could be cobbled together with a trip to the average Sri Lankan electronics shop, with a quick stop at a local hardware store. These units (PVC pipes, systems inside) are cheap to replace, robust to water and UV damage, and can be cobbled together for LKR 8200 (as of 2024). We've provided the designs and a complete guide in the [full documentation](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki) - so you can build it as is, or improve it, or even print a PCB to make it sleeker (but more expensive). We've intentionally used technology that is well known and outdated enough to be available even in economic and infrastructure crises like the ones Sri Lanka went through in 2022 - hence the "Apocalypse" in the title.

What you're reading now is the basic operations and maintenance manual. If you want to learn how to build these units from scratch, please refer to the [full documentation](https://github.com/team-watchdog/apocalypse-sensor-kit/wiki). This manual will walk you through deployment and and maintenance of your sensor network for monitoring environmental conditions in agricultural settings. This assumes you have some technical expertise (if not, get a friend to help you!) 



## 1. Before You Begin
   
The system consists of three main components:
1. Sensor Modules: Battery-powered devices that collect environmental data.
2. Receiver Device: A central hub that receives and stores data from sensor modules.
3. Mobile Application: For visualizing and analyzing the collected data.

Before starting, ensure you have the necessary tools:

1. Shovel or post-hole digger
2. Wire cutters or small scissors
3. Screwdrivers
4. Gloves and protective eyewear


## 2. Deployment

1. Choose a location near your crops, considering factors like shade, accessibility, and potential obstructions.
2. Use a post-hole digger to dig a narrow hole approximately 1 foot deep.
3. Insert the PVC standpipe into the hole, ensuring it's level and secure.
4. Install the soil moisture sensor next to the standpipe at the appropriate depth for your crops.
5. Route sensor wires through the pipe, using zip ties or cable clips to keep them organized.
6. Attach the solar panel, checking for optimal sun exposure throughout the day.
7. Connect all wires to the circuit board, double-checking connections before sealing.
8. Position the DHT11 sensor inside the standpipe, considering adding a desiccant pack to reduce moisture.
9. Verify all connections and seal the enclosure using silicone sealant or weatherproof tape.

## 3. Receiver Device Setup

1. Place the receiver under shelter with adequate ventilation and access to constant power. We recommend keeping it indoors.
2. Ensure all peripherals are securely connected using cable ties or adhesive.
3. Mount the receiver on a wall for better organization and stability, if possible.


## 4. Mobile Application

1. Install the mobile application on your smartphone by downloading the apk from the "Releases" section on this repo 
2. Launch the app and navigate to the "Connect Receiver" section.
3. Scan for available Bluetooth devices and select your receiver.
4. Once connected, you can view sensor data, manage devices, and analyze readings.
5. You can rename sensors to remember them better


![image](https://github.com/user-attachments/assets/5dd4ed69-b037-495a-9931-562cae41249e)


Key features:

Real-time sensor data viewing with screenshots of the app interface
Historical data analysis with graphs and tips on interpreting data
Device management (add/edit/remove sensors and receivers)
Custom time range selection for data viewing
Data export and sharing for collaboration or further analysis


## 5. Maintenance and Troubleshooting

1. Review logs monthly, maintaining a log of tasks performed and issues encountered.
2. Perform physical checks on sensor nodes every two months, inspecting wires for damage.
3. Check and clean solar panels as needed, using compressed air to prevent dust buildup.
4. Keep a spare set of components (sensors, wires, etc.) for quick repairs or replacements.


Troubleshooting:

1. If sensor module LED blinks rapidly, check sensor connections. It will keep blinking as long as it cannot connect. 
2. For receiver issues, use the Command Line Interface (CLI) to access logs and diagnose problems using the provided flowchart or decision tree.
3. Refer to the "Maintenance and Troubleshooting" section in the full documentation for detailed guidance, or contact technical support/community forums for additional help.

![image](https://github.com/user-attachments/assets/87651747-5deb-4b42-b4e8-75cc6ae35c05)

In general, make sure there's no crud on the wires and that everything is sealed nicely.

Battery Life:

1. Sensor modules can run on battery for about two months without solar charging. Keep spare batteries on hand for quick replacement.
2. If a module stops transmitting, check the battery and solar panel connections.
3. Properly dispose of or recycle old batteries.


## 6. Command Line Interface

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

## License

Our work presented under the MIT License - 

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Acknowledgements

This work was created by Watchdog Sri Lanka (Appendix) as a part of the project Building Tools to Strengthen Pluralist, Inclusive and Fact-based Public Discourse, conducted by LIRNEasia. LIRNEasia (www.lirneasia.net) is a pro-poor, pro-market regional digital policy think tank. The project is conducted in partnership with the Strengthening Social Cohesion and Peace in Sri Lanka (SCOPE) programme, co-funded by the European Union and German Federal Foreign Office. SCOPE is implemented by GIZ in partnership with the Ministry of Justice, Prisons Affairs and Constitutional Reforms.  

