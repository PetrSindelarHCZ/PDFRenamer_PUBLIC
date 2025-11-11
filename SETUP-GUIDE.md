# Distribution Repository Setup Guide

This guide shows you how to structure your public distribution repository.

## Repository Structure

```
PDFRenamer-Distribution/
├── README.md                          # Main repository readme (user-facing)
├── LICENSE                            # Your license file
├── docs/
│   ├── USER-MANUAL.md                # Complete user guide
│   ├── QUICK-START.md                # 5-minute getting started guide
│   ├── FAQ.md                        # Frequently asked questions
│   └── TROUBLESHOOTING.md            # Common problems and solutions
└── .github/
    └── ISSUE_TEMPLATE/
        ├── bug_report.md
        └── feature_request.md
```

## Files Created

The following files have been created in `DistributionRepo/`:

1. **README.md** - Main repository readme
   - User-friendly, no developer jargon
   - Clear download instructions
   - System requirements
   - Quick start guide
   - Enterprise deployment info

2. **RELEASE-v1.25.315.2.md** - Release notes for v1.25.315.2
   - What'\''s new summary
   - Download links
   - Installation instructions
   - Upgrade guide
   - Configuration details
   - Support information

## How to Use These Files

### 1. Copy to Your Distribution Repository

```powershell
# Copy the files to your distribution repo
Copy-Item DistributionRepo\README.md <your-distribution-repo-path>\
Copy-Item DistributionRepo\RELEASE-v1.25.315.2.md <your-distribution-repo-path>\
```

### 2. Create Release on GitHub

When creating a release on GitHub:

1. Go to your distribution repo
2. Click "Releases" → "Create a new release"
3. Tag: `v1.25.315.2`
4. Title: `PDFRenamer v1.25.315.2`
5. Copy content from `RELEASE-v1.25.315.2.md` into the description
6. Upload your installer files:
   - `PDFRenamer-Setup-1.25.315.2.exe`
   - `PDFRenamer-1.25.315.2.zip`

### 3. Update Links

The README uses relative GitHub links like:
- `../../releases/latest` - Links to latest release
- `../../releases` - Links to all releases
- `../../issues` - Links to issues

These will work automatically once the repo is published.

## Key Differences from Private Repo

### Private Repo (Development)
- Source code
- Build scripts
- Development documentation
- Internal technical details
- CI/CD configuration

### Public Repo (Distribution)
- User documentation only
- Installer downloads
- Release notes
- Support information
- No source code

## What to Include

✅ **DO Include:**
- User-friendly README
- Release notes for each version
- User manual and guides
- FAQ and troubleshooting
- System requirements
- Installation instructions
- Support contact information

❌ **DON'\''T Include:**
- Source code
- Build scripts
- Development tools
- Internal documentation
- API keys or secrets
- Private company information

## Maintaining the Distribution Repo

### For Each New Release:

1. **Create release notes** using this template:
   ```markdown
   # PDFRenamer v[VERSION]
   
   **Release Date:** [DATE]
   
   ## What'\''s New
   [User-friendly summary]
   
   ## Download
   [Download links]
   
   ## Installation
   [Instructions]
   ```

2. **Update README** if:
   - System requirements change
   - Configuration options change
   - New features affect users
   - Support contact changes

3. **Create GitHub Release**:
   - Tag with version number
   - Upload installer files
   - Copy release notes as description

### Automation

You can automate copying release files from private to public repo:

```powershell
# After building release in private repo
$version = "1.25.315.2"
$privateRepo = "E:\Source\Repos\HCZ\PDFRenamer"
$publicRepo = "E:\Source\Repos\HCZ\PDFRenamer-Distribution"

# Copy installers
Copy-Item "$privateRepo\Output\Artifacts\PDFRenamer-Setup-$version.exe" "$publicRepo\"
Copy-Item "$privateRepo\Output\Artifacts\PDFRenamer-$version.zip" "$publicRepo\"

# Copy release notes (if you want to version them)
Copy-Item "DistributionRepo\RELEASE-v$version.md" "$publicRepo\releases\"
```

## Example Public Repos to Reference

Well-managed distribution repositories:
- **Visual Studio Code** - github.com/microsoft/vscode (releases only)
- **OBS Studio** - github.com/obsproject/obs-studio
- **Notepad++** - github.com/notepad-plus-plus/notepad-plus-plus

## Tips for User-Friendly Distribution

1. **Clear Language**: Avoid technical jargon
2. **Visual Appeal**: Use emojis, badges, formatting
3. **Quick Access**: Put download links prominently
4. **Support Info**: Make it easy to get help
5. **Version History**: Keep changelog visible
6. **Screenshots**: Add screenshots of the application
7. **Video Demos**: Consider adding a demo video link

## Questions?

If you need to adjust these files for your specific needs, the templates are flexible and can be modified.
