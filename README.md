# 🔥 Ian Musa's iOS Shortcuts API

My personal versioning system for iOS Shortcuts hosted on GitHub Pages. This is how I manage updates and downloads for all my shortcuts with a slick dark-themed interface and multiple API endpoints.

## 🚀 Live API

**Main Website**: https://musa-ian.github.io/Shortcuts-updates/

## 📡 My API Endpoints

| Endpoint | URL | Purpose |
|----------|-----|---------|
| **Main Database** | https://musa-ian.github.io/Shortcuts-updates/versions.json | Complete info with descriptions |
| **Simple List** | https://musa-ian.github.io/Shortcuts-updates/shortcuts-list.json | Clean array format |
| **Version Check** | https://musa-ian.github.io/Shortcuts-updates/latest.json | Just ID → version mapping |
| **API Docs** | https://musa-ian.github.io/Shortcuts-updates/api.json | Documentation |

## 📱 My Current Shortcuts

### Numerology Finder v3.1
- **Description**: Find your numerology number based on your name and birthdate
- **Download**: https://www.icloud.com/shortcuts/609b6287d17b43498effe6607a0f26ed
- **API ID**: `numerology-finder`

### Settings Lock v1.0
- **Description**: Lock your Settings app with Face ID
- **Download**: https://www.icloud.com/shortcuts/f0aaf685eecd44b8bef57fc77a47a128
- **API ID**: `settings-lock`
- **Requires**: [Actions App](https://apps.apple.com/app/actions/id1586435171)

## 📱 How Others Can Use My API

### Quick Version Check
```
1. Get Contents of URL: https://musa-ian.github.io/Shortcuts-updates/latest.json
2. Get Value for Key: shortcut-id (e.g., "numerology-finder")
3. Compare with current version
```

### Get Full Shortcut Info
```
1. Get Contents of URL: https://musa-ian.github.io/Shortcuts-updates/versions.json
2. Navigate: shortcuts → shortcut-id → version/download_url/description
```

## 🛠️ How I Manage This

### Adding New Shortcuts
When I release a new shortcut, I update:
1. **versions.json** - Main database with full details
2. **shortcuts-list.json** - Simple array format
3. **latest.json** - Version-only format
4. **api_info.total_shortcuts** - Increment count

### My Workflow
```bash
# Update JSON files
git add .
git commit -m "Add new shortcut: [name] v[version]"
git push origin main
# Changes go live automatically via GitHub Pages
```

## 📁 Repository Structure

```
├── index.html              # Dark-themed web interface with my branding
├── versions.json           # Main database (complete info)
├── shortcuts-list.json     # Simplified array format
├── latest.json            # Version checking format
├── api.json               # API documentation
└── README.md              # This file
```

## 🎨 Features

- **Dark Theme**: Custom black theme with gradient accents
- **My Branding**: "Ian Musa - iOS Shortcuts Developer"
- **Multiple Formats**: Different JSON structures for different use cases
- **Auto-Updates**: GitHub Pages auto-deploys changes
- **Mobile Optimized**: Works great on iPhone/iPad
- **Version Tracking**: Built-in API versioning

## 🔧 Technical Details

### JSON Structure
My main `versions.json` follows this format:
```json
{
  "shortcuts": {
    "shortcut-id": {
      "name": "Display Name",
      "version": "1.0",
      "download_url": "https://www.icloud.com/shortcuts/...",
      "last_updated": "2025-09-22",
      "description": "What it does"
    }
  },
  "api_info": {
    "version": "1.0",
    "last_updated": "2025-09-22",
    "total_shortcuts": 2
  }
}
```

### Shortcut ID Conventions
- Lowercase with hyphens: `settings-lock`, `numerology-finder`
- Descriptive but concise
- Never change once published (breaks API consumers)

## 🌟 Why I Built This

- **Version Management**: Easy way to track shortcut versions
- **Auto-Updates**: People can check for updates programmatically
- **Professional Presence**: Showcases my shortcuts with proper branding
- **API Experience**: Good practice building JSON APIs
- **Open Source**: Others can fork and use for their shortcuts

---

**Created by Ian Musa** - iOS Shortcuts Developer
**API Version**: 1.0
**Last Updated**: September 22, 2025
