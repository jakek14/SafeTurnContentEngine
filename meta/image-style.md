# Safe Turn — Image Style Guide

Shared brand visual identity for Facebook and Instagram. Each daily Meta post must include an image prompt the human can paste into **Nano Banana** (Gemini 2.5 Flash Image) or **ChatGPT Image 2** to generate the asset.

## Brand Visual Identity (sourced from safeturnadvisory.com)

- **Primary palette:**
  - Off-white background `#FAFAFA` (pristine, slight warmth — not pure white)
  - Deep navy `#0F1B2D` (text, structural elements, badge outlines)
  - Muted teal accent `#3A8A8A` (the only color note — used sparingly as punctuation)
- **Typography zone:** Sans-serif (geometric/humanist family — think Inter, Söhne, or similar). Bold weight for pull quotes, regular for subtitle.
- **Aesthetic:** Minimalist corporate financial advisory. Calm, reassuring authority. Buttoned-up but not cold.
- **Distinctive motif:** A small geometric badge/seal mark recurs throughout the brand — use as a quiet anchor in the bottom corner of every image (outline only, no internal text).
- **Tagline / brand voice cue:** "Replace panic with a plan." — every visual should feel grounded and methodical, never urgent or alarming.

## Default Image Format: Pull-Quote Card

This is the format every Meta post uses. It's the most reliable for AI image generators (Nano Banana garbles complex scenes, ChatGPT Image 2 is more accurate but both nail simple text-card layouts). It's also what works on Meta — saveable, scannable at thumbnail, brand-consistent.

**Structure:**
- Pristine off-white background with a subtle paper-texture grain
- A single vertical sliver of muted teal running down one edge (left for FB, left or right for IG — vary)
- Center: clean empty space reserved for a manually-added text overlay
- Bottom corner: small geometric badge mark (dark navy outline, no internal text)
- No people, no stock photography, no decorative icons

## Image-Prompt Best Practices

Every generated prompt must follow these rules. The agent assembles the prompt; the human pastes it into Nano Banana or ChatGPT Image 2.

### DO
- **State aspect ratio explicitly** at the start (e.g., "4:5 portrait, 1080×1350 pixels")
- **Lead with composition** — describe the layout before describing the elements
- **One focal point** — empty center for text overlay, ONE accent element, ONE corner anchor (the badge)
- **Specific colors with hex codes** — `#FAFAFA`, `#0F1B2D`, `#3A8A8A`. Do not say "navy" or "teal" without the hex.
- **Specific texture** — "subtle paper-grain texture, faintly visible at close inspection"
- **Specify what to leave EMPTY** — "the center vertical third left clean and unmarked, reserved for typography to be added in post-production"
- **Specify NO TEXT in the image** — text overlay is added manually after generation (AI text rendering is unreliable even on ChatGPT Image 2)

### DON'T
- **No human faces, hands, bodies, or silhouettes.** Looks fake or generic-stock. Brand uses real photography on the website only — AI-rendered humans never match.
- **No multi-element compositions** — no flowing data streams, network nodes, infographic arrows, or anything that "tells a story" through visual elements
- **No metaphor literalism** — do not draw a road with a safe turn, a wallet with money, a calendar with circled dates, a stressed business owner, etc. AI generators butcher metaphors.
- **No corporate clip-art tropes** — handshakes, building skylines, abstract line graphs trending up, light-bulb idea icons, digital-blue-circuitry backgrounds
- **No words, headlines, statistics, or labels rendered inside the image.** Text overlay is added in post.
- **No bright colors** — the palette is strictly off-white, navy, and a single teal accent. No reds, no oranges, no yellows.

## Output Structure in Each Draft File

Each daily Meta draft file (`meta/facebook/drafts/YYYY-MM-DD.md` and `meta/instagram/drafts/YYYY-MM-DD.md`) must contain three sections in this exact order:

```
<!-- VISUAL: Pull-quote text card. Format: [4:5 portrait | 1:1 square]. -->

[caption text — full, hashtags included]

---

## Image Prompt (paste into Nano Banana or ChatGPT Image 2)

[Full prompt — see template below]

## Text Overlay (add manually after image generation)

Headline: "[short pull-quote from caption — 6–12 words max]"
Subtitle: SafeTurnAdvisory.com
```

