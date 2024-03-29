# TWC_Mesh_device

In this page, we'll introduce the specifications and components of our customized Meshtastic device.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/8f376791-1270-4219-920e-9b1ffa1ac1b5" width="600">
</p>

## Why do we need to build our own?

Currently, you can find a lot of Meshtastic-supported developers on the market.  

This is the most common off-the-shelf hardware available for purchase.  

    RAK WisBlock Devices
    LILYGO® TTGO T-Beam
    LILYGO® TTGO T-Echo
    LILYGO® TTGO Lora
    HELTEC® LoRa 32
    Station G1
    Nano Series
    Raspberry Pi Pico

However, the biggest problem is that most of the devices use ESP32 as the core processor, in other words, it's NOT an option for us.  
The few hardware that don't use ESP32 are more expensive, less expandable, or harder to buy.  

Because of these problems, we had to rebuild the whole project from scratch, evaluating all the available parts and reconstructing the project.
Luckily, Meshtastic is very open source and has a rich user community, with people trying out every conceivable solution and platform!

## Core component

To build a Meshtastic node, it must contain at least the following components.
  * Core processor
  * LoRa communication module
  * Antenna
  * Display Screen
  * GPS module
  * Battery  
  (If you really want to reduce the cost, screen/GPS/batteries are not necessary.)  

Finally, based on the maturity of the program on different platforms, we chose:  

| Parts	|  Model  | 
|---------------|------------  |
|   Processor   |  Nordic NRF52840 (Norway)  |
|   LoRa module |  Semtech sx1262 (USA) |
|   GPS module  |  NEO-6M (Switzerland)   |

As the core components of this project.  


## Prototyping 


After a few twists and turns, we were able to get all the parts we needed.  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/73f6c75d-969b-4bcb-b6e9-cc8828f07458" width="450">
</p>

and successfully ported the meshtestic project to our hardware.  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/75f9df66-1073-467c-b33e-2a17437c0b56" width="450">
</p>

It looks like it will work and communicate properly.  
The next step is to design a device that can be used on the go, so you don't have to run wires everywhere.  


## PCB design

Considering overall size, battery type/position, usage posture, ease of maintenance, placement of various modules, and whether signal lines will be affected.  
We designed a PCB version of these devices to facilitate subsequent experimentation and testing.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4a42b649-fad4-4f2b-886c-be1830702fb7" width="450">
</p>

After a few more iteration, the GPS module is now a detachable design.  


<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/96cc72cd-f229-4290-b758-4fcebd688775" width="550">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/c21f3b53-e619-48ff-93a2-fa3216249190" width="550">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/59f08159-f106-427c-a4ce-e457b45472d6" width="550">
</p>

Finally, by assembling the various parts, we have hardware we're able to present!  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/d9a67539-a224-4bd6-8595-1862bcfbd057" width="500">
</p>

And I even did some basic testing in the campus.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/00905149-701f-4c9d-89bd-123b0c20dd25" width="500">
</p>

But it didn't go that smoothly...  


## About antenna

The thing is, We found that the performance of this prototype system is not as good as the theoretical value, and the difference is a bit big.  

In addition to the occasional disconnection and high packet loss rate, the longest communication distance is only 400m, and the RSSI is also very bad, which is quite different from our previous experience using LoRa (later found out that it is my design problem).  

All in all, the pre-test was not as good as we thought it would be.  

At this point, I started thinking about whether the antenna was defective or not.    
I wondered if the antenna I was holding was good or not, and if it was the right antenna to use.  

So, I bought a NanoVNA

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/9d2532c3-b1cf-4059-b856-fe10b9f7fc96" width="500">
</p>

and went through all the antennas in my lab, measuring, labeling, and categorizing them one by one.   
I even built my own antennas to match the frequencies.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/86cf540f-3ac7-4a04-b3a8-8ed587623ca0" width="500">
</p>


As a result, a 2.4G antenna was mixed in with the 4 sets of 915Mhz antennas I bought.  
Simply put, I used the wrong antenna for testing.  

## Other issue

After fixing the antenna, we started experimenting again, but this time we encountered a different problem.  
I noticed that after sending a message to our node, the node's Bluetooth signal would suddenly disconnect from the smartphone.  

I went through all the code and couldn't figure out why, there was no reason for the system to reset.  

At first there was really no way to debug it, but I was using a suitable antenna, the hardware was theoretically consistent with the official design, the software had no error messages, the power supply was stable, and I ruled out the possibility that the communication module was using more power to generate a surge when sending the commands.  

Also, I began to think about electromagnetic interference and repeatedly adjusted the position of the communication module and the microprocessor, but still without success.  

Finally, I observed these units long enough to conclude that "if you rotate the antenna to a certain angle, the disconnection does not occur," and I was able to reproduce this on several units. (The video below shows that each unit requires a different angle)  


[![vid_1](https://img.youtube.com/vi/ydvMb66vghs/0.jpg)](https://www.youtube.com/watch?v=ydvMb66vghs)

## Redesign PCB

To be honest, I've forgotten how I found this problem, probably after reading a lot of official documents and design guidelines, and comparing various related hardware designs.  

I realized that the line "from the communication module to the SMA connector" was too thin, or more precisely, not "impedance matched".  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/1795a48f-4d07-41c4-b744-1e015d19b1c0" width="500">
</p>

Prior to this project, I had never designed a "high-frequency" circuit board, or had any proper training in this area.   

In the past projects, I needed some UART/I2C/SPI interfaces, and I had a high degree of acceptance of PCB thickness, material, line width, surrounding shielding, etc., so I didn't have any problems with the preset parameters.  

But this time is different, wireless signaling is very demanding, you can't just plug in the cable and hope it works.  

After reading various articles, information and using tools and software to calculate the appropriate combination  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/70da5d0f-8727-4f39-b5ce-d8b675dea42c" width="500">
</p>

I designed the second version of the PCB  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/d34606c7-62db-43ee-9c22-e9d60ee15377" width="500">
</p>

I also designed different configurations of nodes based on my previous experience to make the whole thing more compact and portable.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/a7443c82-08af-49db-b3aa-8d02fa55de01" width="500">
</p>

## Field test

We later tested this version by placing one end on the roof and carrying the other end with us.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/0362bb53-00ef-4638-8d1d-7bae805c57c8" width="500">
</p>

According to the results of the experiment, we were able to achieve a communication distance of more than 4.5km (it should be able to go further, but there is no road).  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/7ab9586f-955c-43b3-9a28-62f4b296be36" width="500">
</p>

However, LoRa is still affected by buildings and terrain, its penetration is limited, and it still can't communicate behind complex buildings and mountains.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/ee93b516-328c-494e-8a88-22bc8c2951d7" width="500">
</p>

But for a battery-operated device with about 120 milliwatts of transmitting power, we're happy with the performance.  


