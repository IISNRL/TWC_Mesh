# Meshtastic



## Introduction  

Meshtastic is an open source wireless communication project that aims to provide **long-distance**, **low-power consumption**, **self-organizing network** (mesh) communication systems. Each node can serve as a relay station for each other.   

<p align="center">
<img src="https://hackmd.io/_uploads/Hkqv-XxJ6.jpg" width="600">
</p>


The goal of this project is to build a reliable communications network that can respond to **disasters**, **emergencies** or **remote communication** needs without relying on traditional mobile networks or the Internet.   




## Hardware selection

Currently, there are several hardware options available for this project, including the **ESP32** series, **NRF52** series, **RP2040**, and others.   

**ESP32**  

The ESP32 chip is older and consumes more power than the nRF52 chip, but is equipped with both WiFi and Bluetooth. Supported ESP32 devices include:

* LILYGO® TTGO T-Beam (>V1.1 recommended)
* LILYGO® TTGO Lora (>V2.1 recommended)
* Nano G1
* Station G1
* Heltec V3 and Wireless Stick Lite V3
* RAK11200 Core module for RAK WisBlock modular boards

**nRF52**

The nRF52 chip is much more power efficient than the ESP32 chip and easier to update, but is only equipped with Bluetooth. Supported nRF52 devices include:

* RAK4631 Core module for RAK WisBlock modular boards
* LILYGO® TTGO T-Echo

**RP2040**

The RP2040 is a dual-core ARM chip developed by Raspberry Pi. Supported RP2040 devices include:

* Raspberry Pi Pico + Waveshare LoRa Module (Note: Bluetooth on the Pico W is not yet supported by Meshtastic)
* RAK11310 Core module for RAK WisBlock modular boards

You have the option to purchase some devices that are already commercialized, or you can DIY a set based on a provided list of components.   

It is important to note that you need to select the **appropriate frequency** according to the radio regulations of different countries.   

## Radio overview


## Range Tests


## Usage

### Android 

### Apple / iOS
