# Citizen_Mesh

<p align="center">
<img src="https://github.com/IISNRL/PureLoRaMesh/blob/main/image/new_hw.png" width="350">
</p>

## Overview

This project is an open-source initiative that integrates hardware and software to establish a cost-effective, long-distance, off-grid communication network.

At the core of this project is the utilization of LoRa technology, which facilitates device communication over significantly longer distances than what Wi-Fi or Bluetooth can offer.

The hardware component of our project is a modified version of the "Meshtastic" design, tailored to enhance performance and reliability.

```
  +-------------+   Bluetooth   +-----------+    LoRa Signal    +-----------+   Bluetooth   +-------------+  
  | Smart Phone | <===========> | Mesh node | <===============> | Mesh node | <===========> | Smart Phone |  
  +-------------+               + ----------+                   +-----------+               +-------------+  
```

## Features

Key features of this project:


* **Long-Range Communication**: Utilizing LoRa technology, this project enables device communication over several kilometers, with the range varying based on environmental conditions and hardware specifications.

* **Low Power Consumption**: Our design prioritizes efficiency, making it ideal for battery-operated devices. This feature is particularly beneficial for outdoor and remote applications where power availability is limited.

* **Mesh Networking**: Devices within this network form a mesh topology, where each node can relay messages for others. This capability significantly extends the network's overall reach.

* **Open-Source Philosophy**: We embrace an open-source approach for both software and hardware components. This ethos encourages community contribution, modification, and the creation of bespoke devices by enthusiasts.

* **GPS Integration**: Equipped with GPS functionality, our hardware devices offer location sharing and tracking capabilities, enhancing the utility of the system in various scenarios.

* **Versatility in Application**: The system is versatile, catering to a wide range of uses such as hiking, camping, and emergency situations, particularly in areas devoid of cellular connectivity.

* **Customizability and Extensibility**: As an open-source project, it provides ample opportunities for developers and hobbyists to tailor and expand its features, fostering innovation and personalized solutions.


## Hardware Components

Components used in this project:


| Component | Description | Quantity |
| -------- | -------- | -------- |
| Adafruit nRF52840 Feather       | micro controller     | 1     |
| U-blox NEO-6M GPS               | GPS module           | 1     |
| Semtech SX1262 LoRa Transceiver | LORA radio chip      | 1     |
| SSD1306 oled display            | visual display       | 1     |
| Custom PCB board                | PCB board            | 1     |
| 90 degree SMA Connector         | Antenna connector    | 1     |
| 923Mhz antena                   | Antenna              | 1     |
| Female header                   | Female header        | some  |





## PCB Layout

![image](https://github.com/IISNRL/PureLoRaMesh/blob/main/image/new_pcb.png)

## Getting Started

1. Prepare materials
2. Solder the component on PCB
3. Update bootloader
4. Compile Meshtastic
5. Upload firmware



### Assembly Guide

![image](https://github.com/IISNRL/PureLoRaMesh/blob/main/image/old_hw.jpg)

### Update bootloader

[Reference link](https://learn.adafruit.com/introducing-the-adafruit-nrf52840-feather?view=all#update-bootloader)

There're three ways to update your bootloader:
1. USE UF2
2. Use Arduino IDE
3. Use Command Line

see reference link for detailed steps. 



### Firmware
> [!IMPORTANT]
> Currently support firmware up to:
> Meshtastic ver 2.1.11

1. Compile
2. Flash

### Usage

[User guide](https://)



