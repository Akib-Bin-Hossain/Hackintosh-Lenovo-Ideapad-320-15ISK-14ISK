 
# Hackintosh-Lenovo-Ideapad-320-15ISK-14ISK

Goal of this repo is to run Mac os on Lenovo Ideapad 320 15ISK Laptop

## OpenCore Installation Guide

Go to [INSTALLATION_GUIDE_OPENCORE.md](INSTALLATION_GUIDE_OPENCORE.md)(**Detailed guide**)

## About this Laptop

### Original Hardware Info 💻

Type | Spec | Status | Link
:---------|:---------|:----------|:----------
Computer		| Lenovo Ideapad 320-15ISK 80XH01DNIN   | Working | -
BIOS Version	| LENOVO Insyde EFI(4WCN29WW) | Working | -
CPU				| DualCore Intel Core i3, 2000 MHz (20 x 100) | Working | -
Chipset			| Intel Sunrise Point-LP, Intel Skylake-U | Working | -
Graphics		| Intel HD Graphics 520, NVIDIA GeForce 920MX (Using Intel GPU only) | Working | [Guide](https://www.tonymacx86.com/threads/guide-intel-framebuffer-patching-using-whatevergreen.256490/)
Audio			| Realtek ALC3240, Codec ID:10EC0230h / 17AA3809h | Working | [Guide](https://github.com/acidanthera/AppleALC/wiki/Installation-and-usage)
Ethernet		| Realtek RTL8168/8111 PCI-E Gigabit Ethernet Adapter() | Working | -
WiFi			| Intel(R) Dual Band Wireless-AC 3165 | Not Working | -
Bluetooth		| Intel(R) Wireless Bluetooth(R) | Working | -
Touchpad		| I2C ELAN0608 | Working | [Guide](Touchpad-Guide.md)
Keyboard		| - | Working | -
Webcam		    | Ven id: 0x04f2(Chicony Electronics Co.,Ltd.) Product id: 0xb5d8| Working | -
Battery		    | Serial Number: L16M2PB2- 1229 Manufacturer: SMP Device Name:	L16M2PB2 | Working | -

### Modifications 🔨

Type | Spec | Status
:--------- |:---------|:----------
D-Link DWA-131 Wireless N Nano USB Adapter (Black) | - | Working
BCM94360CS2 Wireless WIFI Bluetooth 4.0 Airport Card For Macbook Air 11" A1465 13" A1466 2013 MD711LL/A MD760 BCM94360CS2AX | - | Working
Wireless Bluetooth Mouse Rechargeable Mouse | - | Working
Universal for 9.5mm CD/DVD Drive Slot (for SSD and HDD) | - | Working
15.6 inch IPS LCD matrix LP156WF4 LP156WF6 | - | Working

### Software Status 👨‍💻

Type | Spec | Status
:---------|:---------|:----------
Battery Status | - | Working
Brightness With keys(F11 - F12) | - | Working
Sleep | - |  Working

### Kext Used 
 
Kext | Info 
:---------|:---------
[Lilu.kext](https://github.com/acidanthera/Lilu) | Arbitrary kext and process patching on macOS.
[AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm) | Intel Wi-Fi Drivers for macOS.
[itlwm.kext](https://github.com/OpenIntelWireless/itlwm) | Intel Wi-Fi Drivers for macOS.
[IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) | Intel Bluetooth Drivers for macOS.
[AppleALC.kext](https://github.com/acidanthera/AppleALC) | For Audio.
[RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X) | RTL8111/8168/8411 PCI Express Gigabit Ethernet.
[VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) | SMC Emulator Layer.
[SMCBatteryManager.kext](https://github.com/acidanthera/VirtualSMC) | Battery Status Monitoring.
[SMCProcessor.kext](https://github.com/acidanthera/VirtualSMC) | Processor Temp Monitoring.
[SMCSuperIO.kext](https://github.com/acidanthera/VirtualSMC) | Fan Reading.
[USBPorts.kext](https://www.tonymacx86.com/threads/the-new-beginners-guide-to-usb-port-configuration.286553/) | For USB Port mapping.
[VoodooI2C.kext](https://github.com/VoodooI2C/VoodooI2C) | For I2C Touchpad.
[VoodooI2CELAN.kext](https://github.com/VoodooI2C/VoodooI2C) | For ELAN Touchpad.
[VoodooPS2Controller.kext](https://github.com/RehabMan/OS-X-Voodoo-PS2-Controller) | Contains updated Voodoo PS/2 Controller, improved Keyboard & Synaptics TouchPad.
[WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen) | Various patches necessary for certain ATI/AMD/Intel/Nvidia GPUs. This is needed for Intel HD 520.
[HWPEnabler.kext](https://github.com/goodwin/HWPEnable) | HWP is a technology introduced in Skylake which lets the CPU select its own stepping speed without the usage of the CPU Multiplier. Additionally it trottles/boosts itself much faster, which improoves overall CPU performance. With enabled HWP you dont need to create SSDTs with CPU P-States anymore.
[CpuTscSync.kext](https://github.com/acidanthera/CpuTscSync) | It is a Lilu plugin, combining functionality of VoodooTSCSync and disabling xcpm_urgency if TSC is not in sync. It should solve kernel panics after wake.
[HoRNDIS.kext](https://github.com/jwise/HoRNDIS) | Android USB tethering driver for Mac OS X
[ BlueToolFixup.kext,](https://github.com/acidanthera/BrcmPatchRAM) | Required for macOS 12 or newer, as in macOS 12 Apple has changed parts of the Bluetooth stack from kernel-space to user-space
[FeatureUnlock.kext](https://github.com/acidanthera/FeatureUnlock) | Add Sidecar support to unsupported models
[BrightnessKeys.kext](https://github.com/acidanthera/BrightnessKeys) | Handler for brightness keys without DSDT patches
[RTCMemoryFixup.kext](https://github.com/acidanthera/RTCMemoryFixup) | open source kernel extension providing a way to emulate some offsets in your CMOS (RTC) memory


HibernationFixup.kext
### SSDT Used 

Kext | Info | Refrence Link 
:---------|:--------- |:---------
SSDT-EC-USBX.aml | Fix Embedded Controllers. For Skylake laptops and newer. | [Link](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix.html#fixing-embedded-controller-ssdt-ecusbx)
SSDT-EHCx_OFF.aml | USB compatibility table for disable phantoms EHC1, EHC2. Only for 7,8,9-series chipsets and 10.11 and newer! | [Link](https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/SSDT-EHCx_OFF.dsl)
SSDT-GPRW.aml | _PRW USB wake up patch. | [Link](https://1revenger1.gitbook.io/laptop-guide/battery-power-management/correcting-sleep-problems)
SSDT-I2C.aml | Fix trackpad | [Link](https://voodooi2c.github.io/#GPIO%20Pinning/GPIO%20Pinning)
SSDT-KBD.aml | Fix brightness key.(F11 and F12)  | [Link](https://github.com/RehabMan/HP-Envy-DSDT-Patch/blob/master/SSDT-Q10Q11.dsl)
SSDT-MEM2.aml | Add missing MEM2 Device to enhance performance like a real Mac | -
SSDT-PMCR.aml | Add missing PMCR Device to enhance performance like a real Mac | -
SSDT-PNLF.aml | Fix Backlight. For most users. | [Link](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/backlight.html)
SSDT-SBUS-MCHC.aml | Mainly handles the System Management Bus. | [Link](https://dortania.github.io/Getting-Started-With-ACPI/Universal/smbus.html)
SSDT-UIAC.aml | Block empty USB ports. Created using HackinTool. USBPorts.kext is also required. | [Link](https://www.tonymacx86.com/threads/the-new-beginners-guide-to-usb-port-configuration.286553/)
SSDT-XOSI.aml | This SSDT can be used instead of an OS Check Fix patch to simulate a version of Windows for Darwin. | [Link](https://dortania.github.io/Getting-Started-With-ACPI/ssdt-methods/ssdt-prebuilt.html#trackpad)
SSDT-PrtSc-F13.aml | PrtSc Screenshot | -

### TODO
 - USB mapping tutorial.
 - Suggest to me via issue.
  
### Credits
 - [Apple](https://www.apple.com) for macOS.
 - [Acidanthera](https://github.com/acidanthera) for most of the kexts.
 - [goodwin](https://github.com/goodwin) for ALCPlugFix.
 - [RehabMan](https://github.com/RehabMan) for some patches.
 - [Steve Zheng](https://github.com/stevezhengshiqi) for some patches.
 - [Sniki](https://github.com/Sniki) for some patches.
 - [daliansky](https://github.com/daliansky) for some patches.
 - [Moh_Ameen](https://github.com/ameenjuz) for some patches.
 - [OpenIntelWireless](https://github.com/OpenIntelWireless) for Intel WiFi drivers.
 - And anyone else that helped to develop and improve hackintoshing.


## Contributors ✨

Thanks goes to these wonderful people

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
