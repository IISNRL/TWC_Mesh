# Citizen_Mesh

<p align="center">
<img src="https://github.com/IISNRL/PureLoRaMesh/blob/main/image/new_hw.png" width="350">
</p>

## Overview

This project is an innovative open-source initiative to create a cost-effective, long-distance, off-grid communication network. By integrating both hardware and software components, we strive to establish a robust network that transcends the limitations of traditional communication methods.

At the heart of this project lies the advanced use of LoRa technology. LoRa (Long Range) is a unique communication protocol that enables device communication over significantly longer distances than conventional methods like Wi-Fi or Bluetooth. This technology is especially crucial for areas lacking traditional network infrastructure, offering a reliable alternative for long-range communication.

The hardware component of our project is a customized adaptation of the "Meshtastic" design. This modification is specifically engineered to enhance performance and reliability, ensuring stable and efficient communication in various off-grid scenarios. The adaptability of the Meshtastic design allows us to tailor it to meet the specific needs of our project, optimizing both hardware efficiency and network performance.

```
  +-------------+   Bluetooth   +-----------+    LoRa Signal    +-----------+   Bluetooth   +-------------+  
  | Smart Phone | <===========> | Mesh node | <===============> | Mesh node | <===========> | Smart Phone |  
  +-------------+               + ----------+                   +-----------+               +-------------+  
```

## Features

* **Long-Range Communication**: Our project leverages LoRa technology to enable device communication over several kilometers. The range varies based on environmental conditions and hardware specifications, significantly improving traditional Wi-Fi or Bluetooth connections.

* **Low Power Consumption**: Efficiency is at the forefront of our design, making it ideal for battery-operated devices. This feature is especially beneficial for remote applications and outdoor scenarios where power resources are scarce.

* **Mesh Networking**: The network utilizes a mesh topology, allowing each node within the network to relay messages to other nodes. This structure significantly enhances the resilience and range of the network, making communication more reliable over larger areas.

* **Open-Source Philosophy**: We are committed to an open-source approach for this project's software and hardware components. This philosophy fosters a collaborative community environment where users can contribute, modify, and improve the system.

* **GPS Integration**: Our devices have GPS functionality, facilitating location sharing and tracking capabilities. This addition is invaluable for navigation and tracking in various scenarios, from recreational activities to critical emergency responses.

* **Versatility in Application**: Designed to serve many applications, our system is ideal for hiking, camping, emergency communication, and any other situation where conventional connectivity is unavailable or unreliable.

* **Customizability and Extensibility**: Emphasizing the customizable nature of our project, we encourage developers and hobbyists to adapt and extend the system. This openness leads to continuous innovation, allowing for a wide range of personalized applications and enhancements.


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
The top image is Citizen_Mesh_V1_long, and the bottom one is Citizen_Mesh_V1_short.   

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



