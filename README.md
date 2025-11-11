# PDFRenamer

**Professional PDF File Renaming Tool for Windows**

PDFRenamer is an automated solution for renaming PDF files based on their content, metadata, or custom rules. Designed for businesses and professionals who handle large volumes of PDF documents.

![Version](https://img.shields.io/badge/version-1.25.315.2-blue)
![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-brightgreen)
![.NET](https://img.shields.io/badge/.NET-9.0-purple)

---

## ✨ Features

- 🔄 **Automated PDF Renaming** - Automatically rename PDFs based on content or rules
- 📁 **Folder Monitoring** - Watch folders for new PDF files and process them automatically
- 🎯 **Smart Detection** - Extract information from PDF metadata and content
- 🚀 **High Performance** - Process large batches of files efficiently
- 🌐 **Web Interface** - Modern, intuitive web-based UI accessible from any browser
- ��️ **Service Mode** - Run as Windows Service for always-on operation
- 📊 **Real-time Status** - Live updates and progress tracking
- 🔒 **Secure** - Local processing, your files never leave your network

---

## 📥 Download

**Latest Release: v1.25.315.2**

Choose the installer that fits your needs:

### Option 1: Bundle Installer (Recommended)
**[Download PDFRenamer-Setup-1.25.315.2.exe](../../releases/latest/download/PDFRenamer-Setup-1.25.315.2.exe)**
- ✅ Includes .NET 9.0 Runtime
- ✅ One-click installation
- ✅ Best for most users
- 📦 Size: ~4.5 MB

### Option 2: ZIP Archive
**[Download PDFRenamer-1.25.315.2.zip](../../releases/latest/download/PDFRenamer-1.25.315.2.zip)**
- ✅ Contains MSI installer + CAB files
- ✅ For manual deployment
- ✅ Ideal for enterprise/Group Policy deployment
- 📦 Size: ~3.5 MB

> **Note:** If you choose the ZIP archive, you need to have .NET 9.0 Runtime installed separately.

---

## 💻 System Requirements

| Requirement | Minimum |
|------------|---------|
| **Operating System** | Windows 10 (64-bit) or later |
| **RAM** | 2 GB (4 GB recommended) |
| **Disk Space** | 100 MB free |
| **.NET Runtime** | 9.0 (included in bundle installer) |
| **Display** | 1280x720 or higher |

---

## 🚀 Quick Start

### Installation

1. **Download** the installer from the [Releases](../../releases) page
2. **Run** `PDFRenamer-Setup-1.25.315.2.exe`
3. **Follow** the installation wizard
4. **Launch** PDFRenamer from Start Menu or Desktop

### First Use

1. Open your browser and navigate to `http://localhost:5000`
2. Configure your folder monitoring settings
3. Add folders to watch for PDF files
4. Set up your renaming rules
5. PDFRenamer will automatically process new files

### Running as Windows Service

For always-on operation:

```powershell
# Install as service (Run as Administrator)
.\PDFRenamer.ServiceInstaller.exe install

# Start the service
net start PDFRenamerService
```

---

## 📖 Documentation

- **[User Manual](docs/USER-MANUAL.md)** - Complete guide to using PDFRenamer
- **[Quick Start Guide](docs/QUICK-START.md)** - Get up and running in 5 minutes
- **[Release Notes](../../releases)** - What'\''s new in each version
- **[FAQ](docs/FAQ.md)** - Frequently asked questions

---

## 🔧 Configuration

PDFRenamer stores its configuration in:
```
C:\ProgramData\PDFRenamer\appsettings.json
```

### Default Settings

- **Web Interface Port:** 5000
- **Configuration Location:** `C:\ProgramData\PDFRenamer`
- **Log Files:** `C:\ProgramData\PDFRenamer\Logs`

### Accessing from Other Devices

By default, PDFRenamer is accessible from other computers on your network at:
```
http://[your-computer-ip]:5000
```

---

## 🆘 Support

### Get Help

- **Report Issues:** [GitHub Issues](../../issues)
- **Email Support:** petr.sindelar@heidelberg.com

### Before Reporting an Issue

1. Check the [FAQ](docs/FAQ.md)
2. Review the [User Manual](docs/USER-MANUAL.md)
3. Check existing [Issues](../../issues) for similar problems
4. Include your version number and error messages

---

## 🔄 Updating

### Automatic Update Check
PDFRenamer checks for updates automatically and notifies you when a new version is available.

### Manual Update

1. Download the latest installer
2. Stop PDFRenamer (right-click tray icon → Exit)
3. Run the new installer
4. Your settings and configurations will be preserved

### Service Mode Update

```powershell
# Stop the service
net stop PDFRenamerService

# Run the installer
.\PDFRenamer-Setup-1.25.315.2.exe

# Start the service
net start PDFRenamerService
```

---

## 🏢 Enterprise Deployment

### Group Policy Deployment

Use the ZIP archive for silent deployment via Group Policy:

```powershell
# Extract ZIP
Expand-Archive PDFRenamer-1.25.315.2.zip -DestinationPath C:\Temp\PDFRenamer

# Silent install MSI
msiexec /i "C:\Temp\PDFRenamer\PDFRenamer-Setup.msi" /quiet /norestart
```

### Multiple Installations

Each user can run their own instance, or deploy as a centralized service for the entire organization.

---

## 📊 Use Cases

### Document Management
Automatically organize incoming invoices, contracts, and receipts by extracting dates, client names, or document types.

### Compliance & Archiving
Rename documents according to your company'\''s naming conventions for easier retrieval and compliance.

### Workflow Automation
Integrate into your existing document workflows - files are automatically processed as they arrive.

### Batch Processing
Process large volumes of historical PDF files with consistent naming rules.

---

## 🔐 Privacy & Security

- ✅ **100% Local Processing** - All files are processed on your computer
- ✅ **No Cloud Services** - Your data never leaves your network
- ✅ **No Telemetry** - No usage data is collected or sent
- ✅ **Open Configuration** - All settings are stored in plain text JSON
- ✅ **Signed Installer** - Digitally signed for security

---

## 📜 License

This software is distributed as-is for use within your organization.

---

## 🙏 Acknowledgments

PDFRenamer is built with modern technologies:
- .NET 9.0
- Blazor for web UI
- SignalR for real-time updates
- WiX Toolset for installation

---

## 📞 Contact

**Petr Šindelář**  
Email: petr.sindelar@heidelberg.com  
Company: Heidelberg Cement Západ (HCZ)

---

## 🌟 Stay Updated

⭐ **Star this repository** to receive notifications about new releases

📢 **Watch releases** to get notified when we publish updates

---

<div align="center">

**Made with ❤️ for efficient document management**

[Download Latest](../../releases/latest) • [View All Releases](../../releases) • [Report Issue](../../issues)

</div>
