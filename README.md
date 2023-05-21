# Hackintosh

## AirDrop & Bluetooth
[OpenCore Install Guide#WiFi and Bluetooth](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#wifi-and-bluetooth)
我的电脑使用的是BCM94360CD，是免驱的无线网卡，所以并不需要BlueToolRixup,AirportBrcmFixup,BrcmPatchRAM这些kext。



## Set Privacy & Securicy
```
sudo spctl --master-disable
```

## Fix Sleeping
[OpenCore Post-Install#Fixing Sleep](https://dortania.github.io/OpenCore-Post-Install/universal/sleep.html#preparations)
```
sudo pmset autopoweroff 0
sudo pmset powernap 0
sudo pmset standby 0
sudo pmset proximitywake 0
sudo pmset tcpkeepalive 0
```

## Multiboot with OpenCore
Multibooting is greatly affected by the type of firmware you're running. 
* UEFI
  * One disk for all OSes
  * Different disks for different OSes
* Legacy/CSM/BIOS


