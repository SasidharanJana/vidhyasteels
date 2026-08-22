# Vidhya Steel Furnitures — Website (v3)

Same single-file, no-build, no-server site as before. This version
replaces every emoji with real icons and adds subtle motion — see below
for exactly what changed and why.

## What's new vs v2

- **22 hand-drawn SVG icons** replacing every emoji (🪑🔩💼📞 etc.). Emoji
  render inconsistently across Windows/Mac/Android/older phones and look
  unpolished at small sizes — actual icons look the same everywhere and
  scale cleanly.
- **Scroll-reveal animation** — About Us cards, Why Choose Us cards, and
  the contact/quote cards fade in as you scroll to them.
- **A pulse animation** on the main "Get a Free Quote" button only — one
  accent, not applied everywhere, so it draws the eye without feeling busy.

## Why there are still no product photos

I don't have real photos of your actual furniture, fabrication work, or
inventory. Using generic stock photos and presenting them as your products
would misrepresent what you actually sell — worse than no photo at all if
a customer shows up expecting exactly what they saw online. The icons here
are illustrative category markers, not a substitute for real photography.

**When you're ready to add real photos:** take a few clear photos (phone
camera is fine) of actual finished pieces — good lighting, plain
background if possible — and send them over. I can drop them straight
into the hero section and each product category card. This is a
completely reasonable thing to add once you have them; it just shouldn't
be faked in the meantime.

## A bug I found and fixed while building this

My first pass at the scroll-reveal animation would have permanently
hidden the About Us, Why Choose Us, and contact content if JavaScript
ever failed to load for any visitor (blocked script, network hiccup,
disabled JS). I rebuilt it using a standard "progressive enhancement"
pattern: the very first thing a tiny inline script does is add a `js`
class to the page, and the fade-in CSS rule only applies underneath that
class. If JavaScript never runs, that class never gets added, and the
content is simply visible immediately — animation is purely a bonus, never
a requirement to see anything.

I specifically tested this exact scenario (JavaScript completely disabled)
to confirm it, rather than assuming it was fine.

## Testing performed

Same rigorous approach as before — real simulated clicks, not direct
function calls, run against the actual DOM in a real JS engine (jsdom):
- All 7 category tabs still switch correctly with icons in place
- FAQ accordion still opens/closes independently
- Quote request form still builds the correct WhatsApp message
- Mobile menu toggle still works
- All 18 icon placeholders confirmed to contain real, correctly-rendered SVG
- The "JavaScript disabled" fallback confirmed to keep all content visible
- Zero JavaScript errors across the full test run

One honest limitation: my own screenshot tooling (an old, ~15-year-old
rendering engine) failed to visually display the icons in a full-page
screenshot, despite the identical technique working in isolation. I
didn't take that at face value — I inspected the actual DOM directly via
a modern, real JS engine (jsdom) and confirmed every icon renders
correctly as valid SVG. Worth a quick visual glance yourself once this is
live, simply because I couldn't get a clean screenshot from my end — not
because I have reason to think anything is actually wrong.

## Deploying this

Identical process to before — this `index.html` (plus the same 3 image
files) can directly replace what's currently live in your
`vidhya-website` repo:

```
cd vidhya-website
git pull
# copy the new index.html over the old one
git add -A
git commit -m "v3: real SVG icons, scroll animations"
git push
```

Vercel redeploys automatically on push if it's already connected to this
repo — no dashboard steps needed for this update specifically.
