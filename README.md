# 🌐 Windows 10 LTSC Download & Setup Guide

A complete step-by-step guide on how to safely download, install, and activate Windows 10 LTSC, featuring essential troubleshooting tips to prevent random blue screen (BSOD) crashes.

---

### 📌 What is LTSC, and why use it?
<details>
<summary><b>▶ Click here for info</b></summary>

<br>

* **No Bloatware:** Stripped of pre-installed apps like Cortana, Xbox services, and background telemetry.
* **Low System Usage:** Consumes significantly less RAM and CPU, maximizing performance for gaming and video editing.
* **Long-Term Stability:** Receives essential security patches without unexpected feature updates breaking your display or audio drivers.

</details>

---

### 📥 1. Downloading the Windows 10 LTSC ISO

<details>
<summary><b>▶ Click here for ISO download options</b></summary>

<br>

To ensure you get a clean, untouched, and safe copy of Windows 10 Enterprise LTSC, use the official direct links maintained by the **MassGrave (MAS)** community:

1. **Visit the Official GitHub / Documentation Page:**
   * Go directly to **[massgrave.dev](https://massgrave.dev)** or their official GitHub repository **[massgravel/Microsoft-Activation-Scripts](https://github.com/massgravel/Microsoft-Activation-Scripts)**.
2. **Navigate to Downloads:**
   * Click on **Download Windows** in the menu $\rightarrow$ Select **Windows 10 / 11 LTSC**.
3. **Select the Correct Version:**
   * Choose **Windows 10 Enterprise LTSC 2021 (x64)**.
4. **Download the File:**
   * Pick your preferred system language and click the direct link to download the clean `.iso` image.

</details>

---

### ⚠️ 2. Crucial Step During Setup (Avoiding Random BSODs)
<details>
<summary><b>▶ Click here to read before installing!</b></summary>

<br>

When booting from your USB, the installer will ask you to choose between two editions:

1. **Windows 10 Enterprise LTSC** *(Choose This!)*
2. **Windows 10 IoT Enterprise LTSC** *(Do Not Choose Here!)*

> [!CAUTION]
> **DO NOT SELECT IOT ENTERPRISE DIRECTLY FROM THE BOOT MEDIA!**
> 
> Selecting the IoT option during the setup screen applies strict embedded system policies to standard PC hardware. While it boots fine initially, it frequently leads to random **Blue Screen of Death (BSOD)** crashes or missing driver errors after a few days or a week.

#### 💡 The Correct Strategy:
1. Always pick **Option 1: Windows 10 Enterprise LTSC** on the boot screen. This ensures standard desktop drivers load safely.
2. Complete the installation.
3. Once in Windows, run the MAS PowerShell activation script (Step 3). 
4. **The MAS script will automatically convert your license to IoT Enterprise LTSC in the background!** You get extended support until 2032 without any of the installer driver bugs.

</details>

---

### 🔑 3. Safe & Clean Activation via GitHub Script
<details>
<summary><b>▶ Click here for activation commands</b></summary>

<br>

1. Once Windows is installed, right-click the **Start Menu** and open **PowerShell (Admin)**.
2. Run the official PowerShell command from the **[MassGrave GitHub](https://github.com/massgravel/Microsoft-Activation-Scripts)**:
   ```powershell
   irm [https://get.activated.win](https://get.activated.win) | iex
   
