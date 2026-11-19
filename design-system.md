# Evaion design system

The working design language for the Evaion Echo storefront. It documents the
tokens and rules implemented across three hand-written stylesheets:

- `css/style.css` — base system, component mechanics and every CSS-only
  interaction.
- `css/editorial.css` — shared grid, page composition and editorial structure.
- `css/premium.css` — the final premium finish: tokens, type, soft geometry,
  selective Liquid Glass, inset panels and gallery motion.

The short version: **quiet precision.** Warm paper, ink and Violet Alloy;
sentence-case Inter display type; IBM Plex Mono micro labels; Newsreader italic
as a single accent; inset deep-violet panels; pale lavender photography fields;
soft radii; and glass only on floating or transactional surfaces. The interface
should feel like a well-made object in a calm gallery, not a marketplace or a
loud launch campaign.

---

## 1. Foundation

Evaion is a single-product audio studio. The interface should feel considered,
precise and unhurried:

- **One product.** Echo is the only item for sale. No accessories, bundles or
  related-product grids.
- **One verified finish.** Violet Alloy. Photography and colour references must
  not imply additional colourways.
- **Quiet scale.** Display headings are sentence case, weight 540–560, tightly
  tracked, and set from `2.9rem` up to `9.6rem` for the Echo ledger — confident,
  not shouting.
- **Space is structural.** Whitespace and soft colour fields separate sections.
  Hard rules are rare and never decorative.
- **Soft geometry.** Photography, cards, fields, panels, thumbnails and controls
  share rounded corners. Buttons and tags are pills.
- **Selective glass.** Liquid Glass belongs on the fixed header, floating buy
  surfaces, overlays and compact captions — never on large scrolling body copy.
- **Photography carries the page.** The violet product set — pool, portrait,
  macro, stone and held — does more than illustration or decorative UI.
- **Static by default.** Content is visible without scrolling, animation or
  script. Motion is limited to direct interaction feedback.
- **Evidence over atmosphere.** Label policies and transactional pages clearly;
  never present sample details as verified.

### Brand line

> Nature engineered. Future designed.

Campaign line for this launch:

> Sound, folded into form.

---

## 2. Colour

### Premium palette

| Name | Hex | Token | Role |
| --- | --- | --- | --- |
| Ink | `#17141A` | `--pm-ink` | Primary text, dark hero ground |
| Ink soft | `#2B262F` | `--pm-ink-soft` | Secondary dark surface |
| Paper | `#F7F5F1` | `--pm-paper` | Primary light surface |
| Paper deep | `#EFECE5` | `--pm-paper-2` | Quiet fields and gallery frame ground |
| Paper shade | `#E7E2DA` | `--pm-paper-3` | Occasional deeper paper surface |
| Violet Alloy | `#6B5CAD` | `--pm-violet` | Primary accent, focus, selected state |
| Violet deep | `#2A2140` | `--pm-violet-deep` | Dark panel base, accent text on paper |
| Violet soft | `#ECE7F6` | `--pm-violet-soft` | Pale tinted surfaces |
| Violet light | `#CFC4F3` | `--pm-violet-light` | Display accent on dark panels |
| Line | `rgba(23,20,26,0.10)` | `--pm-line` | Hairline rules on paper |
| Line strong | `rgba(23,20,26,0.22)` | `--pm-line-strong` | Stronger dividers and input edges |
| Line dark | `rgba(247,245,241,0.16)` | `--pm-line-dark` | Hairline rules on dark panels |
| Glass | `rgba(255,255,255,0.56)` | `--pm-glass` | Light glass fill |
| Glass dark | `rgba(24,20,31,0.36)` | `--pm-glass-dark` | Dark glass fill |

`--pm-grad-deep` and `--pm-grad-deep-soft` are the only gradients: deep-violet
radial washes used for inset dark panels. There are no decorative gradient text,
glow rings or neon accents. The legacy lime and orange tokens are remapped to
violet so inherited rules cannot reintroduce saturated colour.

### Section rhythm

The homepage alternates fields deliberately:

