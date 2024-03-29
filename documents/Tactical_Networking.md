# Using with ATAK

The combination of Meshtastic and ATAK provides a comprehensive solution for communication and situational awareness in environments where traditional connectivity is limited or absent, utilizing the strengths of both platforms.

## Prepare your device:

> [!Note]
> Unfortunately, current TAK only support Android system

Before we get started, please make sure your device is ready and have the following software installed:  

ATAK-CIV 
> Link: 

Meshtastic Android App   
> Link: [Github](https://github.com/meshtastic/Meshtastic-Android) or [Play Store](https://play.google.com/store/apps/details?id=com.geeksville.mesh&pcampaignid=web_share)  

Meshtastic ATAK Plugin  
> Link:  [Github](https://github.com/meshtastic/ATAK-Plugin)

Meshtastic Firmware
> Link:  [Github](https://github.com/meshtastic/firmware)

## Setting Up Meshtastic:
You can download the Meshtastic Android app either from the Google Play Store, F-Droid, or directly as an APK from GitHub.  
We'll recommend the latest stable version of the app.  
And make sure your node devices are updated to the latest stable or alpha version of the Meshtastic firmware.  

See: [flashing-firmware](https://github.com/IISNRL/TWC_Mesh/blob/main/documents/Meshtastic_Usage.md#flashing-firmware) for more instruction.  

## Connecting to Devices:
Set your node device configuration to suit your situation.   
For the device role, the role is set to TAK (typically it would be set to Client), which allows the device to prioritize ATAK commands over Meshtastic's default behavior.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/d54ea6fa-6fbc-45bd-9aba-f2475fecc141" width="450">
</p>

See: [connect-to-your-device](https://github.com/IISNRL/TWC_Mesh/blob/main/documents/Meshtastic_Usage.md#connect-to-your-device) for more.  

## Testing Meshtastic Communication:
Before integrating ATAK, it's recommended to ensure all devices can communicate within the Meshtastic app to ensure a stable foundation before introducing new variables.

## Installing the ATAK Plugin:
The ATAK plugin installation process involves downloading the plugin from Meshtastic’s GitHub [releases page](https://github.com/meshtastic/ATAK-Plugin), then installing it on your device, potentially requiring permission to install APKs.

In ATAK, go into ```Setting > Tool Preferences > Package Management``` refresh and install the plugin.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/20211a2b-d621-476d-a71e-ab60e955878d" width="650">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4010e744-2de5-4a8f-8bd2-5b628b667a79" width="650">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/1e451b1d-ba61-4813-a3ce-200970cfee90" width="650">
</p>

## Configure and test the plugin with ATAK:  
Once the plugin is loaded, you can start sending messages between devices using LoRa.  
The communication does not depend on 4G / Wi-Fi or TCP/IP, but is transmitted over the LoRa network by Meshtastic.  

## Conclusion:  

The integration of Meshtastic with ATAK represents a powerful fusion of long-range communications and advanced situational awareness capabilities, tailored for the most demanding environments where traditional connectivity falls short.   

This combination will not only increase the efficiency and safety of outdoor adventures and operations, but will also provide users with a level of information sharing and coordination that has previously been limited to high-tech military applications.   

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4cf09b0b-e648-4bb2-b0b4-866d0d8f7f31" width="650">
</p>

By leveraging Meshtastic's robust mesh networking for reliable, off-grid communications and ATAK's detailed geospatial data and real-time collaboration tools, teams can maintain seamless connectivity and awareness regardless of location.   

This synergy opens up new possibilities for exploration, emergency response and remote operations, making it an invaluable asset for anyone requiring reliable communication and navigation support in the field.  
