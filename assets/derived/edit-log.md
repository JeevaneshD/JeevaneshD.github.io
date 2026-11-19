# Derived asset edit log

All product imagery in this folder was produced from supplied Evaion campaign
renders. The originals remain in the project root and are **not** deployed with
the site. Every derivative is local, compressed and sized for a specific layout
slot.

- **Build:** November 2026
- **Colourway:** Violet Alloy only
- **Output format:** WebP for photography, PNG for the texture, JPEG for social
- **Colour space:** sRGB
- **Naming:** lowercase, hyphenated, descriptive
- **Rule:** no generative retouching of the product, no invented finishes, no
  added accessories or claims

---

## 1. Summary

| Output | Dimensions | Source | Treatment |
| --- | --- | --- | --- |
| `echo-hero-orange.webp` | 1200 × 896 | `magnific_hero-product-shot-generate-54_LwX84KDswO.png` | Direct WebP conversion |
| `echo-hero-portrait.webp` | 1200 × 1500 | `echo-hero-orange.webp` | Canvas extended, orange backdrop reconstructed |
| `echo-holding.webp` | 1376 × 768 | `magnific_the-person_Sy850RtUb8.png` | Direct WebP conversion |
| `echo-macro.webp` | 1376 × 768 | `magnific_if-any-text-below-conflicts-with-the-image_mE6Mru5hJQ.png` | Direct WebP conversion |
| `echo-motion.webp` | 1024 × 1024 | `magnific_product-in-motion-generate-11_bx0MUdj5Y2.png` | Direct WebP conversion |
| `echo-pool.webp` | 928 × 1152 | `magnific_the-pool_3zHwuoXREY.png` | Direct WebP conversion |
| `echo-portrait.webp` | 928 × 1152 | `magnific_a-super-photogenic-genz-model_lJBqYAqgv9.png` | Direct WebP conversion |
| `echo-stone.webp` | 928 × 1152 | `magnific_one-flat-matteblack-oval-disc-inset_ovPcgra829.png` | Direct WebP conversion |
| `echo-views.webp` | 928 × 1152 | `magnific_one-flat-matteblack-oval-disc-inset_WDj65sPcXe.png` | Direct WebP conversion |
| `pixel-pattern.png` | 1987 × 2123 | `Evaion Pixel Pattern.png` | Alpha-preserving optimisation |
| `../og-echo.jpg` | 1200 × 630 | `echo-hero-orange.webp` + brand SVGs | Composited social card, JPEG q90 |

“Direct WebP conversion” means: decode source, convert to sRGB, encode WebP with
quality tuned for the image, verify dimensions and visual fidelity. No crop, no
colour grading, no object removal and no added elements.

---

## 2. File notes

### `echo-hero-orange.webp`

- **Source:** `magnific_hero-product-shot-generate-54_LwX84KDswO.png` (1200 × 896).
- **Treatment:** straight WebP encode. The orange field, shadow and product are
  unchanged.
- **Use:** social-card source only. The orange field is no longer shown in the
  current premium layouts.
- **Why this one:** it is the cleanest full-product view on the campaign orange
  field and remains the source for the social card.

### `echo-hero-portrait.webp`

- **Source:** `echo-hero-orange.webp`.
- **Treatment:** canvas extended from 1200 × 896 to 1200 × 1500. The additional
  vertical area is filled with a sampled continuation of the orange backdrop,
  including a subtle tonal falloff to avoid a flat fill. The headphones and
  their shadow are untouched.
- **Purpose:** the desktop hero crop is too wide for a 375px first viewport,
  while the portrait frame keeps the whole product visible above the fold.
- **Use:** retained for archive and social fallback crops. No page in the current
  premium direction references this file; cart and checkout now use
  `echo-stone.webp`.
- **Reversibility:** re-crop from `echo-hero-orange.webp`; no destructive edit
  was made to the source.

### `echo-holding.webp`

- **Source:** `magnific_the-person_Sy850RtUb8.png`.
- **Treatment:** direct WebP encode.
- **Content:** two hands holding the open Echo in Violet Alloy.
- **Use:** homepage in-use gallery, About studio section and product care panel;
  shows scale and hand interaction.

### `echo-macro.webp`

- **Source:** `magnific_if-any-text-below-conflicts-with-the-image_mE6Mru5hJQ.png`.
- **Treatment:** direct WebP encode.
- **Content:** close detail of the violet cup, cushion and machined band.
- **Use:** homepage materials section, technology page and the detail view in the
  four-image product gallery.
- **Caution:** the image shows material texture, not a verified material spec.
  Pair it with the placeholder copy, not a recycled-content claim.

### `echo-motion.webp`

