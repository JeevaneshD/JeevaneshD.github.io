# Evaion Echo — flagship storefront

A complete, responsive, **HTML + CSS only** storefront for **Evaion Echo**, the
single flagship headphone from Evaion. The build covers the full customer-facing
journey — homepage, product page, cart drawer, checkout, confirmation, support,
warranty, shipping and legal pages — with every interaction driven by CSS.

The visual direction is **quiet precision**: sentence-case display type, inset
deep-violet panels, pale lavender fields and carefully rationed Liquid Glass.
Photography and generous whitespace carry the page; the interface should feel
like a precision object in a calm gallery rather than a loud campaign. It is
built from Evaion’s own violet, ink and paper palette rather than a generic
template.

> **Launch status:** front-end demonstration. Product specifications, company
> details, policies and order information are clearly labelled sample copy, not
> verified facts. No payment is processed and no real order is created.

---

## 1. Stack and constraints

| Item | Decision |
| --- | --- |
| Markup | Semantic HTML5, one shared header/footer/cart system |
| Styling | Three hand-written stylesheets: `css/style.css` (base and interactions), `css/editorial.css` (composition layer) and `css/premium.css` (final premium finish) |
| JavaScript | **None.** No `<script>`, no inline handlers, no libraries |
| Fonts | Self-hosted Inter, IBM Plex Mono and Newsreader italic subsets |
| Images | Local WebP/PNG/JPG/SVG; no third-party requests |
| Build step | None. Open the files or serve the folder |
| Commerce | CSS-only demonstration of a hosted-checkout flow |

Interactions use native form controls: checkboxes for navigation and the cart,
radios for galleries and quantities, `<details>` for FAQs, and CSS `:has()` for
state-dependent styling. The mechanism is a static inline SVG diagram; no
content depends on scroll position or script.

`premium.css` is loaded after `editorial.css` on all 11 pages. It is the final
visual layer: revised tokens, sentence-case type, Newsreader accents, soft
geometry, inset deep-violet panels, pale lavender gallery, selective Liquid
Glass and the opacity-only gallery crossfade. `editorial.css` owns the shared
grid and composition; `style.css` continues to own the base system and every
CSS-only interaction. Keeping the premium finish in its own file makes the last
layer auditable instead of adding more overrides to the editorial sheet.

---

## 2. Run locally

```powershell
cd "D:\Project ion\evaion"
python -m http.server 8080
```

Open <http://localhost:8080/>.

Opening `index.html` directly also works, but a local server gives consistent
paths for fonts and images. No package manager, compiler or framework is needed.

---

## 3. Page map

| File | URL | Purpose | Indexed |
| --- | --- | --- | --- |
| `index.html` | `/` | Premium homepage: inset ink hero with glass facts, “Echo.” ledger with overlapping portrait, deep-violet mechanism panel, materials, pale-lavender in-use gallery, quiet numbers, deep-violet closing CTA | Yes |
| `echo.html` | `/echo.html` | Flagship product page: Echo display band, four-view crossfade gallery, glass buy panel, box, design notes, specs, care, FAQ, compliance, violet CTA | Yes |
| `technology.html` | `/technology.html` | Mechanism, Bio-Energy framework, materials and selected specifications | Yes |
| `about.html` | `/about.html` | Studio, principles, Hyderabad and the design point of view | Yes |
| `support.html` | `/support.html` | Support routes, care and charging, warranty, delivery and contact | Yes |
| `shipping.html` | `/shipping.html` | Delivery, tracking and the 14-day return process | Yes |
| `warranty.html` | `/warranty.html` | Two-year cover, exclusions, claims and service | Yes |
| `privacy.html` | `/privacy.html` | What is collected, why, who it is shared with and how to exercise choices | Yes |
| `terms.html` | `/terms.html` | Website and sale terms, demonstration limits and governing law | Yes |
| `checkout.html` | `/checkout.html` | Static hosted-checkout demonstration | No — `noindex` |
| `confirmation.html` | `/confirmation.html` | Demonstration order confirmation | No — `noindex` |

`robots.txt` and `sitemap.xml` list only the nine public pages.

---

## 4. File structure

