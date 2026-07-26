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

### 📥 1. Downloading the ISO from Official GitHub Source
<details>
<summary><b>▶ Click here for official GitHub ISO links</b></summary>

<br>

To ensure your download is 100% clean and untouched, grab the ISO directly through MassGrave's official open-source GitHub repository:

1. **Open the Official GitHub Source File:**
   Go directly to their documentation source page:
   👉 **[MassGrave GitHub: `windows_ltsc_links.md`](https://github.com/massgravel/massgrave.dev/blob/main/docs/windows_ltsc_links.md)**

2. **Verify Genuine Files:**
   As confirmed right on their official GitHub page:
   > *"All download links lead to genuine files only."*

3. **Download Your ISO:**
   * Scroll down to **Windows 10 Enterprise LTSC 2021 (x64)**.
   * Pick your language to start the official download directly.

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
   
