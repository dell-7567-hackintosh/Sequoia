# Hackintosh OpenCore for Dell Inspiron 15 7567 — macOS Sequoia

<p align="center">
  <img src="https://dortania.github.io/OpenCore-Install-Guide/homepage.png" alt="OpenCore Logo" width="100" />
</p>

**Built using `OpCore-Simplify`** — <https://github.com/lzhoang2801/OpCore-Simplify>

---

## Overview

This repository provides a streamlined OpenCore EFI configuration to install **macOS Sequoia** on the **Dell Inspiron 15 7567 Gaming** laptop, using the **MacBookPro15,1** SMBIOS. It merges best practices from existing Hackintosh guides and leverages the `OpCore-Simplify` tool for easy customization.

### Key Details

- **Target Model:** Dell Inspiron 15 7567 Gaming
- **SMBIOS (System ID):** MacBookPro15,1
- **macOS Version:** Sequoia (macOS 15)

---

## Prerequisites

1. A working macOS machine or VM to prepare the USB installer.
2. A USB flash drive (≤32 GB) formatted as **FAT32**.
3. Latest OpenCore release from [Acidanthera/OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/releases).

---

## Creating the USB Installer

1. **Download macOS Sequoia:**

   ```bash
   py macrecovery.py -b Mac-937A206F2EE63C01 -m 00000000000000000 download
   ```

2. **Copy Recovery Boot:**
   - From the download folder, copy `com.apple.recovery.boot` to the root of your USB drive.
3. **Add OpenCore EFI:**
   - Copy your `EFI` folder into the USB root.
4. **Validate Structure:**
   Your USB should look like:

   ```
   /EFI
     └── OC
         ├── Bootstrap.efi
         ├── OpenCore.efi
         ├── config.plist
         └── drivers/ kexts/ tools/
   /com.apple.recovery.boot
   ```

---

## BIOS Setup

1. **Enter BIOS:** Power on and press `F12` repeatedly.
2. **Adjust Settings:**
   - Disable **Legacy Option ROMs**
   - Set **SATA Operation** to **AHCI**
   - Disable **Secure Boot**
   - Disable **Intel SGX**
3. **Boot Order:**
   - Under **General → Boot Sequence**, add `/EFI/OC/OpenCore.efi` on your USB.
   - Save & Exit.

---

## Installation Process

1. **Boot USB:** Press `F12` and select your OpenCore entry.
2. **Select Installer:** Choose **macOS Base System (External)**.
3. **Disk Utility:** Format your target drive to **APFS** with **GUID Partition Map**.
4. **Install:** Follow the prompts. Expect multiple reboots; total install time ~ 1.5–2 hours.

---

## Post‑Installation

1. **Mount System EFI:** Use `Clover Configurator` or `mountEFI.sh`.
2. **Copy EFI:** Copy the `EFI` folder from USB to your macOS system partition EFI.
3. **Eject USB & Reboot:** You should now boot natively.

---

## Post‑Install Fixes & Tweaks

- **USB Mapping:** <https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html>
- **Smooth Scrolling:** [MOS](https://mos.caldis.me/)
- **Audio Jack Fix:** [ComboJack](https://github.com/hackintosh-stuff/ComboJack)
- **Disable Verbose Boot:** Remove `-v` from `boot-args` and reset NVRAM
- **Hide Boot Picker:** Set `PickerAudioAssist` to `false` in `config.plist`

---

## Credits

- **OpCore‑Simplify** — lzhoang2801
- **Dortania OpenCore Guides** — dortania.io
- **Hackintosh Dell Inspiron 7567 EFI** — seathasky, mishailovic, maxis7567, charliekempf

---

*Enjoy your Hackintosh!*
