# TWC_Mesh Device

This article presents the specifications and elements of the Meshtastic device tailored by this study. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/8f376791-1270-4219-920e-9b1ffa1ac1b5" width="600">
</p>

## Why do we need to build our own?

Numerous devices compatible with Meshtastic are available, with the following being among the most popular choices currently on the market.


    RAK WisBlock Devices
    LILYGO® TTGO T-Beam
    LILYGO® TTGO T-Echo
    LILYGO® TTGO Lora
    HELTEC® LoRa 32
    Station G1
    Nano Series
    Raspberry Pi Pico

Given that the project was initiated in Taiwan during increasing geopolitical tensions and cross-strait relations, it is crucial to carefully choose source chips for hardware development to steer clear of products that could potentially present a national security risk. Consequently, ESP32 is ruled out as a viable option, while alternative solutions that do not rely on ESP32 are generally more costly, less versatile, or challenging to procure. 

As a result, the decision was made to start afresh with the device, thoroughly assessing all available components and revamping the project. Fortunately, Meshtastic stands out as an open-source initiative supported by a vibrant user community, where individuals explore a wide range of solutions and platforms.

## Core component

To create a Meshtastic node, it needs to have, at a minimum, the following elements: 

  * Core processor
  * LoRa communication module
  * Antenna
  * Display Screen
  * GPS module
  * Battery  
(If cost reduction is a priority, a screen/GPS/batteries are not essential.)

After considering the program's level of development on various platforms, we have selected the following as the central elements of this project.

| Parts	|  Model  | 
|---------------|------------  |
|   Processor   |  Nordic NRF52840 (Norway)  |
|   LoRa module |  Semtech sx1262 (USA) |
|   GPS module  |  NEO-6M (Switzerland)   |


## Prototyping 


Following some unexpected challenges, we managed to acquire all the necessary components 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/73f6c75d-969b-4bcb-b6e9-cc8828f07458" width="450">
</p>

and effectively transferred the meshtestic project to our hardware. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/75f9df66-1073-467c-b33e-2a17437c0b56" width="450">
</p>

Initial indications suggest that it will function correctly and establish communication seamlessly. Our subsequent objective involves devising a portable device to eliminate the need for extensive wire connections.


## PCB design


Taking into account the overall dimensions, type and positioning of the battery, usage position, maintenance convenience, arrangement of different components, and potential impact on signal lines, we have developed a PCB model of these gadgets to simplify future experimentation and evaluation. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4a42b649-fad4-4f2b-886c-be1830702fb7" width="450">
</p>

Following several refinements, the GPS component now features a removable configuration. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/96cc72cd-f229-4290-b758-4fcebd688775" width="550">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/c21f3b53-e619-48ff-93a2-fa3216249190" width="550">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/59f08159-f106-427c-a4ce-e457b45472d6" width="550">
</p>

Subsequently, through the assembly of the diverse components, we have successfully created the hardware for demonstration purposes! 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/d9a67539-a224-4bd6-8595-1862bcfbd057" width="500">
</p>

Moreover, we conducted some preliminary testing on the campus. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/00905149-701f-4c9d-89bd-123b0c20dd25" width="500">
</p>

However, the process encountered some challenges...  


## About antenna


We observed that the performance of the prototype system did not meet the expected theoretical value, showing a significant discrepancy. 

Along with intermittent disconnections and a high packet loss rate, the maximum communication distance was limited to only 400m, and the Received Signal Strength Indication (RSSI) was notably poor, contrasting with our prior successful experiences with LoRa technology (later identified as a design flaw on our part). 

Overall, the preliminary test results fell short of our initial expectations. This prompted me to question the integrity of the antenna being used. 

We began to wonder about the quality and suitability of the antenna in our possession. Subsequently, we acquired a NanoVNA to assess all antennas available in the laboratory meticulously, conducting measurements, labeling, and categorizing each one. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/9d2532c3-b1cf-4059-b856-fe10b9f7fc96" width="500">
</p>

