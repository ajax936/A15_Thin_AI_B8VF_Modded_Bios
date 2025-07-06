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

1. Format a USB drive to **FAT32**
2. Copy these files to the root of the USB:
   - `AfuEfix64.efi`
   - `E16RKAMS_PATCHED.30D`
   - (Optional) `Shellx64.efi` if booting directly to shell
3. Reboot your laptop
4. Enter BIOS → Disable Secure Boot
5. Set Boot Mode to **UEFI**
6. Boot to UEFI Shell (via Boot Menu or `Shellx64.efi`)
7. In UEFI Shell:
   - Type `fs0:` (or `fs1:`, `fs2:` depending on USB)
   - Then run:
     ```bash
     AfuEfix64.efi E16RKAMS_PATCHED.30D /P /B /N /X /K
     ```
8. Let the flashing process complete. It may auto-reboot.

> 🧠 **Tip:** If the system bricks or doesn't boot, try BIOS recovery below.

---

## 🧯 BIOS Recovery Method (MSI Tested)

1. Rename BIOS file to: `E16RKAMS.30D`  
2. Place on FAT32 USB (root directory)  
3. Unplug AC adapter  
4. Hold **CTRL + ESC**  
5. Plug in power while still holding keys  
6. Release keys after ~10 sec → system should auto-recover BIOS

---

## 🧰 Tools for BIOS Modding & Flashing

| Tool | Description | Download |
|------|-------------|----------|
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

