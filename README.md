# Windows 10 LTSC: Deployment, Optimization & Stability Guide

A clear, step-by-step guide to downloading, setting up, and optimizing **Windows 10 Enterprise LTSC**. Built to help you avoid common post-installation pitfalls, driver instabilities, and unexpected Blue Screen of Death (BSOD) crashes.

---

## Overview

Windows 10 Long-Term Servicing Channel (LTSC) is a streamlined release of Windows designed for system stability and lower resource footprint. Unlike standard Home or Pro editions, LTSC ships without pre-installed bloatware, consumer telemetry apps, or mandatory feature updates.

### Core Advantages
* **Zero Bloatware:** Excludes pre-installed Microsoft Store apps, Cortana, and background tracking services.
* **Predictable Updates:** Receives critical security patches without intrusive, feature-breaking major updates.
* **Low Overhead:** Noticeably lower CPU and RAM usage, making it ideal for older hardware, low-end PCs, and high-performance gaming configurations.

---

## 1. ISO Selection & Download

Official, untouched Windows installation images can be obtained directly via [MassGrave's Media Repository](https://massgrave.dev/genuine-installation-media).

### Edition Comparison

| Edition | Primary Use Case | Stability & Support |
| :--- | :--- | :--- |
| **Windows 10 Enterprise LTSC** *(Recommended)* | Desktop PCs, Laptops, Gaming | Full hardware compatibility, stable driver support, standard 5-year lifecycle. |
| **Windows 10 IoT Enterprise LTSC** | Embedded Systems (Kiosks, ATMs) | Extended 10-year support, but bare ISOs frequently trigger severe driver conflicts and BSODs on consumer PC hardware. |

> 💡 **Recommended Workflow:** Always install the **standard Windows 10 Enterprise LTSC ISO**. If you want the extended 10-year support lifecycle of IoT, install the standard edition first and perform an in-place conversion to IoT using MAS after installation. This avoids driver initialization errors entirely.

### ISO Flashing Instructions
1. Download **Windows 10 Enterprise LTSC 2021 (x64)** from the repository.
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

## 3. License Activation & Edition Conversion

To activate LTSC or convert your standard LTSC installation to IoT LTSC without third-party executables or modified binaries, use the open-source Microsoft Activation Scripts (MAS).

1. Right-click the **Start Button** and launch **PowerShell (Admin)**.
2. Run the following command:

```powershell
irm [https://get.activated.win](https://get.activated.win) | iex
