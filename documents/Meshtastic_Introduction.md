# Meshtastic

![https://meshtastic.org/](https://hackmd.io/_uploads/rknfCvqba.png)
**Project Website:** [https://meshtastic.org/](https://meshtastic.org/)


## Introduction  

Meshtastic is an open-source wireless communication project focused on delivering a **long-distance**, **low-power consumption**, **self-organizing network** (mesh) communication systems. In this network, each node acts as a relay station for others, enhancing connectivity and range.

<p align="center">
<img src="https://hackmd.io/_uploads/Hkqv-XxJ6.jpg" width="600">
</p>

Our project's mission is to establish a robust communication network designed for **disaster response**, **emergency situations**, and **remote communication** requirements, independent of conventional mobile networks or the Internet.


## Hardware selection  

Choosing the right hardware is crucial for your Meshtastic project. The platform supports various hardware options, each with its unique features and capabilities.   
Currently, there are several hardware options available for this project, including the **ESP32** series, **NRF52** series, **RP2040**, and others.   

Selecting the appropriate hardware is a pivotal aspect of your Meshtastic project. The platform accommodates a diverse range of hardware choices, each distinguished by its specific features and capabilities. Presently, the project supports multiple hardware options, notably the **ESP32** series, **NRF52** series, **RP2040**, among others, offering a variety of configurations to meet different project requirements and objectives.

**ESP32**  

The ESP32 chip, while older and less power-efficient than the nRF52 chip, boasts integrated WiFi and Bluetooth capabilities, making it a versatile choice for projects requiring these features. Supported ESP32 devices for the Meshtastic project include:

* **LILYGO® TTGO T-Beam** (Version 1.1 or higher recommended)
* **LILYGO® TTGO Lora** (Version 2.1 or higher recommended)
* **Nano G1**
* **Station G1**
* **Heltec V3 and Wireless Stick Lite V3**
* **RAK11200 Core module** for use with RAK WisBlock modular boards

**nRF52**


The nRF52 chip stands out for its superior power efficiency compared to the ESP32 chip and its simpler update process. However, it is equipped solely with Bluetooth connectivity. Supported nRF52 devices for the Meshtastic project are:

* **RAK4631 Core module** for RAK WisBlock modular boards
* **LILYGO® TTGO T-Echo**

These options cater to projects prioritizing energy efficiency and ease of maintenance while leveraging Bluetooth for communication within the Meshtastic network.


**RP2040**

The RP2040, developed by Raspberry Pi, is a dual-core ARM chip known for its versatility. Supported RP2040 devices in the Meshtastic project include:

* **Raspberry Pi Pico + Waveshare LoRa Module** (Please note: Bluetooth on the Pico W is currently not supported by Meshtastic)
* **RAK11310 Core module** for RAK WisBlock modular boards

Participants in the project have the flexibility to choose between purchasing commercially available devices or assembling a DIY kit based on a specified list of components. This approach allows for a wide range of participation, from those who prefer ready-made solutions to enthusiasts who enjoy customizing their setup.

**Linux**  

The software is also compatible with native Linux machines through the use of the [Portduino framework](https://github.com/geeksville/framework-portduino), extending the flexibility and accessibility of the project to a broader range of devices and setups.

For additional details, you can explore the documentation on [Linux-native hardware support](https://meshtastic.org/docs/hardware/devices/linux-native-hardware/), offering insights into how to integrate Meshtastic with Linux systems and the advantages this combination provides.

## Choosing Your Device

You have the choice to go with commercially available devices or to craft a DIY kit from a provided list of components. Each platform presents its own set of advantages and drawbacks. While the ESP32 Series may be more affordable and includes WiFi connectivity, it consumes more power compared to the nRF52 series.

For enthusiasts inclined towards DIY, a comprehensive step-by-step guide is available [here](), designed to walk you through assembling your own device, allowing for customization and hands-on experience with the technology.

It's crucial to choose the **appropriate frequency** for your device in compliance with the radio regulations of various countries. This ensures not only the lawful operation of your Meshtastic device but also minimizes interference with other wireless communications, contributing to the overall efficiency and reliability of your network.


## Radio overview

### Region

Configures the **region** for your node. The default setting is `unset`. Until this parameter is defined, the node's display will show a notification and refrain from transmitting any packets.


> [!NOTE]  
> You must set your device's region code. This will ensure that you are operating within the legal limits for your area.  

The region codes are:  

| Region Code	| Description  |
|---------------|------------  |
|UNSET          |Unset         |
|US	            |United States |
|EU_433	        |European Union 433MHz|
|EU_868	        |European Union 868MHz|
|CN	            |China         |
|JP	            |Japan         |
|ANZ	        |Australia & New Zealand|
|KR	            |Korea|
|TW	            |Taiwan|
|RU	            |Russia|
|IN	            |India|
|NZ_865        	|New Zealand 865MHz|
|TH	            |Thailand|
|UA_433        	|Ukraine 433MHz|
|UA_868	        |Ukraine 868MHz|
|MY_433	        |Malaysia 433MHz|
|MY_919	        |Malaysia 919MHz|
|LORA_24	    |2.4 GHz band worldwide|


### Modem Preset

The default setting is unset, corresponding to `LONG_FAST`.   
Presets are predefined configurations for modem settings (**Bandwidth**, **Spread Factor**, and **Coding Rate**) that impact the balance between message speed and range. The default setting offers a balanced mix of speed and range suitable for most users.

Presets are tailored to optimize either speed (leading to reduced network congestion) or range, accommodating two common scenarios:

1. **High Device Density or Frequent Messaging**: In environments where many devices are present within the mesh network or messages are transmitted frequently, higher speeds (resulting in less radio time per device) can mitigate mesh network congestion.
2. **Maximum Range Requirement**: For situations where the maximum possible range is essential and a delay of several seconds in message reception is acceptable (e.g., transmitting messages from a town to a distant mountain top).

The available presets span a spectrum from:
`Fastest <--> Slowest` and `Shortest <--> Longest range`:

1. SHORT_FAST (Fastest, highest bandwidth, lowest airtime, shortest range)
2. SHORT_SLOW
3. MEDIUM_FAST
4. MEDIUM_SLOW
5. LONG_FAST (Default)
6. LONG_MODERATE
7. LONG_SLOW
8. VERY_LONG_SLOW (Slowest, lowest bandwidth, highest airtime, longest range)

> [!TIP]
> `LONG_FAST` is the default setting

|    Channel setting     | Alt Channel Name |      Data-Rate      | SF / Symbols | Coding Rate | Bandwidth | Link Budget |
| :--------------------: | :--------------: | :-----------------: | :----------: | :---------: | :-------: | :---------: |
|      Short Range / Fast|        Short Fast|           10.94 kbps|       7 / 128|          4/5|      250|          143dB|
|      Short Range / Slow|        Short Slow|            6.25 kbps|       8 / 256|          4/5|      250|        145.5dB|
|     Medium Range / Fast|       Medium Fast|            3.52 kbps|       9 / 512|          4/5|      250|          148dB|
|     Medium Range / Slow|       Medium Slow|            1.95 kbps|     10 / 1024|          4/5|      250|        150.5dB|
|       Long Range / Fast|         Long Fast|            1.07 kbps|     11 / 2048|          4/5|      250|          153dB|
|   Long Range / Moderate|     Long Moderate|            0.34 kbps|     11 / 2048|          4/8|      125|          156dB|
|       Long Range / Slow|         Long Slow|            0.18 kbps|     12 / 4096|          4/8|      125|        158.5dB|
|  Very Long Range / Slow|    Very Long Slow|            0.09 kbps|     12 / 4096|          4/8|     62.5|        161.5dB|

### More about Preset

Various data-rate options can be configured for a channel, which are inversely proportional to the theoretical range of the devices.

- **Spreading Factor (SF)**: Determines the extent to which data is "spread" over time.
  - Each increase in Spreading Factor doubles the transmission airtime.
  - Each increase in Spreading Factor enhances the link budget by approximately 2.5db.
- **Bandwidth**: Defines the spectrum segment utilized.
  - Doubling the bandwidth nearly results in a 3db decrease in link budget.
  - Bandwidths below 31 may exhibit instability unless paired with a high-quality Crystal Oscillator.
- **Coding Rate**: The level of redundancy applied to mitigate noise interference.
  - Elevating the coding rate boosts reliability at the expense of reducing data-rate.
  - 4/5 coding rate incurs 1.25x overhead
  - 4/6 coding rate incurs 1.5x overhead
  - 4/7 coding rate incurs 1.75x overhead
  - 4/8 coding rate incurs 2x overhead


### Custom Settings

Custom settings can be configured using [supported software](/docs/software).

Beyond the 8 Modem Presets available, there is also the flexibility to tailor the parameters according to your specific requirements.


> [!NOTE]
> After applying the settings, you will need to restart the device.

> [!NOTE]
> After your device is restarted, it will generate a new crypto key and you will need to share the newly generated QR Code or URL to all your other devices.   

Some example settings:

|   Data-rate    | SF / Symbols | Coding Rate | Bandwidth | Link Budget | Note                                                                     |
|   :--------:   | :----------: | :---------: | :-------: | :---------: | :----------------------------------------------------------------------- |
| 37.50 kbps |    6 / 64    |     4/5     |    500    |    129dB    | Fastest possible speed                                                   |
| 3.125 kbps |   8 / 256    |     4/5     |    125    |    143dB    |                                                                          |
| 1.953 kbps |   8 / 256    |     4/8     |    125    |    143dB    |                                                                          |
| 1.343 kbps |  11 / 2048   |     4/8     |    500    |    145dB    |                                                                          |
| 1.099 kbps |   9 / 512    |     4/8     |    125    |    146dB    |                                                                          |
| 0.814 kbps |  10 / 1024   |     4/6     |    125    |    149dB    |                                                                          |
| 0.610 kbps |  10 / 1024   |     4/8     |    125    |    149dB    |                                                                          |
| 0.488 kbps |  11 / 2048   |     4/6     |    125    |    152dB    |                                                                          |
| 0.073 kbps |  12 / 4096   |     4/5     |    31     |    160dB    | Twice the range and/or coverage of "Long Slow", low resilience to noise  |
| 0.046 kbps |  12 / 4096   |     4/8     |    31     |    160dB    | Twice the range and/or coverage of "Long Slow", high resilience to noise |

The link budget calculations are based on an assumed transmit power of 17dBm and an antenna with 0dB gain. It's important to adjust your link budget assumptions according to the specifications of your actual devices.

> [!NOTE]  
> These channel settings may not have been tested. Use at your own discretion. Share on https://meshtastic.discourse.group with your successes or failure.



## Range Tests

### Current Ground Record: 254km

- **Range:** 254km (158 miles)
- **Record Holders:** _kboxlabs_
- **Source:** [Meshtastic Discourse](https://meshtastic.discourse.group/t/practical-range-test-results/692/137)

#### Modem Settings:

Default: `Long_Fast`
- **Frequency:** 915MHz
- **Bandwidth:** 250
- **Spread Factor:** 11
- **Coding Rate:** 4/8

#### Node A

- **Device:** [RAK4631 Core](https://meshtastic.org/docs/hardware/devices/rak/core-module)  with [RAK 5005-O Base Board](https://meshtastic.org/docs/hardware/devices/rak/base-board)
- **Firmware Version:** 2.1.17
- **Antenna:** 902-928MHz 5.8 dBi Slinkdsco Outdoor 

#### Node B

- **Device:** [RAK4631 Core](https://meshtastic.org/docs/hardware/devices/rak/core-module)  with [RAK 19003 Mini Base Board](https://meshtastic.org/docs/hardware/devices/rak/base-board)
- **Firmware Version:** 2.1.18
- **Antenna:** Standard LoRa 915MHz 60mm 2dBi Omnidirectional


Sending Node  
<p align="center">
<img src="https://meshtastic.org/img/records/kboxlabs_sender.webp" width="600"> 
</p>

Receiving Node  
<p align="center">
<img src="https://meshtastic.org/img/records/kboxlabs_receiver.webp" width="600">
</p>

Geographic Locations  
<p align="center">
<img src="https://meshtastic.org/img/records/kboxlabs_map.webp" width="600">
</p>

  
## Source:   
[Meshtastic](https://meshtastic.org)  
[Range Tests](https://meshtastic.org/docs/overview/range-tests/)  
