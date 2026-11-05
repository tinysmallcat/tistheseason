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

## Changing the colours

Every colour on the site can be set in the Info tab of the sheet (setting in column A, value in column B). Use a hex code (`#7a1f2b`) or a colour name (`gold`). Leave a value blank, or leave the row out, to use the standard colour.

| setting | what it colours | standard |
|---|---|---|
| `header_colour` | top bar, header band and footer | `#132640` |
| `header_text_colour` | text and logo on the header | automatic |
| `accent_colour` | dates line on the header; base for the accents | `#ff8a75` |
| `accent_on_light_colour` | maker categories, labels and buttons on the light page | darker shade of accent (`#c4472f`) |
| `button_text_colour` | text on buttons | `#ffffff` |
| `background_colour` | page background | `#eef1f6` |
| `text_colour` | main body text | `#132640` |
| `light_text_colour` | taglines, notes and other secondary text | `#4c5a72` |
| `border_colour` | lines and borders | `#c8d0de` |
| `card_colour` | maker cards | `#fbf7ec` |
| `panel_colour` | boxes on maker and visit pages, filter buttons | `#ffffff` |

With no page colours set, visitors in dark mode get a built-in dark version of the site. Setting any page colour (background, text, light text, border, card or panel) turns that off, so everyone sees exactly the sheet's colours. Header text picks light or dark automatically unless `header_text_colour` is set.

## Adding maker photos

1. Upload the photo to the `images` folder in this repo (Add file → Upload files).
2. In the Vendors tab of the sheet, type the file name into `photo_1` (or `photo_2`, `photo_3`), e.g. `harbour-prints-1.jpg`.

The name must match exactly, capitals included. The photo appears once GitHub Pages has redeployed, usually within a minute or two.

## Hosting with GitHub Pages

Settings → Pages → Build and deployment → Deploy from a branch → `main` / root. The site will appear at `https://<username>.github.io/<repo-name>/`.
