# 'Tis the Season Folkestone

Website for the 'Tis the Season Christmas pop-up shop in Folkestone, open 20 Nov – 24 Dec.

The whole site is one file, `index.html`. The makers, opening hours and event details are read from a Google Sheet each time the page loads, so day-to-day updates happen in the sheet, not here.

## Files

- `index.html` – the website
- `sheet-template.xlsx` – starting point for the Google Sheet (tabs: How to use, Vendors, Hours, Info)
- `images/` – maker photos (see `images/README.md`)
- `logo/` – the bauble logo as SVG, in white (for dark backgrounds) and navy (for light backgrounds)

## Connecting the Google Sheet

1. In Google Sheets, import `sheet-template.xlsx` (File → Import → Upload → Replace spreadsheet).
2. Share the sheet so that anyone with the link can view it.
3. Copy the sheet ID from its address: `docs.google.com/spreadsheets/d/THIS-PART/edit`
4. In `index.html`, paste it between the quotes in `const SHEET_ID = "";`

Until a sheet ID is set, the site shows example content.

## Adding maker photos

1. Upload the photo to the `images` folder in this repo (Add file → Upload files).
2. In the Vendors tab of the sheet, type the file name into `photo_1` (or `photo_2`, `photo_3`), e.g. `harbour-prints-1.jpg`.

The name must match exactly, capitals included. The photo appears once GitHub Pages has redeployed, usually within a minute or two.

## Hosting with GitHub Pages

Settings → Pages → Build and deployment → Deploy from a branch → `main` / root. The site will appear at `https://<username>.github.io/<repo-name>/`.