| Section | Ground |
| --- | --- |
| Hero | Ink photograph inside a rounded, page-inset frame |
| Echo ledger | Paper with a faint violet radial wash |
| Open / Closed mechanism | Inset deep-violet gradient panel |
| Violet Alloy materials | Paper |
| In use gallery | Rounded pale lavender field (`#F2EEFA` → `#E9E3F3`) |
| Quietly specific numbers | Paper |
| Two halves closing | Inset deep-violet gradient panel |
| Footer | Full-width deep-violet gradient |

Interior pages use paper as their default ground and reserve deep-violet panels
for mechanism, product closing and CTA moments. Do not stack two accent fields
without a paper interval.

### Contrast rules

Verified with axe at 375, 768 and 1440px: **zero violations on all 11 pages**.

- Body and metadata text use a floor of `rgba(23,20,26,0.62)` on paper. Do not
  go lighter for essential copy.
- `--faint` is calibrated to `0.62`; `--muted` is `0.68`. These values pass AA
  for the small labels used in tables, ledgers and forms.
- On deep-violet panels use full paper text for body copy. Dimmed paper text may
  be used only for non-essential fine print that still clears 4.5:1 against the
  composited panel.
- Do not use ink at low opacity on glass or photographs without measuring the
  final composite. Glass captions and the mobile buy bar were measured with
  their real backdrop, not the nominal panel colour.
- Violet is for fields, focus, links and short accent text on paper. Long body
  copy stays ink.
- The hero display line is paper below the accent line and violet-light for the
  Newsreader accent. Measured from rendered pixels: paper lines stay at or above
  7.67:1 and the accent at or above 4.37:1 across 375, 700 and 1440px. Both clear
  the 3:1 large-text threshold.
- Large display type may use the 3:1 threshold; body copy and micro labels must
  meet 4.5:1.

---

## 3. Typography

### Families

| Role | Family | Token | Notes |
| --- | --- | --- | --- |
| Display and body | Inter | `--font-display`, `--font-body` | Variable Latin subset, weight 430–560 |
| Micro labels | IBM Plex Mono | `--font-mono` | 400 and 500 subsets, uppercase and tracked |
| Accent | Newsreader italic | `--font-serif` | Italic only, second-line accents |

**Brand substitution:** the brand guide names **Nura** as the primary face. Nura
files were not supplied. Inter is the licensed stand-in until the real files are
available; update both font tokens when that changes.

### Display scale

```css
--ed-display: clamp(2.9rem, 6.2vw, 5.9rem);
--ed-title:   clamp(2.3rem, 5vw, 4.6rem);
--ed-heading: clamp(1.85rem, 3.4vw, 3.1rem);
--ed-body:    clamp(0.98rem, 1.02vw, 1.06rem);
--ed-micro:   0.64rem;
```

| Use | Size | Notes |
| --- | --- | --- |
| Homepage hero | `clamp(3rem, 6.4vw, 6.1rem)` | Sentence case, weight 540, line-height 1.02, `-0.052em` |
| Hero accent line | `1.04em` of display | Newsreader italic, violet-light |
| Echo ledger | `clamp(4rem, 10.5vw, 9.6rem)` | Weight 550, line-height 0.9 |
| Section heading | `--ed-title` / `--ed-heading` | Sentence case, weight 560 |
| Interior page hero | `clamp(2.6rem, 5.4vw, 5rem)` | Max 17ch, line-height 1.04 |
| Product panel title | `clamp(2rem, 3vw, 2.8rem)` | Sentence case, weight 550 |
| Checkout title | `clamp(2.2rem, 4.2vw, 3.8rem)` | Sentence case, weight 550 |
| Closing panel | `clamp(2.6rem, 5.6vw, 5rem)` | Sentence case, weight 550 |
| Confirmation title | `clamp(2.2rem, 4.2vw, 3.8rem)` | Sentence case, weight 550 |
| Body | `--ed-body` | Line-height 1.6–1.68 |
| Micro labels | `0.58–0.64rem` | IBM Plex Mono, uppercase, `0.1–0.13em` tracking |

### Typesetting rules

- Display headings are sentence case. Do not restore uppercase display type.
- Newsreader italic is a second-line accent only: hero, interior page hero,
  closing panel and confirmation title. Never set a paragraph, button or label
  in the serif.
- Body copy stays between 26rem and 36rem measure. Policy body caps at 45rem and
  the policy column at 54rem.