We even ventured into constructing custom antennas tailored to the specific frequencies. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/86cf540f-3ac7-4a04-b3a8-8ed587623ca0" width="500">
</p>

The investigation revealed that a 2.4GHz antenna had been mistakenly included among the four sets of 915MHz antennas we had purchased. In essence, the incorrect antenna had been utilized during the testing phase.


## Other issue


After repairing the antenna, we resumed our experiments, only to encounter a new issue this time. Upon sending a message to our node, we observed that the Bluetooth signal of the node would abruptly disconnect from the smartphone. Despite thoroughly reviewing the code, we could not identify any apparent cause for the system reset. 

Initially, there seemed to be no viable method for debugging the issue. However, we had ensured the use of an appropriate antenna, the hardware aligned with the official design specifications, the software displayed no error messages, the power supply remained steady, and we dismissed the likelihood of the communication module drawing excessive power leading to a surge during command transmission. 

Delving into the realm of electromagnetic interference, we made numerous adjustments to the placement of both the communication module and the microprocessor, yet to no avail. It was only after a prolonged observation of these components that we deduced that by rotating the antenna to a specific angle, the disconnection issue could be averted. Subsequently, we successfully replicated this phenomenon across multiple units. (The video below demonstrates the unique angle required for each unit)


[![vid_1](https://img.youtube.com/vi/ydvMb66vghs/0.jpg)](https://www.youtube.com/watch?v=ydvMb66vghs)

## Redesign PCB

Honestly, we have forgotten the exact source where we encountered this issue. It likely came about after extensively reviewing official documents, design guidelines, and analyzing various related hardware designs. 

It became apparent to me that the connection "from the communication module to the SMA connector" was inadequately thin and lacked impedance matching. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/1795a48f-4d07-41c4-b744-1e015d19b1c0" width="500">
</p>

Before undertaking this project, we had no prior experience in designing high-frequency circuit boards nor had we received formal training in this specific domain. 

In previous projects, our requirements were mainly centered around UART/I2C/SPI interfaces, and we had always adhered to the prescribed parameters for PCB thickness, material, line width, and shielding without encountering any difficulties. 

However, this time was different as wireless communication demands precision; simply connecting a cable and hoping for it to function was not feasible. 

After conducting extensive research, consulting various resources, and utilizing tools and software to determine the optimal configuration, 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/70da5d0f-8727-4f39-b5ce-d8b675dea42c" width="500">
</p>

We revised the PCB design for the second iteration. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/d34606c7-62db-43ee-9c22-e9d60ee15377" width="500">
</p>


Drawing from our past projects, we also devised different node setups to enhance compactness and portability of the overall system.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/a7443c82-08af-49db-b3aa-8d02fa55de01" width="500">
</p>


## Field test

We conducted a trial with this iteration by positioning one extremity on the rooftop and transporting the other end along with us. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/0362bb53-00ef-4638-8d1d-7bae805c57c8" width="500">
</p>

The outcomes of the test revealed that a communication range exceeding 4.5km was attained (although it could potentially reach further if there were no obstacles). 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/7ab9586f-955c-43b3-9a28-62f4b296be36" width="500">
</p>

Nonetheless, LoRa remains susceptible to interference from structures and topography, with its signal penetration being constrained, hindering communication capabilities behind intricate buildings and mountains. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/ee93b516-328c-494e-8a88-22bc8c2951d7" width="500">
</p>

Nevertheless, considering it operates on approximately 120 milliwatts of transmitting power for a battery-powered device, we are content with its performance.  


## Conclution 


Through the development of our Meshtastic device, we successfully crafted a custom solution that precisely met our requirements and offered significant insights to the wider audience. Demonstrating a communication range exceeding 4.5 km truly showcases the capabilities of LoRa technology and the meticulous attention given to enhancing both the hardware and software components. 

We are eager to further enhance our design, delve into fresh opportunities, and enrich the communal knowledge base. Your support towards the advancement of the TWC_Mesh device is greatly appreciated.
