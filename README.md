# Windows 10 LTSC: Deployment, Optimization & Stability Guide

A clear, step-by-step guide to downloading, setting up, and optimizing **Windows 10 Enterprise LTSC**. Built to help you avoid common post-installation pitfalls, driver instabilities, and unexpected Blue Screen of Death (BSOD) crashes.

---

## Overview

Windows 10 Long-Term Servicing Channel (LTSC) is a streamlined release of Windows designed for system stability and lower resource footprint. Unlike standard Home or Pro editions, LTSC ships without pre-installed bloatware, consumer telemetry apps, or mandatory feature updates.

### Core Advantages
* **Zero Bloatware:** Excludes pre-installed Microsoft Store apps, Cortana, and background tracking services.
* **Predictable Updates:** Receives critical security patches without intrusive, feature-breaking major updates.
* **Low Overhead:** Noticeably lower CPU and RAM usage, making it ideal for older hardware, low-end PCs, and gaming configurations.

---

## 1. ISO Selection & Download

Official, untouched Windows installation images can be obtained directly via MassGrave's official documentation:
👉 **[MassGrave Windows LTSC Download Page](https://massgrave.dev/docs/windows_ltsc_links.md)**

> ⚠️ **CRITICAL WARNING FOR DESKTOP & LAPTOP USERS:**
> Do **NOT** clean install the **Windows 10 IoT Enterprise LTSC ISO** image on standard desktop PCs or laptops.
> 
> * **The Issue:** The raw IoT edition ISO is built specifically for embedded systems (ATMs, kiosks, factory hardware). Installing it directly on regular PCs frequently leads to driver initialization failures and random **Blue Screen of Death (BSOD)** crashes within 1 hour, 1 day, or 1 week of usage.
> * **The Solution:** Always download and install the **Standard Windows 10 Enterprise LTSC ISO**. 
> * **Safe IoT Conversion:** If you want the extended 10-year support lifecycle of IoT, simply install standard Enterprise LTSC first. Once installed, you can safely convert your system to **IoT Enterprise LTSC** in seconds using the MassGrave activation script (MAS)—100% safe, stable, and driver-issue free!

---

### Edition Comparison

| Edition | Primary Use Case | Stability & Support |
| :--- | :--- | :--- |
| **Windows 10 Enterprise LTSC** *(Recommended)* | Desktop PCs, Laptops, Gaming | Full hardware compatibility, stable driver support, standard 5-year lifecycle. |
| **Windows 10 IoT Enterprise LTSC** *(Avoid Clean ISO Install)* | Embedded Systems (Kiosks, ATMs) | Extended 10-year support, but bare ISOs frequently trigger severe driver conflicts and BSODs on consumer PC hardware. |

---

### ISO Flashing Instructions
1. Open the **[MassGrave LTSC Links Page](https://massgrave.dev/docs/windows_ltsc_links.md)** and download **Windows 10 Enterprise LTSC 2021 (x64)** *(Standard, Non-IoT)*.
2. Open **Rufus** and select your USB flash drive (8GB+ recommended).
3. Set **Partition scheme** based on your motherboard firmware:
   * `GPT` for modern UEFI systems.
   * `MBR` for older Legacy BIOS motherboards.
4. Flash the drive and proceed with a clean installation on your main system drive.

---

## 2. Critical Post-Install Stability Tweaks

To prevent random system crashes (`DRIVER_POWER_STATE_FAILURE` or `WHEA_UNCORRECTABLE_ERROR`) shortly after a fresh installation, complete these configuration steps immediately upon reaching the desktop:

### Disable Fast Startup
Fast Startup forces Windows into a hybrid hibernation state that often corrupts low-level driver states on cold boots:
1. Open **Control Panel** $\rightarrow$ **Power Options**.
2. Select **Choose what the power buttons do** in the left sidebar.
3. Click **Change settings that are currently unavailable**.
4. Uncheck **Turn on fast startup (recommended)** and save changes.

### Install Direct Vendor Drivers
* Avoid relying on generic display or chipset drivers provided through Windows Update.
* Manually download and install official drivers directly from your hardware manufacturer:
  * Graphics: AMD Radeon / Nvidia GeForce / Intel Graphics
  * Motherboard: Official Chipset, LAN, and Audio drivers provided by the board vendor.

### Configure PCI Express Power Policy
Prevent PCIe-related bus timeouts and system freezes:
1. Navigate to **Control Panel** $\rightarrow$ **Power Options** $\rightarrow$ **Change plan settings**.
2. Click **Change advanced power settings**.
3. Expand **PCI Express** $\rightarrow$ **Link State Power Management**.
4. Change the setting to **Off** for both *On battery* and *Plugged in*.

---

## 3. License Activation & Safe IoT Conversion

To activate LTSC or convert your standard LTSC installation to IoT LTSC safely without third-party executables or modified binaries, use the open-source Microsoft Activation Scripts (MAS).

1. Right-click the **Start Button** and launch **PowerShell (Admin)**.
2. Run the following command:

```powershell
irm [https://get.activated.win](https://get.activated.win) | iex
