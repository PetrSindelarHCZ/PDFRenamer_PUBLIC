# Release v1.25.288.7

**Release Date:** October 15, 2025

## Overview

This release introduces **Distribution Repository Sync Automation**, a powerful new feature that automatically synchronizes releases from the private development repository to the public distribution repository. This streamlines the release process and ensures end-users always have access to the latest versions.

## What's New

### 🚀 Major Features

#### Distribution Repository Sync Automation
- **Automatic Sync Script** (`sync_to_distribution.ps1`)
  - Automatically clones and syncs to the public distribution repository
  - Copies installers (Bundle EXE + ZIP archive) to distribution repo
  - Copies release notes and user documentation
  - Creates GitHub releases automatically in the distribution repo
  - Supports dry-run mode for testing without making changes
  - Includes comprehensive error handling and cleanup

- **Integrated Release Workflow**
  - Added `-SyncToDistribution` parameter to `create_release.ps1`
  - One-command release creation and distribution sync
  - Automatic fallback if sync fails (doesn't break release process)

- **VS Code Integration**
  - **Release: Sync to Distribution Repo** - Manual sync task
  - **Release: Full Release + Distribution Sync** - Complete automated workflow
  - **Release: Full Release + Distribution Sync (AI-Powered)** - AI + automation

### 📚 Documentation

- **Scripts/README-SYNC.md** - Comprehensive sync documentation
  - Complete usage guide with examples
  - Parameter reference
  - Troubleshooting section
  - Manual sync instructions
  - Security considerations
  
- **RELEASES/README.md** - Updated release guide
  - Added Step 8: Distribution Repository Sync
  - Integration examples with existing workflow
  - Best practices for public releases

### 🛠️ Previous Features (from v1.25.288.6)

#### AI-Powered Release Notes Generation
- Support for 3 AI providers: GitHub Copilot CLI, OpenAI, Ollama
- Automatic commit analysis and categorization
- Auto-detection of available AI providers
- User-friendly release note generation

#### Build System Improvements
- Fixed PowerShell compatibility issues (migrated to pwsh)
- Resolved build script exit code issues
- ZIP archive distribution (in addition to EXE installer)
- Enhanced error handling throughout build process

## Installation

### Download

**Latest Version:** v1.25.288.7

**Installation Files:**
- **PDFRenamer-Setup-1.25.288.7.exe** (Bundle Installer) - Recommended
- **PDFRenamer-1.25.288.7.zip** (Installation Archive) - For manual/enterprise deployment

### Installation Instructions

#### Option 1: Bundle Installer (Recommended)
1. Download `PDFRenamer-Setup-1.25.288.7.exe`
2. Run the installer
3. Follow the installation wizard
4. Launch PDFRenamer from Start Menu

#### Option 2: ZIP Archive (Enterprise/Manual)
1. Download `PDFRenamer-1.25.288.7.zip`
2. Extract to desired location
3. Run the included MSI installer
4. Configure according to your enterprise policies

### Upgrade Instructions

**Upgrading from previous versions:**
1. Stop PDFRenamer if it's running
2. Run the new installer
3. Choose "Upgrade" when prompted
4. Your settings and configurations will be preserved
5. Restart PDFRenamer

## Usage

### For Developers: Syncing Releases

#### Quick Start
```powershell
# Create release and automatically sync to distribution repo
.\Scripts\create_release.ps1 -UseAI -SyncToDistribution

# Or sync separately after release
.\Scripts\sync_to_distribution.ps1
```

#### VS Code Tasks
Press `Ctrl+Shift+P` → **Tasks: Run Task** → Choose:
- **Release: Full Release + Distribution Sync**
- **Release: Full Release + Distribution Sync (AI-Powered)**

#### Testing Before Sync
```powershell
# Dry run - see what would be synced without making changes
.\Scripts\sync_to_distribution.ps1 -DryRun

# Prepare locally without pushing to GitHub
.\Scripts\sync_to_distribution.ps1 -SkipPush
```

### What Gets Synced

**From:** https://github.com/PetrSindelarHCZ/PDFRenamer (Private)  
**To:** https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC (Public)

**Files Synced:**
- ✅ Bundle installer (EXE)
- ✅ Installation archive (ZIP)
- ✅ Release notes (user-friendly format)
- ✅ README and setup guides
- ✅ GitHub release with attachments

## Technical Details

### New Scripts

**sync_to_distribution.ps1**
- **Lines:** 280+
- **Purpose:** Automate distribution repository synchronization
- **Parameters:** `-Version`, `-DistributionRepoPath`, `-SkipClone`, `-SkipPush`, `-DryRun`
- **Features:** Auto-detection, verification, error handling, cleanup

### Modified Scripts

**create_release.ps1**
- Added `-SyncToDistribution` parameter
- Integrated sync workflow as Step 9
- Graceful error handling for sync failures

### New Documentation

- `Scripts/README-SYNC.md` (250+ lines)
- Updated `RELEASES/README.md` (Step 8 added)
- Enhanced distribution repository guides

### VS Code Tasks

Added 3 new tasks to `.vscode/tasks.json`:
1. Release: Sync to Distribution Repo
2. Release: Full Release + Distribution Sync
3. Release: Full Release + Distribution Sync (AI-Powered)

### Build Information

**Version:** 1.25.288.7  
**Build Date:** October 15, 2025  
**.NET Version:** 9.0  
**Platform:** Windows 10/11 (64-bit)  
**PowerShell:** 7.0+ (pwsh) required for scripts

## Configuration

No configuration changes required. The distribution sync uses these defaults:

- **Distribution Repo URL:** https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC.git
- **Temp Directory:** `$env:TEMP\PDFRenamer_Distribution_Sync`
- **Target Branch:** `main`

To customize, edit `Scripts/sync_to_distribution.ps1` configuration section.

## Known Issues

None at this time.

## Breaking Changes

None. This release is fully backward compatible.

## Dependencies

### For Distribution Sync Feature
- **GitHub CLI (`gh`)** - Required for creating GitHub releases
- **Git** - Required for cloning and pushing to distribution repo
- **PowerShell 7+** - Required for running sync scripts

All other existing dependencies remain unchanged.

## Security Notes

- Distribution repository sync only copies public-facing files
- No source code or internal documentation is synced
- Release files are automatically scanned by GitHub for malware
- Consider code signing for additional trust (see `Scripts/sign_file.py`)

## Rollback Procedure

If you need to rollback this release:

```powershell
# Delete the tag locally
git tag -d v1.25.288.7

# Delete the tag remotely
git push origin :refs/tags/v1.25.288.7

# Delete the GitHub release
gh release delete v1.25.288.7 --yes

# For distribution repo
gh release delete v1.25.288.7 --repo PetrSindelarHCZ/PDFRenamer_PUBLIC --yes
```

## Testing

This release has been tested with:
- ✅ Dry-run mode verification
- ✅ File verification checks
- ✅ Error handling scenarios
- ✅ PowerShell 7.x compatibility
- ✅ GitHub CLI integration
- ✅ VS Code task execution

## Commit History

This release includes the following commits:

1. **695d065** - feat: add distribution repository sync automation
   - Created sync_to_distribution.ps1 (280+ lines)
   - Added 3 new VS Code tasks
   - Integrated with create_release.ps1
   - Comprehensive documentation

2. **d78d46f** - chore: remove test release notes file v1.25.288.6.md
   - Cleaned up test artifacts
   - Removed temporary files

## Full Changelog

**Compare:** [v1.25.287.2...v1.25.288.7](https://github.com/PetrSindelarHCZ/PDFRenamer/compare/v1.25.287.2...v1.25.288.7)

### All Changes in This Build Cycle
- 695d065 - Distribution repository sync automation
- d78d46f - Cleanup test release artifacts
- 74940eb - AI-powered release notes generation
- 59e49b7 - PowerShell compatibility fixes
- a52bb52 - Build script exit code fix
- 80ac77d - ZIP archive distribution format
- 17f3b8d - VS Code task automation

## Acknowledgments

Special thanks to:
- GitHub Copilot for AI assistance in development
- WiX Toolset team for installer framework
- .NET team for the excellent runtime

## Support

**For Issues or Questions:**
- GitHub Issues: https://github.com/PetrSindelarHCZ/PDFRenamer/issues
- Documentation: https://github.com/PetrSindelarHCZ/PDFRenamer/tree/master/RELEASES

## Next Steps After Installation

1. ✅ Verify release on GitHub
2. ✅ Test download and installation
3. ✅ Sync to distribution repository (for maintainers)
4. ✅ Announce release to users

## Resources

- **Main Repository:** https://github.com/PetrSindelarHCZ/PDFRenamer
- **Distribution Repository:** https://github.com/PetrSindelarHCZ/PDFRenamer_PUBLIC
- **Release Process Guide:** [RELEASES/README.md](README.md)
- **Sync Guide:** [Scripts/README-SYNC.md](../Scripts/README-SYNC.md)
- **AI Release Notes Guide:** [RELEASES/AI-RELEASE-NOTES.md](AI-RELEASE-NOTES.md)

---

**Published:** October 15, 2025  
**Author:** Petr Šindelář  
**License:** [Check repository for license information]
