# Field Try and Tests


## Range test

### Prototype test

Device:  
Handmade prototype  * 2  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/a270a49b-4de5-479c-8a1f-0760ba1eb5ed" width="600">
</p>

Frequency:   
923.875 MHz  

Modem Settings:  
Long_Fast  

Max distance:  
395m  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/02b74421-2345-40a6-9919-36e70e4ed9fe" width="600">
</p>


Note:  
This is an initial trial; the device is assembled using the breadboard and wires.

---  

### Prototype test 2

Device:  
TWC_Mesh_V3  * 2  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/b3d132c9-b54d-453a-bb64-70d6226e18d7" width="600">
</p>

Frequency:   
923.875 MHz  

Modem Settings:  
Long_Fast  

Max distance:  
464m  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/e79c5a1c-12f5-432c-b249-c1fd13e6ae53" width="600">
</p>

Note:  
The first version of our design prototype has several design flaws and lacks refinements in all areas.

---  

### Prototype test 3

Device:  
TWC_Mesh_V4  * 2  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/b094a6ef-d014-407f-bd0c-7fd6dd940bb1" width="600">
</p>

Frequency:   
923.875 MHz  

Modem Settings:  
Long_Fast  

Max distance:  
1.7 km (stop due to no roads ahead)  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/e5fb212b-999c-4a40-ac46-545275391a30" width="600">
</p>

Note:  
In TWC_mesh_V4, we corrected the flawed PCB design, selected the suitable antenna, and reviewed the battery selection.


---  

### Prototype test

Device:  
TWC_Mesh_V4  * 2  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4fc040b3-422e-4639-91de-197cd72de54b" width="600">
</p>

Frequency:   
923.875 MHz  

Modem Settings:  
Long_Fast  

Max distance:  
4.49km  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/6402543c-fc84-42b1-9b67-accb12b95f64" width="340" />
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/9f21f623-2c26-4492-a432-15d0c31d76f5" width="530" />
</p>


Note:  
LoRa technology can be affected by interference caused by buildings and natural surroundings, leading to limitations in signal penetration. These obstacles can reduce the effectiveness of communication in regions characterized by complex architectural layouts and mountainous landscapes.


## Antenna test

Throughout our investigation, it became evident that the antenna plays a significant role in communication.


<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/04aec9a0-7d42-4adc-b811-67e38f28209f" width="800">
</p>

Paying a higher price for antennas does not always mean that the quality is superior, as their effectiveness can appear somewhat mysterious at times. It is recommended to: 

* Exercise caution with antennas that assert to provide increased coverage. 
* Avoid products that do not provide comprehensive specifications. 
* Examine the vendor's other products, as their understanding of the items they sell may be insufficient on occasion.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/948fb426-59a3-46f2-ad1e-c0cd3395bbb3" width="500" />
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/edea5d91-540c-4796-a57e-ef439ca8da02" width="500" />
</p>  
(These antenna comes in wrong spec and frequency)  
  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/15a76e9b-ae10-49eb-891c-44ccb9d5d3f4" width="600">
</p>  
(And these two should be the same.)  
  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/0517fba1-a2c2-48dd-8ee8-60b9c3bc4c65" width="500">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/af2b9075-da30-4416-b78b-90559a669035" width="500">
</p>  

Designing our own antenna allows for a high level of customization, but it can become challenging when multiple devices need to be built.

## Vector Network Analyzers

Ensuring that your antenna is properly tuned to the operational frequency is a critical step. Many low-cost antennas are often misaligned to an inaccurate frequency, resulting in a significant reduction in signal strength. Using a vector network analyzer (VNA) can validate that the antenna is correctly calibrated with the transmission circuit, ensuring that it operates at the correct frequency.


<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/8662999a-8e3a-46b6-90fd-c32d48c63338" width="600">
</p>

Having the testing performed by a professional laboratory is always a good idea.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/80c3748d-e126-4c98-aecc-20085eece704" width="500" />
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/ee8f942e-7eb9-48bc-82b4-e1b25b338b59" width="500" />
</p>

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/0684b916-cfc8-46af-a9fa-c0b75475dfb1" width="600" />
</p>

At present, [ANT-916-CW-HWR-SMA](https://www.mouser.tw/ProductDetail/TE-Connectivity-Linx-Technologies/ANT-916-CW-HWR-SMA?qs=K5ta8V%252BWhtZqsDF9HiOBpg%3D%3D) performs optimally with our device; please refer to the other antenna report provided [here](https://github.com/meshtastic/antenna-reports).



## More antenna information

Hackaday's Introduction to Antenna Basics ([link](https://www.youtube.com/playlist?list=PL_tws4AXg7authztKFg5ZN5qWGtq3N_nI))  
An excellent series of presentations on the basics of antenna design and functionality, presented by spacecraft radio engineer Karen Rucker.

### Coverage prediction 

[HeyWhat'sThat](http://www.heywhatsthat.com/)  
Free with path profiling options  

[Radio Mobile Online](https://www.ve2dbe.com/rmonline_s.asp)  
Radio Mobile Online is a radio wave propagation prediction tool dedicated to amateur radio  

### RF Tools

[Times Microwave Systems](https://www.timesmicrowave.com/calculator/?Product=RG-6&RunLength=10&Frequency=868)  
Coaxial Cable Attenuation & Power Handling Calculator  

[Solwise Link Budget Calculator](https://www.solwise.co.uk/link-budget.htm)  
Predict the received signal strength  

[Amateur Radio Toolkit](https://play.google.com/store/apps/details?id=com.daveyhollenberg.amateurradiotoolkit)  
Android app with lots of antenna information  

### Antenna designs

[1/4 Wave Ground Plane Antenna Calculator](https://m0ukd.com/calculators/quarter-wave-ground-plane-antenna-calculator)  

[Quadrifilar helicoidal antenna calculator](https://jcoppens.com/ant/qfh/calc.en.php)  

[Building an 868/915 MHz co-linear antenna tutorial](https://www.youtube.com/watch?v=1_1LxuOngHs)  
[868 MHz antenna schematic PDF](https://github.com/IRNAS/ttn-irnas-gw/blob/master/Collinear868MHzLoRaantenna.PDF)  
[915 MHz antenna schematic PDF](https://github.com/IRNAS/ttn-irnas-gw/blob/master/CollinearLoRaantenna915MHzIRNAS.PDF)  

[NEC based antenna modeler and optimizer](https://www.qsl.net/4nec2)  


## References:
- [Meshtastic antenna](https://meshtastic.org/docs/hardware/antennas/resources/)
