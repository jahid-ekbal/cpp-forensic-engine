# 🚀 REGIX Core Forensic & Anti-Cheat Engine v6.5

![C++](https://img.shields.io/badge/Language-C%2B%2B20-blue.svg)
![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-lightgrey.svg)
![Architecture](https://img.shields.io/badge/Architecture-x64-orange.svg)
![Security](https://img.shields.io/badge/Security-Kernel%20%26%20Memory-red.svg)

An advanced, light-weight memory-mapped forensic audit and anti-cheat tool engineered in native C++ for local machine verification. Utilizing direct Windows API routines, the engine detects environment anomalies, active memory injection states, macro systems, and runs multi-drive integrity checks backed by cloud-based threat intelligence.

Developed by **REGIX STUDIO**.

---

## ✨ Key Capabilities

- **🖥️ Anti-VM & Sandbox Isolation Lookups:** Checks Windows internal registry architectures and ACPI tables to verify if running inside VirtualBox, VMware, or sandboxed environments.
- **⚡ Hardware DMA Channel Inspection:** Scans PCIe hardware mapping lanes to alert on potential physical DMA card vulnerabilities.
- **🪝 API Inline Hook Audits:** Monitors core system function pointers (like `ntdll!NtOpenProcess`) to identify third-party detour trampolines.
- **🗂️ Driver Verification System:** Detects blacklisted or modified kernel-mode drivers used in Bring Your Own Vulnerable Driver (BYOVD) attacks.
- **🧠 Targeted VAD Descriptor Extraction:** Dynamically profiles memory-mapped subsystems for specific emulators and processes, analyzing active `EXECUTE_READWRITE` (RWX) injection states.
- **📂 Multi-Drive PE Core Crawler:** Scans files recursively across all mounted fixed volumes (`C:\`, `D:\`, etc.) utilizing a 0% false-positive filter that skips non-executable data layer logs.

---

## ⚠️ Critical Configuration: Adding Your VirusTotal API Key

By default, the cloud intelligence module is in bypass mode. To enable automated real-time hash verification against 70+ global antivirus engines, **you must use your own VirusTotal API key.**

### 🛠️ How to set up your API Key:

1. Create a free account at [VirusTotal](https://www.virustotal.com/).
2. Navigate to your Profile Settings and copy your unique **API Key**.
3. Open `RegixScanner.cpp` in Visual Studio.
4. Locate line **28** (or look for the `VT_API_KEY` constant):

```cpp
   // Replace this with your actual VirusTotal API key
   const std::string VT_API_KEY = "YOUR_VIRUSTOTAL_API_KEY_HERE";
```