- Micro labels are IBM Plex Mono, uppercase and tracked. They are metadata, not
  headings, and must clear 4.5:1.
- Minimum body size is `0.98rem`. Fine print may reach `0.58rem` but must pass
  contrast and should not carry essential information alone.
- Use `text-wrap: balance` on short display headings and `text-wrap: pretty` on
  closing fine print to avoid orphaned words.

---

## 4. Layout

| Token | Value | Meaning |
| --- | --- | --- |
| `--ed-max` | `100rem` | Page shell |
| `--ed-gut` | `clamp(1.2rem, 3.6vw, 4rem)` | Horizontal gutter |
| `--ed-gap` | `clamp(0.9rem, 1.6vw, 1.5rem)` | Grid gap |
| `--header-h` | `4.2rem` desktop / `3.8rem` mobile | Sticky header offset |
| `--max` | `var(--ed-max)` | Shell alias used by base components |
| `--gut` | `var(--ed-gut)` | Gutter alias used by base components |

- `.shell` centres content at `--ed-max` with the fluid gutter.
- `.ed-grid` is a mobile-first 12-column grid. Its children span all columns by
  default; desktop rules assign explicit column spans.
- Major homepage sections, the materials grid, the in-use gallery and the closing
  panel align to the same 12 columns.
- Photography and dark panels are inset from the page edge by
  `clamp(0.5rem, 1.2vw, 1.1rem)` and rounded, rather than full-bleed.
- Sections are separated by whitespace, a colour change or a single hairline
  rule. Cards are used only where a genuine container is needed.
- Elevation is soft and inset-led: `--pm-shadow-sm`, `--pm-shadow-md` and
  `--pm-shadow-dark`. No hard black drop shadows on light cards.

### Breakpoints

| Width | Rem | Behaviour |
| --- | --- | --- |
| 640px | 40rem | Homepage gallery takes staggered spans; checkout summary moves alongside the form; mobile buy bar hides |
| 768px | 48rem | Product gallery and panel split two-up; editorial section heads take the 12-column layout |
| 900px | 56.25rem | Desktop nav appears; product grid rebalances to 7fr / 5fr; the buy panel becomes sticky |
| 1024px | 64rem | Support topics settle into three columns; checkout summary widens |
| 1280px | 80rem | Wider media and a more generous display stage |
| 1440px | 90rem | Gutter widens and display type reaches its upper range |

Test at **375, 768, 1280, 1440 and 1536px**. The product buy panel is sticky only
when it fits: below a `55rem` viewport height it falls back to static flow so its
last assurance row is never trapped below the viewport.

---

## 5. Surfaces and geometry

- Radii: `--pm-radius-sm` `0.65rem`, `--pm-radius-md` `1rem`,
  `--pm-radius-lg` `1.45rem`, `--pm-radius-xl` `2rem`.
- Buttons, tags, quantity segments and finish options are pills (`100vmax`).
  Fields use `0.8rem`; panels use the large radii.
- Paper surfaces are warm and opaque. Glass surfaces use a translucent fill, a
  hairline light border and an inset top highlight.
- Liquid Glass is limited to: the sticky header, hero facts strip, homepage
  gallery caption, product badge and gallery caption, mobile menu, cart drawer,
  product buy panel, mobile buy bar and closing CTA box.
- On large light surfaces use `backdrop-filter: blur(20–24px) saturate(140–150%)`
  at most. Do not apply heavy blur to long scrolling content.
- Deep-violet panels use `--pm-grad-deep` or `--pm-grad-deep-soft`, a soft outer
  shadow and an inset light edge. They are fields, not cards floating on a page.
- The in-use gallery is a pale lavender field with a rounded border and no dark
  overlay. Captions sit in compact glass pills.
- Hairline rules are the default divider. Remove a border before adding another
  shadow.
- No background grids, noise, pixel textures, rings, stickers or floating logo
  capsules. The pixel pattern and concept SVGs remain on disk but are not shown.

---

## 6. Motion

### Tokens

```css
--ease: cubic-bezier(0.22, 1, 0.36, 1);
--dur-1: 0.18s;
--dur-2: 0.3s;
--dur-3: 0.46s;
--dur-4: 0.6s;
```

### Principles

