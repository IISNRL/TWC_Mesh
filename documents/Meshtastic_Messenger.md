# Meshtastic

![https://meshtastic.org/](https://hackmd.io/_uploads/rknfCvqba.png)

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

### Region
Sets the **region** for your node. Default is `unset`.   
As long as this is not set, the node screen will display a message and not transmit any packets.  


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

Default is unset which equates to `LONG_FAST`.   
Presets are pre-defined modem settings (**Bandwidth**, **Spread Factor**, and **Coding Rate**) which influence both message speed and range.  
The default will provide a strong mixture of speed and range, for most users.

The presets are designed to provide further options for optimizing either speed (and reduced network congestion) or range, which can be useful for two real world scenarios:

1. A high number of devices exist in the mesh, or messages are sent very frequently. Faster speeds (and therefore lower radio time per device) can help with mesh network congestion.
2. Maximum range is desired, for long range scenarios where a several second delay in message receipt is acceptable (for instance, attempting to send messages from a town to a distant mountain top).

The Presets available are as follows, and follow a linear pattern of:  
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

Various data-rate options are available when configuring a channel and are inversely proportional to the theoretical range of the devices.

- **Spreading Factor (SF)** - How much we "spread" our data over time.
  - Each step up in Spreading Factor doubles the airtime to transmit.
  - Each step up in Spreading Factor adds about 2.5db extra link budget.
- **Bandwidth** - How big of a slice of the spectrum we use.
  - Each doubling of the bandwidth is almost 3db less link budget.
  - Bandwidths less than 31 may be unstable unless you have a high quality Crystal Oscillator.
- **Coding Rate** - How much redundancy we encode to resist noise.
  - Increasing coding rate increases reliability while decreasing data-rate.
  - 4/5 - 1.25x overhead
  - 4/6 - 1.5x overhead
  - 4/7 - 1.75x overhead
  - 4/8 - 2x overhead

### Custom Settings

Custom settings can be applied by using [supported software](/docs/software).

In addition to the 8 Modem Presets, you can also customize the parameters to your need.   

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

The link budget used by these calculations assumes a transmit power of 17dBm and an antenna with 0dB gain. Adjust your link budget assumptions based on your actual devices.

> [!NOTE]  
> These channel settings may not have been tested. Use at your own discretion. Share on https://meshtastic.discourse.group with your successes or failure.



## Range Tests


## Usage

### Android 

### Apple / iOS
