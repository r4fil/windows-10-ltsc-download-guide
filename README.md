# Windows 10 LTSC: Beginner’s Download & Setup Guide

A straightforward guide to picking the right version of **Windows 10 LTSC**, downloading genuine files, and setting up a clean, stable system without driver crashes.

---

## 📌 Which Version Should You Choose?

When downloading Windows 10 LTSC, you will see two main options. Picking the right one before installing is important for a smooth experience.

| Edition | Best For | Support Duration | Recommended? |
| :--- | :--- | :--- | :--- |
| **Windows 10 Enterprise LTSC** | Everyday PCs, Laptops & Gaming | 5 Years | **YES** *(Best choice for most users)* |
| **Windows 10 IoT Enterprise LTSC** | Kiosks, ATMs & Industrial Hardware | 10 Years | **NO** *(Do not clean install from ISO)* |

---

### ⚠️ Important Warning for Desktop & Laptop Users

> **Do not clean install directly from the IoT Enterprise LTSC ISO.**

* **The Problem:** The standalone IoT ISO is tailored for specialized embedded hardware. Installing it on regular PC hardware often leads to missing driver conflicts and unexpected **Blue Screen of Death (BSOD)** crashes within a few hours or days.
* **The Safe Way:** Always install the standard **Windows 10 Enterprise LTSC ISO** first.
* **Want 10 Years of Support?** Install standard Enterprise LTSC first. Once you reach the desktop, you can safely convert your edition to IoT Enterprise in seconds using the activation script—giving you the full 10-year support lifecycle without any driver instability.

---

## 1. Downloading the ISO File

You can get untouched, official Microsoft images directly from MassGrave:

* **GitHub Links Page:** [massgrave.dev/docs/windows_ltsc_links.md](https://github.com/massgravel/massgrave.dev/blob/main/docs/windows_ltsc_links.md)
* **Official Website:** [massgrave.dev](https://massgrave.dev)

**Steps:**
1. Open either link above.
2. Find and download **Windows 10 Enterprise LTSC 2021 (x64)** *(Standard, Non-IoT)*.

---

## 2. Creating a Bootable USB Drive

1. Plug an 8GB (or larger) USB flash drive into your computer. *(Make sure to back up any important files on it first, as this process erases the drive).*
2. Download and run **Rufus** (a free USB creation tool).
3. Select your flash drive at the top under **Device**.
4. Click **Select** and choose the Windows 10 LTSC ISO file you just downloaded.
5. Choose your **Partition scheme**:
   * Select **GPT** if your PC is modern (UEFI).
   * Select **MBR** if you are installing on an older computer.
6. Click **Start** and wait for it to finish.

---

## 3. Post-Installation Checklist (Prevent Crashes)

Once Windows is installed and you reach your desktop, complete these basic fixes to prevent potential system freezes or driver errors:

### Disable Fast Startup
Fast Startup forces Windows into a hybrid sleep mode that can mess up driver loading when turning your PC on:
1. Open **Control Panel** $\rightarrow$ **Power Options**.
2. Click **Choose what the power buttons do** on the left menu.
3. Click **Change settings that are currently unavailable**.
4. Uncheck **Turn on fast startup (recommended)** and click **Save changes**.

### Install Graphics & Motherboard Drivers
* Avoid relying on basic drivers installed automatically by Windows Update.
* Download and install the latest official drivers directly from your graphics maker (**Nvidia**, **AMD**, or **Intel**) and your motherboard manufacturer's support page.

---

## 4. Activation & Converting to IoT

To activate your system cleanly—or to convert your installation to the 10-year IoT support edition safely—use MassGrave (MAS):

1. Right-click the **Start Menu** icon and choose **PowerShell (Admin)** or **Terminal (Admin)**.
2. Paste this command and hit **Enter**:

```powershell
irm [https://get.activated.win](https://get.activated.win) | iex
