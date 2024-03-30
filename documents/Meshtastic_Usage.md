# Meshtastic usage  

In this document, we'll guide you through the steps required to set up your device.


## Getting Started with Meshtastic  

The initial step in setting up your Meshtastic project involves selecting the appropriate hardware to meet your communication requirements and adapt to your environment. Meshtastic supports a range of devices, each with its unique set of features including GPS capabilities, battery life, and range.

- **For wilderness adventurers:** Opt for devices with extended battery life and durable construction to withstand challenging conditions.
- **For urban explorers or community networking:** A device that offers higher data throughput with a shorter range might be more suitable. 

When choosing your device, consider the intended application, the geographical scope of your network, and any additional features you might need, such as GPS tracking.

Popular options are the `ESP32-based` boards, known for their adaptability, and the `nRF52` series, recognized for their energy efficiency. This crucial first step not only affects the setup process but also the success of your Meshtastic network in fulfilling your communication demands.


## Prepare your device

Before getting started with Meshtastic, the first step is to get your hardware ready, making sure you have all the necessary components to build a successful mesh network.

1. **Identify a Compatible Device**: Begin by choosing a Meshtastic-compatible device, like an ESP32 or nRF52-based board. This will serve as the primary node for communication within your network.
   
2. **Smartphone with Bluetooth**: Make sure you have a smartphone that supports Bluetooth. You'll use this to configure and manage your Meshtastic device through the official app.


<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/76be35f6-9eb0-4c2e-9f79-db5df4880d9f" width="600">
</p>


In short, you need a Meshtastic device and a smartphone/tablet (with Bluetooth).  
```Android``` and ```IOS``` are both supported.  

```
[Smartphone] <-Bluetooth-> [Node] <~~ LoRa ~~> [Node] <-Bluetooth-> [Smartphone]
      |                                 |                                 |
    (App)                            (Mesh)                             (App)
```

## Flashing Firmware

After preparing your hardware, the next critical step is to flash the Meshtastic firmware onto your device. This step is essential for enabling your device to communicate over the LoRa network and to connect with the smartphone app. The Meshtastic firmware is the software component that facilitates this connectivity and functionality.


### For ESP32-base devices:

