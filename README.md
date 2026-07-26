# Windows 10 LTSC: Complete Beginner’s Download & Setup Guide

A simple, straightforward guide to help you choose the right version of **Windows 10 LTSC**, download genuine installation files, and set it up on your PC without driver issues or system crashes.

---

## Which Version Is Right for You?

When downloading Windows 10 LTSC, you will see two main editions listed. Choosing the right one before you install is very important for system stability.

| Edition | Who It’s For | Support Lifecycle | Recommended? |
| :--- | :--- | :--- | :--- |
| **Windows 10 Enterprise LTSC** | Standard Desktop PCs, Laptops & Gaming | 5 Years | **YES (Best Choice)** |
| **Windows 10 IoT Enterprise LTSC** | ATM Machines, Kiosks & Factory Hardware | 10 Years | **NO (Avoid Clean ISO Install)** |

---

### ⚠️ Important Notice for PC & Laptop Users

> **Do NOT perform a clean installation using the IoT Enterprise LTSC ISO.**

* **Why?** The raw IoT ISO is intended for specialized embedded hardware (like digital kiosks and ATMs). Installing it directly on normal desktop PCs or laptops frequently leads to missing driver conflicts and random **Blue Screen of Death (BSOD)** crashes within a few hours or days.
* **The Easy Solution:** Always download and install the standard **Windows 10 Enterprise LTSC ISO** first. 
* **Want 10 Years of Support?** If you want the longer 10-year support lifecycle that IoT offers, simply install standard Enterprise LTSC. Once you reach your desktop, you can convert your system to IoT Enterprise in seconds using the activation script safely—without any driver issues!

---

## 1. How to Download the ISO

Official, untouched Microsoft Windows installation files can be found directly on MassGrave’s open-source repository:

* **GitHub Source Page:** [massgrave.dev/docs/windows_ltsc_links.md](https://github.com/massgravel/massgrave.dev/blob/main/docs/windows_ltsc_links.md)
* **Web Mirror:** [massgrave.dev/docs/windows_ltsc_links.md](https://massgrave.dev/docs/windows_ltsc_links.md)

1. Open either link above.
2. Look for **Windows 10 Enterprise LTSC 2021 (x64)** *(Standard, Non-IoT)* and download the ISO file.

---

## 2. How to Create a Bootable USB Drive

1. Insert a USB flash drive (8GB or larger) into your PC. *(Note: This will erase everything on the USB drive, so backup any important files on it first).*
2. Download and open **Rufus** (a free bootable USB creation tool).
3. Select your USB drive at the top under **Device**.
4. Click **Select** and choose the Windows 10 LTSC ISO file you just downloaded.
5. Set the **Partition scheme**:
   * Choose **GPT** if your PC is relatively modern (UEFI).
   * Choose **MBR** if you are installing on an older legacy PC.
6. Click **Start** and wait for the flashing process to complete.

---

## 3. Recommended Post-Install Fixes

After installing Windows and reaching your new desktop, complete these basic setup steps to prevent system crashes (`DRIVER_POWER_STATE_FAILURE` or `WHEA_UNCORRECTABLE_ERROR`):

### A. Turn Off Fast Startup
Fast Startup can cause hardware drivers to load improperly on cold boots:
1. Open **Control Panel** $\rightarrow$ **Power Options**.
2. Click **Choose what the power buttons do** on the left menu.
3. Click **Change settings that are currently unavailable**.
4. Uncheck **Turn on fast startup (recommended)** and click **Save changes**.

### B. Install Your Official Hardware Drivers
* Avoid relying solely on generic display or motherboard drivers provided by Windows Update.
* Manually download and install the latest official drivers directly from your graphics vendor (**AMD**, **Nvidia**, or **Intel**) and your motherboard manufacturer.

---

## 4. Activation & Safe IoT Conversion

To activate your system or upgrade your standard LTSC installation to the 10-year IoT support build safely:

1. Right-click the **Start Menu** icon and select **PowerShell (Admin)** or **Terminal (Admin)**.
2. Paste the following command and press **Enter**:

```powershell
irm [https://get.activated.win](https://get.activated.win) | iex