- **Source:** `magnific_product-in-motion-generate-11_bx0MUdj5Y2.png`.
- **Treatment:** direct WebP encode, square crop retained from source.
- **Content:** multiple exposure of the product on a lime field.
- **Use:** retained for archive; the lime-field motion crop is not used in the
  current premium direction.
- **Note:** the lime field is a campaign art direction choice; do not use this
  image as evidence of a lime colourway.

### `echo-pool.webp`

- **Source:** `magnific_the-pool_3zHwuoXREY.png`.
- **Treatment:** direct WebP encode.
- **Content:** Echo suspended over a dark reflective pool with stone props.
- **Use:** page-inset homepage hero and the lead view in the four-image product
  gallery.

### `echo-portrait.webp`

- **Source:** `magnific_a-super-photogenic-genz-model_lJBqYAqgv9.png`.
- **Treatment:** direct WebP encode.
- **Content:** model wearing Echo in Violet Alloy.
- **Use:** homepage in-use gallery and the worn view in the product gallery.
- **Caution:** model image is campaign photography. Do not imply the model is an
  employee, endorser or customer unless a release and credit are confirmed.

### `echo-stone.webp`

- **Source:** `magnific_one-flat-matteblack-oval-disc-inset_ovPcgra829.png`.
- **Treatment:** direct WebP encode.
- **Content:** Echo resting on a pale stone plinth.
- **Use:** homepage in-use and closing panels, product gallery still view, cart
  line thumbnail and checkout summary.

### `echo-views.webp`

- **Source:** `magnific_one-flat-matteblack-oval-disc-inset_WDj65sPcXe.png`.
- **Treatment:** direct WebP encode.
- **Content:** configuration sheet showing open, closed and folded states.
- **Use:** retained for archive; not used in the current premium direction.
- **Caution:** the sheet is illustrative. It does not replace engineering
  validation, cycle ratings or a user manual. Mechanism claims stay placeholders.

### `pixel-pattern.png`

- **Source:** `Evaion Pixel Pattern.png`.
- **Treatment:** alpha-preserving optimisation; dimensions unchanged.
- **Use:** retained for archive; the decorative texture is not used in the
  current premium direction.
- **Rule:** if it returns, never place body copy directly over the pattern
  without an opaque scrim.

### `../og-echo.jpg`

- **Source:** `echo-hero-orange.webp`, `evaion-icon.svg`, `evaion-wordmark.svg`.
- **Composition:** 1200 × 630 canvas. Left: orange hero crop. Right: deep-violet
  panel with brand plate, eyebrow “Echo / Violet Alloy”, headline “Sound, folded
  into form.”, supporting line and “Designed in Hyderabad / evaion.in”.
- **Typography:** Inter for the headline and body, IBM Plex Mono for metadata.
- **Export:** Chromium screenshot at 1×, converted to progressive JPEG, quality
  90, sRGB.
- **Use:** Open Graph and Twitter card image on every page.
- **Note:** the card is a campaign composition, not a product-detail image. It
  contains no price, rating or certification.

---

## 3. Brand files copied unchanged

| File | Origin | Notes |
| --- | --- | --- |
| `../evaion-icon.svg` | `ICON.svg` | Supplied icon; favicon, social card and archived brand plate. Hidden in the current wordmark-only header |
| `../evaion-wordmark.svg` | `Wordmark.svg` | Supplied wordmark; used standalone in the header and footer |
| `../favicon-64.png` | Generated from the icon | 64 × 64 PNG |
| `../apple-touch-icon.png` | Generated from the icon | 180 × 180 PNG on an opaque plate |

The spaced wordmark, brand pattern, packaging renders, accessory illustrations
and material crops from the previous site are preserved in
`_archive/evaion-v1/assets` and are not part of this build.

---

## 4. Reproduction notes

To rebuild a derivative:

1. Open the source PNG from the project root.
2. Convert to sRGB if needed; do not apply auto-tone, sharpening or denoise.
3. Resize only with a high-quality resampler if a smaller slot is required.
4. Encode WebP at a quality that keeps the violet gradient free of banding.
   Check the cup highlight and the backdrop at 100% before accepting.
5. Keep the filename and update `width`/`height` attributes anywhere the image
   is referenced.
6. Verify the image still reads as **Violet Alloy**; reject any output that
   shifts the cup toward blue, pink or black.
7. Update this log if the source, crop or treatment changes.

For the social card, the original HTML composition is a build artefact and is not
shipped. Recreate it at 1200 × 630 with the same copy and brand plate, then export
JPEG q90.

---

## 5. Rights and usage

Campaign photography and brand marks are supplied by Evaion. The derived files
are for this storefront only. Do not reuse them in marketplace listings, ads or
press without confirming the applicable usage rights and model releases. Do not
alter the product shape, finish or included contents in derivative imagery.
