# GSheets NFT Slideshow

This web app makes it easy to curate & display media slideshows (ideal for NFTs) using Google Sheets as the back end / admin interface.

This is built to deploy on [Netlify](https://netlify.com), but of course can be edited for other environments.

## Getting Started

1. Copy and save this [google sheet template](https://docs.google.com/spreadsheets/d/19vLAcJ1chfbkRZGzwcbt1pIDednMHTSXtNI86eGh0s0/edit#gid=654882609).
   * Each sheet in the workbook can be a playlist.  You can create multiple playlists by duplicating the first playlist sheet.
   * Each row per sheet is a single NFT. The sample sheet shows the fields required for each NFT you want to display.  
   * NFTs can be of type: Image, Video or Generator.  Generator is for certain NFTs (e.g., Art Blocks) where the output is a script rather than a static media file -- Generators are displayed using <iframe>s.

2. Set up an account at [sheet.best](https://sheet.best), which makes it easy to access Google Sheets data via API. Create a new Connection.  

3. Configure environmental vars
   * your Sheet Best connection URL will be stored as an environmental variable, and used to make API calls via Javascript.
   * create a file named `env.js`.  it should look like this:
     ```      
        env = {
          SHEET_BEST_CONNECTION_URL: 'your-connection-url'
        }
     ```
     Note: `env.js` file is for local development only, and will be ignored by Git when you commit.
   * In your netlify application settings, create a new environmental variable called SHEET_BEST_CONNECTION_URL and add your URL there.
   * When you deploy to Netlify, `netlify.toml` will collect your environmental variables from your app config and make them available to javascript via `env.js`.  (Hat tip for this trick to [Simone Web Design](https://simonewebdesign.it/how-to-get-environment-variables-in-the-browser/))
 
 4. Test
    * if you're working locally, run `netlify dev` from the command line (requires the [Netlify CLI Client](https://cli.netlify.com/))
    * Whenever you run the app, you'll need to add a query parameter `tab` which specifies which tab in the spreadsheet you're using.  For example, a Netlify development URL would look like `http://localhost:8888/?tab=Sample_Vertical` where `Sample_Vertical` is the exact name of the tab for this slideshow.
    * Another optional parameter is `slide_timing` which specifies an amount of time for each item, in seconds (the default is 30).
    
  5. Deploy
    * push to Netlify and enjoy! 

