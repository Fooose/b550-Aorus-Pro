Welcome to the b550-Aorus-Pro wiki!<br><br>
**Update: 2022/10/14**

![B550 Aorus Pro](https://royjonesmusic.publicvm.com/opencore/B550.png)


* Motherboard: Gigabyte B550 Aorus Pro | rev. 1.0
* Bios: F15 (2022.07.20)
* Major vulnerabilities updates, customers are strongly encouraged to update to this release at the earliest. Credits to "Assaf Carlsbad and Itai Liba from * SentinelOne" • Introduce capsule BIOS support starting this version.
* CPU: Ryzen 7 3700x
* GPU: Sapphire RX5500 XT
* RAM: 32 GB 3200
* Festplatte: M2 1TB
* Audio Device: ALC 1220
* SMBIOS: ~~iMacPro 1.1~~ macPro7.1


Hello, everyone, I finally got my system (Ryzen3700x, B550AorusPro, RX5500XT) up and running - everything works, including (Sound,Bluetooth,CPU_Temp,etc). For all who are not so patient I provide my debug-EFI. Who still has tips and optimizations, can share them with me, especially regarding USB-mapping. So, now have fun!

Best regards Fooose

LAN-Fix-Realtek® 2.5GbE LAN : open Terminal: "sudo ifconfig en0 media 1000baseT mediaopt full-duplex"
Thanks DSM2!
~~Update to LucyRTL8125Ethernet.kext Vers.(1.1.0d8) -->lan fix~~ no longer required.

Bios: F15 Unfortunately, sleep does not work for me with all versions after F12.

Major settings to be changed based on the default optimal settings:

* ~~deactivate I2C and ESPI (essential to solve the random freeze problem) it must be in BIOS (advanced mode) under Settings -> AMD CBS -> FCH Common Options * NEW BiosVersion 14c~~ no longer necessary
* ~~if applicable, set PCIe slot to Gen4 instead of Auto (may contribute to a better stability) NEW BiosVersion 14c~~ no longer necessary
* enable X.M.P. memory profile
* disable trusted computing
* disable wake and boot over LAN
* enable power loading in Platform Power settings (may contribute to a better stability)
* setup fan profiles
* Other relevant default settings:
* Above 4G Decoding: ~~disabled~~ →enabled (bootoption: ncpi=2000 removed)
* Resizable BAR support disabled
* XHCI Hand-off: enabled
* HPET: enabled
* CSM support: ~~enabled~~ →disabled
* BIOS → Advanced Mode → Settings → Re-Size BAR Support, choose “Auto” (from version OC 0.7.5)
* ~~USB declared via DSDT by https://www.hackintosh-forum.de/user/34281-apfelnico/ (from version OC 0.7.5)~~ until OC 0.8.4
* USB via SSDT (SSDT-B550-PTXH-TO-XHC2, SSDT-B550-XHC0-TO-XHC) defines.(vers. OC 0.8.5)
