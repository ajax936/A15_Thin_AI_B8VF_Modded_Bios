# 🔧 MSI A15 Thin AI B8VF - Modded BIOS (E16RKAMS.30D)

## 📌 System Details

- **Model:** MSI A15 Thin AI B8VF  
- **BIOS Vendor:** American Megatrends International, LLC  
- **BIOS Version:** E16RKAMS.30D  
- **BIOS Date:** 2025-06-27  
- **Microcode Patch Level:** A705206  
- **EC Version:** 16RKIMS2.110  
- **Motherboard:** MS-16RK REV:1.0  
- **CPU:** AMD Ryzen 9 8945HS w/ Radeon 780M  
- **GPU:** NVIDIA RTX 4060 Laptop GPU  
- **RAM:** 64GB Corsair Vengeance DDR5 5600MHz  
- **Chassis Type:** Notebook  

---

## 🛠️ What’s Modded

This BIOS mod includes extensive changes to unlock full control and remove critical firmware protections.

### ✅ Features Unlocked / Protections Removed

- ✅ All hidden BIOS menus/options unlocked  
- ✅ NVRAM lock disabled  
- ✅ fTPM/TPM state check bypassed  
- ✅ BIOS update/rollback restrictions removed  
- ✅ Flash write protection bypassed  
- ✅ SMM write lock logic removed  
- ✅ Trap logic removed to prevent boot lockout from flagged settings  

---

## ⚠️ Known Issue

> ❌ **USB Flash Method not working currently**  
> Rejection due to:
- File size mismatch (removed modules)
- Possibly invalid BIOS header

### 🔄 Goal:
Restore USB flash support (`E16RKAMS.30D` via FAT32 USB) or use alternative flashing methods.

---

## 💾 Flashing via AFUEFI (Step-by-Step)

> This method uses AMI’s AFUEFI tool under UEFI Shell.  
> Recommended for **advanced users**.

### ✅ What You Need:
- `AfuEfix64.efi` (included)
- The modded BIOS file (e.g., `E16RKAMS_PATCHED.30D`)
- A USB stick formatted to **FAT32**
- Optional: `Shellx64.efi` if launching directly from boot

### 🔧 Steps:

**[RELEASE] MSI A15 Thin AI B8VF — Unlocked BIOS & Recovery Flash Kit**
!!!!!!!!!!!!! Backup everything first.!!!!!!!!!!!!!!!!!!!!

🔧 BIOS Base: E16RKAMS.30D

✅ MODIFICATIONS:
- ✅ All hidden BIOS menus/options unlocked  
- ✅ NVRAM lock disabled  
- ✅ fTPM/TPM state check bypassed  
- ✅ BIOS update/rollback restrictions removed  
- ✅ Flash write protection bypassed  
- ✅ SMM write lock logic removed  
- ✅ Trap logic removed to prevent boot lockout from flagged settings

📦 PACKAGE INCLUDES:
- `Patched BIOS (E16RKAMS.30D)`
- `AFUEFIx64.efi`
- `Shellx64.efi`
- `startup.nsh`
- `Flashable ISO`
- `Python automation tools to recompile with your own mods`

⚠️ **FLASHING INSTRUCTIONS:**
Due to flash protection, you must flash from BIOS built in recovery mode:

Use Rufus to Create USB ISO:

Open Rufus

Select:

Device: Target USB

Boot Selection: Flashable recovery ISO

Partition Scheme: GPT

Target System: UEFI (non-CSM)

Filesystem: FAT32

⚠️ Disable Runtime UEFI Media Validation

Click Start

Flashing Using Recovery Method

⚠️ MSI blocks normal flashing — you must use recovery mode.

Recovery Steps:

