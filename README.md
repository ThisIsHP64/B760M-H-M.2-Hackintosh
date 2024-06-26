# 14.5 Hackintosh based on the [ASRock B760M-H/M.2](https://www.asrock.com/MB/Intel/B760M-HM.2/index.asp) motherboard, powered by [OpenCore 1.0.0](https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.0)
![Screenshot 2024-06-17 at 9 13 46 AM](https://github.com/ThisIsHP64/B760M-H-M.2-Hackintosh/assets/115088986/990a2032-8ebb-4e56-9d47-84275ffbac5d)
## Do NOT use my EFI folder for your Hackintosh. Construct your own using the [Dortania guide](https://dortania.github.io/OpenCore-Install-Guide/) and [chriswayg's Alder/Raptor Lake guide](https://chriswayg.gitbook.io/opencore-visual-beginners-guide/advanced-topics/using-alder-lake) (if applicable). For AMD CPU-based systems, refer to [ChefKissInc's guide](https://chefkissinc.github.io/guide).

## Parts

**CPU:**
- Intel Core i5-12600KF

**CPU cooler:**
- Scythe Fuma 3

**Motherboard:**
- ASRock B760M-H/M.2

**RAM:**
- 2x Crucial 16GB DDR5-4800 (CT16G48C40U5)

**Storage:**
- 512GB TEAMGROUP T-Force Vulcan Z SATA III SSD (macOS Sonoma 14.5)
- 240GB Kingston A400 SATA III SSD (Windows 11 Pro)

**GPU:**
- PowerColor Fighter Radeon RX 6600

**Case:**
- Cooler Master MasterBox Q300L

**Power supply:**
- MSI MAG A550BN

**Wireless card:**
- fenvi FV-T919 PCIe Network Adapter

## Observations

iMacPro1,1 SMBIOS yields far better performance than MacPro7,1. CPUFriend.kext was not used, as iMacPro1,1 handles power management on its own with no issues. Benchmark scores indicate that macOS performance is approximately 2% slower than Windows.

**Benchmark scores:**

Geekbench 6.3.0 (Windows):

![Screenshot 2024-06-16 at 5 27 28 PM](https://github.com/ThisIsHP64/B760M-H-M.2-Hackintosh/assets/115088986/f03874fb-9f10-4530-b980-98696da06dbb)

Geekbench 6.3.0 (macOS):

![Screenshot 2024-06-16 at 5 27 55 PM](https://github.com/ThisIsHP64/B760M-H-M.2-Hackintosh/assets/115088986/3b3b98b5-0d85-4a88-a7ae-7f2ef2e52a91)

Cinebench 2024 (macOS):

![Screenshot 2024-06-16 at 5 22 59 PM](https://github.com/ThisIsHP64/B760M-H-M.2-Hackintosh/assets/115088986/bac5ca36-1cf3-4ff2-b6c8-31a5d58b4f39)

**What works:**
- Wi-Fi
- Bluetooth
- AirDrop
- Handoff
- Universal Control
- AirPlay to Mac
- All iServices (iMessage, iCloud, FaceTime, etc.)
- Sleep (including wake from USB)
- Audio
- CPU power management
- All USB ports
- GPU hardware acceleration
- DRM content
- Hypervisor software

**What DOESN'T work:**
- Enabling SIP
- Apps that require SIP enabled (Adobe CC, Dropbox, etc.)
- OTA delta updates (full update packages work fine)

## Tools used

**Bootloader:**
- [OpenCore 1.0.0](https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.0)

**SSDTs (all generated with [SSDTTime](https://github.com/corpnewt/SSDTTime)):**
- SSDT-EC
- SSDT-HPET
- SSDT-PLUG-ALT
- SSDT-RTCAWAC
- SSDT-USBX

**Kexts:**
- [AMFIPass](https://github.com/dortania/OpenCore-Legacy-Patcher/blob/main/payloads/Kexts/Acidanthera/AMFIPass-v1.4.0-RELEASE.zip)
- [AppleALC](https://github.com/acidanthera/AppleALC)
- [CpuTopologyRebuild](https://github.com/b00t0x/CpuTopologyRebuild)
- [IO80211FamlyLegacy and IOSkywalkFamily](https://github.com/dortania/OpenCore-Legacy-Patcher/tree/main/payloads/Kexts/Wifi)
- [Lilu](https://github.com/acidanthera/Lilu)
- [RealtekRTL8111](https://github.com/Mieze/RTL8111_driver_for_OS_X)
- [RestrictEvents](https://github.com/acidanthera/RestrictEvents)
- [SMCProcessor, SMCSuperIO, and VirtualSMC](https://github.com/acidanthera/VirtualSMC)
- [SMCRadeonSensors](https://github.com/ChefKissInc/SMCRadeonSensors)
- [USBToolBox](https://github.com/USBToolBox/kext) and [UTBMap](https://github.com/USBToolBox/tool)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen)

Feel free to message me on Discord @gdhp if you have any questions.
