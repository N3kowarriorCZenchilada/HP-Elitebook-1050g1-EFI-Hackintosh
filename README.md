# HP Elitebook 1050G1 Hackintosh based on Opencore 0.9.5
<p align="center">
  <img src="hpelitebookImage.jpg" width="400">
</p>

## This wouldn't be possible to make for me without help from [Feartech](https://www.tonymacx86.com/members/feartech.877703/#about) and [TonyMacx86 Forum](https://www.tonymacx86.com).
<p>
  <img src="image.png" width="50" title="hover text" align="left">
  <img src="image2.png" width="180" title="hover text" align="right">
</p>

>  His [Github](https://github.com/feartech)⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁯⁬⁯⁬⁯⁬ ◦
>  Original [Post](https://www.tonymacx86.com/threads/hp-elitebook-1050-g1-cannot-boot-to-recovery.327519/)
<p>&nbsp;</p>

## Before Installation

> Replace your NVMe with NVMe SATA SSD, or look for a compatible one with successful installation.
> (Don't forget to hide TMP chip and disable legacy and SecureBoot in your BIOS.)

1. Use SSDTTime to **generate device-specific ACPI** (Just replace mine).

2. **Generate your own SMBIOS** for **MacBookPro15,2**.

3. **Install AirportItlwm.kext** for your macOS version (If you want to install MacOS I don't have a release for).

4. Your hardware may vary: Use USBToolbx tool to generate **UTBMap.kext** specific to your hardware.

5. After you boot to Opencore, clear NVRAM and reboot your laptop.

6. Start Installation.

### Warning: Expect post errors between installation steps.
It cannot automatically reboot to the installer.

## Installation Process

After going through recovery and starting the installation of MacOS, you will be rebooted to Opencore or the default boot option (If that happens, don't worry and reboot to your USB stick with Opencore).

After you boot to Opencore, there will be a new option "install macOS...". Select it and let it do its things. It will prompt logs, ignore it and wait. After a while, you will be rebooted again; you will need to select the same option. This time after a while, you should get an Apple logo with a progress bar under it.

After that, you will be rebooted once again, and in Opencore, there should be two new options: Recovery (dmg) and one that should be named after your drive name (the one you installed MacOS on).

Select the option named after your installation drive and do the final setup. After that, you will enter the desktop environment, and you are done with installation.

## After Installation

1. Re-enable kexts in config.plist:
   - IntelBTPatcher.kext / IntelBlueToolFixup.kext
   - IntelBluetoothInjector.kext
   - IntelBluetoothFirmware.kext
   - HibernationFixup.kext
   - RealtekCardReader.kext
   - RealtekCardReaderFriend.kext

2. Use tools like Hackintool, Opencore Configurator to customize the installation to your needs and hardware specifics.

3. Settings after installation :
   - Disable Haptic feedback
   - Configure Trackpad speed
   - Configure Microphone and Default Audio device

## Big Sur (OS soon out of support)

**Working:**

- Wifi
- Bluetooth
- Audio
- Backlight
- IGPU - Minor Graphics glitches
- Sleep
- Keyboard
- TouchPad
- SD card reader
- Battery indicator 

**Doesn't work:**

- Camera - (If you have model without ir camera, it may work)
- DGPU - (Needs to be patched with opencore legacy patcher)
- Ambient Light sensor 
- HDMI (This port is connected to DGPU)
- USB-C to HDMI adapter
- Air drop

## Monterey (Very stable)

**Working:**

- Wifi
- Bluetooth
- Audio
- Backlight
- IGPU
- Sleep
- Keyboard
- Touchpad
- SD card reader
- Battery indicator


**Doesn't work:**
- Camera - (If you have model without ir camera, it may work)
- DGPU - (Needs to be patched with opencore legacy patcher)
- Ambient Light sensor 
- HDMI (This port is connected to DGPU)
- USB-C to HDMI adapter
- Air drop

## Ventura (Fairly stable)

**Working:**

- Wifi
- Bluetooth
- Audio
- Backlight - Sometimes glitches (It will fix it self after few seconds to minutes)
- IGPU
- Sleep
- Keyboard
- Touchpad
- SD card reader - DO NOT UPDATE THE KEXT (newer version doesnt work)
- Battery indicator


**Doesn't work:**
- Camera - (If you have model without ir camera, it may work)
- DGPU - (Needs to be patched with opencore legacy patcher) -disabled in config.plist (remove disable-gpu flag)
- Ambient Light sensor
- HDMI (This port is connected to DGPU)
- USB-C to HDMI adapter (Port is configured as standart usb3c port)
- Air drop 
