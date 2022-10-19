# GSheets NFT Slideshow

This web app makes it easy to curate & display media slideshows (ideal for NFTs) using Google Sheets as the back end / admin interface.

## How it works
1. Copy and save this [google sheet template](https://docs.google.com/spreadsheets/d/19vLAcJ1chfbkRZGzwcbt1pIDednMHTSXtNI86eGh0s0/edit#gid=654882609).
   * Each sheet in the workbook can be a playlist
   * Each row per sheet is a single NFT. The sample sheet shows the fields required for each NFT you want to display.  
   * NFTs can be of type: Image, Video or Generator.  Generator is for certain NFTs (e.g., Art Blocks) where the output is a script rather than a static media file -- Generators are displayed using <iframe>s.

2. Set up an account at [sheet.best](https://sheet.best), which makes it easy to access Google Sheets data via API. 
* configure env.js

env = {
  SHEET_BEST_CONNECTION_ID: 'your-connection-id'
}

(you can put it in your local repo)

* deploy.  this is designed to work on netlify but could work elsewhere.