```text
evaion/
├─ index.html
├─ echo.html
├─ technology.html
├─ about.html
├─ support.html
├─ shipping.html
├─ warranty.html
├─ privacy.html
├─ terms.html
├─ checkout.html
├─ confirmation.html
├─ README.md
├─ design-system.md
├─ .env.example                  production reference only — not read by this build
├─ robots.txt
├─ sitemap.xml
├─ css/
│  ├─ style.css                  base design system, page styles and CSS interactions
│  ├─ editorial.css              shared grid and composition layer
│  └─ premium.css                final premium finish: type, glass, panels, gallery motion
└─ assets/
   ├─ evaion-icon.svg            supplied brand icon
   ├─ evaion-wordmark.svg        supplied wordmark
   ├─ favicon-64.png             generated from the brand icon
   ├─ apple-touch-icon.png       generated from the brand icon
   ├─ og-echo.jpg                1200 × 630 social preview
   ├─ art/                         retained concept art — hidden in current layouts
   │  ├─ mechanism.svg           open headphones beside the closed sphere
   │  ├─ box-contents.svg        exploded view of Echo, case and cable
   │  ├─ shipping.svg            parcel on a dotted route
   │  ├─ warranty.svg            shield and ear cup
   │  ├─ support.svg             ear cup with waveform and message
   │  └─ policy.svg              document, ring and lock
   ├─ fonts/
   │  ├─ inter-latin.woff2           display and body typeface
   │  ├─ ibm-plex-mono-400-latin.woff2  micro labels and metadata
   │  ├─ ibm-plex-mono-500-latin.woff2  micro labels and metadata
   │  ├─ newsreader-400-latin.woff2     retained; roman not used
   │  └─ newsreader-400-italic-latin.woff2  second-line accent
   └─ derived/
      ├─ echo-hero-orange.webp
      ├─ echo-hero-portrait.webp
      ├─ echo-holding.webp
      ├─ echo-macro.webp
      ├─ echo-motion.webp
      ├─ echo-pool.webp
      ├─ echo-portrait.webp
      ├─ echo-stone.webp
      ├─ echo-views.webp
      ├─ pixel-pattern.png
      └─ edit-log.md             source, crop and use for every derived file
```

The previous site is preserved at `_archive/evaion-v1`; it is not part of this
build and is not linked from any page.

---

## 5. Brand and design

The final direction is **quiet precision**: a premium single-product storefront
with the calm of a gallery and the tactility of a well-made object. The layout
keeps editorial confidence but lowers the volume — sentence-case headlines, fewer
hard rules, softer colour fields, more air and a restrained use of Liquid Glass.

- **Palette:** ink `#17141A`, warm paper `#F7F5F1`, paper deep `#EFECE5`,
  Violet Alloy `#6B5CAD`, deep violet `#2A2140`, soft violet `#ECE7F6` and light
  violet `#CFC4F3`. The legacy lime and orange tokens are remapped to violet so
  inherited rules cannot reintroduce saturated accents.
- **Type:** Inter carries display and body copy at weights 540–560, with
  sentence-case display settings from `2.9rem` up to `9.6rem` for the Echo
  ledger. IBM Plex Mono is reserved for small tracked labels and metadata.
  Newsreader italic appears only as a second-line accent in heroes, the closing
  panel and confirmation — never as body copy.
- **Grid and rhythm:** the shared 12-column shell remains, with a fluid
  `1.2–4rem` gutter and a 100rem maximum. Sections are separated by whitespace
  and soft colour changes rather than stacked rules.
- **Surfaces:** paper is the default. The mechanism, materials, gallery and
  closing moments sit in rounded, inset panels; the gallery is a pale lavender
  field and the dark panels use deep-violet gradients instead of flat violet.
  Photography, cards, fields and thumbnails share soft radii and inset highlights.
- **Liquid Glass:** used selectively on the fixed header, hero facts strip,
  mobile menu, cart drawer, gallery captions and product badge, product buy
  panel, mobile buy bar and closing CTA box. Glass never sits on large scrolling
  body copy, and large surfaces avoid heavy blur.
