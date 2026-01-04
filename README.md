# Google Sheet Transposer & Viewer

A simple web app that transforms Google Sheets data into a card-based record viewer. Instead of viewing data in a spreadsheet grid, browse through records one at a time with each column displayed as a labeled field.

[View Demo](https://transposer.alextran.org)

## Features

- Paste any public Google Sheet URL to load data
- View records one at a time in a clean card layout
- Navigate with arrow buttons or keyboard arrow keys
- Hide fields you don't need
- Shareable URLs - both the sheet and hidden fields are saved in the URL
- Mobile-friendly responsive design

## Usage

1. Make your Google Sheet publicly accessible
2. Copy the sheet URL
3. Paste it into the input field and click "Load"
4. Use the arrow buttons or keyboard to navigate between records
5. Hover over any field and click the X to hide it

You can share a direct link by appending `?sheet=<your-sheet-url>` to auto-load a specific sheet. Hidden fields are also preserved in the URL via the `hide` parameter (e.g., `?sheet=...&hide=0,2,5` hides columns 0, 2, and 5).

## Deployment

This is a static single-page app. Deploy to any static host or use Cloudflare Pages:

```bash
wrangler pages deploy
```

## How It Works

The app uses Google's Visualization API (gviz) via JSONP to fetch sheet data directly in the browser - no backend required. The first row of your sheet is used as field labels.
