# Safe Turn — Image Style Guide

Shared brand visual identity for Facebook and Instagram. Each daily Meta post must include an image prompt the human can paste into **ChatGPT Image 2** (recommended for accurate text rendering) or **Nano Banana** to generate the **finished asset, fully ready to post — no Canva/Figma editing required.**

## Brand Visual Identity (sourced from safeturnadvisory.com)

- **Primary palette:**
  - White background `#FFFFFF` (clean, pure white)
  - Dark blue `#242E40` (headline text, structural elements, badge outlines)
  - Brand green `#23A85B` (subtitle text, single edge sliver — the only color note, used sparingly)
- **Typography zone:** Sans-serif geometric/humanist family. Specify "modern sans-serif similar to Inter, Söhne, or Neue Haas Grotesk" in the prompt.
- **Aesthetic:** Minimalist corporate financial advisory. Calm, reassuring authority. Buttoned-up but not cold.
- **Distinctive motif:** A small geometric badge/seal mark recurs throughout the brand — included as a quiet anchor in the bottom corner of every image (outline only, no internal text).
- **Tagline / brand voice cue:** "Replace panic with a plan." — every visual feels grounded and methodical, never urgent or alarming.

## Default Image Format: Pull-Quote Card (Text Embedded)

Every Meta post uses this format. The image generator produces a finished, post-ready asset with the headline and subtitle rendered directly in the image. No post-production.

**Structure:**
- Pristine white background with subtle paper-texture grain
- A single thin vertical sliver of brand green running down one edge
- **Headline text rendered in the upper-middle center** — bold sans-serif, dark blue, exact wording specified in the prompt
- **Subtitle text rendered below the headline** — lighter weight sans-serif, brand green, the URL `SafeTurnAdvisory.com`
- Bottom corner: small geometric badge mark (dark blue outline, no internal text)
- No people, no stock photography, no decorative icons

## Image-Prompt Best Practices for Embedded Text

ChatGPT Image 2 is the best current option for rendering text accurately in images. Nano Banana is more inconsistent — if generating with Nano Banana, expect to occasionally regenerate when text comes out garbled.

### DO
- **Quote the exact text** in the prompt: `the headline reads exactly: "Fast cash isn't the same as affordable cash."` — quotation marks help the model lock in the literal string
- **Specify font characteristics** — "modern sans-serif, bold weight, similar to Inter Bold" for headline; "modern sans-serif, regular weight, similar to Inter Regular" for subtitle
- **Specify exact colors with hex codes** — `#FFFFFF`, `#242E40`, `#23A85B`
- **Specify position precisely** — "headline centered horizontally, vertically positioned in the upper-middle third of the frame; subtitle on a single line directly below the headline, smaller size"
- **Specify aspect ratio at the start** — "4:5 portrait, 1080×1350 pixels"
- **Add 'render the text exactly as written, with correct spelling and punctuation'** to reinforce
- **State 'no other text anywhere in the image except the headline and subtitle specified'** to prevent the model from adding extra labels

### DON'T
- **No human faces, hands, bodies, or silhouettes.** AI-rendered humans never match the brand's real photography.
- **No multi-element compositions** — flowing data, network nodes, infographic arrows, anything that "tells a story" through visuals
- **No metaphor literalism** — do not draw a road with a safe turn, a wallet, a stressed business owner, etc.
- **No corporate clip-art tropes** — handshakes, building skylines, abstract trending-up graphs, light-bulb icons, digital-blue-circuitry
- **No bright colors beyond the brand palette** — strictly white, dark blue, single green accent. No reds, oranges, yellows.
- **No additional text beyond the headline and subtitle** — no taglines, watermarks, social handles outside of `SafeTurnAdvisory.com` subtitle

## Output Structure in Each Draft File

Each daily Meta draft file contains two sections:

```
<!-- VISUAL: Pull-quote card. Format: 4:5 portrait. Text embedded. -->

[caption text — full, hashtags included]

---

## Image Prompt (paste into ChatGPT Image 2 — recommended — or Nano Banana)

[Full prompt — paste-ready, includes exact headline/subtitle text and full styling]
```

Just two sections. No "Text Overlay" / no "Add manually after generation" step. The image generator produces the finished asset.

## Prompt Templates

### Template A — Pull-Quote Card (default)

Use for ~90% of posts.