- **Footer:** a deep-violet gradient panel with quiet link columns and a large,
  low-opacity light wordmark that stays clipped by the panel edge.
- **Voice:** restrained, specific and calm. No exaggerated claims.
- **Motion:** 180–600ms on one easing curve,
  `cubic-bezier(0.22, 1, 0.36, 1)`. The product gallery is an opacity-only
  300ms crossfade with no scale; all four frames are eagerly loaded so a view
  change never waits on the network. Entrance reveals and scroll progress remain
  absent.
- **Signature motif:** the headphone closes into a sphere. The idea is carried
  by a static line diagram, by proportion, by the ledger of specifications and
  by the product photography — not by decorative clutter.
- **Imagery:** the violet product set is the primary visual language: the pool
  hero, worn portrait, held study, macro detail and stone still. The orange
  portrait and the unused motion/views crops remain on disk but are not shown.
- **Commerce:** all demo commerce stays visibly labelled, and the layout does not
  disguise the absence of a backend with fake urgency or invented reviews.

Full tokens, type scale, components and usage rules live in
[`design-system.md`](design-system.md).

---

## 6. Sales model (`SALES_MODE`)

The product page supports three storefront states through a single attribute on
the root element:

```html
<html lang="en" data-sales-mode="buy">
```

| Value | What appears |
| --- | --- |
| `buy` | Price, quantity, Add to bag, dispatch note |
| `preorder` | Preorder CTA to checkout, sample shipping window, stock label |
| `waitlist` | Email waitlist form, invitation note, waitlist stock label |

All pages currently ship with `data-sales-mode="buy"`. To preview another state,
edit that attribute in `echo.html` (and any page whose cart CTA should match).
No JavaScript reads this value; the variants are pure CSS.

**Limitation:** production `SALES_MODE` should come from the commerce backend so
product state, CTA, schema availability and checkout behaviour cannot drift
apart. This build cannot do that without JavaScript or server rendering.

---

## 7. Cart and quantity demonstration

The cart is a CSS state machine:

1. `#cart-open` (header checkbox) opens the drawer on every page.
2. `#cart-filled` exists only on `echo.html`. “Add to bag”, the closing CTA and
   the mobile buy bar check it, which opens the filled drawer.
3. Quantity radios update the line price, order total, drawer quantity, header
   count and subtotal with `:has()` selectors.
4. Closing the filled drawer unchecks `#cart-filled`, returning the demo to an
   empty bag. State does not persist across pages or reloads.

Product quantity controls use `pq1`–`pq3`. The Echo drawer labels target those
same inputs, so the panel and drawer stay in sync without duplicated controls.
Other pages include `cq1`–`cq3` inside the hidden filled state for markup
completeness, but the filled state cannot be reached there.

The drawer itself is intentionally compact: line item, quantity, price, remove,
three assurances and a subtotal. There is no duplicate promotion block or
secondary cross-sell.

**Limitation:** a real cart needs persistent storage, line-item identity,
inventory checks, price recalculation and backend validation. CSS alone cannot
provide these.

---

## 8. Checkout and confirmation

`checkout.html` demonstrates the structure of a hosted checkout:

- contact and delivery fields with native validation;
- one standard delivery method and three payment-method radios;
- a sticky order summary with the sample price and tax note;
- a visible demonstration badge and a note that no payment is taken;
- a submit button that opens `confirmation.html` with the entered values as a
  query string. Nothing is transmitted to a server.

`confirmation.html` is explicitly labelled a demonstration. It shows the intended
post-payment timeline but states that no payment, order, invoice or email exists.
Example order number `EV-2601-0482` and the dispatch date are sample details.

**Production requirement:** replace the demo submission with a server-created
checkout session from Shopify Checkout or Razorpay. Verify payment via webhook on
the server, create the order, issue the GST invoice and send confirmation mail.
Never trust a browser redirect as proof of payment.

`.env.example` documents the variables a production integration would need. The
static site does not read environment files, and no secret should ever be placed
in HTML, CSS or client-delivered JavaScript.

---

## 9. Motion and accessibility

- Content is visible by default. Entrance reveals, scroll progress and the
  scroll-driven open/close sequence were removed; only hover, focus and
  control-state transitions remain, at 180–600ms.
