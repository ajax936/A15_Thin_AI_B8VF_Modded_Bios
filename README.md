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

This BIOS mod for the MSI Thin A15 AI B8VF includes extensive changes to unlock full system control and remove hardcoded restrictions:

### ✅ Features Unlocked / Protections Removed

- ✅ **All hidden menus and advanced BIOS settings unlocked**  
- ✅ **NVRAM lock disabled**  
- ✅ **fTPM / TPM state check bypassed**  
- ✅ **BIOS update restrictions removed**  
- ✅ **Rollback protection disabled**  
- ✅ **SMM (System Management Mode) write lock logic removed**  
- ✅ **Flash write protection bypassed**  
- ✅ **Trap logic removed** — prevents system lockout after modifying flagged settings  

---

## ⚠️ Known Issue

> ❌ Currently **cannot be flashed via USB FAT32** method with `E16RKAMS.30D` as the filename — the modded file is rejected due to:
- File size mismatch (removed modules)
- Possibly invalid or altered firmware header

🔧 **Plan:**  
Working to resolve this so it can be flashed with standard UEFI tools. For now, flashing via hardware SPI programmer or AFUEFI may be required.

---

## 📂 Files

- `E16RKAMS_PATCHED.30D` – Modded BIOS file (use with caution)
- `AfuEfix64.efi` – AMI Firmware Update UEFI tool (for advanced users)

---

## 🔓 BIOS Recovery Method (Tested Safe)

If your system doesn’t boot after a bad flash or invalid config:

1. **Unplug power adapter**
2. Hold **CTRL + ESC**
3. Plug power adapter in while holding keys
4. System will enter BIOS recovery (if BIOS is structured correctly)

---

## 🧪 For Advanced Users

Feel free to:
- Disassemble and analyze the `.30D` file
- Improve the header or module map to restore USB flashing support
- Provide feedback or contribute fixes via pull requests

---

## 💬 Disclaimer

> This BIOS mod is provided as-is with **no warranty**. Flashing modified firmware can **brick your device**.  
> You accept all risk when using this mod. Backup your original BIOS before flashing.

---

## 🧠 Credits

Modded and tested on:
> **System UUID:** `6CC9AAD6-4F4A-4394-8804-A857AE567F96`  
> **System Serial:** `K2408N0106176`  
> **Motherboard Serial:** `BSS-0123456789`

---

## ✍️ Author

**Robert Mitchell**  
BIOS modder, hardware tinkerer, and performance tweaker.  
Reach out or contribute if you’ve got BIOS expertise to share.

