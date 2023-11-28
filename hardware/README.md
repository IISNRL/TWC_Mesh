# Project Name: Citizen_Mesh

## Overview

This is a open-source project that combines hardware and software to create a low-cost, long-range, off-grid communication network. 

This project primarily uses LoRa to enable devices to communicate over distances much greater than Wi-Fi or Bluetooth.

Our hardware design is a variant of "Meshtestic"
```
  +-------------+   Bluetooth   +-----------+    LoRa Signal    +-----------+   Bluetooth   +-------------+  
  | Smart Phone | <===========> | Mesh node | <===============> | Mesh node | <===========> | Smart Phone |  
  +-------------+               + ----------+                   +-----------+               +-------------+  
```

## Features

Key features of this project:

* **Long Range Communication**: Leveraging LoRa technology, it allows devices to communicate over several kilometers, depending on the environment and hardware used.
* **Low Power Consumption**: Designed for efficiency, it's suitable for battery-powered devices, making it ideal for outdoor and remote applications.

* **Mesh Networking**: The devices form a mesh network, meaning each node can relay messages for others, extending the network's overall range.

* **Open-Source**: Both the software and hardware designs are open-source, allowing anyone to contribute, modify, or build their own devices.

* **GPS Integration**: Our hardware devices come with GPS, enabling location sharing and tracking functionalities.

* **Versatility**: It can be used for various applications, including hiking, camping, or during emergencies, especially in areas without cell service.

* **Customizable and Extensible**: Being open-source, it allows developers and hobbyists to customize and extend its functionalities.

## Hardware Components

Components used in this project:


| Component | Description | Quantity |
| -------- | -------- | -------- |
| Adafruit nRF52840 Feather     | micro controller     | 1     |
| U-blox NEO-6M GPS             | GPS module           | 1     |
| Semtech SX1262 LoRa Transceiver| LORA radio chip     | 1     |
| SSD1306 oled display          | visual display       | 1     |
| Custom PCB board              | PCB board            | 1     |
| 90度 SMA Connector            | Antenna connector    | 1     |
| 923Mhz天線                     | Antenna              | 1     |
| 適量排母                       | Female header        | some   |





## PCB Layout

![image](https://github.com/IISNRL/PureLoRaMesh/blob/main/image/new_pcb.png)

## Getting Started

Provide step-by-step instructions on how to assemble the hardware, including soldering components, mounting the PCB, etc.



## Assembly Guide

![image](https://github.com/IISNRL/PureLoRaMesh/blob/main/image/old_hw.jpg)

## Firmware

> Currently support firmware:
> Meshtastic ver 2.1.11 

## Usage

[User guide](https://)


## Contributing

We welcome contributions from the community. Please read our CONTRIBUTING.md file for details on how to submit pull requests, the process for submitting bugs, and other ways you can contribute to the project.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

## Acknowledgements

Thanks to the open-source community for continuous inspiration and support. Special thanks to volunteers and contributors who dedicate their time to the project.

## Contact


* Project Lead: [Your Name] - email@example.com
* Project URL: https://github.com/IISNRL/Together_We_Connect


