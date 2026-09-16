<p align="right">
  <a href="README_FA.md"> <strong>فارسی</strong></a>
</p>

---

# USB Immunizer & Customizer

A lightweight, automated Windows batch utility designed to immunize USB flash drives against automatic junk folder creation (such as `Android/`) and customize drive branding with a custom icon and volume label.

It keeps your USB storage clutter-free, stops smartphones and media devices from polluting your root directory, and makes your flash drive stand out with a professional appearance in Windows Explorer.

---

## 💡 How It Works (Folder Collision Immunity)

In standard filesystems (FAT32, exFAT, NTFS), a file and a folder **cannot share the exact same name** in the same directory.

When connecting a USB drive to an Android device (via OTG) or car multimedia system, the operating system attempts to automatically create directories like `Android/`. 

This tool creates a zero-byte **file** named `Android` marked with Hidden (`+h`) and System (`+s`) attributes. As a result, the OS is permanently blocked from generating unwanted folders in your root directory.

---

## 📁 Repository Contents

| File | Type | Description |
| :--- | :--- | :--- |
| **`Prevent Automatic Folder Creation on USB Drive.bat`** | Batch Script | Main script that creates immunity dummy files, writes `autorun.inf`, and applies hidden/system attributes. |
| **`.autorun.ico`** | Icon File | High-resolution custom flash drive icon applied to your USB drive. |

---

## ✨ Features

- **🛡️ Directory Immunity:** Blocks Android OS and external devices from creating root junk folders like `Android/`.
- **🎨 Custom Drive Branding:** Configures `autorun.inf` to display `.autorun.ico` and names the drive volume `Files` in Windows Explorer.
- **👻 Clean Root Directory:** Automatically applies Hidden and System attributes (`+h +s`) to:
  - `Android` (immunity dummy file)
  - `System Volume Information !` (immunity dummy file)
  - `autorun.inf` & `.autorun.ico`
  - `System Volume Information` & `.cm0013` (if already present)
- **🔑 Self-Elevating (UAC):** Automatically requests Administrator privileges via a temporary VBScript routine if not launched with elevated rights.
- **⚡ 100% Native & Portable:** Zero dependencies. Powered purely by Windows native utilities (`attrib`, `type`).

---

## 🚀 How to Use

1. Copy both **`Prevent Automatic Folder Creation on USB Drive.bat`** and **`.autorun.ico`** directly into the **root directory** of your USB flash drive (e.g., `E:\`).
2. **Double-click** the `.bat` file to execute.
3. Click **Yes** when prompted by the User Account Control (UAC) dialog.
4. The script will write the immunity files and apply the hidden/system flags.
5. **Safely remove and reconnect** your USB drive to see your custom drive icon and label in Windows Explorer.

---

## 💻 System Requirements

- **Operating System:** Windows 7, Windows 8.1, Windows 10, or Windows 11.
- **Filesystem:** FAT32, exFAT, or NTFS formatted USB drives.
