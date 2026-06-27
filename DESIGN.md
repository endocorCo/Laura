---
name: Laura Zapién Studio
description: One-page atelier site for a hair artist & makeup artist in Papalotla, Estado de México
colors:
  ivory: "#FBF8F4"
  sand: "#F1E9DE"
  beige: "#E4D5C3"
  warmbeige: "#D8C3AC"
  rosegold: "#B76E79"
  copper: "#B06A4A"
  champagne: "#D9C2A6"
  ink: "#1C1815"
  softgray: "#9C948B"
typography:
  display:
    fontFamily: "Playfair Display, serif"
    fontSize: "clamp(2.5rem, 6vw, 4.5rem)"
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: "normal"
  body:
    fontFamily: "Manrope, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "normal"
  label:
    fontFamily: "Manrope, sans-serif"
    fontSize: "0.72rem"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: "0.32em"
rounded:
  none: "0px"
  full: "9999px"
spacing:
  sm: "0.75rem"
  md: "1.25rem"
  lg: "2rem"
  xl: "5rem"
components:
  button-primary:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.ivory}"
    rounded: "{rounded.none}"
    padding: "16px 36px"
  button-primary-hover:
    backgroundColor: "{colors.rosegold}"
    textColor: "{colors.ivory}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.ivory}"
    rounded: "{rounded.none}"
    padding: "16px 36px"
---

# Design System: Laura Zapién Studio

## 1. Overview

**Creative North Star: "El Atelier de Luz Cálida"**

The site reads like a boutique beauty atelier bathed in soft gold-hour light, not a software product. Every surface is a warm ivory or sand, every accent a muted rosegold or copper, every headline set in Playfair Display so the page feels hand-curated rather than templated. Density is generous: sections breathe with large vertical rhythm (`py-28` to `py-40`), and the page never rushes the visitor toward a CTA grid.

This system explicitly rejects the SaaS-template register: no identical icon-in-circle card grids repeated past their useful count, no scroll-fade-in applied uniformly to every section just because GSAP is loaded, no stock-photo Instagram walls, no hero-metric blocks, no side-stripe borders or gradient text. Real client photography (real hair color results, real quinceañera makeup) carries the proof, not decorative iconography.

**Key Characteristics:**
- Warm ivory/sand backgrounds, never pure white or pure black
- Playfair Display serif for all headlines, italic rosegold accents for emphasis words
- Thin rosegold borders (≤1px, 10-15% opacity) instead of shadows as the default separator
- Editorial list rhythm on mobile (numbered rows + dividers) instead of stacked boxed cards
- Motion is occasional and purposeful (the before/after slider, the scroll progress bar), not a default applied to every section

## 2. Colors

A warm, low-chroma palette: ivory and sand carry the page, rosegold and copper appear only as accents, never as backgrounds for large blocks.

