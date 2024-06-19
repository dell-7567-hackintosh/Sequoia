# Use this if you know what you're doing!
- [SMBIOS](https://github.com/corpnewt/GenSMBIOS) Model: `MacBookPro15,1`
- [USBToolBox](https://github.com/USBToolBox/tool): `MacBookPro15,1`

# Notes:
- Connect your external mouse before booting into the USB
- Boot time before install: 20m
- Install time: 1h 40m (depends on your internet & disk speed)
- Boot time after install: 5m

# Issues:
- Bluetooth Enabled but does not work
- Display brightness buttons do not work
- Sleep / Hibernate does not work properly

# To Do: (help required, ignore this)

Compare config-original.plist and config-alternative.plist on [diffchecker](https://www.diffchecker.com/text-compare/) and combine them using the best options!
Please refer with [dortania-configuration](https://dortania.github.io/docs/latest/Configuration.html)

## I have done this partially, placed it at EFI/OC/config.plist here's what I need help with:
- Why is `DisplayLevel` set to `2147483650`, should I change that to `0`?
- `Target` under `SysReport` is `0`, what about `67`?
- I'm assuming `SpoofVendor` is supposed to stay at `false`
- `AudioSupport` is `false`
- `InitialMode` was empty, I set it to `Auto`
- Should I enable `AppleAudio`?
- `AppleCpuPmCfgLock` is set to `false`
- Changed `LauncherOption` to `Full`