- Content is visible by default. There are no entrance reveals and no scroll
  progress bar; `.reveal` and `.reveal-scale` are forced visible and
  `.scroll-progress` is hidden.
- The open/closed mechanism is a **static inline SVG**. It is not a scroll
  timeline and must not be described as an animated product demonstration.
- Motion is limited to direct feedback: hover, focus, pressed, selected and
  drawer or menu open/close.
- Animate colour, border and opacity. Use transform only for the cart drawer and
  menu sheet. Do not add parallax, sheen sweeps, image zooms or ambient loops.

### Product gallery

- Four radio-controlled views (`pg-1`–`pg-4`): pool, worn portrait, macro detail,
  stone still.
- The stage is `4 / 5` with `contain: paint` and `isolation: isolate`.
- Frames are absolutely layered. The incoming frame gets `z-index: 2` and fades
  in over the outgoing frame.
- Transition: `opacity 0.3s var(--ease)`, with visibility delayed on the outgoing
  frame. **No scale.**
- All four main images are `loading="eager"` / `decoding="async"` so a view
  switch never waits on a lazy load.

### Reduced motion

`prefers-reduced-motion: reduce` must:

1. set animation and transition durations to near-zero;
2. keep every reveal fully visible;
3. leave the static mechanism diagram unchanged;
4. disable smooth scrolling;
5. collapse the gallery crossfade to an instant cut.

No content or function may depend on motion to be understood.

---

## 7. Components

### Header

- Sticky glass-paper rail, `4.2rem` desktop and `3.8rem` mobile, with a light
  hairline and a subtle inset highlight.
- Black `evaion` wordmark; the brand icon is hidden in the header.
- Desktop navigation is sentence-case Inter at a quiet size, with a soft
  current-page pill rather than a hard underline.
- Actions: round cart trigger with count and round mobile menu trigger.
- `aria-current="page"` marks the active destination only.
- At <900px the nav collapses into a glass paper sheet driven by `#nav-open`. The
  sheet is a labelled region and keeps the header and menu button visible.
- The header stays light on every page, including checkout and confirmation.

### Buttons

Base `.btn`; variants `.btn--primary`, `--light`, `--dark`, `--ghost`,
`--outline`; sizes `--sm`, `--lg`, `--block`.

- Pill, sentence case, 0.84rem, minimum height `3rem`, soft horizontal padding.
- Primary is ink on light surfaces and paper on dark surfaces. The hero primary
  is paper with ink text; hover shifts fill quietly without translation.
- Ghost is transparent with a current-colour hairline and is used on photographs,
  dark bands and glass panels.
- Outline is a quiet paper-surface secondary action.
- The arrow icon sits in a small circular well, not a square.
- No sheen, translate or glow on hover. One primary action per view.

### Tags and labels

`.tag` is a small pill with a hairline border and a very light fill. It
describes state — launch edition, in stock, preorder — and does not replace a
heading. Status dots always keep a text label beside them.

### Eyebrow

`.eyebrow` is an IBM Plex Mono uppercase label at `0.62rem` with `0.13em`
tracking and a short rule or violet dot. Use once per section, directly above
the heading. On dark panels the label switches to paper or violet-light; on
paper it uses the `0.62` ink floor.

### Text links

`.text-link` and `.ed-arrow-link` are quiet sentence-case actions with an
optional arrow. Hover changes colour and border, not position. The arrow may
nudge 2–3px; do not animate the underline.

### Fields

- Always a visible `<label>`; placeholders are examples, never labels.
- Inputs, selects and textareas are near-white, `0.8rem` radius, `3.05rem` tall
  and bordered with a readable ink alpha.
- Focus uses a violet border plus a 2px violet outline with offset.
- `.field__hint` carries format or privacy notes and uses the `0.62` ink floor.
- Invalid styling uses `:user-invalid` only, so fields do not start red.
- Demo forms state that they do not submit or charge.

### Product display band

- Sits directly below the breadcrumb and above the product grid.
- `Echo.` in sentence-case display with a small `Violet Alloy / 001` mono line at
  the far right; the underline is a single quiet rule.
- Decorative and `aria-hidden`; the real `<h1>` is in the buy panel.
- On mobile the meta line wraps beneath the word; do not shrink the display below
  a readable scale.

### Product buy panel