For flashing the firmware, we recommend using the [Web Flasher](https://flasher.meshtastic.org/).

The process is simple and straightforward:
- Select your device.
- Choose the firmware version you wish to install.
- The web interface will handle the rest. 

You also have the option to upload custom firmware if needed. Note that for the best experience and full functionality, using Chrome or Edge as your browser is advised.

For more experienced developers seeking additional control and options, `esptool` remains a valuable resource for most scenarios.


### For nRF52 & RP2040 Devices:

Upgrading the firmware on nRF52-based devices is notably straightforward, requiring no additional driver or software installations across any platform. Simply connect your device to your computer, then [drag and drop](https://meshtastic.org/docs/getting-started/flashing-firmware/nrf52/drag-n-drop/) the firmware file, and you're all set with the update!

However, there's a caveat: if your device has a bootloader version older than 0.4.0, you'll need to update to a newer version to utilize the drag & drop method effectively.

To verify your bootloader version:
1. Connect your device to your computer.
2. Navigate to `.../BOOT` then to `INFO_UF2.TXT`.
3. Look for the version number following "UF2 Bootloader". It should be 0.4.0 or higher. If not, you'll likely need to update your bootloader.

For instructions on how to update your bootloader, please visit: [Update Bootloader](https://learn.adafruit.com/introducing-the-adafruit-nrf52840-feather/update-bootloader).



## Download the software

Next, it's time to install the Meshtastic app on your smartphone:

- For **Android**: [Download from the Play Store](https://play.google.com/store/apps/details?id=com.geeksville.mesh&pcampaignid=web_share)
- For **iOS**: [Download from the App Store](https://apps.apple.com/us/app/meshtastic/id1586432531)

Simply navigate to the Play Store or App Store on your device and search for the Meshtastic app to download and install it.

Alternatively, for Android users, the app can be sideloaded. This involves manually installing the app using the .APK file available on the [GitHub Releases](https://github.com/meshtastic/Meshtastic-Android/releases/) page. This method can be useful if you're looking for a specific version of the app or if you're unable to access the Play Store.

## Connect to your device  

To connect your smartphone to your Meshtastic node:

1. **Power On Your Node Device**: Once powered on, you'll see the device name and a notice message displayed on its screen. For example, `Meshtastic_3338`.

   <p align="center">
   <img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/2e3f4dc5-1e6e-488a-925e-443b0d48c133" width="450">
   </p>

2. **Enable Bluetooth & Open the App**: Turn on the Bluetooth functionality on your smartphone and open the Meshtastic app. You might need to grant the app Bluetooth access permissions to proceed.

3. **Add a New Device**: Tap the "+" button located in the lower-right corner of the app. The app will then begin searching for nearby Meshtastic devices.

   <p align="center">
   <img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/734a93d5-d572-46af-90d9-bf375740ec63" width="400">
   </p>

4. **Select Your Device**: Choose the device that matches your node's name. Your smartphone will attempt to connect to the node via Bluetooth.

   <p align="center">
   <img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/a74c7bca-b24b-48b0-9d87-9fc35599bf2b" width="400">
   </p>

5. **Enter the PIN**: A PIN number will be displayed on your node device.

   <p align="center">
   <img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/06ff03b2-f02c-47b0-bf16-b68c48d92c23" width="400">
   </p>  

   Input this PIN into your smartphone to complete the pairing process.

After successfully pairing your device, there's still one crucial step remaining to finalize the basic setup.



## Initial Configuration

To begin communicating over your mesh network, it's essential to select a region for your device. This configuration determines the frequency band your device will operate on, which must align with your geographical location to ensure compliance with local regulations.

Refer to the [Region Settings](https://meshtastic.org/docs/getting-started/initial-config/#set-regional-settings) for a comprehensive list of region codes and their corresponding areas.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/fc15e3e5-2e53-4119-8f01-9fc78b6cf59c" width="400">
</p>  

Upon selecting the appropriate region, your Node device will automatically reboot and commence operation.



## Channel setting  

To facilitate communication with other devices in your mesh network, all devices must be configured to use the same channel. The default channel is `#LongFast-I`, optimized for long-range and fast data transmission.

To align your device with others in the network, you have two options:

- **Join an Existing Channel**: If a channel has already been established by other devices in your network, you can join this channel to synchronize communication.

- **Create Your Own Channel**: Alternatively, you have the freedom to create a new channel. This can be especially useful if you are setting up a new network or require a channel with specific settings for your use case.


### Join an existing channel

There are two primary methods for joining an existing channel on your Meshtastic device:

1. **By Scanning a QR Code from Another User**: 
   - Navigate to the Channel tab in the Meshtastic app and tap `Scan`.
   
     <p align="center">
     <img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/9cc20a45-a78a-47a3-9815-df9779340d37" width="400">
     </p>  
   
   - This action will activate your camera, allowing you to scan the QR code which automatically configures your device to match the scanned channel settings.
   - Following a brief reboot, your device will be set to communicate with others on the selected channel.

2. **Channel URL Shared from a File or Link**: 
   - In instances where channel information is distributed as a link or file, simply click on the provided file or link and choose "Open with Meshtastic" from the options.
   - This method also automatically configures your device to align with the shared channel settings.


### Create a new channel

To create a custom channel on your Meshtastic device, follow these steps:

1. Go to the Channel tab in the Meshtastic app and tap on the `Channel Name` section.
   
   <p align="center">
   <img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/86d79b30-e7d1-4266-ba84-4c6eba8aedea" width="400">
   </p>  

2. This action will lead you to a parameter page, allowing you to customize your channel's settings to fit your specific requirements.

You have the capacity to create up to 8 channels on your device, with channel 0 designated as the primary channel and channels 1 through 7 as secondary channels.

> [!NOTE]
> Simply setting the same Name and Options will not replicate a channel exactly due to additional radio settings, such as the unique pre-shared key, that are encoded in the QR code or link. To ensure compatibility and security, these details must be explicitly configured.


## Communicate  

Once everything is configured, you can begin sending messages between devices using Meshtastic. Similar to other messaging systems, Meshtastic supports both group chat and direct messages, allowing you to communicate effectively within your mesh network.

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/84b99091-8869-4bb6-9eab-926706459720" width="400">
</p>



## Map

If your device is equipped with GPS or can provide location information, and you've enabled this feature, you can view any active mesh node with a known location directly on the map. This functionality enhances situational awareness and can be especially useful for tracking the movement and positioning of nodes within your network.


<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/e34c5d00-c72b-45aa-be1a-f9f02d553430" width="400">
</p>


## Conclusion

Congratulations on setting up your Meshtastic network! You've taken significant steps towards establishing a versatile communication system that extends beyond the capabilities of conventional networks.

Meshtastic is more than just a tool for communication; it's a vibrant, open-source project that thrives on the contributions and evolution driven by its community. As you delve deeper and tinker with your setup, keep in mind that your experiences and feedback are invaluable to the continuous development and enhancement of Meshtastic.

We encourage you to stay active within the Meshtastic community, share your discoveries, and keep pushing the boundaries of what's possible. Your participation not only enhances your own journey but also plays a crucial role in shaping the future of Meshtastic for everyone involved.



## References

[Meshtastic](https://meshtastic.org)  
[Installation guide](https://meshtastic.org/docs/software/android/installation/)  
[Application Usage](https://meshtastic.org/docs/software/android/usage/)  


