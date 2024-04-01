# Scenario disscussion

"What tools do we have when disaster strikes?"  
"What if we don't have internet?"  

## About the Project.

In the face of natural disasters, emergencies, or other crisis situations, communication is often a matter of life and death.   
However, in many disaster situations, traditional communications infrastructure can be damaged or disrupted, leaving people unable to get the information they need in a timely manner or to seek rescue or assistance.  

As a result, the TWC_Mesh project was developed to provide a robust and reliable communications system to respond to disasters and emergencies.   
The project was born out of a desire to provide a communications solution that would work during emergencies to ensure that people could stay connected, share information, coordinate actions, and receive timely assistance.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/e9f4aeae-1d48-4882-a2ae-b352c0b9aa14" width="600">
</p>

The TWC_Mesh project includes the use of wireless technology, self-organizing networks, and sensors to create a flexible and scalable communications network that can operate in a variety of environments.   
The goal of this project is to improve the effectiveness of disaster response, minimize losses, and ensure the safety of personnel.  


## Scenarios

This project is designed to address some of the most challenging and extreme conditions for communications:  

* Infrastructure failure:   
  
  In scenarios where traditional communications infrastructure such as telecom towers are unavailable, it is necessary to create an independent network.  
Each unit within this network must operate autonomously and maintain connectivity without relying on fixed infrastructure.  

* Lack of cellular networks:  
  
  Without access to standard cellular services (4G/5G), the project must use alternative means of communication.  
Long-range wireless technologies become critical in these situations, allowing messages to be transmitted over long distances where traditional networks fall short.  

* Limited power sources:  
  
  Scarcity of power sources is a critical factor. Communication tools must be designed for energy efficiency, capable of operating extensively on minimal power.  
  This includes integrating low-power hardware and implementing battery management strategies to avoid power outages at critical moments.  

* Challenging terrain:  
  
  The project will also address the challenges posed by mountainous regions or areas without cellular infrastructure.  
  These landscapes can impede signal reach, requiring strategic considerations for signal propagation and the establishment of reliable communication paths despite natural obstacles.  

These focus areas underscore the project's commitment to ensuring robust communications capabilities under the most challenging conditions, using innovative technologies to overcome connectivity barriers.  


## What we want to achieve  

We want to achieve the following goals:  

* Provide long distance communication capability
* Adequate bandwidth
* Consume less power or be able to sustain power until communication is restored.
* Be mobile*.
* Require limited prior knowledge
* Positioning/Navigation
* Provides geographic information


## Related Research/Projects

Emergency communication networks have always been a hot topic, and related research and projects play an important role in the field of disaster emergency communication networks, representing different technical approaches and solutions to meet communication needs in different scenarios.  

Below are some of the projects and programs that exist today:  


### High bandwidth, ("Wi-Fi" like)

* AREDN (Amateur Radio Emergency Data Network).  
  
AREDN is an Amateur Radio Emergency Data Network designed to provide high-bandwidth communications capabilities.  
It is built on the foundation of amateur radio technology and allows users to create networks to transmit data in disaster situations.   
https://www.arednmesh.org/

* San Francisco Wireless Emergency Mesh (SFWEM).  
  
SFWEM is a wireless emergency communications network designed for the San Francisco area to provide high-bandwidth, Wi-Fi-like communications for disaster situations such as earthquakes.  
https://www.sfwem.net/

### Low Bandwidth, (Radio like)

* Meshtastic  
  
The Meshtastic project is an open source project for low-bandwidth, long-range communications.  
It uses LoRa wireless technology to allow users to build self-organized networks to share information over long distances.  
https://meshtastic.org/

* project-owl  
  
project-owl aims to build a rapidly deployable disaster communications solution using IoT technology and LoRa wireless communications.  
It aims to provide information sharing and collaboration capabilities during emergencies.  
https://www.project-owl.com/

  * disaster-radio  

disaster-radio is an open-source wireless communications project that uses ESP32 and LoRa hardware to provide low-bandwidth, long-range communications.   
It is designed for community networking and emergency communications.  
https://github.com/sudomesh/disaster-radio
  
  * duck-link / sparrow-mesh
    
The duck-link and sparrow-mesh projects are designed to create a low-power, long-range communications network for emergency communications needs.  
They use ad hoc mesh and LoRa technologies and provide open source hardware and software.  
https://github.com/sparrow-platform/duck-sparrow-link

  * lora-mesh  
  
lora-mesh is a wireless networking solution based on LoRa technology that allows users to create a network and communicate in low bandwidth.   
It is suitable for rural areas or places without traditional communication infrastructure.  
https://github.com/nootropicdesign/lora-mesh

  * Lantern  
  
Lantern is a communication and emergency response platform that uses Raspberry Pi and LoRa hardware to explore the capabilities of distributed networks for disaster response, especially in remote and disaster-prone areas.  
https://www.lantern.works/


## Possible options

Based on the existing projects, we have summarized the following options:  

* Satellite Communication
  
Satellite communication is a reliable means of communication that is not geographically limited. It can provide worldwide coverage and can communicate at locations far from the base station.   
This allows people to use satellite phones or data connections to stay in touch during a disaster situation. However, satellite communications are more expensive and may require specialized equipment.

* Handheld radios  
  
Handheld radios are portable communications devices commonly used in emergency and rescue operations.  
They typically use short- to medium-range wireless communication technologies, such as walkie-talkies or radios, and do not rely on traditional communication networks.  
This method is useful for communicating in small areas, but is limited in range.  

* Wi-Fi Mesh  
    
Wi-Fi Mesh is based on the existing Wi-Fi infrastructure, but can form a self-organizing network that allows direct communication between users.   
This is useful for communicating in limited areas, especially in cities or neighborhoods where many Wi-Fi devices are available.  
However, it requires power and network infrastructure support.  

* LPWAN  
  
LPWAN is a low-power, long-range communication technology, such as LoRaWAN and NB-IoT, that enables communication at low bandwidths and has excellent signal penetration for buildings in mountainous areas or cities.  
LPWANs typically use low-power devices that can operate on battery power for long periods of time.  


## Our Choice

Considering the time, cost, and labor, we finally chose:  

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


