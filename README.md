# 📱 iOS Shortcuts Versions API

A complete versioning system for iOS Shortcuts hosted on GitHub Pages. Provides multiple API endpoints optimized for both web browsers and iPhone Shortcuts app integration.

## 🚀 Quick Start

1. **Web Interface**: Visit your GitHub Pages URL to see all shortcuts
2. **iPhone Shortcuts**: Use the JSON API endpoints to check versions programmatically
3. **Direct Downloads**: Each shortcut includes an iCloud download link

## 📡 API Endpoints

| Endpoint | Purpose | Best For |
|----------|---------|----------|
| `versions.json` | Complete database with all info | Full shortcut details, descriptions |
| `shortcuts-list.json` | Simplified list format | Quick browsing, mobile apps |
| `latest.json` | Version numbers only | Fast version checking |
| `api.json` | API documentation | Understanding available endpoints |

## 📱 Using with iPhone Shortcuts

### Basic Version Check
```
1. Add "Get Contents of URL" action
2. URL: https://yourusername.github.io/Shortcuts-updates/latest.json
3. Add "Get Value for Key" action
4. Key: your-shortcut-id
5. Compare result with current version
```

### Full Shortcut Info
```
1. Add "Get Contents of URL" action
2. URL: https://yourusername.github.io/Shortcuts-updates/versions.json
3. Add "Get Value for Key" actions:
   - shortcuts.your-shortcut-id.version
   - shortcuts.your-shortcut-id.download_url
   - shortcuts.your-shortcut-id.description
```

## ➕ Adding New Shortcuts

### 1. Update `versions.json`
```json
{
  "shortcuts": {
    "your-shortcut-id": {
      "name": "Your Shortcut Name",
      "version": "1.0",
      "download_url": "https://www.icloud.com/shortcuts/your-actual-shortcut-id",
      "last_updated": "2024-09-22",
      "description": "What your shortcut does"
    }
  }
}
```

### 2. Update simplified endpoints
- Add to `shortcuts-list.json` for the list view
- Add to `latest.json` for quick version checks
- Update `total_shortcuts` count in `versions.json`

### 3. Commit and push
Changes go live automatically via GitHub Pages!

## 🔧 File Structure

```
├── index.html              # Web interface
├── versions.json           # Main database
├── shortcuts-list.json     # Simplified list
├── latest.json            # Version numbers only
├── api.json               # API documentation
└── README.md              # This documentation
```

## 🎯 Best Practices

### Shortcut IDs
- Use lowercase with hyphens: `my-awesome-shortcut`
- Keep them short but descriptive
- Don't change IDs once published (breaks existing shortcuts)

### Version Numbers
- Use semantic versioning: `1.0`, `1.1`, `2.0`
- Increment for any functionality changes
- Update `last_updated` date when changing versions

### iCloud Links
- Get the actual shortcut ID from the iCloud share URL
- Test links before publishing
- Format: `https://www.icloud.com/shortcuts/ACTUAL_SHORTCUT_ID`

## 🔍 Example iPhone Shortcut

Here's how to create a shortcut that checks for updates:

1. **Get URL Contents**: `https://yourusername.github.io/Shortcuts-updates/latest.json`
2. **Get Dictionary Value**: Key = `your-shortcut-id`
3. **Set Variable**: Name = `LatestVersion`
4. **If Condition**: `LatestVersion` > `CurrentVersion`
5. **Show Notification**: "Update available!"

## 🌐 GitHub Pages Setup

1. Go to your repo Settings > Pages
2. Source: Deploy from a branch
3. Branch: `main`
4. Folder: `/ (root)`
5. Your API will be available at: `https://yourusername.github.io/repo-name/`
