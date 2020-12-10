# Gigabyte-Z390M-GAMING-iMacPro-i9
[OpenCore](https://github.com/acidanthera/OpenCorePkg) bootloader ONLY, Clover not supported (Let it go).

## Gigabyte Z390M GAMING hackintosh w/ OpenCore

Verified working with macOS version 11.0.1 (20B29) Big Sur and OpenCore 0.6.4.

![System](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/About-System.png?raw=true)

## Important! Important! Important!

**F9l BIOS from GIGABYTE resolves the Apple Watch unlock(SERIAL PORT disabled) issue and provides the CFG Unlock in the BIOS. CFG Unlock is required for this EFI to work properly. Be sure to upgrade F9l.**

**YOU MUST modify SN/UUID/MLB/ROM values in config.plist file. ROM value is the MAC address of your motherboard built-in network card, check it on BIOS settings.**
![SN/UUID/MLB](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/MLBUUIDSN.png?raw=true)

## Updates
2020-12-08 / Version 1.6.9
Upgrade to OpenCore 0.6.4 and others Kexts.(Lilu/AppleALC/WhateverGreen/etc)

2020-11-13 / Version 1.6.8
Big Sur 11.0.1 (20B29) Verified. Fixed booter issue 'Start Image Failed'.

2020-11-03 / Version 1.6.7
Upgrade to OpenCore 0.6.3 and others Kexts.(Lilu/AppleALC/WhateverGreen/etc)

[Changelog History](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/tree/master/Changelog.txt)

Included items table

Items | Last Version | Comments
------------ | ------------- | -------------
[BIOS](https://www.gigabyte.com/Motherboard/Z390-M-GAMING-rev-10/support#support-dl-bios) | F9l | Be sure to upgrade F9l
[OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) | 0.6.4 |
[Lilu](https://github.com/acidanthera/Lilu/releases) | 1.5.0 | 
[AppleALC](https://github.com/acidanthera/AppleALC/releases) | 1.5.5 |
[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases) | 1.1.9 |
[WhateverGreen](https://github.com/acidanthera/whatevergreen/releases) | 1.4.5 |
[NVMeFix](https://github.com/acidanthera/NVMeFix/releases) | 1.0.4 |
[IntelMausi](https://github.com/acidanthera/IntelMausi/releases) | 1.0.4 |

**Important! Important! Important**
**Highly recommended to try the lastest BIOS 'F9l' version. Download [BIOS](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/tree/master/BIOS/mb_bios_z390-m-gaming_f9l.zip) and flash it for CFG unlocked, SERIAL PORT disabled from BIOS settings.**

## Overview
Installation procedure is quite straightforward, but requires prior knowledge or experience with Hackintoshes. 
It can be simple and complicated at the same time, refer directly to this manual for a better experience.

## Hardware
Components | Recommended SKU | Comments
------------ | ------------- | -------------
**CPU** | Intel i9-9900K | 8th/9th-gen both fine (9900K/9700/8700/etc)
**Motherboard** | Gigabyte Z390M Gaming mATX | 
**WiFi Adapter** | BCM943602CDP (4 antennas) | Bluetooth 4.2 (Including NGFF to M.2 Adapter)
**Graphics Card** | Gigabyte Radeon™ RX VEGA 56 GAMING OC 8G
**Thunderbolt Card** | Gigabyte GC-TITAN RIDGE | Thunderbolt 3 Certified (Need hard-flash)
SSD |  2x Samsung 970 Evo Plus 500GB | 
HDD | 5x Seagate IronWolf 4TB | 
RAM | Corsair Vengeance LPX 64GB (4x16GB) DDR4 X.M.P | Recommend 3200MHz 
PSU | Corsair RM850x |
PC Case | Jonsbo RM2 ATX | Silver
CPU Cooler | Jonsbo TW2-240 | Version 601
SSD Cooler | CRYORIG Frostbit (M.2) | 
Cooling Fan | Noctua NF-F12 PWM | 12cm
Monitors | LED Cinema Display 24 & AOC U2790PQU IPS 4K | ACD 24 including Camera / Mic / Speaker / USB hub
Keyboard & Mouse | Magic Keyboard & Magic Mouse 2 & Magic Trackpad 2 | Prefer to wireless devices

**IMPORTANT: Core components (Motherboard / Graphics Card / WiFi Adapter) are CRUCIAL and you HAVE TO follow the instructions above.**

If you want a smooth experience using wireless functionalities such as AirDrop / AirPlay / Sidecar / Handoff / iMessage / Facetime / Contiuenity / etc, only a specific range of wifi adapters are recommended: **BCM94360CD/BCM943602CDP/BCM943602CS**

## BIOS Settings

Based on F9l version.

#### First setup,

* Save & Exit
	- Load Optimized Defaults, Save & Exit Setup reboot it.

#### Second setup,

* Tweaker
	- Advanced CPU Settings
		- VT-d → **Disabled**
		- Intel(R) Speed Shift Technology → **Enabled**
		- Energy Efficient Turbo  → **Enabled**
		- Intel(R) Turbo Boost Technology → **Enabled**
		- C-States Control
			- CPU Enhanced Halt(C1E) → **Enabled**
			- C3 State Support → **Enabled**
			- C6/C7 State Support → **Enabled**
			- C8 State Support → **Enabled**
			- C10 State Support → **Enabled**
			- Package C State limit → **Auto**
	- Extreme Memory Profile(X.M.P.) → **Profile 1**
	- Advanced Memory Settings
		- Memory Boot Mode → **Enable Fast Boot**
		- Memory Enhancement Settings → **Enhanced Performance**
* Settings
	- Platform Power
		- Platform Power Management → **Disabled**
		- AC Back → **Always On**
		- ErP → **Disabled**
		- Soft-Off by PWR-BTTN → **Delay 4 Sec.**
		- Power Loading → **Enabled**
		- RC6(Render Standby) → **Enabled**
	- IO Ports
		- Initial Display Output → **PCIe 1 Slot**
		- Internal Graphics → **Enabled**
		- DVMT Pre-Allocated → **64M**
		- DVMT Total-Gfx Mem → **MAX** (Need reboot)
		- Aperture Size → **256M**
		- Audio Controller → **Enabled**
    	- Above 4G Decoding → **Enabled**
    	- Super IO Configuration (F9l BIOS only)
    		- Serial Port → **Disabled**
    	- USB Configuration
    		- XHCI Hand-off → **Enabled**
    		- Legacy USB Support → **Enabled**
    		- USB Mass Storage Driver Support → **Enabled**
    		- Port 60/64 Emulation → **Disabled**
    	- Network Stack Configuration
    		- Network Stack → **Disabled**
	- Miscellaneous
		- Intel Platform Trust Technology(PTT) → **Disabled**
		- Software Guard Extensions(SGX) → **Disabled**
* System Info.
	- System Language → **English**
* Boot
	- CFG Lock → **Disabled** (F9l BIOS only)
	- Full Screen LOGO Show → **Disabled**
	- Fast Boot → **Enabled**
		- PS2 Devices Support → **Disabled**
		- Next Boot After AC Power Loss → **Fast Boot**
	- Windows 8/10 Features → **Other OS**
	- CSM Support → **Disable**
	- Secure Boot → **Disable** (Secure Boot will be disabled by default, but good to check)

#### For Thunderbolt Card GC-TITAN RIDGE

* Thunderbolt(TM) Configuration
	- Discrete Thunderbolt(TM) Support → **Enabled**
	- TBT Vt-d base security → **Disabled**
   - Thunderbolt Boot Support → **Boot once**
   - Wake From Thunderbolt(TM) Devices → **Enabled**
   - Security Level → **No Security**
   - Discrete Thunderbolt(TM) Configuration
       - Thunderbolt Usb Support → **Enabled**
       - GPIO3 Force Pwr → **Enabled**


## Tips
* How to hard-flash GC-TITAN RIDGE BIOS with SSDT patched? Ref here [Post 1](https://www.tonymacx86.com/threads/success-gigabyte-designare-z390-thunderbolt-3-i7-9700k-amd-rx-580.267551/page-1640#post-2087524) [Post 2](https://www.tonymacx86.com/threads/success-gigabyte-designare-z390-thunderbolt-3-i7-9700k-amd-rx-580.267551/page-1624#post-2086862) [Post 3](https://github.com/ameyrupji/thunderbolt-macpro-5-1/blob/master/GC-TitanRidge.md) [Post 4](https://github.com/ameyrupji/thunderbolt-macpro-5-1/blob/master/GC-TitanRidge-CustomFirmware.md)
* How to force RGB mode for displays? Ref [here](https://forums.macrumors.com/threads/big-sur-force-rgb-mode-for-displays.2268099/)


## Not Working / Issues
Please [report and track](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/issues)

## Known Issues
* Big Sur seems to break the support for Apple TV+ DRM. [Ref](https://github.com/acidanthera/bugtracker/issues/1034)
* Multiple key press to wake from sleep with bluetooth (known issue with Gigabyte Gaming X or M boards)

## Kexts & Tools
* [Lilu](https://github.com/acidanthera/Lilu)
* [AppleALC](https://github.com/acidanthera/AppleALC)
* [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
* [WhateverGreen](https://github.com/acidanthera/WhateverGreen)
* [IntelMausi](https://github.com/acidanthera/IntelMausi)
* [NVMeFix](https://github.com/acidanthera/NVMeFix)
* [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all)
* [OpenCore Configurator](https://mackie100projects.altervista.org/category/opencore-configurator-changelog/)
* [OcBinaryData](https://github.com/acidanthera/OcBinaryData)
* [Hackintool](https://github.com/headkaze/Hackintool)
* [PLIST Editor](https://apps.apple.com/us/app/plist-editor/id1157491961?mt=12)
* [Sanity Checker for config.plist](https://opencore.slowgeek.com)
* [FreeDOS](http://www.freedos.org/download/)


## References
* [https://www.tonymacx86.com/threads/gigabyte-z390-m-gaming-build-with-working-nvram.291193/](https://www.tonymacx86.com/threads/gigabyte-z390-m-gaming-build-with-working-nvram.291193/)
* [https://dortania.github.io/OpenCore-Install-Guide/](https://dortania.github.io/OpenCore-Install-Guide/)
* [https://dortania.github.io/Getting-Started-With-ACPI/](https://dortania.github.io/Getting-Started-With-ACPI/)


## Geekbench 5 Scores
![CPU](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/CPUbench.png?raw=true)
![OpenCL](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/OpenCLbanche.png?raw=true)
![CPU](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/Metalebench.png?raw=true)


## System ScreenShots
![Display](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/Display.png?raw=true)
![RAM](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/RAM.png?raw=true)
![H264H265](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/H264H265.png?raw=true)
![Watch](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/watchunlock.png?raw=true)
![SSDSpeed](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/SSDSpeed.png?raw=true)
![RAWSpeed](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/RAWSpeed.png?raw=true)
![IntelPower](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/intelpower.png?raw=true)
![TB3](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/tb3.png?raw=true)
![TB3PCI](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/tb3pci.png?raw=true)
![SSD](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/SSD.png?raw=true)
![USB](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/USB.png?raw=true)
![RAMSlots](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/RAMSlots.png?raw=true)
![VideoCard](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/VideoCard.png?raw=true)
![Power](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/power.png?raw=true)
![Audio](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/audio.png?raw=true)
![Bluetooth](https://github.com/BenjaminX/Hackintosh-Gigabyte-Z390M-GAMING/blob/master/Tips/bluetooth.png?raw=true)
