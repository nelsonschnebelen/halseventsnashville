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

## Still to confirm (placeholders in `index.html`)

- Street address, phone number, and events email (in the footer)
- Private-room capacities (currently 14 / 40 / 180)
