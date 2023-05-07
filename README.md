# Hackintosh

## AirDrop & Bluetooth
[OpenCore Install Guide#WiFi and Bluetooth](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#wifi-and-bluetooth)
我的电脑使用的是BCM94360CD，是免驱的无线网卡，所以并不需要BlueToolRixup,AirportBrcmFixup,BrcmPatchRAM这些kext。



## Set Privacy & Securicy
```
sudo spctl --master-disable
```