
## 1. Fix Random Wakeup
The first thing to do is to confirm the cause of the wakes by entering the following command 
```bash
log show --last 1d | grep "Wake reason"     # Which will list all wake events in the recent 1 day
log show --last boot --style syslog | fgrep "Wake reason"   # Which will list all wake events since the last boot and will look something like this

2023-05-21 00:16:34.987156-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 00:16:34.987157-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 01:26:57.514569-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 01:26:57.514569-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 03:15:22.147797-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 03:15:22.147798-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 03:20:20.339629-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 03:20:20.339748-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 05:08:44.818881-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 05:08:44.818882-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 06:29:39.309869-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 06:29:39.309871-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 08:18:04.615797-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 08:18:04.615798-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: RTC XDCI CNVW (Alarm)
2023-05-21 10:06:30.650085-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: XDCI CNVW
2023-05-21 10:06:30.650088-0700  localhost kernel[0]: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: XDCI CNVW
```
Wake reasons will be prefixed by one or more device id's (eg: XDCI, CNVW, PEGx, RP0x, RTC), followed by the type of wake reason in brackets `()`.


```bash
log show --last 1d | grep "Wake reason"

sudo pmset -a proximitywake 0
```


**Reference**
* [Mojave - Wake reason: RTC XDCI XHC (Alarm)](https://www.reddit.com/r/hackintosh/comments/9j3v1n/mojave_wake_reason_rtc_xdci_xhc_alarm/)
* [Cannot put Mac to sleep while wearing watch!](https://forums.macrumors.com/threads/cannot-put-mac-to-sleep-while-wearing-watch.2286017/)
* [[SOLVED] Ventura - Random (Scheduled PM) Wake from Sleep](https://www.tonymacx86.com/threads/solved-ventura-random-scheduled-pm-wake-from-sleep.323359/)