- Glass card with a light border, soft inset highlight and a large radius.
- Sticky from 900px on tall screens, offset by the header plus `1rem`.
- Panel order: eyebrow and tag, title, description, price, finish, quantity,
  total, actions, stock line, assurances.
- Padding `clamp(1.15rem, 2.1vw, 1.55rem)`, gaps `0.95rem`. This keeps the panel
  at roughly 800px so it fits a 900px viewport when pinned.
- Below `55rem` viewport height the panel is static; never let a sticky panel
  hide its own last row.
- Primary CTA is ink; secondary actions are hairline pills.
- Price is the largest number in the panel. MRP is qualified as inclusive of
  taxes; the figure is sample pricing.
- Sales-mode blocks (`.mode-buy`, `.mode-preorder`, `.mode-waitlist`) are shown
  by `data-sales-mode` on `<html>`.
- Mobile: the panel follows the gallery; a fixed dark-glass `.mobile-buy` bar
  appears below 640px with price and Add to bag.

### Gallery

- Four radio-controlled views in this order: pool, worn portrait, macro detail,
  stone still.
- Main stage is `4 / 5`, rounded, with a quiet border and no hover scale.
- Caption is a compact glass pill at the lower left, not a full-width bar.
- Thumbnails are four even square columns, rounded, with a translucent edge; the
  checked state raises opacity and border contrast.
- The gallery crossfades with opacity only over 300ms. All four main images are
  eager-loaded; thumbnails may remain lazy.
- The stage uses `contain: paint` and `isolation: isolate` to keep the fade
  compositor-friendly.

### Quantity

- Radios (`pq1`–`pq3`, `cq1`–`cq3`) styled as a small pill segmented control.
- Maximum three units; the limit is stated in the control.
- Totals, drawer line price, header count and subtotal are computed by CSS
  `:has()` state, not by script.

### Cart drawer

- Fixed dark-glass layer with a scrim and a rounded left edge, `z-index: 200`.
- The layer is a labelled region; the drawer is an unnamed `<section>` whose
  heading identifies it.
- Opens from `#cart-open`; filled state from `#cart-filled` (Echo only).
- Empty state: explanation, Continue browsing and a link to Echo.
- Filled state: rounded thumbnail, line item, quantity, price, remove, three
  assurances, compact subtotal and a light checkout CTA.
- Close targets uncheck the state and clear the demo. The close control is round
  and keeps a paper icon on the dark glass.
- Focus is not trapped because this is a CSS-only demonstration; production
  should use a dialog with focus management.

### FAQ

Native `<details>` / `<summary>` with a custom +/− indicator. One open item is
not enforced; users may compare answers. Body copy stays within the reading
measure. The row uses a soft rule and generous vertical padding.

### Policy pages

- Light paper hero with the page title, lede and a short meta row. Concept art is
  hidden.
- A single editorial column capped at 54rem, with body copy at 45rem. No sticky
  table of contents.
- Body sections use `h2`, short paragraphs, lists, semantic tables and callouts.
- Tables use Inter for values and IBM Plex Mono for labels, with hairline rules
  and real `<th scope>`.
- A demonstration callout at the end labels the wording as sample copy.
- Contact rows keep labels small and values in ink, with hairline dividers.

### Checkout

- Calm opening block: sentence-case display title, short lede and a quiet rule.
- Single-column form cards with rounded corners and a small numbered step.
- Sticky order summary at ≥768px, with a rounded stone thumbnail.
- Payment and shipping methods are rounded radios with provider labels; card
  data is never collected.
- Demonstration badge and hosted-payment note stay visible and readable.
- Primary CTA is an ink pill that opens the demonstration confirmation.
- A compact `checkout-page-foot` replaces the full site footer.

### Confirmation

- Rounded white card on paper, soft check mark, sentence-case title with a serif
  accent, four-column order meta grid and a quiet total row.
- Uses the same compact footer as checkout.
- Never imply a real order without a backend reference.

### Footer

- Deep-violet gradient panel with paper link columns, a quiet legal row and a
  single light hairline above it.
- Light wordmark, one line of positioning copy and a contact block.
- Two link columns on mobile, three from 640px. Only three link groups exist; do
  not add a fourth column without new content.