The HTML comment at the top is the human-readable visual brief. The `## Image Prompt` block is what gets pasted into the image generator. The `## Text Overlay` block is what the human adds in Canva/Figma/Photoshop after the AI image is generated.

## Prompt Templates

### Template A — Pull-Quote Card (default)

Use this for ~90% of posts. Most reliable, most consistent.

```
A minimalist [4:5 portrait | 1:1 square] pull-quote graphic.
Background: pristine off-white #FAFAFA with a subtle paper-grain texture, faintly visible at close inspection.
A single vertical sliver of muted teal #3A8A8A running down the [left | right] edge, approximately 8% of the frame width, soft and unobtrusive.
Center two-thirds of the frame: completely clean, empty, reserved for typography to be added in post-production.
Bottom-[left | right] corner: a small geometric badge/seal mark in dark navy #0F1B2D outline only, simple and modern, approximately 6% of the frame width.
No people, no faces, no hands, no silhouettes, no decorative icons, no clip-art, no graphs, no infographic elements, no words or text rendered anywhere in the image.
Calm, professional, financial-advisory aesthetic. High-end editorial feel, like a quiet page in a financial quarterly.
[4:5 portrait, 1080×1350 pixels | 1:1 square, 1080×1080 pixels].
```

Substitute the bracketed `[options]` per channel and per post (alternate edge sides for visual variety across the calendar).

### Template B — Architectural Texture (use sparingly, ~10% of posts)

Use only when the post's core idea benefits from a quiet abstract texture in the background — e.g., for a "structure" or "foundation" themed post. Slightly higher generation risk; review output before posting.

```
A minimalist [4:5 portrait | 1:1 square] graphic.
Background: pristine off-white #FAFAFA, with a subtle close-up architectural texture occupying the [top third | left third] of the frame — soft focus, [exposed concrete | brushed steel | matte stone | aged paper grain], in muted neutral tones with a faint navy #0F1B2D shadow gradient. The remainder of the frame is clean off-white empty space.
Bottom-right corner: a small geometric badge/seal mark in dark navy #0F1B2D outline, approximately 6% of the frame width.
No teal accent in this variant — let the texture carry the visual weight.
No people, no words, no decorative icons, no clip-art, no graphs.
Calm, grounded, structural — the visual equivalent of "stability under pressure".
[4:5 portrait, 1080×1350 pixels | 1:1 square, 1080×1080 pixels].
```

## Channel-Specific Aspect Ratios

- **Facebook** → **4:5 portrait (1080×1350)** preferred for FB feed (33% more mobile screen). 1:1 (1080×1080) acceptable second choice.
- **Instagram** → **4:5 portrait (1080×1350)** preferred for feed. 1:1 (1080×1080) for grid-consistency or carousel use.

If FB and IG land on the same aspect ratio in a given week, that's fine — the captions are different so the posts read as distinct.

## Text Overlay (Manual Step — Done in Canva/Figma)

After the image is generated, the human adds the text overlay before posting:

- **Font:** Inter Bold for headline, Inter Regular for subtitle (or closest sans-serif available)
- **Headline color:** Deep navy `#0F1B2D` on the off-white background
- **Subtitle color:** Muted teal `#3A8A8A`
- **Headline placement:** Centered horizontally, vertically positioned in the upper-middle of the empty center zone
- **Subtitle placement:** A line below the headline, smaller, lighter weight
- **Safe zones (Instagram especially):** Keep all text within the center 70% — Instagram overlays UI elements (profile picture, username, action buttons) in the top 14% and bottom 35%
- **Headline length:** 6–12 words. Pull a phrase directly from the caption.

## What This Engine Does NOT Do

- The engine does **not** call any image-generation API directly. It writes the prompt; the human runs it in Nano Banana or ChatGPT Image 2.
- The engine does **not** add text overlay. That's a manual step in Canva/Figma after the image is generated.
- The engine does **not** post the image to Vista. Jake creates the final asset and uploads it manually to the editable Vista draft (already populated with the caption from this engine).
