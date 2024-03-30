# Using with ATAK

The combination of Meshtastic and ATAK provides a comprehensive solution for communication and situational awareness in environments where traditional connectivity is limited or absent, utilizing the strengths of both platforms.

## Prepare your device

> [!Note]
> Unfortunately, current TAK only support Android system

Before we begin, please ensure that your device is prepared and that the subsequent software is installed:


ATAK-CIV 
> Link: 

Meshtastic Android App   
> Link: [Github](https://github.com/meshtastic/Meshtastic-Android) or [Play Store](https://play.google.com/store/apps/details?id=com.geeksville.mesh&pcampaignid=web_share)  

Meshtastic ATAK Plugin  
> Link:  [Github](https://github.com/meshtastic/ATAK-Plugin)

Meshtastic Firmware
> Link:  [Github](https://github.com/meshtastic/firmware)

## Setting Up Meshtastic

The Meshtastic Android application can be obtained from the Google Play Store, F-Droid, or directly as an APK from GitHub. It is advisable to install the most recent stable release of the app. Additionally, ensure that your node devices are running on the latest stable or alpha iteration of the Meshtastic firmware. 

Refer to the [flashing-firmware](https://github.com/IISNRL/TWC_Mesh/blob/main/documents/Meshtastic_Usage.md#flashing-firmware) section for detailed instructions.

## Connecting to Devices:
Set your node device configuration to suit your situation.   
For the device role, the role is set to TAK (typically it would be set to Client), which allows the device to prioritize ATAK commands over Meshtastic's default behavior.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/d54ea6fa-6fbc-45bd-9aba-f2475fecc141" width="450">
</p>

See: [connect-to-your-device](https://github.com/IISNRL/TWC_Mesh/blob/main/documents/Meshtastic_Usage.md#connect-to-your-device) for more.  

## Testing Meshtastic Communication

Prior to incorporating ATAK, it is advisable to confirm that all devices are able to communicate effectively through the Meshtastic app to establish a solid base before introducing any new elements.

## Installing the ATAK Plugin

The installation procedure for the ATAK plugin includes downloading the plugin from Meshtastic's GitHub  [releases page](https://github.com/meshtastic/ATAK-Plugin) and then installing it on the device, which may necessitate authorization to install APKs.

Within ATAK, navigate to ```Setting > Tool Preferences > Package Management``` to refresh and install the plugin.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/20211a2b-d621-476d-a71e-ab60e955878d" width="650">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4010e744-2de5-4a8f-8bd2-5b628b667a79" width="650">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/1e451b1d-ba61-4813-a3ce-200970cfee90" width="650">
</p>

## Configure and test the plugin with ATAK

Once the plugin is activated, communication between devices via LoRa can commence. 

This method of communication is independent of 4G/Wi-Fi or TCP/IP, as it is transmitted through the LoRa network by Meshtastic.


## Conclusion 

The merging of Meshtastic with ATAK signifies a potent amalgamation of extended-range communication and sophisticated situational awareness abilities, designed for challenging environments where conventional connectivity is inadequate. 

This amalgamation will not only enhance the effectiveness and security of outdoor activities and missions but will also offer users a degree of information exchange and cooperation that was previously restricted to advanced military uses. 

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/4cf09b0b-e648-4bb2-b0b4-866d0d8f7f31" width="650">
</p>

By utilizing Meshtastic's resilient mesh networking for dependable off-grid communication and ATAK's intricate geospatial information and real-time collaboration features, teams can sustain uninterrupted connectivity and awareness irrespective of their whereabouts. 

This collaboration introduces fresh opportunities for exploration, emergency response, and remote operations, rendering it an invaluable resource for individuals in need of dependable communication and navigation assistance in the field.
