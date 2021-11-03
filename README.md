# b550-Aorus-Pro
Hackintosh  Bootloader OC-EFI

Hello, everyone, I finally got my system (Ryzen3700x, B550AorusPro, RX5500XT) up and running - everything works, including (Sound,Bluetooth,CPU_Temp,etc). For all who are not so patient I provide my debug-EFI. Who still has tips and optimizations, can share them with me, especially regarding USB-mapping. So, now have fun!

Update: 2021/10/05

Best regards Fooose
​

LAN-Fix-Realtek® 2.5GbE LAN : open Terminal: "sudo ifconfig en0 media 1000baseT mediaopt full-duplex"
Thanks DSM2!
Update to LucyRTL8125Ethernet.kext Vers.(1.1.0d8) -->lan fix no longer required.

I have taken these settings from this post: #1

Bios:
Version: F14c | 2021.09.06 | Unfortunately, sleep does not work for me with all versions after F12.
Major settings to be changed based on the default optimal settings:
deactivate I2C and ESPI (essential to solve the random freeze problem) it must be in BIOS (advanced mode) under Settings -> AMD CBS -> FCH Common Options NEW BiosVersion 14c, no longer necessary
if applicable, set PCIe slot to Gen4 instead of Auto (may contribute to a better stability) NEW BiosVersion 14c, no longer necessary
enable X.M.P. memory profile
disable trusted computing
disable wake and boot over LAN
enable power loading in Platform Power settings (may contribute to a better stability)
setup fan profiles
Other relevant default settings:
Above 4G Decoding: disabled enabled (bootoption: ncpi=2000 removed)
Resizable BAR support disabled
XHCI Hand-off: enabled
HPET: enabled
CSM support: enabled disabled