### Recovery Flash Instructions:
1. Write ISO to USB (use Rufus, FAT32, GPT, no UEFI validation)
2. Insert USB into USB drive and restart
3. Press DEL key whiel splash screen pops up to enter bios
4. Once you enter the bios go to the "Advanced" menu and press "Co-Piolit+Fn+Right Shift+Left Alt+F2" to enable the hidden bios menu
5. Enable Allow "Bios Downgrade" Option
6. Then go down to "AMD fTPM configuration and Disable that
7. Return to the "Advanced" menu and go down to "AMD CBS" from there go down to "NBIO common Options" go to PSPP Policy and Disable it
8. Now go down to "FCH Common Options" from there go down to "SPI Configuration Options"  and disable both "HID and HID2"
9. Return to "AMD CBS" menu and go down to "SOC Miscellaneous Control" now select "Customized" for "Microsoft Security Levels", select "disable" these following options "Secure-core Auto-enablement", "Trusted Platform Module", "Pluton Security Processor", "DRTM Support", "SMM Isolation Support".
10. Now go down to "Pluton Options" and select "Disable" for both options in that menu
11. Now go back one menu to "SOC Misc. Control" and go to "Firmware Anti-rollback (FAR) and select "Disable"
12. Now go back to the "SOC Misc. Control" menu and go to "Intrusion Detection menu and set to "0"
13. Go back one menu to "SOC Misc. Control" and go down to "ABL Console Out Control" and disable it
14. Go down to "PSP RSPM Switch" and also disable that
15. Now go to the right to the "Boot" menu and go to "Quiet boot" and disable it
16. Also go down and disable "Fastboot" 
17. Make sure "Boot mode select" is set to UEFI
18. Now go down to "Boot options" and select your USB Drive you flashed and select it from the menu
19. Now go to the right menu to "Security" go down to "Trusted computing" and disable it both times it appears on there
20. Now go down to "Secure boot" and disable it and set "Secure boot mode" to "Custom"
21. Now go to the "Save and exit" menu and select "Save changes and exit"
22. Now you should potentionally boot into the UEFI Shell
23. Flash should auto-initiate via `startup.nsh`
24. When you enter the UEFI Shell type the command "map -r" then locate which device ID is your USB. 
25. Type the device ID eX. "fs0:" this will select that drive
26. Now type the command "AFUEFIx64.efi E16RKAMS.30D /p /b /n /x /RECOVERY"
25. Now it will go through the native flashing method via Recovery and reboot. Now remove the IUSB and boot into windows



Use at your own risk — backup original and ensure recovery access.
UEFI Shell should launch and startup.nsh runs automatically

If auto-run fails, manually enter:

Try fs1: or fs2: if fs0: is not found.

💡 Tip: Use `map -r` in shell if paths don't map to `fs0:`

✅ Flash successful? You now have an unlocked BIOS!

1. Type map -r to locate your USB Flash Drive
2. Type fsX: (X=Your USB Flash Drive number)
3. Type AFUEFIx64.efi E16RKAMS.30D /p /b /n /x /RECOVERY
4. Wait for the bios to update, system will ask to confirm reboot and click "Y" and quickly remove the USB Flash drive

✅ Once done, enjoy your unlocked BIOS! Use responsibly. Backup everything first.

> 🧠 **Tip:** If the system bricks or doesn't boot, try BIOS recovery below.

💡 Manual fallback:
1. Power off laptop
2. Disconnect battery and charger
3. Hold the power button for 30 seconds
4. Hold `Ctrl + Esc`
5. While holding Ctrl+Esc Plug in AC

---

## 🧰 Tools for BIOS Modding & Flashing
| 
| Tool | Description | Download |
|------|-------------|----------|
[MSI ISO CREATOR](https://drive.google.com/file/d/1eIipSw4_YGn1haPM1PDGcZhvCDCkSsms/view?usp=drive_link) | ISO Creation Tool | ✓ |
| [AFUEFI](https://ami.com/en/download/) | AMI UEFI flash tool | _Included in repo_ |
| [AMI MMTool](https://www.majorgeeks.com/files/details/mmtool.html) | Insert/replace UEFI modules | ✓ |
| [UEFITool NE A59](https://github.com/LongSoft/UEFITool/releases) | Visual BIOS structure editor | ✓ |
| [IFR Extractor](https://github.com/dellkaze/IFR-Extractor) | Extract BIOS Setup strings | ✓ |
| [UEFIReplace](https://github.com/LongSoft/UEFIReplace) | Replace PE32/UEFI modules | ✓ |
| [Universal IFR Extractor](https://github.com/LongSoft/Universal-IFR-Extractor) | Decode setup options | ✓ |
| [AMI Change Logo Tool](https://www.majorgeeks.com/files/details/ami_change_logo_tool.html) | Modify boot logo | ✓ |

---

## ⚠️ Disclaimer

> This modded BIOS is experimental and provided **as-is**.  
> Flashing a modded BIOS carries the risk of **bricking your laptop**.  
> Always back up your current BIOS and understand recovery procedures.

---

## 🧠 System IDs (for reference)

- **System UUID:** `6CC9AAD6-4F4A-4394-8804-A857AE567F96`  
- **System Serial Number:** `K2408N0106176`  
- **Motherboard Serial:** `BSS-0123456789`  

---

## 🙌 Contributions Welcome

Have a fix for the file header, USB flash compatibility, or just want to explore?  
> 🛠️ **Fork the repo and submit a pull request!**

---

## ✍️ Author

**Robert Mitchell**  
BIOS modder | Firmware tinker | Hardware optimizer  
> Always pushing laptops beyond their limits.

