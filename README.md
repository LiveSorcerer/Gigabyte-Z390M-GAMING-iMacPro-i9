# Gigabyte-Z390M-GAMING-iMacPro-i9
[OpenCore](https://github.com/acidanthera/OpenCorePkg) bootloader ONLY.

## Gigabyte Z390M GAMING hackintosh w/ OpenCore

Verified working with macOS version 11.0.1 (20B29) Big Sur and OpenCore 0.6.4.

![System](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/iMac.png?raw=true)

## Important!

**YOU MUST modify SN/UUID/MLB/ROM values in config.plist file. ROM value is the MAC address of your motherboard built-in network card, check it on BIOS settings.**
![SN/UUID/MLB](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/MLB.png?raw=true)


Included items 

Items | Last Version | 
------------ | ------------- | 
[BIOS](https://www.gigabyte.com/Motherboard/Z390-M-GAMING-rev-10/support#support-dl-bios) | F9l | 
[OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) | 0.6.4 |
[Lilu](https://github.com/acidanthera/Lilu/releases) | 1.5.0 | 
[AppleALC](https://github.com/acidanthera/AppleALC/releases) | 1.5.5 |
[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases) | 1.1.9 |
[WhateverGreen](https://github.com/acidanthera/whatevergreen/releases) | 1.4.5 |
[NVMeFix](https://github.com/acidanthera/NVMeFix/releases) | 1.0.4 |
[IntelMausi](https://github.com/acidanthera/IntelMausi/releases) | 1.0.4 |

**Important!**
**Highly recommended to try the lastest BIOS 'F9l' version.** 

## Overview
Installation procedure is quite straightforward, but requires experience with Hackintoshes. 
It can be simple and complicated at the same time, refer directly to this manual for a better experience.

## Hardware
Components | Recommended SKU | Comments
------------ | ------------- | -------------
**CPU** | Intel i9-9900K | 8th/9th-gen both fine (9900K/9700/8700/etc)
**Motherboard** | Gigabyte Z390M Gaming mATX | 
**WiFi Adapter 1** | BCM94360CD (4 antennas) | Bluetooth 4.0 (Including NGFF to PCI-e 1x Adapter)
**WiFi Adapter 2** | Intel AC 9560 (2 antennas) | Bluetooth 5.0 (NGFF CNVi Connector)
**Graphics Card** | Gigabyte Radeon™ RX VEGA 56 GAMING OC 8G | 
**Thunderbolt Card** | Gigabyte GC-TITAN RIDGE | Thunderbolt 3 Certified
**SSD** |  2x Samsung 970 Evo Plus 500GB | Dual Boot 500GB MacOS & 500GB Win 10 Pro
**HDD** | 5x Seagate IronWolf 4TB | 20TB Total
**RAM** | Corsair Vengeance LPX 64GB (4x16GB) DDR4 X.M.P | 3200MHz 
**PSU** | Corsair RM850x | 850W 80 Plus Gold 
**PC Case** | MacPro 3.1| Year 2008
**CPU Cooler** | Noctua NH-U12A| Low Noise
**Cooling Fan** | 3x Noctua NF-S12A PWM | 12cm
**Monitors** | LG 32"4K UK550 & 2 Dell UltraSharp U2419H | LG 32 including  Speaker & Dell USB hub
**Keyboard & Mouse** | Aigo V800 Keyboard & Logitech M720 Mouse | Keyboard MacOS/Windows layout

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


## Not Working / Issues
Please [report and track](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/issues)


## Kexts & Tools
* [Lilu](https://github.com/acidanthera/Lilu)
* [AppleALC](https://github.com/acidanthera/AppleALC)
* [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
* [WhateverGreen](https://github.com/acidanthera/WhateverGreen)
* [IntelMausi](https://github.com/acidanthera/IntelMausi)
* [NVMeFix](https://github.com/acidanthera/NVMeFix)
* [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all)
* [OpenCore Configurator](https://mackie100projects.altervista.org/category/opencore-configurator-changelog/)
* [Hackintool](https://github.com/headkaze/Hackintool)
* [PLIST Editor](https://apps.apple.com/us/app/plist-editor/id1157491961?mt=12)
* [Sanity Checker for config.plist](https://opencore.slowgeek.com)


## References
* [https://www.tonymacx86.com/threads/gigabyte-z390-m-gaming-build-with-working-nvram.291193/](https://www.tonymacx86.com/threads/gigabyte-z390-m-gaming-build-with-working-nvram.291193/)
* [https://dortania.github.io/OpenCore-Install-Guide/](https://dortania.github.io/OpenCore-Install-Guide/)
* [https://dortania.github.io/Getting-Started-With-ACPI/](https://dortania.github.io/Getting-Started-With-ACPI/)


## Geekbench 5 Scores
![CPU](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/CPU%20Bench.png?raw=true)
![OpenCL](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/OpenGL.png?raw=true)
![Metal](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/Metal.png?raw=true)


## System ScreenShots
![Display](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/Display.png?raw=true)
![RAM](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/Memory.png?raw=true)
![SSDSpeed](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/Speed.png?raw=true)
![RAWSpeed](https://github.com/LiveSorcerer/Gigabyte-Z390M-GAMING-iMacPro-i9/blob/main/screenshots/Speed%20raw.png?raw=true)

