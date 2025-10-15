# PDFRenamer v1.25.288.7

**Release Date:** October 15, 2025  
**Status:** Stable Release

## 📥 Download

Choose the installation method that best suits your needs:

### Recommended: Bundle Installer
**File:** `PDFRenamer-Setup-1.25.288.7.exe`  
**Size:** ~4.5 MB  
**Best for:** Most users, automatic installation

[Download Bundle Installer →](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC/releases/download/v1.25.288.7/PDFRenamer-Setup-1.25.288.7.exe)

### Alternative: Installation Archive
**File:** `PDFRenamer-1.25.288.7.zip`  
**Size:** ~3.5 MB  
**Best for:** Enterprise deployment, manual installation

[Download ZIP Archive →](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC/releases/download/v1.25.288.7/PDFRenamer-1.25.288.7.zip)

## ✨ What's New

This is an **infrastructure release** focused on improving the development and release process. While there are no user-facing feature changes, this release ensures you'll continue to receive high-quality updates more efficiently.

### Behind the Scenes
- **Automated Release Distribution** - Releases are now automatically synced to this repository
- **AI-Powered Release Notes** - Comprehensive release documentation generated with AI assistance
- **Enhanced Quality Control** - Improved build and testing processes
- **Streamlined Updates** - Faster delivery of future releases

## 📦 Installation

### First-Time Installation

1. **Download** the Bundle Installer (recommended)
2. **Run** `PDFRenamer-Setup-1.25.288.7.exe`
3. **Follow** the installation wizard
4. **Launch** PDFRenamer from your Start Menu

### Upgrading from Previous Version

1. **Stop** PDFRenamer if it's currently running
2. **Download** the new installer
3. **Run** the installer - it will automatically detect and upgrade your existing installation
4. **Your settings will be preserved** during the upgrade
5. **Restart** the application

## 🖥️ System Requirements

- **Operating System:** Windows 10 (1809 or later) or Windows 11
- **Architecture:** 64-bit (x64)
- **.NET Runtime:** 9.0 (included in installer)
- **Disk Space:** ~200 MB
- **Memory:** 512 MB RAM minimum (1 GB recommended)
- **Permissions:** Administrator rights for installation

## 🎯 Key Features

PDFRenamer helps you automatically organize and rename your PDF files:

- **Automatic Monitoring** - Watches specified folders for new PDF files
- **Smart Renaming** - Renames files based on customizable rules
- **Folder Management** - Automatically organizes files into appropriate folders
- **Web Interface** - Modern browser-based UI for easy configuration
- **Cross-Platform UI** - Access from any device on your network
- **Background Service** - Runs automatically in the background (Windows Service)
- **Activity Logging** - Track all file operations and changes
- **Configuration Backup** - Easy backup and restore of settings

## 🔧 Configuration

After installation, PDFRenamer runs as a Windows Service and provides a web interface for configuration:

**Access the Web Interface:**
- Local: `http://localhost:5000`
- Network: `http://[your-pc-ip]:5000`

**Default Configuration Location:**
- `C:\ProgramData\PDFRenamer\`

**Service Management:**
- Use the web interface to start/stop the worker service
- Or use Windows Services (services.msc) to manage the background service

## 🚀 Quick Start

1. **Install** PDFRenamer using the instructions above
2. **Open** your web browser and navigate to `http://localhost:5000`
3. **Configure** your folders to monitor
4. **Set up** your renaming rules
5. **Start** the worker service
6. **Done!** PDFRenamer will now automatically process new PDF files

## 🏢 Enterprise Deployment

### Group Policy Deployment

1. Download `PDFRenamer-1.25.288.7.zip`
2. Extract the ZIP file
3. Deploy the MSI using Group Policy:
   ```
   msiexec /i PDFRenamer-Setup.msi /quiet
   ```

### Silent Installation

```cmd
PDFRenamer-Setup-1.25.288.7.exe /quiet /norestart
```

### Configuration Management

For enterprise environments, you can pre-configure settings by placing a configuration file at:
```
C:\ProgramData\PDFRenamer\appsettings.json
```

## 🔒 Security & Privacy

- **No Data Collection** - PDFRenamer does not collect or transmit any personal data
- **Local Processing** - All file operations happen locally on your machine
- **Network Access** - Only for the local web interface (configurable port)
- **Open Source** - Full transparency of what the software does

## 🐛 Known Issues

None at this time. This is a stable release.

## 📝 Technical Details

**Version:** 1.25.288.7  
**Build Date:** October 15, 2025  
**Framework:** .NET 9.0  
**Platform:** Windows x64  
**Installer Type:** WiX Bundle + MSI

## 🆘 Support

### Documentation
- [User Manual](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC#readme)
- [Setup Guide](SETUP-GUIDE.md)
- [FAQ](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC/wiki)

### Getting Help
- **Issues:** Report bugs or request features on [GitHub Issues](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC/issues)
- **Email:** [Your contact email]
- **Response Time:** We aim to respond within 48 hours

## 🔄 Upgrade Path

| From Version | To v1.25.288.7 | Notes |
|-------------|----------------|-------|
| v1.25.287.x | ✅ Direct upgrade | Seamless upgrade, settings preserved |
| v1.25.282.x | ✅ Direct upgrade | Seamless upgrade, settings preserved |
| v1.24.x.x | ✅ Direct upgrade | Recommended to backup configuration first |
| Earlier | ⚠️ Clean install | Recommend uninstalling old version first |

## 🎯 What's Next

We're constantly working to improve PDFRenamer. Upcoming features:
- Enhanced OCR capabilities
- More advanced renaming rules
- Improved performance for large file sets
- Additional file format support

## 📜 Version History

- **v1.25.288.7** (October 15, 2025) - Infrastructure improvements
- **v1.25.287.2** (October 14, 2025) - Previous stable release
- **v1.25.282.1** (October 9, 2025) - Initial public release

[View all releases →](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC/releases)

## ⚖️ License

[Your license information here]

## 🙏 Acknowledgments

- Built with ❤️ using .NET 9.0 and Blazor
- Icons by [icon provider]
- Special thanks to all contributors and testers

---

**Questions or feedback?** We'd love to hear from you!  
[Open an issue](https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC/issues) | [Email us](mailto:your-email@example.com)

**Enjoying PDFRenamer?** Consider leaving a ⭐ on GitHub!
