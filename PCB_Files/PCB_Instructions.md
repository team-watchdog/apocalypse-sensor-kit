# Apoc Sensor Kit PCB Design and Gerber Files

For and easier build of the electronic componet of this project, we have designed PCBs for both the sensor module circuit and the receiver device circuit.

The PCB was perposefully designed to use only through hole components to make it easier for person with average soldering skills to use. The PCB version of the sensor module circuit is also made to be smaller in foamfacter as it sould allow the use of smaller enclosures.

This repository contains the Gerber files and EasyEDA design files for **Apocalype Sensor Kit.** You can use these files to manufacture the PCB or modify the circuit if needed.

## Table of Contents
- [Getting Started](#getting-started)
- [Manufacturing the PCB](#manufacturing-the-pcb)
- [Modifying the Circuit](#modifying-the-circuit)

## Getting Started

To use the files in this repository, you can either manufacture the PCB directly using the provided Gerber files or modify the design using the EasyEDA files.

### Files Included
- **Gerber Files:** These are the manufacturing files used by PCB manufacturers to create the board.
- **EasyEDA Project Files:** These files allow you to modify the PCB design using the EasyEDA platform.

## Manufacturing the PCB

Follow the steps below to get the PCB manufactured using the Gerber files.

### Step 1: Download the Gerber Files
- Download the Gerber files from the `PCB_Gerber_Files/` directory in this repository.
- There are sepeare .zip files for the sensor module circuit and the receiver device circuit.

### Step 2: Upload the Gerber Files to a PCB Manufacturer
- Use a PCB manufacturing service such as [JLCPCB](https://jlcpcb.com), [PCBWay](https://www.pcbway.com), or [OSH Park](https://oshpark.com).
- Most PCB manufacturers accept Gerber files directly. Upload the downloaded Gerber (.zip) files in their ordering form.

### Step 3: Configure PCB Options
- Configure the PCB specifications (e.g., number of layers, color, thickness) according to your needs or leave the default options.
- Submit the order and wait for your PCB to be manufactured and delivered.

## Modifying the Circuit

If you want to modify the circuit design, follow the steps below using EasyEDA:

### Step 1: Open EasyEDA
- Create an account and log in to [EasyEDA](https://easyeda.com) (either the web version or the desktop app).

### Step 2: Import the EasyEDA Files
- Download the EasyEDA files from the `EasyEDA_Project_Files/` directory in this repository.
- Open EasyEDA and select **File > Open** to import the `.json` files.
- The folder contains both the schematic file and the PCB layout file, Open and save both of those files under the same project.
- Save the Sensor Module files in its own project and Receiver Device files in its own seperate project.

### Step 3: Modify the Design
- You can now modify the schematic and PCB layout using the EasyEDA tools.
- Once the design changes are complete, you can export new Gerber files by selecting **Fabrication > Generate Gerber**.

### Step 4: Export the Updated Gerber Files
- After making changes, export the new Gerber files and follow the same process as outlined in the "Manufacturing the PCB" section to manufacture your modified design.