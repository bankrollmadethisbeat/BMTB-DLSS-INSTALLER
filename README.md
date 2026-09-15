# BMTB-DLSS-INSTALLER
Official releases and automatic updates for the BMTB FiveM DLSS 5 Installer.

<img width="1254" height="1254" alt="ChatGPT Image Sep 15, 2026, 08_34_05 AM" src="https://github.com/user-attachments/assets/5a63d6df-7900-40ea-a469-e64c1466e888" />

<div align="center">

# ⚡ BMTB FiveM DLSS 5 Installer

### One-Click DLSS Installation for FiveM

**Fast. Simple. Safe. Built for FiveM.**

<br>

[![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D6?style=for-the-badge&logo=windows&logoColor=white)](#-system-requirements)
[![NVIDIA RTX](https://img.shields.io/badge/NVIDIA-RTX%2020%20%7C%2030%20%7C%2040%20%7C%2050-76B900?style=for-the-badge&logo=nvidia&logoColor=white)](#-supported-gpus)
[![Free](https://img.shields.io/badge/PRICE-FREE-2EA44F?style=for-the-badge)](#)
[![No Telemetry](https://img.shields.io/badge/TELEMETRY-NONE-success?style=for-the-badge)](#-privacy)
[![GitHub Releases](https://img.shields.io/badge/UPDATES-GITHUB%20RELEASES-181717?style=for-the-badge&logo=github)](#-automatic-updates)

<br>

### 🟢 Free Community Utility  
### 🔒 No Account • No Ads • No Telemetry

</div>

---

# 📖 About

**BMTB FiveM DLSS 5 Installer** is a free Windows utility designed to make installing the correct DLSS package for FiveM as simple as possible.

Forget manually copying DLL files, digging through FiveM folders, or figuring out which GPU package you need.

The installer can automatically:

> 🔍 Detect your FiveM installation  
> 🎮 Detect your NVIDIA RTX GPU  
> 📦 Select the recommended DLSS package  
> 💾 Back up existing files  
> ⚡ Install the required files  
> 🛠️ Repair damaged installations  
> ♻️ Restore your previous files  
> 🔄 Check GitHub for application updates  

The normal installation process is designed to be:

```text
Open Installer
      ↓
Detect FiveM
      ↓
Detect GPU
      ↓
Click INSTALL DLSS 5
      ↓
Done
✨ Features
Feature	Status
🔍 Automatic FiveM Detection	✅
📁 Custom FiveM Path Support	✅
🎮 Automatic NVIDIA RTX Detection	✅
🟩 RTX 20 Series Support	✅
🟩 RTX 30 Series Support	✅
🟩 RTX 40 Series Support	✅
🟩 RTX 50 Series Support	✅
📦 Automatic Package Selection	✅
🎛️ Manual Package Override	✅
⚡ One-Click Installation	✅
💾 Automatic File Backup	✅
♻️ Restore Previous Files	✅
🛠️ Repair Installation	✅
🔐 File Integrity Verification	✅
🚫 FiveM Running Detection	✅
🩺 Installation Diagnostics	✅
🔄 GitHub Update Checking	✅
🎨 Premium BMTB Interface	✅
🌐 Offline DLSS Installation	✅
👤 Account Required	❌
📊 Telemetry	❌
📢 Advertisements	❌
🎮 Supported GPUs

The installer currently supports NVIDIA GeForce RTX graphics cards through two package groups.

🟩 RTX 20 / 30 / 40 Series Package

Designed for supported:

NVIDIA GeForce RTX 20 Series
NVIDIA GeForce RTX 30 Series
NVIDIA GeForce RTX 40 Series

Examples:

RTX 2060
RTX 2080 Ti
RTX 3060
RTX 3070
RTX 3090 Ti
RTX 4060 Ti
RTX 4070 Ti SUPER
RTX 4090
🟢 RTX 50 Series Package

Designed for supported:

NVIDIA GeForce RTX 50 Series

Examples:

RTX 5060
RTX 5060 Ti
RTX 5070
RTX 5070 Ti
RTX 5080
RTX 5090

[!TIP]
The installer attempts to detect your GPU automatically and select the recommended package for you.

You can still manually change the package if needed.

📥 Installation
1️⃣ Download

Go to the Releases section of this repository.

Official Repository
bankrollmadethisbeat/BMTB-DLSS-INSTALLER

Download:

BMTB_FiveM_DLSS5_Installer.exe

[!IMPORTANT]
Download official builds only from this GitHub repository.

2️⃣ Run the Installer

Open:

BMTB_FiveM_DLSS5_Installer.exe

The installer will automatically begin checking your system.

3️⃣ Confirm FiveM

The installer will attempt to automatically detect:

%LOCALAPPDATA%\FiveM\FiveM.app

Example:

C:\Users\USERNAME\AppData\Local\FiveM\FiveM.app

If FiveM is detected correctly, you should see something similar to:

✓ FiveM Detected

C:\Users\USERNAME\AppData\Local\FiveM\FiveM.app
4️⃣ Confirm Your GPU

Example:

✓ GPU Detected

NVIDIA GeForce RTX 5070 Ti

Recommended Package:
RTX 50 Series

Or:

✓ GPU Detected

NVIDIA GeForce RTX 4070 Ti

Recommended Package:
RTX 20 / 30 / 40 Series
5️⃣ Install

Press:

INSTALL DLSS 5

The installer handles the rest.

📁 FiveM Detection

BMTB automatically checks the standard FiveM installation location:

%LOCALAPPDATA%\FiveM\FiveM.app

The final plugin destination is:

FiveM.app\plugins

Example:

C:\Users\USERNAME\AppData\Local\FiveM\FiveM.app\plugins
📂 Custom FiveM Location

If your FiveM installation is somewhere else, press:

Change Location

Then select your:

FiveM.app

folder.

The installer will validate the selected directory before allowing installation.

🧠 Automatic GPU Detection

BMTB automatically checks your graphics card and attempts to choose the correct package.

Example — RTX 50 Series
GRAPHICS CARD

✓ Detected

NVIDIA GeForce RTX 5070 Ti

Package:
RTX 50 Series
Example — RTX 40 Series
GRAPHICS CARD

✓ Detected

NVIDIA GeForce RTX 4070 Ti

Package:
RTX 20 / 30 / 40 Series

If automatic detection fails, select the package manually using:

Change Package
💾 Automatic Backup

Before BMTB replaces supported existing files, the installer creates a backup.

This is designed to make returning to your previous setup much easier.

BMTB will attempt to preserve:
Existing supported DLL files
Existing ReShade configuration
Existing files being replaced by the installer
Unrelated FiveM plugins
Unrelated ReShade shaders

[!IMPORTANT]
BMTB does not intentionally wipe your entire plugins folder.

The installer only manages files associated with the BMTB DLSS installation.

♻️ Restore Previous Files

Want to return to your setup from before BMTB DLSS was installed?

Use:

Restore Previous Files

The restore system will attempt to:

✅ Restore files that existed before installation
✅ Remove files created by BMTB
✅ Preserve unrelated FiveM plugins
✅ Preserve unrelated ReShade shaders
✅ Restore the original pre-install state

🛠️ Repair Installation

FiveM updates, graphics modifications, or accidental file changes can sometimes affect installed files.

If BMTB detects files that are:

❌ Missing
⚠️ Modified
🧩 Corrupted
🔄 Replaced
📦 Using the wrong package

the installer can offer:

REPAIR INSTALLATION

Repair restores BMTB-managed files while preserving unrelated content.

🔐 File Integrity

BMTB can verify managed files using file integrity checks.

This helps detect:

Missing Files
Modified Files
Incorrect Package Files
Corrupted Files

Possible status:

✓ INSTALLATION HEALTHY

or:

⚠ REPAIR AVAILABLE
🩺 Installation Diagnostics

The installer includes diagnostic checks designed to help identify problems.

Diagnostics may check:

FiveM installation path
GPU detection
Selected GPU package
FiveM running status
File availability
File integrity
Write permissions
Installation manifest
Backup availability
Application version

This can make troubleshooting much easier.

🔄 Automatic Updates

BMTB FiveM DLSS 5 Installer uses this GitHub repository as its official application update source.

bankrollmadethisbeat/BMTB-DLSS-INSTALLER

When a newer stable release is available, the application may display:

┌─────────────────────────────────────┐
│ ↑ UPDATE AVAILABLE                  │
│                                     │
│ BMTB FiveM DLSS 5 v1.1.0           │
│                                     │
│ Current Version: v1.0.0             │
│                                     │
│         [ UPDATE NOW ]              │
└─────────────────────────────────────┘

Updates are retrieved from official GitHub Releases.

🔄 Example Version Flow
Installed:
v1.0.0

GitHub:
v1.1.0

Result:
UPDATE AVAILABLE

Future releases may look like:

v1.0.0
v1.0.1
v1.1.0
v1.2.0
v2.0.0
🌐 Offline Support

Internet access is not required to install the bundled DLSS files.

The main installation process works locally.

Internet access is used for optional functionality such as:

Checking GitHub for BMTB application updates

If GitHub or your internet connection is unavailable, the normal installer can still operate.

🔒 Privacy

BMTB FiveM DLSS 5 Installer is designed to remain lightweight and private.

We do NOT require:

❌ User accounts
❌ BMTB accounts
❌ Login credentials
❌ Subscriptions
❌ Discord authentication
❌ Advertising
❌ Analytics
❌ Telemetry

FiveM detection and GPU detection occur locally on your PC.

🛡️ Installer Safety

The installer includes several protections designed to reduce the chance of damaging an existing FiveM installation.

Safety Systems
✓ FiveM Path Validation
✓ Automatic Backup
✓ Installation Manifest
✓ File Integrity Verification
✓ Rollback Support
✓ Repair Support
✓ Restore Support
✓ FiveM Running Detection

If FiveM is running while an installation is attempted, BMTB may ask you to close FiveM first.

Example:

FiveM is currently running.

Please close FiveM before installing DLSS files.

[ CHECK AGAIN ]
📊 Installation Status

BMTB may display several installation states.

🟢 Ready
READY TO INSTALL
✅ Healthy
INSTALLATION HEALTHY
⚠️ Repair Required
REPAIR AVAILABLE
🔄 New Application Version
UPDATE AVAILABLE
💾 Backup Detected
BACKUP AVAILABLE
💻 System Requirements
Requirement	Supported
Windows 10	✅
Windows 11	✅
64-bit Windows	✅
NVIDIA RTX GPU	✅
FiveM	✅
Administrator Account Required	❌ Normally Not Required
Internet for DLSS Installation	❌
Internet for Update Checking	✅

[!NOTE]
Compatibility may vary depending on your specific FiveM, GTA V, driver, ReShade, and graphics-mod configuration.

📦 Latest Release
BMTB FiveM DLSS 5 Installer

Current initial release:

v1.0.0

Official executable:

BMTB_FiveM_DLSS5_Installer.exe
Download Location

Use the Releases section on this repository.

[!WARNING]
Do not trust unofficial builds claiming to be BMTB releases.

🚀 v1.0.0 — Initial Release
🎉 Initial Public Release

Included features:

🔍 FiveM auto detection
📂 Custom FiveM path support
🎮 NVIDIA RTX GPU detection
🟩 RTX 20 / 30 / 40 Series package support
🟢 RTX 50 Series package support
📦 Automatic package selection
⚡ One-click DLSS installation
💾 Automatic backup
♻️ Restore previous files
🛠️ Repair installation
🔐 File integrity verification
🩺 Installation diagnostics
🔄 GitHub update checker
🎨 Premium BMTB user interface
🌐 Offline installation support
🔒 No telemetry
👤 No account required
🆘 Troubleshooting
<details> <summary><strong>🔍 FiveM was not detected</strong></summary> <br>

Press:

Change Location

Then manually select:

FiveM.app

Example:

C:\Users\USERNAME\AppData\Local\FiveM\FiveM.app
</details>
<details> <summary><strong>🎮 My GPU was not detected</strong></summary> <br>

Use:

Change Package

Then select the package matching your GPU.

RTX 20 / 30 / 40

Choose:

RTX 20 / 30 / 40 Series
RTX 50

Choose:

RTX 50 Series
</details>
<details> <summary><strong>🚫 FiveM is currently running</strong></summary> <br>

Close FiveM completely.

Then return to the installer and press:

Check Again

Do not install graphics-related files while FiveM is actively using them.

</details>
<details> <summary><strong>🛠️ My installation stopped working</strong></summary> <br>

Open the BMTB installer.

If the installation is detected as modified or incomplete, use:

Repair Installation
</details>
<details> <summary><strong>♻️ I want my previous files back</strong></summary> <br>

Use:

Restore Previous Files

BMTB will attempt to restore the files saved before installation.

</details>
<details> <summary><strong>🔄 The installer says an update is available</strong></summary> <br>

Select:

Update Now

The application will retrieve the newer official BMTB release from this GitHub repository.

</details>
⚠️ Compatibility

BMTB FiveM DLSS 5 Installer is designed to simplify installation of the files bundled with the utility.

Compatibility can vary depending on:

FiveM updates
GTA V updates
NVIDIA driver versions
Windows updates
Existing ReShade installations
Existing graphics modifications
Existing proxy DLLs
Other injected plugins
Other FiveM modifications

[!IMPORTANT]
Although BMTB includes backup and restore functionality, keeping copies of important custom configurations is always recommended.

🔏 Security

For your safety:

Only download BMTB from:
github.com/bankrollmadethisbeat/BMTB-DLSS-INSTALLER

Official application filename:

BMTB_FiveM_DLSS5_Installer.exe

Avoid modified executables redistributed by unknown third parties.

📝 Release Naming

Official releases follow this format:

v1.0.0
v1.0.1
v1.1.0
v1.2.0
v2.0.0

Official release executable:

BMTB_FiveM_DLSS5_Installer.exe
🧩 Repository
Owner:
bankrollmadethisbeat

Repository:
BMTB-DLSS-INSTALLER

Branch:
main

This repository serves as the official release and automatic update source for the BMTB FiveM DLSS 5 Installer.

⚖️ Disclaimer

BMTB FiveM DLSS 5 Installer is an unofficial community utility.

This project is not affiliated with, sponsored by, approved by, or endorsed by:

NVIDIA Corporation
Rockstar Games
Take-Two Interactive
Cfx.re
FiveM

NVIDIA, GeForce, RTX, DLSS, GTA, Grand Theft Auto, FiveM, ReShade, and other names, technologies, logos, and trademarks are the property of their respective owners.

Third-party files, libraries, technologies, and components included with or supported by this utility remain the property of their respective owners and are subject to their respective terms and licenses.

<div align="center">
🟢 BMTB
Better Mechanics. Trusted Builds.

Simple tools. Clean installs. Better FiveM experiences.

<br>






</div> ```
