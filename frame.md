---
version: alpha
name: e2a — Frame (video / frame layer)
description: >
  Warm-editorial brand system for the e2a launch film, at frame scale (1920×1080).
  Atoms are sacred: warm cream paper (never pure white), dark ink voice, a single
  amber accent as scarce "voltage", and canopy green as the structural dark surface
  (agent cards, terminal, end card). Fraunces for all display + Inter body + JetBrains
  Mono for the index / code / address voice. Sentence-case display, hairline elevation.
unit: the frame — 1920×1080 primary
principle: atoms are sacred · composition is free · text comes from the script
canvas: "#faf7f2"

colors:
  ink: "#1a1714"
  ink-soft: "#23201c"
  cream: "#faf7f2"
  tile: "#f2ece2"
  tile-strong: "#ece4d6"
  fg-muted: "#6e665b"
  fg-subtle: "#9a9082"
  border: "#e5ded3"
  border-strong: "#d5ccbc"
  canopy: "#2b4033"
  canopy-hov: "#223529"
  canopy-deep: "#1e2e24"
  canopy-fg: "#f2ece2"
  canopy-line: "#3c5545"
  moss: "#5c6f51"
  amber: "#c17d2b"
  amber-soft: "#f6ead3"
  amber-strong: "#8a5214"
  info: "#2d6cff"

borders:
  hairline: "1px solid ink@12%"
  hairline-strong: "1px solid ink@20%"
  dark: "1px solid canopy-fg@14% (on canopy)"
shadows:
  card: "0 1px 3px ink@8%, 0 6px 20px ink@5%"
  none: "none"

typography:
  body:      { fontFamily: "Inter", cqw: 1.5, weight: 400, lineHeight: 1.5 }
  lead:      { fontFamily: "Inter", cqw: 2.08, weight: 400, lineHeight: 1.5 }
  card-title:{ fontFamily: "Inter", cqw: 2.3, weight: 500, lineHeight: 1.25, tracking: "-0.005em" }
  button:    { fontFamily: "Inter", cqw: 1.46, weight: 500, lineHeight: 1.0 }
  tag-upper: { fontFamily: "Inter", cqw: 1.35, weight: 500, tracking: "0.18em", upper: true }
  kicker:    { fontFamily: "JetBrains Mono", cqw: 1.35, weight: 500, tracking: "0.16em", upper: true }
  mono-label:{ fontFamily: "JetBrains Mono", cqw: 1.35, weight: 500, tracking: "0.02em" }
  address:   { fontFamily: "JetBrains Mono", cqw: 1.7, weight: 500, tracking: "0em" }
  code:      { fontFamily: "JetBrains Mono", cqw: 1.6, weight: 400, lineHeight: 1.6 }
  # — display ramp: Fraunces, sentence case, negative tracking —
  headline:  { fontFamily: "Fraunces", cqw: 4.6, weight: 400, lineHeight: 1.06, tracking: "-0.018em" }
  display:   { fontFamily: "Fraunces", cqw: 7.3, weight: 400, lineHeight: 1.02, tracking: "-0.022em" }
  display-cover:{ fontFamily: "Fraunces", cqw: 9.4, weight: 400, lineHeight: 0.98, tracking: "-0.028em" }

spacing:
  slide-pad: "4.2cqw"
  gap-md: "1.7cqw"
  hairline: "1px"
  radius-sm: "6px"
  radius-md: "10px"
  radius-lg: "14px"
  radius-pill: "9999px"

components:
  card-hairline:
    backgroundColor: "{colors.cream} or {colors.tile}"
    border: "1px solid {colors.ink}@12%"
    rounded: "{spacing.radius-lg}"
    shadow: "{shadows.card}"
    description: "The editorial content card. Elevation is the hairline + ONE soft warm shadow — never a heavy drop, glow, or gradient."
  agent-card:
    backgroundColor: "{colors.canopy} body / {colors.canopy-hov} header"
    textColor: "{colors.canopy-fg}"
    border: "1px solid {colors.canopy-line}"
    rounded: "{spacing.radius-lg}"
    description: "An agent identity card on the canopy-green surface: avatar dot, agent name (Inter 500), and its real address in JetBrains Mono. The address is exact vector text, e.g. research@agents.e2a.dev."
  email-card:
    backgroundColor: "{colors.cream}"
    border: "1px solid {colors.border}"
    rounded: "{spacing.radius-md}"
    description: "An email / message row: from-address (mono), subject (Inter 500), one-line preview (Inter 400 muted), a hairline meta strip. Threaded replies indent one step under the original."
  amber-callout:
    backgroundColor: "{colors.amber} (full-bleed) or {colors.cream} with an amber edge"
    textColor: "{colors.cream} on amber"
    rounded: "{spacing.radius-md}"
    description: "The ONE voltage moment per frame — a CTA, an Approve action, or a status stamp. Never two ambers in one frame."
  status-stamp:
    description: "A small pill stamp: 'delivered' / 'sent' in moss green, 'Held for approval' in amber. Mono uppercase 0.14em."
  code-surface:
    backgroundColor: "{colors.canopy-deep} body / {colors.canopy-hov} title bar"
    textColor: "{colors.canopy-fg} (JetBrains Mono); prompt in {colors.moss}, command emphasis in {colors.amber}"
    border: "1px solid {colors.canopy-fg}@14%"
    rounded: "{spacing.radius-md}"
    description: "The terminal surface for the install command. Command is exact text: claude plugin install e2a@e2a."
  section-rule:
    rule: "1px solid {colors.ink}@12%"
    description: "The only separator. An amber 1px rule may draw on to introduce a beat. Never 2px+, never heavy."
  kicker-spike:
    typography: "{typography.kicker}"
    mark: "✱ amber spike prefix"
    description: "The eyebrow — JetBrains Mono uppercase, indexical (2–4 words), prefixed with an amber ✱."
