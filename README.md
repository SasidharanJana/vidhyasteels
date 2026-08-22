# Vidhya Steel Furnitures — Website (v2, enhanced)

Same single-file, no-build, no-server approach as before, with more
sections modeled on patterns from established B2B manufacturer sites
(trust badges, tabbed category browser, benefit highlights, FAQ,
structured quote request) — all original content for Vidhya, not copied
from anywhere.

## What's new vs the first version

- **Top trust bar** — GST registered, manufacturer since 2017, location
- **Tabbed category browser** — click a category (Furniture, Wooden
  Furniture, Stainless Steel Fabrication, etc.) to see its items, instead
  of one long scrolling grid
- **Why Choose Us** — 6 benefit callouts (custom fabrication, durable
  build, competitive pricing, quick turnaround, GST billing, local service)
- **FAQ accordion** — 6 original questions relevant to furniture/steel
  fabrication buyers
- **Quote request form** — collects name, requirement, and details, then
  opens WhatsApp with a ready-to-send message. Nothing is stored or sent
  anywhere except through WhatsApp itself when the visitor chooses to send it.

## What I deliberately left out

Client logos and customer testimonials — sections like that only work if
they're real. I don't have real customer names, quotes, or logos to use,
and inventing them would be actively misleading to anyone visiting the
site. Once you have a few real customers willing to be quoted or named,
tell me and I'll add a proper section for it — it's a genuinely good
addition, just not one to fake in the meantime.

## Testing performed

Every interactive element was tested with real simulated clicks (not
direct function calls) in a proper JS engine:
- All 7 category tabs switch correctly and show the right items
- FAQ items open and close correctly, independently
- The quote form builds the correct WhatsApp message from name +
  requirement + details, and correctly refuses to proceed if the name
  field is empty
- Mobile menu toggle opens/closes
- Zero JavaScript errors across the full interaction sequence

## Deploying this

Identical process to before — see the earlier deployment steps for
`vidhya.smithtechnologysolutions.com` (Vercel, Framework Preset "Other",
add the subdomain, add the CNAME record it gives you). This file can
directly replace the previous `index.html` in that same repo.

## Updating content later

Everything is data-driven from arrays near the bottom of the `<script>`
tag — `PRODUCTS`, `WHY`, and `FAQ`. Edit an array entry and the relevant
section rebuilds itself; nothing else needs to change.
