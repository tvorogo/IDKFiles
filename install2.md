# Installation Guide 
> [!Warning]
> This guide covers flashing ROMs using **Auto Installer by [°⊥⋊ɹ∀°**](http://t.me/ArKT_7). Improper use may **permanently brick your device**. Follow each step carefully and do not skip any instructions.

---

## Pre-installation

Before attempting to flash your device, it is **critical** to prepare carefully:

1. [**Download the ROM ZIP**](https://github.com/hxfuxyy/infota/releases) file and any support scripts from a trusted source.  
   - Make sure the files are **not corrupted**. A corrupted ZIP can cause irreversible damage.
2. **Decide your installation method**:  
   > **PC-based Fastboot installation** (automated via scripts)  
   > **Recovery flash** (directly via TWRP/PBRP on the device)
3. **Ensure device battery** is above 50% to prevent shutdown during flashing.  
   - Unexpected shutdowns during flashing can brick your device.
---
> [!Tip]
> If you are unsure about your installation method, **Recovery flash is usually safer** for first-time users. Fastboot scripts are faster but require careful attention to PC connectivity and script execution.
> First-time installation requires a clean install, which will **delete all user data**.  
 Use cloud backup, PC transfer, or an external SD card to save important files.
---





## Flash via Recovery(noPC Installation)

<details>
    <summary> TWRP </summary>
   
> This method is often safer for first-time users. Recovery handles encryption, formatting, and optional root automatically.

- Boot into [TWRP](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win) recovery.
```
Fastboot boot path/to/twrp.img
```

- Flash the ZIP file:

> Tap Install, select the downloaded ROM ZIP, and swipe to confirm.

+ After installation:

> Recovery may ask if you want to reboot back into it for additional packages.
- Select “No” and tap Reboot to system.

</details>


# Flash via Fastboot (PC Installation)

<details>
    <summary> Windows </summary>

> Only use this method if you are familiar with connecting your tablet to a computer and running scripts. Using Fastboot incorrectly can erase essential system partitions.

1. **Extract** the ROM `.zip` file to a location you can easily access.  
   - Avoid paths with spaces or special characters to prevent script errors.
2. Connect your tablet in **Fastboot mode**:  
```
adb -d reboot bootloader
```
> Or power off the device and hold Volume Down + Power until the bootloader screen appears.

- Verify the device is detected by the computer:

```
fastboot devices
```

> If the device does not appear, check USB connection, try another cable, or install proper drivers.


- Run the Auto Installer scripts provided in the ZIP:

> install_..._windows.bat for first-time installation


>Update_..._windows.bat for update existing ROM

- Follow the on-screen instructions carefully.

> Scripts will automate partition flashing, installation of system files, and optional root setup.

# Do not disconnect your tablet during script execution. Interruption can leave your device unbootable.

</details>

<details>
    <summary> Linux / macOS </summary>
   
> Only use this method if you are familiar with connecting your tablet to a computer and running scripts. Using Fastboot incorrectly can erase essential system partitions.

1. **Extract** the ROM `.zip` file to a location you can easily access.  
   - Avoid paths with spaces or special characters to prevent script errors.
2. Connect your tablet in **Fastboot mode**:  
```
adb -d reboot bootloader
```
> Or power off the device and hold Volume Down + Power until the bootloader screen appears.

- Verify the device is detected by the computer:

```
fastboot devices
```

> If the device does not appear, check USB connection, try another cable, or install proper drivers.

- Open terminal in the folder where you extracted the ZIP and run:
```
sudo bash ./install_..._linux.sh    # first-time installation
```
```
sudo bash ./update_..._linux.sh     # update existing ROM
```

> Scripts require root privileges (sudo) to access USB devices.

- Pay attention to the terminal output. Scripts may prompt for confirmation before wiping partitions.

# Keep your terminal open and monitor progress. Closing the terminal early can interrupt flashing.
</details>


# First boot may take longer than usual. Do not panic if it takes 5–10 minutes.

## Update Installation


> For updating an existing installation, factory reset is not required.

- Via OTA: Use the in-built Updater (Settings > System > Update).

- Via Recovery: Follow Step 2 without performing Factory Reset.


# Always double-check that the ZIP or update file matches your current ROM version. Installing an incompatible version may cause boot loops or permanent damage.

> Maded by [tvorogo](github.com/tvorogo) for [hxfuxyy](https://github.com/hxfuxyy/)
