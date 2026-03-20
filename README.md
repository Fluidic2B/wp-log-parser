# wp-log-parser
WP Activity Log parser tool

A lightweight, browser-based tool for parsing raw plugin event data from the [WP Activity Log](https://melapress.com/wordpress-activity-log/) WordPress plugin. Paste your raw log output and instantly get a clean, alphabetized list of plugin changes.

---

## What It Does

WP Activity Log records every change on your WordPress site, including plugin installs and updates. The raw log data is messy — packed with timestamps, usernames, IP addresses, and other noise. This tool strips all of that away and gives you a clean, readable summary in seconds.

**Handles two event types:**

| Event Code | Type | Output Format |
|---|---|---|
| 5000 | New plugin install | `Plugin Name 1.0.0 (new install)` |
| 5004 | Plugin update | `Plugin Name 1.0.0 → 1.1.0` |

---

## How To Use

1. Open the tool in any browser
2. In WP Activity Log, search for `Installed the plugin` and/or `Updated the plugin` to surface the relevant entries
3. Copy the raw log output and paste it into the textarea
4. Click **Parse Log**
5. A clean, alphabetized list appears instantly
6. Use the **Copy to Clipboard** button to grab the plain text output

You can mix 5000 and 5004 entries in the same paste — the tool handles both in one pass.

---

## Example

**Raw input (paste this in):**
```
5004March 20, 2026 11:33:20.000 am
WP Admin Administrator192.168.1.100PluginUpdated
Updated the plugin LiteSpeed Cache. Updated version: 7.8.0.1 Install location: litespeed-cache Previous version: 7.8 View plugin information
5000 20 March, 2026 11:10:21.000 am
wpadmin Administrator192.168.1.101PluginInstalled
Installed the plugin WPML SEO. Version: 2.2.5 Install location: /wp-content/plugins/plugin.php
```

**Clean output:**
```
LiteSpeed Cache 7.8 → 7.8.0.1
WPML SEO 2.2.5 (new install)
```

---

## Features

- No installation, no dependencies, no server required
- Runs entirely in the browser — nothing is sent anywhere
- Handles mixed 5000 and 5004 entries in a single paste
- Results sorted A–Z (case-insensitive)
- Displays a visual list with color-coded badges (blue = update, green = new install)
- Shows a summary count of total changes, updates, and new installs
- One-click plain text copy for use in emails, docs, or reports
- Load Sample button to test the tool with example data

---

## WP Activity Log — Free vs Premium Note

The free edition of WP Activity Log only supports basic keyword search. To surface plugin events:

- Search for `Installed the plugin` to find 5000 entries
- Search for `Updated the plugin` to find 5004 entries
- Paste both result sets together into this tool

The Premium edition supports structured Event ID filtering, which lets you filter by `(Event ID is 5000) OR (Event ID is 5004)` in one search.

---

## Running Locally

No setup needed. Just download `index.html` and open it in any browser — Chrome, Edge, or Firefox. Works completely offline.

---

## Deploying

Since this is a single self-contained HTML file it can be deployed anywhere:

- **GitHub Pages** — push `index.html` to a repo and enable Pages under Settings
- **Any web server** — drop the file in any directory and access it via URL
- **WordPress site** — upload via FTP to any directory (e.g. `/wp-content/uploads/tools/`)
- **Netlify / Vercel** — drag and drop the file for an instant live URL

---

## Privacy

This tool runs entirely client-side. No data is transmitted, logged, or stored anywhere. Everything stays in your browser.

---

## License

MIT — free to use, modify, and distribute.