- A large, low-opacity `EVAION` wordmark sits in normal flow and is clipped by
  the footer edge. It is decorative and must not introduce horizontal overflow.
- Do not return the footer to a solid flat violet or dim essential link text
  below AA.

---

## 8. Page compositions

### Homepage

1. Rounded, page-inset ink hero over `echo-pool.webp`: top meta rule, “Sound
   folded *into form.*”, lede, pill Shop Echo button, arrow link and a glass facts
   strip with three facts.
2. Paper ledger: large `Echo.` with an overlapping portrait card, intro copy and
   a three-column specification table closed by a tinted price row.
3. Inset deep-violet mechanism panel: “Open. Closed.”, static SVG open → closed
   and three numbered steps.
4. Paper materials section: “Violet Alloy.”, macro photograph, four material rows
   and a material-approach link.
5. Pale lavender in-use gallery: worn portrait, held study and stone still on a
   12-column grid with deliberate negative space.
6. Paper numbers: “Quietly specific.” and four large figures — 40 hours, 285 g,
   40 mm, 5.3.
7. Inset deep-violet closing panel: “Two halves. *One whole.*”, price, two actions
   and the stone image.
8. Deep-violet footer with the large low-opacity wordmark.

### Echo product page

1. Breadcrumb and `Echo.` display band with `Violet Alloy / 001`.
2. Two-column gallery and glass buy panel from 768px, rebalanced to 7fr / 5fr at
   900px with a sticky panel when height allows. Four views and four even square
   thumbnails.
3. Box contents: four hairline columns with small violet icons.
4. Design notes: four soft white cards.
5. Specifications: short aside plus a semantic ledger table.
6. Care: held photograph plus a definition list in a rounded panel.
7. FAQ, compliance and a deep-violet closing CTA with a glass price box.
8. Mobile buy bar below 640px.

### Editorial pages

- Light paper hero, left-aligned, no artwork. Title, lede and meta rule.
- Section heads use the 12-column grid from 768px: label, heading, supporting
  copy.
- Cards and principles are soft white surfaces separated by space, not heavy
  containers.
- Technology keeps a macro photograph and selected specification tables; about
  keeps the held photograph; policy pages stay typographic.
- Closing CTA is an inset deep-violet panel with paper text and a glass price box.

---

## 9. Accessibility

Target: **WCAG 2.1 AA**.

- One `<main id="main">` per page; skip link first in the tab order.
- Header, nav, main, aside and footer landmarks are used once and correctly. The
  mobile menu and cart layer are labelled regions; the cart panel itself is a
  plain `<section>` so it cannot nest a complementary landmark.
- Heading order is sequential; display size never substitutes for an `h1`/`h2`
  level. Decorative display bands are `aria-hidden`.
- Interactive targets are at least 44 × 44px where practical.
- Focus is always visible and never removed without a replacement.
- All images have appropriate `alt`; decorative images use `alt=""`.
- Form controls have persistent labels, hints and error text.
- State changes are announced through native control semantics where possible.
- `aria-current="page"` marks the current nav item.
- Motion respects `prefers-reduced-motion`; content never depends on it.
- Axe scans at 375px, 768px and 1440px return **zero violations** on all 11
  pages, with no external requests.
- The cart and menu are CSS-only; production should upgrade them to dialogs with
  focus trapping, escape handling and restored focus.

### Contrast cautions

- Muted ink uses a `0.62` alpha floor on paper. Lower alphas fail AA for the
  small mono labels used throughout the build.
- Paper at 90% opacity on Violet Alloy is too light for body copy. Use full
  paper; create hierarchy with size and weight.
- Ink at low opacity on a dark panel is decorative only. Body copy on deep violet
  must be paper or violet-light.
- Glass surfaces must be measured against their real composited backdrop. The
  mobile buy bar and gallery caption were checked with the product photography
  behind them.
- Violet `#6B5CAD` is for fields, focus, rules and short accent text on paper,
  not long body copy.
- The hero accent line is Newsreader italic in violet-light. Keep the underlying
  photograph dark enough at every crop; the measured minimum is 4.37:1.
- Do not bring back lime or orange for small text. The remapped tokens exist only
  to neutralise inherited rules.
- Disabled controls are exempt from contrast but must still be identifiable.

---

## 10. Content style