- The product gallery is an opacity-only 300ms crossfade. The incoming frame is
  layered above the outgoing frame, no scale is applied, and all four images are
  eagerly loaded so switching never waits on a lazy load.
- The mechanism is a static inline SVG showing the open form, the transfer and
  the closed sphere. Every browser sees the same composition, and nothing
  depends on scroll position.
- `prefers-reduced-motion: reduce` reduces the remaining transitions to
  near-zero and disables smooth scrolling, including the gallery crossfade.
- Skip link, one `<main>` per page, ordered headings, visible focus, labelled
  form controls, `aria-current`, text alternatives and colour-independent state
  cues are implemented.
- The mobile menu and cart layer are labelled regions so their content stays
  inside landmarks.
- Axe (WCAG 2.0/2.1 A, AA and best-practice rules) returns **zero violations**
  on all 11 pages at 375, 768 and 1440px.
- Colour is never the only signal: stock states, errors and selections include
  text or shape changes.

---

## 10. SEO and sharing

- Unique title, description and canonical URL on every page.
- Open Graph and Twitter card tags with a 1200 × 630 image.
- Product, Offer and Brand microdata on `echo.html` using visible HTML rather
  than JSON-LD, preserving the no-`<script>` rule.
- `robots.txt` permits public pages and points to `sitemap.xml`.
- Checkout and confirmation are `noindex, nofollow`.
- Semantic landmarks, descriptive link text and real content throughout.

**Structured-data limitation:** microdata cannot express every rich-result
property as cleanly as JSON-LD. Price and availability must be generated from
live commerce data before launch. Do not publish review markup until real
reviews exist.

---

## 11. Asset summary

### Supplied brand assets

| Asset | Use |
| --- | --- |
| `evaion-icon.svg` | Favicon and social image; hidden in the wordmark-only header |
| `evaion-wordmark.svg` | Header and footer wordmark |
| Official colour sheet | Base for the palette tokens in `css/style.css`, `css/editorial.css` and `css/premium.css` |
| Campaign renders and packaging photography | Source material for `assets/derived` |

### Vector artwork

The six SVGs in `assets/art/` remain in the repository but are hidden in the
current premium layouts. The homepage mechanism is a purpose-built inline SVG
line diagram; the other concepts are now carried by photography and copy.

| File | ViewBox | Use |
| --- | --- | --- |
| `mechanism.svg` | 1200 × 800 | Technology hero: open headphones and closed sphere |
| `box-contents.svg` | 1200 × 800 | Echo page: exploded view of the box contents |
| `shipping.svg` | 900 × 700 | Shipping hero: parcel on a route |
| `warranty.svg` | 900 × 700 | Warranty hero: shield and ear cup |
| `support.svg` | 900 × 700 | Support hero: ear cup, waveform and message |
| `policy.svg` | 900 × 700 | Privacy and terms heroes: document and lock |

Each artwork includes a `<title>` and `<desc>` and remains available for future
campaign work. None is referenced by the current premium layouts.

### Derived imagery

All product photography shows the single available colourway, **Violet Alloy**.
Every file is local and sized for its layout slot. The product page uses four
views — pool, worn, macro and stone — and the homepage reuses the same set in its
hero, materials, in-use gallery and closing panel.

| File | Dimensions | Primary use |
| --- | --- | --- |
| `echo-pool.webp` | 928 × 1152 | Homepage hero; product gallery view 1 and lead thumbnail |
| `echo-portrait.webp` | 928 × 1152 | Homepage in-use gallery; product gallery view 2 |
| `echo-macro.webp` | 1376 × 768 | Homepage materials; technology page; product gallery view 3 |
| `echo-stone.webp` | 928 × 1152 | Homepage in-use and closing panel; product gallery view 4; cart and checkout thumbnail |
| `echo-holding.webp` | 1376 × 768 | Homepage in-use gallery; about; product care |
| `echo-hero-orange.webp` | 1200 × 896 | Social-card and portrait-crop source only |
| `echo-hero-portrait.webp` | 1200 × 1500 | Retained; no longer referenced by any page |
| `echo-motion.webp` | 1024 × 1024 | Retained; not used in the premium direction |
| `echo-views.webp` | 928 × 1152 | Retained; not used in the premium direction |
| `pixel-pattern.png` | 1987 × 2123 | Retained; decorative texture removed |
| `og-echo.jpg` | 1200 × 630 | Open Graph / Twitter image |

