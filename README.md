# Labelmaker — KSB Shipping Label System

A retro Windows 95-style shipping label generator built for **KSB Indonesia**.

![Labelmaker Screenshot](https://file.garden/ad-wGPVIV3ilAD_L/WORK%20PROJECT/LABEL%20MAKER/Icon/single%20label.png)

## 🚀 Live Demo

**GitHub Pages:** `https://YOUR_USERNAME.github.io/ksb-labelmaker/`

Replace `YOUR_USERNAME` with your actual GitHub username after deployment.

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Single Label** | Print one-off shipping labels with recipient/sender info |
| **Batch Labels** | Card entry mode or paste from Excel (columns A-G) |
| **Print History** | Track printed labels with timestamps |
| **Minesweeper** | Classic Windows 95 Minesweeper with best times |
| **Calculator** | Full-featured calculator with memory functions |
| **Google Sheets** | Auto-sync print history to Google Sheets (optional) |

## 🖨 Label Layouts

- 1 × 1 (default)
- 1 × 2
- 2 × 2
- 2 × 3
- 3 × 2
- 3 × 3

All layouts optimized for **A4 Landscape** printing.

## 📋 Excel Paste Format

Paste tab-separated data with columns:

| A | B (Penerima) | C | D | E | F (Address + Phone) | G (Attn) |
|---|-------------|---|---|---|---------------------|----------|
| — | PT EMBLEM ASIA | — | — | — | MM2100 INDUSTRIAL TOWN... (08123456789) | IBU ARNETA |

## 🔧 Setup

### 1. Deploy to GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Under **Source**, select **Deploy from a branch → main**
4. Your site will be live at `https://YOUR_USERNAME.github.io/ksb-labelmaker/`

### 2. Google Sheets Integration (Optional)

To enable print history sync:

1. Create a new Google Sheet
2. Open [script.google.com](https://script.google.com) → New Project bound to that sheet
3. Paste the Apps Script code (found in the app under **History → Google Sheets Backup**)
4. Deploy → New Deployment → **Web app**
   - Execute as: **Me**
   - Who has access: **Anyone**
5. Copy the Web App URL
6. In the Labelmaker app, go to **History** and enter the URL in the config field

### 3. CORS for GitHub Pages

If hosting on GitHub Pages, update your Apps Script `doPost()` to allow your domain:

```javascript
function doPost(e) {
  // ... your existing code ...

  return ContentService.createTextOutput(JSON.stringify({success: true}))
    .setMimeType(ContentService.MimeType.JSON)
    .setHeader('Access-Control-Allow-Origin', 'https://YOUR_USERNAME.github.io');
}
```

## 🎨 Credits

- **Design:** Windows 95 aesthetic with custom KSB branding
- **Fonts:** VCR OSD Mono, MS Sans Serif, Helvetica Neue
- **Icons:** Custom KSB icon set
- **Built for:** KSB Indonesia Shipping Department

## 📄 License

Internal use only — KSB Indonesia.
