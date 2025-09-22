# Shortcuts Versions (Static JSON)

A minimal static "database" you can host on GitHub Pages (or Vercel) to expose live version numbers for your iOS Shortcuts.

## Files
- `versions.json`: Source of truth. Add your shortcuts and versions here.
- `index.html`: Small viewer that fetches `versions.json` for quick verification.

## JSON format
```json
{
  "shortcuts": {
    "numerology-finder": {
      "name": "Numerology Finder",
      "version": "3.1"
    }
  }
}
```
- Keys under `shortcuts` should be URL-safe identifiers you choose (e.g. `numerology-finder`).
- Store user-facing name in `name` and version string in `version`.

## Add a new shortcut
1. Open `versions.json`.
2. Add a new entry under `shortcuts`:
```json
"your-shortcut-key": { "name": "Your Shortcut Name", "version": "1.0" }
```
3. Commit and push.

## Consume from iOS Shortcuts or apps
- Production URL (after GitHub Pages is enabled):
  - `https://<YOUR_USERNAME>.github.io/<YOUR_REPO>/versions.json`
- Example fetch (curl):
```bash
curl -s https://<YOUR_USERNAME>.github.io/<YOUR_REPO>/versions.json | jq .
```
- iOS Shortcuts: Use Get Contents of URL → `versions.json` URL → Get Dictionary → Get Dictionary Value `shortcuts` → Get Dictionary Value for your key → Get Dictionary Value `version`.

## Publish on GitHub Pages
1. Create a new GitHub repository (public is simplest).
2. Add these files and push to the `main` branch.
3. In the repo: Settings → Pages → Build and deployment → Source: `Deploy from a branch`.
4. Select branch `main`, folder `/ (root)`, Save.
5. Wait ~1–2 minutes, then visit `https://<YOUR_USERNAME>.github.io/<YOUR_REPO>/`.
   - `index.html` shows the viewer; append `/versions.json` to see raw JSON.

## GitHub Pages vs Vercel
- GitHub Pages: Simple, free, perfect for static JSON. No server required.
- Vercel: Also great, adds custom domains, headers, and edge caching if you need it later.

Recommendation: Start with GitHub Pages for this use case. Move to Vercel only if you later need custom headers, redirects, or advanced caching.