Exact source files, crops and treatments are recorded in
[`assets/derived/edit-log.md`](assets/derived/edit-log.md).

### Fonts

| Family | Files | Role | Licence |
| --- | --- | --- | --- |
| Inter | variable Latin subset | Display, body copy, buttons and form labels | SIL Open Font License |
| IBM Plex Mono | 400, 500 Latin subsets | Small tracked labels, ledgers and metadata | SIL Open Font License |
| Newsreader | 400 italic Latin subset | Second-line italic accent only | SIL Open Font License |

**Typography limitation:** the brand guide names **Nura** as the primary face.
Nura files were not supplied, so Inter is used as the licensed substitute. The
site should not be described as using Nura until the licensed files are added
and the `--font-display` / `--font-body` tokens are updated.

---

## 12. Verification performed

- 11 pages checked at 375, 768, 1280, 1440 and 1536px after the premium layer:
  no horizontal scrollbar, console errors or failed requests.
- Internal links, fragment anchors, asset paths and ARIA ID references resolve.
- No duplicate IDs, missing image `alt`, `<script>` tags or inline event handlers.
- One `<main id="main">` per page; skip link resolves and receives visible focus.
- Axe scans at 375, 768 and 1440px: **zero violations** on all 11 pages,
  including colour contrast. The scans also confirm no external requests.
- Hero text-over-image contrast measured from rendered pixels: paper display
  lines stay at or above 7.67:1 across 1440, 700 and 375px; the violet-light
  accent line stays at or above 4.37:1. Both clear the 3:1 large-text threshold.
- Reduced-motion test: all content remains visible and the static mechanism
  diagram is unchanged; transition duration is reduced to near-zero.
- Mobile menu opens and closes; cart opens empty on non-product pages; quantity
  1/2/3 updates the panel total, drawer line, header count and subtotal; Add to
  bag opens the filled drawer; close clears the demo state. Both overlays are
  labelled regions.
- Gallery radio switching verified for all four product views at 1440 and 375px:
  a 300ms opacity-only crossfade with the incoming frame layered above the
  outgoing frame, and all four main images loaded eagerly.
- Product buy panel pins fully inside the viewport at 1440 × 900 and 1536 × 900,
  and falls back to static flow on short desktop viewports where the full panel
  would not fit.
- Homepage in-use gallery checked at 640, 700 and 768px: all three images remain
  visible and no horizontal overflow is introduced.
- Keyboard focus is visible on nav links, gallery controls, quantity controls,
  buttons and form fields.
- No-JavaScript test: all pages render, CSS-only quantity totals work and no
  content depends on script.
- Sales-mode variants verified for `buy`, `preorder` and `waitlist` by toggling
  `data-sales-mode` and checking the visible CTA, stock label and waitlist form.
- Checkout validation rejects an empty form; a completed form reaches the
  demonstration confirmation page with the entered values in the query string.
  No payment is processed.

These checks are a point-in-time front-end audit, not a substitute for testing
with real assistive technology, real content, real payment credentials or a
production backend.

---

## 13. Example content requiring sign-off

There are no visible `[PLACEHOLDER]` markers. Instead, the site uses plausible
sample copy and labels the legal and transactional pages as demonstration
content. Replace the following before a live launch:

| Area | Sample content in this build |
| --- | --- |
| Price | **₹34,990**, inclusive of all taxes |
| Product | Bluetooth 5.3, USB-C, up to 40 hours playback, 40 mm driver, 20 Hz–20 kHz, 32 Ω, 285 g |
| Box | Echo, 1.2 m USB-C cable, travel case, documentation |
| Commerce | Payment provider, keys, test mode, webhooks, tax treatment, shipping charge, serviceability, inventory |
| Logistics | Dispatch window, delivery estimates, remote coverage, tracking provider, packaging tests |
| Returns | 14-day window, condition rules, 5–7 business day refund timeline |
| Warranty | Two-year period, coverage categories, battery threshold, exclusions, service turnaround |
| Legal | Legal entity, registered address, GSTIN, grievance officer, jurisdiction, liability limits, policy dates |
| Support | Phone, email, hours, response targets, ticketing endpoint, spam protection |
| Marketing | Reviews (intentionally absent), certifications, recycled content, carbon or environmental metrics |
| Typography | Licensed Nura files |

