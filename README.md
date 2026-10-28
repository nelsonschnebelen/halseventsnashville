# Hal's The Steakhouse — Nashville · Private Events

A standalone landing page for private events at **Hal's The Steakhouse, Nashville**.
Guests browse the spaces and submit a party request through the embedded
Tripleseat form.

## Structure

```
index.html          # the whole page (self-contained HTML + CSS + a little JS)
images/             # photography + logo
  hals-logo.png
  private-dining-room.jpg
  private-event.jpg
  starters.jpg
  table-spread.jpg
```

No build step — it's a single static page. Open `index.html` locally, or deploy
the folder to any static host (GitHub Pages, Netlify, Vercel, S3, …).

## The booking form

The "Request Your Date" section embeds the venue's **Tripleseat party-request
form** (Nashville, form `37321`) via an iframe, so submissions flow straight into
the Tripleseat account.

To switch to Tripleseat's official auto-resizing embed, grab the snippet from
**Tripleseat → Settings → Lead Forms → Embed** (it includes a `lead_form_id` and
`public_key`) and replace the iframe in `index.html` — there's a comment marking
the exact spot.

## Tracking

The **Meta (Facebook) Pixel** is installed in `<head>`, using the **same pixel
ID as hals.net** (`1146270633761669`) so this page reports into the same Meta
account. It fires `PageView` on load (matching the main site) and a custom
`RequestFormOpened` event when a visitor opens the booking form.

hals.net runs no other trackers (no Google Analytics, GTM, Ads, or other
pixels), so none are added here.

**Note on lead conversions:** the Tripleseat form is a cross-origin iframe, so
its submission can't be detected from this page. To count true submissions as a
Meta `Lead` event, add the pixel + Lead event inside Tripleseat (Settings → Lead
Forms → the form's tracking / confirmation settings, or a thank-you redirect).

## Still to add — the four room photos

"The Spaces" lists the four real private rooms with capacities — Conservatory
(6–14), Library (8–16), Study (12–24), 2nd Floor (24–64). Each card opens its
photo in a lightbox. Add these four files to `images/` and they appear
automatically; until a file exists, the lightbox falls back to a house photo:

- `images/conservatory.jpg`
- `images/library.jpg`
- `images/study.jpg`
- `images/second-floor.jpg`

Footer contact details are live: 407 Korean Veterans Blvd, Nashville, TN 37203 ·
(615) 560-7733 · NashvilleEvents@hals.net
