# Dell Latitude 5480 Hackintosh EFI - macOS 11 and 12
**Introducing my new hack: Dell Latitude 5480 running macOS!**

**Can be used for the Dell Latitude 5280/5580 and the Dell Precision 3520 as well (w/ some modifications)**

OpenCore bootloader for stability.

**NOTE:**
* Please [**disable your CFG Lock**](/Disable_CFG_Lock.md) and [**Adjust your DVMT**](/Adjusting_DVMT.md).
* The EFI was designed to boot Monterey, to boot Big Sur you will need to make some changes with your kext folder as described in the release's description since 1.2.

![screenshot with neofetch](https://user-images.githubusercontent.com/73286927/134603078-0e84dd30-b772-41c0-83b8-c9c946951edd.png)
**Running fine on macOS Big Sur. Monterey should work, but you'll need to update your Wi-Fi kext.**

![Dual Display - VGA](https://user-images.githubusercontent.com/73286927/134603760-0973d4ed-5a09-480b-8e1b-0e6785ccb6e9.jpg)
**Dual Display with VGA port** (somehow it worked)

![Dual Display - USB-C](https://user-images.githubusercontent.com/73286927/134603810-fbbc3409-e3d5-409d-a0c5-0a340c62ee3f.jpg)
**Dual Display with USB-C hub** (HDMI also works and it outputs the same image)

## Laptop Specs!
![image1.png](https://cdn.discordapp.com/attachments/839427463334461490/891240486684209152/image1.jpg)

**Model: Dell Latitude 5480**
- **CPU:** Intel® Core™ i5-7200U
- **GPU:** Intel® HD Graphics 620
- **RAM:** 8GB/16GB DDR4 2133MHz
- **Ethernet:** Intel® Ethernet I219-LM
- **Wi-Fi:** Intel® Dual Band Wireless-AC 8265
- **Sound Card:** ALC256 (layout-id `69` with [**ALC256.kext**](https://github.com/ic005k/ALC256))
- **Trackpad:** AlpsAlpine U1 Dual I2C Touchpad (`0x120b`)
- **SD Card Reader:** Realtek RTS525A
- **Internal Display:** 1920x1080 Full HD Screen
- **Runs Big Sur with Monterey perfectly 👌**

## ✅ Whats workin'
* Graphics acceleration (Intel® HD Graphics 620)
* Dual Display with VGA, USB-C and HDMI ports.
* All USB ports (3x USB 3.0, 1x USB-C)
* Ethernet
* Audio (using [**ALC256.kext with `layout-id` set to `69`**](https://github.com/ic005k/ALC256))
* SD Card slot (using [**RealtekCardReader**](https://github.com/0xFireWolf/RealtekCardReader) and [**RealtekCardReaderFriend**](https://github.com/0xFireWolf/RealtekCardReaderFriend/))
* Sleep & Wake with Lid (now works with USB mapping and [**GPRW and UPRW Instant Wake Patch**](https://dortania.github.io/OpenCore-Post-Install/usb/misc/instant-wake.html))
* CPU Power Management
* iServices (using **this guide: https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html**)
* SMBUS
* Microphone
* Multi gestures touchpad (thanks to [**Juico's AlpsT4USB**](https://github.com/juico/AlpsT4USB)!)
* Front Camera
* Boot Chime
## ❌ Not workin'
* DRM (not possible on iGPU-only hacks)
* Handoff, AirDrop and Apple Watch Unlock (until you use a Broadcom Wi-Fi card)
* **You tell me**
## Credits
* [Apple](https://apple.com) for [**macOS**](https://apple.com/macos)
* [acidanthera](https://github.com/acidanthera) for [**OpenCore**](https://github.com/acidanthera/OpenCorePkg), [**Lilu**](https://github.com/acidanthera/Lilu), [**WhateverGreen**](https://github.com/acidanthera/WhateverGreen) and [**AppleALC**](https://github.com/acidanthera/AppleALC)
* [Dortania](https://dortania.github.io) for [**OpenCore Install Guide**](https://dortania.github.io/OpenCore-Install-Guide)
* [RehabMan](https://github.com/RehabMan) for [**USBInjectAll**](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) (without this kext i will not be able to map USB)
* [headkaze](https://github.com/headkaze) for [**Hackintool**](https://github.com/headkaze/Hackintool)
* [cholonam](https://github.com/cholonam), [syscl](https://github.com/syscl) and [sinetek](https://github.com/sinetek) for [**Sinetek-rtsx**](https://github.com/cholonam/Sinetek-rtsx) (thanks for bringing my SD Card reader back to life)
* [0xFireWolf](https://github.com/0xFireWolf) for [**RealtekCardReader**](https://github.com/0xFireWolf/RealtekCardReader) and [**RealtekCardReaderFriend**](https://github.com/0xFireWolf/RealtekCardReaderFriend/) (basically a better version of [**Sinetek-rtsx**](https://github.com/cholonam/Sinetek-rtsx))
* And special thanks to [**Văn Hùng Nguyễn**](https://github.com/vanhung4499) (vanhung4499) for helping me with the touchpad fix (the hardest part)
