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

## Per-Channel Template Defaults (REQUIRED)

Facebook and Instagram must look visibly different at a glance — same brand, different aesthetic register. Use the channel's default template every day:

- **Facebook → Template A (Light Editorial Pull-Quote)** — white background, dark-blue headline, restrained. Caption does most of the work; image is quiet authority. Matches FB's older, more analytical reader.
- **Instagram → Template C (Dark Bold Poster)** — dark-blue background, white headline, bolder/more graphic. Image carries the post; caption supplements. Matches IG's image-first feed and faster scroll.

Same color palette in both, opposite color emphasis. A user following both feeds sees the brand's range, not duplicate posts.

Template B (Architectural Texture) is a structural-themed variant used sparingly on either channel — see below.

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

### Template A — Light Editorial Pull-Quote (Facebook default)

The quiet, restrained version. White background, dark-blue headline. Use for ~90% of Facebook posts.

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

### Template C — Asymmetric Color-Block Poster (Instagram default)

A fundamentally different *layout* than Template A — not just different colors. Template A is a centered editorial card on white. Template C is an asymmetric color-block composition with the headline left-aligned in a dark zone next to a bold green color block. Magazine-cover energy.

Use for ~90% of Instagram posts. This is the deliberate visual differentiator from Facebook — side-by-side with a Template A image, the layouts read as obviously different design languages.

```
A bold, asymmetric [4:5 portrait | 1:1 square] poster graphic for a financial advisory brand.

The frame is split vertically into two solid color blocks with a clean, crisp boundary between them — no gradient, no texture across the seam:
- LEFT 30% of the frame: solid brand green #23A85B, full height. Flat color.
- RIGHT 70% of the frame: solid dark blue #242E40, full height. Flat color.

The seam between the two color blocks is a clean vertical line at 30% from the left edge.

Inside the dark blue area (the right 70% of the frame), positioned vertically centered, render this headline text exactly as written, with correct spelling and punctuation: "[EXACT HEADLINE TEXT — pulled from the caption, 6–12 words]"
The headline is left-aligned (NOT centered horizontally — left-aligned to a vertical axis approximately 5% inside the dark blue area, near but not touching the green/blue seam). Modern sans-serif typography, similar to Inter Bold or Söhne Bold, in pure white #FFFFFF, large and confident, breaking onto multiple lines if needed. Generous tracking, comfortable line spacing.

Below the headline, on the same left-aligned axis, render this subtitle text exactly: "SafeTurnAdvisory.com"
The subtitle is in modern sans-serif regular weight, smaller, in pure white #FFFFFF.

Inside the green area (the left 30%), at the bottom, render a small geometric badge/seal mark in white #FFFFFF outline only, simple and modern, approximately 50% of the green block's width. No text inside the badge.

NO other text anywhere in the image except the headline and the SafeTurnAdvisory.com subtitle specified above.
NO people, faces, hands, silhouettes, decorative icons, clip-art, graphs, or infographic elements.
NO additional shapes, lines, or accent marks beyond the two color blocks, the headline, the subtitle, and the small badge.
NO horizontal bands, edge slivers, or border elements — the design IS the asymmetric color block.

Confident, graphic, magazine-spread or movie-poster aesthetic. Strong asymmetric composition that reads as a deliberate design choice, not an unbalanced layout. Should feel like a deliberate poster, not a quote card.

[4:5 portrait, 1080×1350 pixels | 1:1 square, 1080×1080 pixels].
```

Substitute every bracketed `[option]` per post. The 30/70 split stays constant across the calendar — that's the visual signature of the IG feed.

### Template B — Architectural Texture (use sparingly, ~10% of posts on either channel)

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
