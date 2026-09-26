# iQOO Z9x / Vivo T3x GhostLock Root

Professional one-tap root solution for iQOO Z9x (I2219) and Vivo T3x (V2407) devices using CVE-2026-43499 kernel exploit with KernelSU integration.

**⚠️ Z9x/T3x ONLY** — Not compatible with Z9 5G or T3 5G

## 🎯 Supported Devices

| Device | Model | Firmware | Kernel | SoC | Status |
|--------|-------|----------|--------|-----|--------|
| iQOO Z9x | I2219 | PD2353BF_EX_A_16.2.16.0.W30 | 5.10.246-android12-9 | Snapdragon 6 Gen 1 | ✅ Tested |
| Vivo T3x | V2407 | - | 5.10.246-android12-9 | Snapdragon 6 Gen 1 | ✅ Supported |

## ✨ Features

- 🎯 **Automatic Device Detection** - Identifies I2219 and V2407 automatically
- 💣 **CVE-2026-43499 Exploit** - Futex PI UAF kernel vulnerability
- 🔐 **KernelSU Integration** - Full root permission management
- ⚡ **One-Tap Installation** - Simple install process
- 📱 **Shizuku Support** - Optional privilege escalation mode
- 📊 **Install History** - Track all installation attempts
- 🛡️ **Verified Payloads** - GitHub-hosted, checksummed binaries

## 📦 Release Contents

```
├── ghostlock-z9x-t3x-v0.0.2.apk    (62 MB) - Main application
├── ksud-z9x-i2219                   (6 MB)  - KernelSU daemon
├── README.md                                - This file
├── INSTALL.md                               - Installation guide
├── RELEASE_NOTES.md                         - Version history
└── checksums.txt                            - SHA256 verification
```

## 🚀 Quick Start

### Prerequisites
- iQOO Z9x (I2219) or Vivo T3x (V2407)
- Android 12+ (API 31+)
- ARM64-v8a processor
- 4GB+ free storage
- USB debugging enabled (optional)

### Installation Steps

1. **Download APK**
   ```bash
   wget https://github.com/RahadHack99/iqoo-z9x-vivo-t3x-ghostlock/releases/download/v0.0.2/ghostlock-z9x-t3x-v0.0.2.apk
   ```

2. **Enable Unknown Sources**
   - Settings → Security → Install unknown apps → Enable for your file manager

3. **Install APK**
   - Open downloaded APK
   - Tap "Install"
   - Wait for completion

4. **Root Device**
   - Launch GhostLock app
   - Review device information
   - Tap "Install"
   - Wait 2-5 minutes

5. **Install KernelSU Manager**
   - Tap "Download KernelSU Manager" when prompted
   - Install KernelSU Manager APK
   - Open and verify root status

### Via ADB

```bash
adb install ghostlock-z9x-t3x-v0.0.2.apk
```

## 🔍 Verification

### Check Device Compatibility

```bash
# Via ADB
adb shell getprop ro.product.model        # Should show I2219 or V2407
adb shell uname -r                        # Should show 5.10.246-android12-9...
adb shell getprop ro.product.cpu.abi      # Should show arm64-v8a
```

### Verify Root Installation

```bash
adb shell su -c id
# Expected output: uid=0(root) gid=0(root) groups=0(root),...
```

Or use a root checker app from Play Store.

## 🛠️ Technical Details

### Exploit Information
- **CVE**: CVE-2026-43499
- **Vulnerability**: Futex PI (Priority Inheritance) Use-After-Free
- **Attack Vector**: UMH (User Mode Helper) injection - Path A
- **Kernel Impact**: Memory corruption → code execution → kernel privileges

### Privilege Escalation
- **Method**: Kernel memory manipulation via pipe physrw
- **Target**: futex_pi_requeue kernel function
- **Technique**: SELinux bypass via kernel code execution

### Root Implementation
- **Framework**: KernelSU v3.3.0
- **Integration**: Late-load module injection
- **Persistence**: Kernel module (survives reboots)
- **Management**: KernelSU Manager app

## ⚠️ Risks & Disclaimer

**CRITICAL WARNINGS:**
- ❌ **Voids Warranty** - Device warranty will be voided
- ❌ **Bootloop Risk** - Improper use may brick your device
- ❌ **Security Exposure** - Root access exposes device to malware
- ❌ **Banking Apps** - Many banking/payment apps will refuse to work
- ❌ **Data Loss** - Rooting may cause data loss or corruption

**This tool is for:**
- ✅ Educational purposes
- ✅ Security research
- ✅ Device customization (at your own risk)
- ✅ Authorized testing only

**This tool is NOT for:**
- ❌ Circumventing paid services
- ❌ Modifying system for illegal purposes
- ❌ Unauthorized device access
- ❌ Malware distribution

## 📋 Troubleshooting

### "Unsupported device" error
- ✅ Verify model: Settings → About Phone → Model number
- ✅ Must be I2219 (Z9x) or V2407 (T3x)
- ✅ Kernel must match: `5.10.246-android12-9-00010-g8ca7539b1d84-ab14517425`

### Installation fails
1. Restart device
2. Clear app data: Settings → Apps → GhostLock → Storage → Clear data
3. Try again
4. Check install history for error details

### KernelSU not working
1. Reinstall KernelSU Manager (exact version shown in app)
2. Grant all requested permissions
3. Reboot device
4. Verify in KernelSU Manager

### Banking apps detect root
- Use KernelSU's "Hide" feature for specific apps
- Enable "Unmount modules" per app
- Some apps may still refuse (by design)

## 🔄 Uninstalling Root

To remove root access:
1. Flash stock firmware via ADB/Fastboot
2. Perform factory reset
3. Device will be restored to original state

**⚠️ Backup your data before rooting!**

## 📚 Documentation

- [Installation Guide](INSTALL.md) - Detailed step-by-step instructions
- [Release Notes](RELEASE_NOTES.md) - Version history and changes
- [Checksums](checksums.txt) - SHA256 for file verification

## 🙏 Credits

- **GhostLock Framework** - Original exploit framework authors
- **CVE-2026-43499** - Vulnerability researchers
- **KernelSU** - https://github.com/tiann/KernelSU
- **Shizuku** - https://github.com/RikkaApps/Shizuku

## 📊 Project Statistics

- **Supported Devices**: 2 (I2219, V2407)
- **Exploit**: CVE-2026-43499
- **Root Framework**: KernelSU 3.3.0
- **Android Version**: 12+
- **Architecture**: arm64-v8a

## 🔗 Links

- **GitHub**: https://github.com/RahadHack99/iqoo-z9x-vivo-t3x-ghostlock
- **KernelSU**: https://github.com/tiann/KernelSU
- **Shizuku**: https://github.com/RikkaApps/Shizuku

## 📄 License

This project is for research and educational purposes only.

---

**Last Updated**: September 14, 2026  
**Version**: v0.0.2  
**Status**: Production Ready

⚡ **Strike clean. Roost warm. fuck u
