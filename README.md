# macOS Sequoia Hackintosh based on the [ASRock B760M-H/M.2](https://www.asrock.com/MB/Intel/B760M-HM.2/index.asp) motherboard, powered by [OpenCore 1.0.3](https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.3)
![Screenshot 2024-09-15 at 12 44 22 PM](https://github.com/user-attachments/assets/3f0038f0-7158-4dcd-8c8c-89109ea821f9)

Latest macOS version verified working: 15.3
## Do NOT use my EFI folder for your Hackintosh. Construct your own using the [Dortania guide](https://dortania.github.io/OpenCore-Install-Guide/) and [chriswayg's Alder/Raptor Lake guide](https://chriswayg.gitbook.io/opencore-visual-beginners-guide/advanced-topics/using-alder-lake) (if applicable). For AMD CPU-based systems, refer to [ChefKissInc's guide](https://chefkissinc.github.io/guide).

## Parts

**CPU:**
- Intel Core i5-12600KF (Alder Lake)

**CPU cooler:**
- Scythe Fuma 3

**Motherboard:**
- ASRock B760M-H/M.2 (BIOS 5.08)

**RAM:**
- 2x Crucial 16GB DDR5-4800 (CT16G48C40U5)

**Storage:**
- 1TB Samsung 870 Evo (macOS Sequoia)
- 500GB Samsung 870 Evo (Windows 11 Pro)

**GPU:**
- PowerColor Fighter Radeon RX 6600

**Case:**
- Cooler Master MasterBox Q300L

**Power supply:**
- MSI MAG A550BN

**Wireless card:**
- fenvi FV-T919 PCIe Network Adapter

## BIOS Settings

**Advanced > CPU Configuration:**
- Intel Hyper Threading Technology: Enabled
- Active Processor P-Cores: All
- Active Processor E-Cores: All
- CFG Lock: Disabled
- Intel Virtualization Technology: Enabled

**Advanced > Chipset Configuration:**
- Above 4G Decoding: Enabled
- C.A.M. (Clever Access Memory): Enabled
- VT-d: Enabled

**Advanced > Storage Configuration:**
- SATA Mode Selection: AHCI

**Advanced > USB Configuration:**
- XHCI Hand-off: Enabled

**Security:**
- Intel(R) Platform Trust Technology: Disabled

**Security > Secure Boot:**
- Secure Boot: Disabled

**Boot:**
- Fast Boot: Disabled

**Boot > CSM(Compatibility Support Module):**
- CSM: Disabled

## Observations

iMacPro1,1 SMBIOS yields far better performance than MacPro7,1. CPUFriend.kext was not used, as iMacPro1,1 handles power management on its own with no issues. Benchmark scores indicate that macOS performance is approximately 2% slower than Windows. Wi-Fi does not work out of the box, requires use of [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) to enable.

**Benchmark scores:**

Geekbench 6.3.0 (Windows):

![340338679-f03874fb-9f10-4530-b980-98696da06dbb](https://github.com/user-attachments/assets/cd822d93-642e-4722-8b25-054091a29589)

Geekbench 6.3.0 (macOS):

![340338849-3b3b98b5-0d85-4a88-a7ae-7f2ef2e52a91](https://github.com/user-attachments/assets/43167d6e-c4e4-4946-8e12-54dee0ba3f9b)

**What works:**
- Wi-Fi (with OCLP root patches)
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
- Continuity Camera
- iPhone Mirroring
- Enabling SIP
- OTA delta updates (full update packages work fine)

## Tools used

**Bootloader:**
- [OpenCore 1.0.3](https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.3)

**SSDTs (all generated with [SSDTTime](https://github.com/corpnewt/SSDTTime)):**
- SSDT-EC
- SSDT-HPET
- SSDT-PLUG-ALT
- SSDT-RTCAWAC
- SSDT-USBX

**Kexts:**
- [AMFIPass](https://github.com/dortania/OpenCore-Legacy-Patcher/tree/main/payloads/Kexts/Acidanthera)
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
