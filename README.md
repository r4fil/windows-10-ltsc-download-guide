# 🪟 Windows 10 LTSC Download & Setup Guide

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

### 📥 1. Downloading the ISO
<details>
<summary><b>▶ Click here for info</b></summary>

<br>

1. Get the official scripts and ISO links from the **[MassGrave GitHub Repository](https://github.com/massgravel/Microsoft-Activation-Scripts)** or their documentation site at **[massgrave.dev](https://massgrave.dev)**.
2. Select **Windows 10 Enterprise LTSC 2021** (x64).
3. Download the ISO in your preferred language.

</details>

---

### ⚠️ 2. Crucial Step During Setup (Avoiding Random BSODs)
<details>
<summary><b>▶ Click here to read before installing!</b></summary>

<br>

During the Windows installation process, you will be presented with two main options:

1. **Windows 10 Enterprise LTSC** *(Recommended)*
2. **Windows 10 IoT Enterprise LTSC**

> 🚨 **Real-World Warning:** Do **not** pick option 2 (IoT LTSC). While it may boot up fine initially, it frequently causes random **Blue Screen (BSOD)** crashes after 1 hour, 1 day, or even a week due to system driver incompatibilities on desktop PCs.

#### 💡 Solution:
* Always choose **Option 1: Windows 10 Enterprise LTSC** during setup.
* Proceed with a clean installation, then activate using the official GitHub script below.

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
   
