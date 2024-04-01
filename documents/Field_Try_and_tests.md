# Field_Try_and_tests


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
This is an early test, device is built with bread board and wires .  

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
First prototype of our design, with a lot of design flaws and no tweaks in any section.  

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
In TWC_mesh_V4 we fixed the wrong PCB design, selected the right antenna and reconsidered the battery option.  


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
LoRa is not immune to interference from buildings and natural landscapes, and its signal penetration is limited.  
These obstacles can reduce the effectiveness of communications behind complex architectural structures and mountainous terrain.  


## Antenna test

During our development, we found that the antenna plays a massive role in communication.  


<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/04aec9a0-7d42-4adc-b811-67e38f28209f" width="800">
</p>

Not always the more expensive the better, antennas can sometimes be a bit "magical".  

The rule of thumb is:
* Don't trust the "long range" antenna.
* Avoid products that don't provide specifications 
* Check the vendor's other products, sometimes they don't understand what they're selling. 

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
Building our own antenna gives us the most customizable option, but it's not very easy if we need to build multiple devices.   

## Vector Network Analyzers

Ensuring that your antenna is properly tuned to your operating frequency is a critical step. Many low-cost antennas are inaccurately tuned to the wrong frequency, resulting in a significant reduction in signal strength.  
Using a vector network analyzer (VNA) can verify that the antenna is properly matched to the transmission circuit.   
This ensures that the antenna is operating at the correct frequency.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/8662999a-8e3a-46b6-90fd-c32d48c63338" width="600">
</p>

And it's always nice to have a professional lab do the testing for you.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/80c3748d-e126-4c98-aecc-20085eece704" width="500" />
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/ee8f942e-7eb9-48bc-82b4-e1b25b338b59" width="500" />
</p>

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/0684b916-cfc8-46af-a9fa-c0b75475dfb1" width="600" />
</p>

Currently [ANT-916-CW-HWR-SMA](https://www.mouser.tw/ProductDetail/TE-Connectivity-Linx-Technologies/ANT-916-CW-HWR-SMA?qs=K5ta8V%252BWhtZqsDF9HiOBpg%3D%3D) works the best with our device, check other antenna report [here](https://github.com/meshtastic/antenna-reports).   


## More antenna information

Hackaday's Introduction to Antenna Basics ([link](https://www.youtube.com/playlist?list=PL_tws4AXg7authztKFg5ZN5qWGtq3N_nI))  
An excellent series of presentations on the basics of antenna design and function, presented by spacecraft radio engineer Karen Rucker.  

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
