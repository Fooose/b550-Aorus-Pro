Welcome to the b550-Aorus-Pro wiki!<br><br>
**Update: 2021/11/03**

![B550 Aorus Pro](https://royjonesmusic.publicvm.com/opencore/B550.png)


Motherboard: Gigabyte B550 Aorus Pro | rev. 1.0 <br>
Bios: F14c | 2021.09.06<br>
CPU: Ryzen 7 3700x<br>
GPU: Sapphire RX5500 XT<br>
RAM: 32 GB 3200<br>
Festplatte: M2 1TB<br>
Audio Device: ALC 1220<br>
macOS Version: 12.0.1 (20G165)<br>
SMBIOS: iMacPro 1.1 macPro7.1<br>
OpenCore Version: 0.7.5-Release<br><br>

Hello, everyone, I finally got my system (Ryzen3700x, B550AorusPro, RX5500XT) up and running - everything works, including (Sound,Bluetooth,CPU_Temp,etc). For all who are not so patient I provide my debug-EFI. Who still has tips and optimizations, can share them with me, especially regarding USB-mapping. So, now have fun!

Best regards Fooose
​

LAN-Fix-Realtek® 2.5GbE LAN : open Terminal: "sudo ifconfig en0 media 1000baseT mediaopt full-duplex"<br>
Thanks DSM2!<br>
Update to LucyRTL8125Ethernet.kext Vers.(1.1.0d8) -->lan fix no longer required.<br><br>



Bios:
[https://download.gigabyte.com/FileList/BIOS/mb_bios_b550-aorus-pro_f14e.zip?v=257ab98d48bfbaeffcbdf6857f430e24](Bios) | Unfortunately, sleep does not work for me with all versions after F12.<br><br>

Major settings to be changed based on the default optimal settings:<br><br>
* deactivate I2C and ESPI (essential to solve the random freeze problem) it must be in BIOS (advanced mode) under Settings -> AMD CBS -> FCH Common Options NEW BiosVersion 14c, no longer necessary
* if applicable, set PCIe slot to Gen4 instead of Auto (may contribute to a better stability) NEW BiosVersion 14c, no longer necessary
* enable X.M.P. memory profile
* disable trusted computing
* disable wake and boot over LAN
* enable power loading in Platform Power settings (may contribute to a better stability)
* setup fan profiles
* Other relevant default settings:
* Above 4G Decoding: disabled enabled (bootoption: ncpi=2000 removed)
* Resizable BAR support disabled
* XHCI Hand-off: enabled
* HPET: enabled
* CSM support: enabled disabled
* BIOS → Advanced Mode → Settings → Re-Size BAR Support, choose “Auto” (from version OC 0.7.5)
* USB declared via DSDT by [https://www.hackintosh-forum.de/user/34281-apfelnico/](apfelnico) (from version OC 0.7.5)