- Sentence case for product prose, policy text, form labels and display headings.
  Uppercase is reserved for short mono labels and tags.
- Short paragraphs; one idea each.
- Prefer concrete nouns and verbs over adjectives.
- No exclamation marks, no “revolutionary”, “game-changing” or “best-in-class”.
- Do not claim awards, reviews, certifications or performance without evidence.
- Use “Echo” on subsequent references after the first “Evaion Echo”.
- Currency: `₹34,990`, with “MRP inclusive of all taxes” spelled out.
- Policy dates and company details are sample values, labelled as demonstration
  content on the page.
- Support copy routes people to a topic before asking them to fill a form; the
  static build does not submit support requests.
- Describe the mechanism as geometry, not as an animated trick.
- Bio-Energy is a design framework, never a battery or medical technology.

---

## 11. CSS architecture

The site loads three stylesheets in this order on every page:

```html
<link rel="stylesheet" href="css/style.css">
<link rel="stylesheet" href="css/editorial.css">
<link rel="stylesheet" href="css/premium.css">
```

`css/style.css` keeps the base system, component mechanics and responsive rules.
`css/editorial.css` supplies the shared grid and page composition. `css/premium.css`
is the final visual layer: tokens, type scale, soft geometry, glass, inset panels
and gallery motion. It intentionally supersedes earlier visual styling; it is not
a second theme.

| File / section | Contents |
| --- | --- |
| `style.css` 00–25 | Fonts, tokens, reset, base components, page styles, motion and responsive rules |
| `style.css` 26–45 | Earlier premium palette, header, buttons, forms, cart, footer and page refinements |
| `editorial.css` 01–03 | Editorial tokens, page frame, shared grid, light header and footer |
| `editorial.css` 04–11 | Controls and the homepage composition |
| `editorial.css` 12–14 | Product page, editorial pages, checkout and confirmation |
| `editorial.css` 15–16 | Responsive grid and reduced-motion overrides |
| `premium.css` 01–02 | Premium tokens and sentence-case type |
| `premium.css` 03–04 | Glass header and soft controls |
| `premium.css` 05–12 | Homepage sections and footer |
| `premium.css` 13–15 | Product page, content and closing band |
| `premium.css` 16–18 | Editorial, policy, checkout and confirmation |
| `premium.css` 19–21 | Mobile menu, cart, motion and responsive refinements |

Rules:

- Put final visual work in `premium.css`. Put interaction state, control
  mechanics and base fixes in `style.css`. Keep composition changes in
  `editorial.css`.
- Do not add a fourth override layer.
- Use semantic tokens. Raw brand hex values belong in the token blocks only.
- Keep selectors flat (max two levels) and avoid IDs for styling except where a
  native state control requires it.
- Use `:has()` for state that genuinely depends on a descendant control.
- Preserve the load order; loading `premium.css` before `editorial.css` breaks
  the finish.
- Test every new rule at 375px and 1280px before considering it done, then verify
  no overflow at 768, 1440 and 1536px.

---

## 12. Quality checklist

Before shipping a page:

- [ ] One `h1`, ordered headings, one `main`.
- [ ] All links and assets resolve; no duplicate IDs.
- [ ] All controls have labels and visible focus.
- [ ] No horizontal overflow at 375/768/1280/1440/1536.
- [ ] Text contrast passes against the composited background, especially on
      glass, photography and deep-violet panels.
- [ ] Reduced-motion view is complete and static.
- [ ] No entrance reveal, scroll progress or scroll-driven mechanism remains.
- [ ] Content is visible without JavaScript.
- [ ] No invented claims presented as verified facts.
- [ ] Sample content is labelled where it could be mistaken for policy or fact.
- [ ] Only Echo is sold; only Violet Alloy is shown.
- [ ] No `<script>`, inline handler or third-party runtime.
- [ ] Display headings are sentence case; serif italic is an accent only.
- [ ] Micro labels use the mono family and clear AA.
- [ ] Glass is limited to floating or transactional surfaces.
- [ ] Violet is the only UI accent; no lime or orange controls.
- [ ] Every page loads `style.css`, `editorial.css` and `premium.css` in order.
- [ ] Meta title, description, canonical and OG image are present.
- [ ] Checkout/confirmation remain `noindex`.