```
A minimalist [4:5 portrait | 1:1 square] pull-quote graphic for a financial advisory brand.

Background: pristine white #FFFFFF with a subtle paper-grain texture, faintly visible at close inspection.

A single vertical sliver of brand green #23A85B running down the [left | right] edge, approximately 8% of the frame width, soft and unobtrusive.

Centered horizontally, vertically positioned in the upper-middle third of the frame, render this headline text exactly as written, with correct spelling and punctuation: "[EXACT HEADLINE TEXT — pulled from the caption, 6–12 words]"
The headline is in modern sans-serif typography, similar to Inter Bold or Söhne Bold, in dark blue #242E40, large enough to read clearly at thumbnail size, with comfortable line spacing.

On a single line directly below the headline, smaller and lighter, render this subtitle text exactly: "SafeTurnAdvisory.com"
The subtitle is in modern sans-serif regular weight, in brand green #23A85B.

Bottom-[left | right] corner: a small geometric badge/seal mark in dark blue #242E40 outline only, simple and modern, approximately 6% of the frame width. No text inside the badge.

NO other text anywhere in the image except the headline and the SafeTurnAdvisory.com subtitle specified above.
NO people, faces, hands, silhouettes, decorative icons, clip-art, graphs, or infographic elements.

Calm, professional, financial-advisory aesthetic. High-end editorial feel, like a quiet page in a financial quarterly.

[4:5 portrait, 1080×1350 pixels | 1:1 square, 1080×1080 pixels].
```

Substitute every bracketed `[option]` per channel and per post (alternate edge sides for visual variety across the calendar).

### Template B — Architectural Texture (use sparingly, ~10% of posts)

Use only when the post's core idea is genuinely structural (foundations, stability under pressure, etc.).

```
A minimalist [4:5 portrait | 1:1 square] graphic for a financial advisory brand.

Background: pristine white #FFFFFF, with a subtle close-up architectural texture occupying the [top third | left third] of the frame — soft focus, [exposed concrete | brushed steel | matte stone | aged paper grain], in muted neutral tones with a faint dark blue #242E40 shadow gradient. The remainder of the frame is clean white empty space.

Centered in the lower-middle of the frame, render this headline text exactly as written: "[EXACT HEADLINE TEXT — 6–12 words]"
The headline is in modern sans-serif bold, similar to Inter Bold, in dark blue #242E40, large enough for thumbnail readability.

On a single line directly below, smaller, lighter weight, render this subtitle exactly: "SafeTurnAdvisory.com"
Subtitle in modern sans-serif regular, brand green #23A85B.

Bottom-right corner: a small geometric badge/seal mark in dark blue #242E40 outline, approximately 6% of the frame width. No text inside the badge.

NO green edge sliver in this variant — the architectural texture carries the visual weight.
NO other text anywhere in the image except the headline and SafeTurnAdvisory.com subtitle specified above.
NO people, decorative icons, clip-art, graphs, or infographic elements.

Calm, grounded, structural — the visual equivalent of "stability under pressure".

[4:5 portrait, 1080×1350 pixels | 1:1 square, 1080×1080 pixels].
```

## Channel-Specific Aspect Ratios

- **Facebook** → **4:5 portrait (1080×1350)** preferred. 1:1 (1080×1080) acceptable second choice.
- **Instagram** → **4:5 portrait (1080×1350)** preferred. 1:1 (1080×1080) for grid consistency or carousel use.

## Instagram Safe Zone (when asking the generator to position text)

For Instagram feed posts at 4:5, headline text should sit within the **center 80% vertically** so it isn't cropped when the post displays in IG's grid view (grid crops 4:5 down to 1:1 by trimming top and bottom). The "upper-middle third" position in Template A already satisfies this.

Stories format is not used by this engine.

## Recommended Generator: ChatGPT Image 2

ChatGPT Image 2 renders text with high accuracy and follows positional instructions reliably. It's the safer default for these prompts.

**Nano Banana** (Gemini 2.5 Flash Image) can also produce these but text rendering is less consistent — be ready to regenerate 1–2 times to get clean text.

If Nano Banana keeps garbling the text after 2 retries, fall back to ChatGPT Image 2.

## What This Engine Does NOT Do

- The engine writes the prompt; the human runs it through ChatGPT Image 2 or Nano Banana.
- The engine does NOT call any image-generation API directly.
- The engine does NOT post FB/IG to Vista. Jake uploads the finished image alongside the caption to Vista manually.
