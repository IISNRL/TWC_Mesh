# Scenario disscussion

"What tools do we have when disaster strikes?"  
"What if we don't have Internet?"  

## About the Project.

During natural disasters, emergencies, or crises, effective communication becomes critical for survival. Unfortunately, in such scenarios, conventional communication systems are frequently compromised, making it challenging for individuals to access necessary information promptly or to request help.

Consequently, the TWC_Mesh initiative was created with the aim of offering a sturdy and dependable communication system to address disasters and emergencies. The project originated from the need to create a communication system that could function effectively in emergencies to enable individuals to remain in touch, exchange information, collaborate on tasks, and obtain prompt help.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/e9f4aeae-1d48-4882-a2ae-b352c0b9aa14" width="600">
</p>

The TWC_Mesh initiative integrates wireless technology, self-organizing networks, and sensors to establish a versatile and expandable communication network suitable for diverse settings. The primary aim of this endeavor is to enhance the efficiency of disaster management, reduce damages, and guarantee the well-being of staff.


## Scenarios

This project aims to tackle some of the most difficult and severe communication conditions:

* Infrastructure failure:
   
  In situations where conventional communication systems like telecommunication towers are not accessible, it becomes essential to establish a self-sufficient network. Each component in this network should function independently and sustain connectivity without depending on stationary infrastructure.

* Lack of cellular networks:  
  
  In the absence of conventional cellular services (4G/5G), the project needs to rely on alternative communication methods. Long-distance wireless technologies play a crucial role in such scenarios, enabling the transmission of messages across vast distances that traditional networks cannot cover.

* Limited power sources:  
  
  The limited availability of power sources is a significant consideration. Communication devices need to be crafted with energy efficiency in mind, enabling them to function for long periods with minimal power usage. This involves incorporating low-power components and deploying battery management tactics to prevent power failures during crucial times.

* Challenging terrain:  
  
  The project will also tackle the difficulties presented by hilly terrains or regions lacking cellular infrastructure. These geographical features may hinder signal coverage, necessitating careful planning for signal transmission and the creation of dependable communication routes despite natural hindrances. These specific areas highlight the project's dedication to guaranteeing strong communication abilities even in demanding circumstances, by leveraging creative technologies to surmount connectivity challenges.


## What we want to achieve  

We want to achieve the following goals:  

* Provide long-distance communication capability
* Adequate bandwidth
* Consume less power or be able to sustain power until communication is restored.
* Be mobile.
* Require limited prior knowledge
* Positioning/Navigation
* Provides geographic information


## Related Research/Projects

Emergency communication networks have consistently been a significant area of interest, with research and initiatives playing a crucial role in the domain of disaster emergency communication networks. These efforts encompass various technical strategies and resolutions aimed at addressing communication requirements across diverse scenarios. 

The following are a few of the current projects and initiatives in this realm:


### High bandwidth, ("Wi-Fi" like)

* AREDN (Amateur Radio Emergency Data Network).  
  
  AREDN is a network intended for emergency data communication in the realm of amateur radio, aiming to offer robust bandwidth capacities. Leveraging amateur radio technology, it enables users to establish networks for the transmission of data during times of crisis.
https://www.arednmesh.org/

* San Francisco Wireless Emergency Mesh (SFWEM).  
  
  SFWEM is an emergency communication network that is wireless and specifically created for the San Francisco region. It aims to offer high-bandwidth communication similar to Wi-Fi during emergencies like earthquakes.
https://www.sfwem.net/

### Low Bandwidth, (Radio like)

* Meshtastic  
  
  The Meshtastic initiative is a freely available project designed for long-distance communication with low bandwidth. It employs LoRa wireless technology to enable users in constructing self-organized networks for sharing information across extended distances.
https://meshtastic.org/

* project-owl  
  
  The aim of the project-owl is to develop a rapidly deployable communication system for disaster scenarios, making use of IoT technology and LoRa wireless communications. The primary goal is to provide functionalities for exchanging information and working together in times of emergencies.
https://www.project-owl.com/

* disaster-radio  

  disaster-radio is a wireless communications initiative based on ESP32 and LoRa technology, aiming to deliver long-distance, low-bandwidth communication. It is specifically crafted for community networking and emergency communication purposes.
https://github.com/sudomesh/disaster-radio
  
* duck-link / sparrow-mesh
    
  The duck-link and sparrow-mesh initiatives aim to establish an energy-efficient, extensive communication system for emergency communication requirements. These projects utilize ad hoc mesh and LoRa technologies, offering open-source hardware and software solutions.
https://github.com/sparrow-platform/duck-sparrow-link

* lora-mesh  
  
  lora-mesh is a wireless networking solution that makes use of LoRa technology, allowing individuals to create a network and exchange information with limited bandwidth capabilities. This technology is particularly suitable for rural areas or regions that do not have traditional communication infrastructure.
https://github.com/nootropicdesign/lora-mesh

* Lantern  
  
  Lantern is a communication and emergency response system that employs Raspberry Pi and LoRa technology to investigate the potential of decentralized networks for disaster relief efforts, particularly in remote and disaster-prone regions.
https://www.lantern.works/


## Possible options

Drawing from the current projects, we have compiled the subsequent choices:

* Satellite Communication
  
  Satellite communication, a dependable form of communication, is not constrained by geography. It offers global coverage and enables communication in remote areas distant from the primary station. This capability allows individuals to utilize satellite phones or data connections to maintain contact in times of emergency. Nevertheless, satellite communications tend to be pricier and may necessitate specialized equipment.

* Handheld radios  
  
  Handheld radios are compact communication tools frequently employed in emergency and rescue missions. They generally utilize short- to medium-distance wireless communication technologies like walkie-talkies or radios and are not dependent on conventional communication infrastructures. While effective for communication within close proximity, their range is restricted.

* Wi-Fi Mesh  
    
  Wi-Fi Mesh utilizes the current Wi-Fi framework, yet has the capability to establish a self-regulating network enabling direct interaction among users. It proves beneficial for communication within confined spaces, particularly in urban or residential areas abundant with Wi-Fi devices. Nonetheless, it necessitates support from power and network infrastructure.

* LPWAN  
  
  LPWAN refers to a communication technology characterized by low power consumption and long-range capabilities, exemplified by technologies like LoRaWAN and NB-IoT. This technology facilitates communication at reduced bandwidths and boasts exceptional signal penetration, particularly in urban areas or mountainous regions. LPWAN networks commonly employ energy-efficient devices capable of prolonged operation on battery power.


## Our Choice

Taking into account factors such as time, expenses, and manpower, we ultimately decided on:

* LPWAN  

  Meshtastic

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/303f8ef8-d464-4faf-a21e-37233e0d7747" width="600">
</p>

* Wi-Fi mesh  

  AREDN

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/2cdd9f9e-5990-4ca2-b637-f3745d40cda1" width="600">
</p>



These two projects represent long distance and high bandwidth scenarios respectively.  