---

# e2a — Frame (video / frame layer)

## Overview

e2a at frame scale is a **warm-editorial brand book in motion** — the register of a
literary imprint that ships open-source software. The thesis is three colors: **cream
is the ground, ink is the voice, amber is the voltage** — and a fourth, **canopy
green**, only where the product's own surfaces show themselves (agent identity cards,
the terminal, the end card). Every surface is **warm cream** (never pure white, never
cool gray); content gathers on a **tile** surface half a step darker. Elevation is a
**1px hairline** ink border at low alpha plus, rarely, one soft warm shadow.

Three voices, three faces: **Fraunces** carries every display moment (hook, headline,
tagline) at large sizes with gentle negative tracking, sentence case, weight 400.
**Inter** carries body, leads, card titles, UI chrome. **JetBrains Mono** carries the
indexical layer — kickers, status stamps, terminal, and every **email address** (the
address is the product; it is always mono, always exact).

**Key characteristics:**

- **Cream / ink / amber trinity** + a **canopy-green** product surface.
- **Fraunces** sentence-case display; **Inter** body/chrome; **JetBrains Mono** addresses + code + kickers.
- **Hairline elevation** — 1px low-alpha ink border + at most one soft warm shadow. No heavy drop, glow, or gradient on content.
- **Amber is rationed** — at most ONE amber moment per frame (an Approve, a status stamp, or a CTA); amber never sets a headline or body run.
- **The ✱ amber spike** opens kickers; canopy green anchors the agent cards, terminal, and end card.

## The Frame

- **Primary:** 1920×1080 (16:9). Display authored in **`cqw`** (`px ÷ 1920 × 100 = cqw`).
- **Container law:** every frame ground sets `container-type: size`; all frame-relative units are `cqw`/`cqh`, never `vw`. Hairlines stay 1px; radii stay 6/10/14px.
- **Safe area:** `slide-pad` ~4.2cqw; kicker/mono chrome sit inside it.

## Colors

Default ground `cream`; content gathers on `tile` / `tile-strong` (half-step warm
steps, never hard contrast). Headlines & body `ink` on cream; `canopy-fg` on canopy.
**Amber** is the scarce voltage — one moment per frame, never body text, never a card
fill of a content card. **Canopy green** (`canopy` / `canopy-hov` / `canopy-deep`) is
the product / terminal / identity surface — a structural anchor, not a fourth accent.
Status: success/delivered `moss`, hold `amber`. **No cool grays, no pure white, no
pure black.**

## Typography

- **Legibility floor:** any load-bearing line ≥ **1.4cqw**.
- **Fit-to-measure:** ≤3 words → `display-cover`; 4–6 → `display`; 7+ → `headline`.
- **Fraunces display is sentence case** (not title case, not uppercase), weight 400,
  negative-tracked. **Inter body** sentence case weight 400. **JetBrains Mono**
  kickers UPPERCASE 0.16em with the amber ✱; **addresses** in mono, exact, not tracked.
- One brand word may take amber in a headline (e.g. "agents") — that spends the frame's
  one amber moment.

## Depth & Surface

- **1px hairline** ink border ~12% alpha is the primary lift.
- **One soft warm shadow** used rarely, never heavy.
- **Half-step surface** — a tile block on cream reads elevated by warmth, not shadow.
- **Ceiling:** no heavy drop shadow, glow, gradient on content, or tilt.

## Shapes

- **6px** small chrome, **10px** cards / email rows / terminal, **14px** large cards,
  **9999px** true pills only. Gently rounded, never hard, never heavy.

## Components

- **card-hairline** — editorial content card. **agent-card** — canopy-green identity card (avatar, name, mono address). **email-card** — a message row; threaded replies indent one step.
- **amber-callout** — the one voltage moment (Approve / CTA / status stamp). **status-stamp** — `delivered`/`sent` (moss) or `Held for approval` (amber).
- **code-surface** — the canopy-deep terminal for the install command. **section-rule** — the only separator. **kicker-spike** — the ✱ amber eyebrow.

## Approved Real Entities

- **e2a wordmark** — set as lowercase `e2a` in Fraunces (or the captured SVG at `capture/assets/logo-7019259d.svg` when it reads cleanly). **Addresses:** `research@agents.e2a.dev`, `sales@agents.e2a.dev` — exact mono, the shared domain (never `@e2a.dev` root). **URL:** `e2a.dev`. **Command:** `claude plugin install e2a@e2a` — exact.

## Do / Don't

**Do:** stand every frame on warm cream; set display in Fraunces sentence case; ration
amber to one moment; elevate with a hairline; render every address in exact mono;
reserve canopy green for the product surfaces.

**Don't:** no pure white / cool gray / pure black; no heavy drop shadow / glow /
gradient / tilt; no uppercase or title-case Fraunces; no sans headline; no serif-set
address; no two amber moments in one frame; never invent an address or alter the
install command.

## Fonts

Load Fraunces (display, 400), Inter (400/500), and JetBrains Mono (400/500) via
`<link>` to Google Fonts in each frame; if a serif fails to load, fall to Georgia —
never to a sans.