The company details used throughout — Evaion Audio Pvt. Ltd., Hyderabad;
`care@evaion.in`; `privacy@evaion.in`; +91 40 4567 8900; Mon–Fri, 10:00–18:00
IST — are sample details for the demonstration. They are not verified contact
channels.

Do not present the sample specifications, policies or company details as
approved facts. Replace them with verified content before accepting orders.

---

## 14. Deployment

The site is fully static. Upload the contents of `evaion/` to any static host
(Netlify, Cloudflare Pages, GitHub Pages, S3, nginx). Requirements:

1. Serve `index.html` at `/`.
2. Preserve the `assets/` and `css/` paths.
3. Enable HTTPS.
4. Internal links, canonical tags, OG URLs and the sitemap use `.html`
   filenames so the site works on any static host without rewrite rules. If
   clean paths are required, add host rewrites and update every canonical,
   OG URL and sitemap entry together.
5. Replace `https://evaion.in` in canonical/OG tags if the domain changes.
6. Keep `.env.example` out of the public document root in production, or treat
   it as documentation only — it contains no live secrets.

Suggested cache policy: long-lived immutable caching for fonts and derived
images, short cache for HTML and CSS during launch week, then fingerprinted
filenames if the build moves to a bundler.

---

## 15. Known limitations

1. **No real commerce.** Cart, checkout, confirmation and sales modes are
   front-end demonstrations. Nothing persists, charges, reserves stock or sends
   email.
2. **No serviceability check.** The checkout pincode validates format only; no
   delivery date or coverage is confirmed.
3. **No dynamic SALES_MODE.** Changing state requires editing HTML.
4. **No reviews.** The review section is absent because no verified reviews
   exist; inventing them would breach the brief.
5. **No legal completeness.** All policy pages are clearly labelled sample
   wording pending legal review, not published terms.
6. **No Nura typeface.** Inter is a substitute.
7. **No animated mechanism.** The open/closed mechanism is a static line
   diagram. A true product animation would require video, JavaScript or WebGL,
   which the HTML + CSS brief excludes.
8. **Sample content is not verified.** Product specifications, company details,
   dates, policies and order information must be replaced before launch.
9. **Checkout does not transmit data to a server.** Native validation works and
   the demo proceeds to confirmation, but no order exists.
10. **One colourway only.** Violet Alloy is the only finish shown; do not add
    colour variants without approved photography and SKUs.

---

## 16. Content and claims policy

- Sample copy is allowed for the demonstration, but must stay plausible and
  must be labelled where it could be mistaken for a real policy or order.
- Do not present sample specifications, certifications, awards, reviews,
  environmental metrics, contact details or legal facts as verified.
- Bio-Energy is described as a **design framework**, not a battery, medical,
  therapeutic or energy-harvesting technology.
- Sustainability language names materials honestly and avoids unsupported
  recycled-content, carbon or end-of-life claims.
- Policy pages carry a visible demonstration callout and a “last updated” date
  marked as sample wording.
- Product imagery must remain Violet Alloy until another colourway is verified.
- No `<script>`, inline handler, tracking pixel or third-party runtime may be
  added without revisiting the accessibility and privacy documentation.

---

## 17. Credits

Brand assets, colour sheet and campaign imagery supplied by Evaion. Site design,
copy and front-end build produced for the Evaion Echo launch. Vector artworks
and derived imagery created for this build. Inter carries display and body type,
IBM Plex Mono carries micro labels, and Newsreader italic is used as an accent;
all three are self-hosted under the SIL Open Font License.

For design tokens and component rules, continue to
[`design-system.md`](design-system.md).
