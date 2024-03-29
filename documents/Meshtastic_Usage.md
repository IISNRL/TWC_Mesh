# Meshtastic usage  

In this part, we'll go through the process of how to set up your device.

## Getting Started with Meshtastic  

The first step in your Meshtastic project is selecting the right hardware to suit your communication needs and environment.  
Meshtastic is compatible with a variety of devices, each offering different features such as GPS, battery life, and range capabilities.  

For wilderness adventurers, a device with a long battery life and robust build might be ideal.   
In contrast, for urban explorers or community networking, a device with higher data throughput and shorter range may suffice.  
Consider factors like the intended use case, the geographical area you plan to cover, and whether you need additional features like GPS tracking.  

Popular choices include the ```ESP32-based``` boards for their versatility and the ```nRF52``` series for their energy efficiency.  
This foundational step is crucial, as the choice of hardware will determine the setup process and the overall effectiveness of your Meshtastic network in meeting your communication needs.  

## Prepare your device

Before diving into Meshtastic, the initial step is to prepare your hardware, ensuring you have everything needed to establish a successful mesh network.  
Start with identifying a compatible Meshtastic device, such as an ESP32 or nRF52-based board, which will act as your primary communication node.  
Next, ensure you have a smartphone with Bluetooth capability, as you'll need it to configure and interact with your Meshtastic device via the official app.  

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

Once your hardware is ready, the next pivotal step is flashing the firmware onto your Meshtastic device.  
This process involves installing the Meshtastic firmware, which is the software that allows your device to communicate over the LoRa network and interface with the smartphone app.  

### For ESP32-base devices:

Generally, I'll suggest using the [Web_Flasher](https://flasher.meshtastic.org/)  

It's simple and straightforward, just choose your device, select the firmware you want, and the website does the rest.   
You can even upload your own firmware.  
Just remember to use Chrome or Edge for full functionality.  

And for more experenced developer who want more options, ```esptool``` still comes handy in most of the time.  

### For nRF52 & RP2040 Devices:

The nRF52-based devices have the simplest firmware upgrade process. No driver or software installation is required on any platform.  
Just connect your device to your computer, [drag and drop](https://meshtastic.org/docs/getting-started/flashing-firmware/nrf52/drag-n-drop/), and your update is complete!  

However, there is a catch: if your device somehow comes with a bootloader older than 0.4.0, you will need to update to a later version to use the drag & drop method.  

To check the bootloader version ```connect your device --> .../BOOT --> INFO_UF2.TXT -->  the number after "UF2 Bootloader" ```  
It should be at least 0.4.0 or higher, otherwise you may want to update your bootloader.   

See update instructions here: [update bootloader](https://learn.adafruit.com/introducing-the-adafruit-nrf52840-feather/update-bootloader)

## Downloading the software

Next, you need to install the software on your smartphone.  
* For [Andiroid](https://play.google.com/store/apps/details?id=com.geeksville.mesh&pcampaignid=web_share)
* For [IOS](https://apps.apple.com/us/app/meshtastic/id1586432531)

Go to Play Store / APP Store and download the APP for your smartphone.  

Alternatively, the app can also be sideloaded by downloading the .APK from the [Github Releases](https://github.com/meshtastic/Meshtastic-Android/releases/) page.

## Connect to your device  

To connect to your node.  
Power on your node device, you should see the device name and Notice message showing on the screen.  
In this case ```Meshtastic_3338``` :  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/2e3f4dc5-1e6e-488a-925e-443b0d48c133" width="450">
</p>

Next, turn on the bluetooth and open the Meshtastic app on your phone.  
(you may need to allow Bluetooth access permissions to continue)  

Press the + button on the lower right, the APP will search for nearby node device.
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/734a93d5-d572-46af-90d9-bf375740ec63" width="400">
</p>

Sellect the correspond device, and your smartphone will try to connect to your node device through Bluetooth.  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/a74c7bca-b24b-48b0-9d87-9fc35599bf2b" width="400">
</p>

The pin number will show on your node device.  
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/06ff03b2-f02c-47b0-bf16-b68c48d92c23" width="400">
</p>  

After entering the PIN code, the paring process between the Node device and your phone is  finished.  
But we still have one important thing to do to complete the basic setup.  

## Initial Configuration

In order to start communicating with your mesh, you must select a region.  
This setting controls which frequency your device uses and should be set according to your location.  
See Region Settings for a list of [region codes](https://meshtastic.org/docs/getting-started/initial-config/#set-regional-settings) and their meanings.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/fc15e3e5-2e53-4119-8f01-9fc78b6cf59c" width="400">
</p>  

After you select the region, the Node device will automatically reboots and starts running.  


## Channel setting  

To communicate with other device, you have to be on the same channel.  
The default channel is ```#LongFast-I (Long range / Fast)```  

You can either **join an existing channel** or **create your own**.  

### Join an existing channel

There are two ways to join an exsisting channel:  
1. By scanning the QR code from another user  
   Navigate to the Channel tab and click ```Scan```.
<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/9cc20a45-a78a-47a3-9815-df9779340d37" width="400">
</p>  
  This will open your camera and set your device according to the QR code.   
  After a short reboot, you should be able to talk to the other device on the given channel.   

2. Channel url shared from a file or link  
  Sometimes the channel information may come in link/file format, you can click on the file or link and select "Open with Meshtastic".   
  This will also set your device accordingly.

### Create a new channel

If you want to create your own channel, navigate to the Channel tab and click on the ```Channel Name``` section.  
This will open a parameter page where you can customize your channel.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/86d79b30-e7d1-4266-ba84-4c6eba8aedea" width="400">
</p>  

You can create up to 8 channels for your device, 0 as the primary cahnnel 1~7 as secondary channel.  

> [!NOTE] 
> Setting the same Name and Options directly doesn't work as there are other radio settings (like the unique pre-shared key)  
> encoded in the QR code or link.

## Communicate!  

Once every thing is set, yous can start sending message between devices.  
Just like other message system, Meshtastic support group chat and direct messages.   

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/84b99091-8869-4bb6-9eab-926706459720" width="400">
</p> 


## Map

If your device has GPS or provides location information, and you enable the option  
You can see any active mesh node with a known location on the map.  

<p align="center">
<img src="https://github.com/IISNRL/TWC_Mesh/assets/11376362/e34c5d00-c72b-45aa-be1a-f9f02d553430" width="400">
</p>


## Conclusion

Well done on setting up your Meshtastic network!  
You’ve taken crucial steps towards creating a versatile communication system that operates beyond conventional networks.  

Meshtastic is more than a communication platform; it's part of a dynamic, open-source project that evolves with its community.  
As you explore further and experiment with your setup, remember that your experiences and feedback contribute to the growth and improvement of Meshtastic.  

We encourage you to remain engaged with the Meshtastic community, share your insights, and continue to innovate.  
Your involvement not only enriches your own experience but also helps shape the future of Meshtastic for everyone.  


## Source

[Meshtastic](https://meshtastic.org)  
[Installation guide](https://meshtastic.org/docs/software/android/installation/)  
[Application Usage](https://meshtastic.org/docs/software/android/usage/)  


