# HP-EliteDesk-800-G2-DM-Hackintosh
This repository contains the files and scripts to install macOS on the HP EliteDesk 800 G2 Desktop Mini Business PC (35W/65W).

![HP EliteDesk 800 G2 Desktop Mini Business PC](https://ssl-product-images.www8-hp.com/digmedialib/prodimg/lowres/c04876268.png)

## Hardware Specs
### Basic info
Here is my EliteDesk 800 G2 DM specs:
- Product Number: XXX
- Product Name: HP EliteDesk 800 G2 DM 65W
- BIOS: XXX

### Specs:
- CPU: Intel® Core i5-6500 @ 3.20 GHz processor (65 W model only)
- GPU: Integrated Intel® HD Graphics 530 (2 DisplayPorts + 1 VGA Port)
- Memory: 2 x 8GB DDR4-2400
- Storage: Intenso NVMe drive 
- LAN: Intel® I219M Gigabit Network Connection LOM
- WLAN: Intel® Wi-Fi 6 AX200
- Audio: Realtec ALC221 Audio Codec (all ports are stereo, 1 internal speaker, 1 front headphone, 1 front headphone/mic combo)

## Configure BIOS Settings
To start, set BIOS to defaults.
Then insure:
- Advanced -> Boot Options
  - Disable **Fast Boot**
  - Disable **CD-ROM Boot**
  - Enable **USB Storage Boot**
  - Disable **Network (PXE) Boot**
  
- Advanced -> Secure Boot Configuration
  - Select **Legacy Support Enable and Secure Boot Disable**, press **F10** to save changes, system will reboot and lead you to Secure Boot and ask you to input a 4 digits security code for authorization, type in the code shows on the screen and enter to reboot and then press **F10** again to enter BIOS configuration

- Advanced -> System Options
  - Disable **Virtualization Technology (VTx)**
  - Disable **Virtualization Technology for Directed I/O (VTd)**
  - Enable **M.2 SSD** if you're using a NVME SSD
  - Check **M.2 WLAN/BT** as I am using BCM943224PCIEBT2 - May 11, 2021
  - Check **Allow PCIe/PCI SERR# Interrupt** (Uncheck it if have interruption issues)

#### Advanced -> Built-in Device Options
- Disable **Wake on LAN**
- Set Video memory size to **64MB** or larger
- Disable **LAN/WLAN Auto Switching**
- Disable **Wake on WLAN**

#### Advanced -> Port Options
- Enable **all** if no specific reasons.

#### Advanced -> Power Management Options
- Disable **Extended Idle Power States**

#### Advanced > Option ROM Launch Policy (Dual displays support)
- Configure Option ROM Launch Policy to **All UEI**


Press **F10** to save changes.

### Tested OS
- macOS Monterey 12.6.X

### Bootloader
- OpenCore 0.9.1

### Kexts
- AirportItlwm.kext
- AppleALC.kext
- BlueToolFixup.kext
- CPUFriend.kext
- FeatureUnlock.kext
- IntelBluetoothFirmware.kext
- IntelBTPatcher.kext
- IntelMausi.kext
- Lilu.kext
- RTCMemoryFixup.kext
- SMCProcessor.kext
- USBPorts.kext
- VirtualSMC.kext
- WhateverGreen.kext

### USB 3.0 Ports
**USB 2.0 Device**
- HS01: Back left up USB2
- HS02: Back left down USB2
- HS03: Front Left USB2
- HS04: Back right down USB2
- HS05: Back right up USB2
- HS13: Front right USB2

**USB 3.0 Device**
- SS01: Back left up USB3
- SS02: Back left down USB3
- SS03: Front left USB3
- SS04: Back right down USB3
- SS05: Back right up USB3
- SS08: Front right USB3

**Type-C**
- HS09: Front Type-C

**Bluetooth**
- HS07: Internal Bluetooth

## Known Issues:
- VGA port is not supported
- Front headphone/mic combo jack is not working