### Primary
- **Rosegold** (#B76E79): the signature accent. Used for the eyebrow labels, link underlines, the scroll progress bar, hover states on borders and icons, italic accent words in headlines (e.g. "*Zapien*"). Never fills a large surface.

### Secondary
- **Copper** (#B06A4A): paired with rosegold in gradients (progress bar, gradient-motion text) and for eyebrow text color. Slightly deeper and warmer than rosegold; used where rosegold would feel too light against ivory.

### Tertiary
- **Champagne** (#D9C2A6): the lightest of the three accent tones, used in the rosegold→copper gradient stops and in the timeline's vertical line. Decorative, not load-bearing.

### Neutral
- **Ivory** (#FBF8F4): the dominant page background.
- **Sand** (#F1E9DE): alternating section background, used to separate sections without a hard line (e.g. Services, Instagram-formerly section, Gallery).
- **Beige** (#E4D5C3) / **Warm Beige** (#D8C3AC): secondary neutral surfaces, icon-badge backgrounds.
- **Ink** (#1C1815): all body text and the dark footer/CTA-band background. A warm near-black, never `#000`.
- **Soft Gray** (#9C948B): muted secondary text and disabled-feeling states.

### Named Rules
**The Rare Accent Rule.** Rosegold and copper are accents, not backgrounds. If an edit is about to fill more than a thin border, an icon, or a short text run with rosegold/copper, reconsider; the warmth comes from ivory/sand doing most of the work.

## 3. Typography

**Display Font:** Playfair Display (serif)
**Body Font:** Manrope (sans-serif)

**Character:** A classic editorial pairing: Playfair's high-contrast serif curves read as couture and confident, Manrope's low-contrast geometric sans keeps body copy calm and legible. The contrast between the two is the entire personality of the page; never substitute a sans for headlines or a serif for body copy.

### Hierarchy
- **Display** (500, `clamp(2.5rem, 6vw, 4.5rem)`, line-height 1.1): hero and section H2s. Often mixes roman and italic weight within the same line for emphasis (italic in rosegold).
- **Title** (500-600, 1.5-2rem): card and subsection headings (service titles, testimonial names).
- **Body** (300-400, 1rem, line-height 1.6): paragraph copy, capped informally around 60-70ch by the `max-w-2xl`/`max-w-3xl` containers already in use.
- **Label** (600, 0.72rem, letter-spacing 0.32em, uppercase): the `.eyebrow` class; section labels and button text. Always copper-colored when used as a section label, ink/ivory when used inside a button.

### Named Rules
**The Whisper Label Rule.** Uppercase tracked labels (`.eyebrow`) are always small (0.72rem) and wide-tracked (0.32em). They introduce a section; they never compete with the Playfair Display headline that follows.

## 4. Elevation

The system is flat by default. Depth comes from thin rosegold borders and warm background-color steps (ivory → sand → ink), not from box-shadow stacking. Shadows exist only as a hover response, never at rest.

### Shadow Vocabulary
- **Card hover lift** (`box-shadow: 0 28px 50px -28px rgba(176,106,74,.3)`): appears only on `.svc-card:hover` at desktop widths; pairs with a `translateY(-8px)` lift. Never present at rest, never on mobile (mobile services are a flat list, no card surface to lift).
- **Generic lift** (`.card-lift`, `box-shadow: 0 30px 60px -30px rgba(28,24,21,.35)`): used for testimonial cards and similar floating panels on hover.

### Named Rules
**The Hover-Only Shadow Rule.** No element carries a shadow at rest. Shadows are a state response to hover/focus, sized and colored to match the warm palette (copper-tinted, not neutral gray).

## 5. Components

### Buttons
- **Shape:** square corners, no border-radius (`rounded.none`) — the page uses zero rounded corners anywhere, which is itself the signature.
- **Primary** (`.btn-primary`): ink background, ivory text, uppercase tracked label, 16px/36px padding. On hover, a rosegold→copper gradient slides up from the bottom (`translateY(101%)` to `0`) rather than a flat color swap.
- **Ghost** (`.btn-ghost`): transparent fill, 1px ivory/60%-opacity border, used over photographic/dark backgrounds (hero CTA secondary action). Hover brightens the border to solid white and tints the fill `rgba(251,248,244,.12)`.

### Cards / Containers
- **Corner style:** square, no radius.
- **Background:** ivory on sand sections (desktop services cards), or fully transparent (mobile services rows, testimonials sit on ivory directly).
- **Border:** 1px rosegold at 14-15% opacity is the default container edge; it brightens to 40% opacity on hover.
- **Shadow strategy:** see Elevation; hover-only.
- **Internal padding:** generous, `2rem` (`p-8`) on desktop card variants; mobile rows use `1rem` vertical (`py-4`) and no horizontal card padding since they're list rows, not boxes.

### Navigation
- Sticky glass nav: `rgba(251,248,244,.72)` background with `blur(18px) saturate(140%)`, 1px rosegold-tinted bottom border. Logo in Playfair Display with the surname in italic rosegold. Links are Manrope, gain a rosegold underline (`.link-underline`) on hover, animated left-to-right via `width: 0 → 100%`.

### Before/After Slider (signature component)
The `.ba-wrap` drag-slider is the one place the system embraces an interactive, tactile component: a draggable vertical handle (`.ba-handle`, 2px white line) with a circular grip (`.ba-grip`, 54px, white at 92% opacity, soft shadow) reveals "después" under "antes". This is the template for what purposeful motion looks like elsewhere: physical, user-driven, tied to real content comparison, not decorative.

## 6. Do's and Don'ts

### Do:
- **Do** keep all corners square (no `border-radius`) except the fully-round `9999px` used for nav buttons, icon badges, and the before/after grip.
- **Do** use Playfair Display for every headline and Manrope for every paragraph; never swap the pairing.
- **Do** treat rosegold/copper as accents on ≤10-15% of any given section's surface.
- **Do** keep shadows hover-only; nothing carries a shadow at rest.
- **Do** use the editorial list pattern (numbered row + thin divider, no boxed card) for repeated content on mobile, matching the Services section fix already shipped.
- **Do** animate only where it clarifies real content (the before/after slider, the scroll progress bar) or signals state (button hover, nav underline).

### Don't:
- **Don't** add identical icon-in-circle card grids repeated past 3-4 items; this is the SaaS-template tell PRODUCT.md explicitly rejects.
- **Don't** apply a uniform scroll-fade-in (`opacity:0; translateY(40px)` reveal pattern) to every section by default. It was already removed from the Services section per direct user feedback ("no te dije que lo animaras, solo que cambiaras el formato") — treat that as the standing rule, not a one-off.
- **Don't** use stock-photo grids (e.g. a generic Instagram wall); the Instagram section was removed entirely for this reason.
- **Don't** use gradient text, side-stripe borders (`border-left`/`border-right` accents), glassmorphism beyond the nav, or hero-metric blocks.
- **Don't** let rosegold/copper become a background fill on anything larger than a thin border, icon, or short text run.
- **Don't** mix in a second display typeface or a rounded-corner system; square corners and the Playfair/Manrope pairing are non-negotiable identity markers.
