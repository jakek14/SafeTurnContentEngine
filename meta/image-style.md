# Safe Turn — Image Style Guide

Shared brand identity and creative direction for Facebook and Instagram images. **Every post gets its own custom image design — no templates, no fill-in-the-blank layouts.** The engine reads the caption, identifies a visual hook unique to that post, and writes a paste-ready prompt for **ChatGPT Image 2** (recommended) or **Nano Banana** that produces a finished, post-ready asset with text embedded directly in the image.

## North Star

The Meta feed should look like a real graphic designer makes one custom card per day, not like a content engine cranking out the same template with different words.

If two consecutive posts on the same channel look like the same design with different headlines, the engine has failed its job. Each post needs a different *composition, visual centerpiece, color emphasis,* and *mood* than the last several posts on its channel.

---

## Brand Identity (immutable)

- **Palette:**
  - White `#FFFFFF`
  - Dark blue `#242E40`
  - Brand green `#23A85B`
  - That's it. No other colors. The variety comes from how the three are arranged, not from new hues.
- **Typography:** Modern sans-serif. Inter, Söhne, Neue Haas Grotesk, or close visual equivalents. Specify in every prompt.
- **Tone:** Calm, reassuring authority. Buttoned-up but not cold. The brand cue is "Replace panic with a plan" — never urgent, never alarming.
- **Recurring motif:** A small geometric badge/seal mark in dark blue or white outline, placed as a quiet anchor somewhere in the composition. Position varies — corner, edge, inside a color block, or omitted entirely some posts.

---

## Hard Rules (apply to every image)

- **No human faces, hands, bodies, silhouettes.** AI-rendered humans never match a real-photography brand.
- **No clip-art / corporate stock tropes.** Handshakes, skylines, trending-up graphs, light-bulb icons, digital-blue-circuitry, briefcases, gears, etc. — all banned.
- **No metaphor literalism.** Do not draw a road with a safe turn, a wallet, a stressed founder, a clock, a key, a lock. Visual ideas come from typography, color, composition, abstract shapes, and texture — never from drawing the metaphor.
- **No fabricated stats inside the image.** Numbers in the image must come from a real source cited in the post.
- **No additional text beyond the headline + subtitle specified in the prompt.** No taglines, watermarks, extra labels, social handles, or stray words. The model often wants to add "trusted" or "premium" — block it explicitly.
- **No bright colors outside the brand palette.** Strictly white, dark blue, brand green.
- **Aspect ratio:** 4:5 portrait (1080×1350) is the default for both FB and IG. 1:1 (1080×1080) only when there's a deliberate reason.

---

## Variety Mandate

When generating today's image prompt, the engine MUST review the **last 5 image prompts on the same channel** (read the most recent draft and published files in `meta/facebook/` or `meta/instagram/`) and ensure the new prompt differs meaningfully on at least three of these five axes:

1. **Composition** — where does the eye go first? Centered, asymmetric, full-bleed type, off-axis, framed, layered, diagonal, stacked-hierarchy, color-blocked, edge-anchored.
2. **Visual centerpiece** — what's carrying the image? The headline typography, a stat numeral, a geometric shape, a texture, negative space, a color block, a typographic echo / repetition.
3. **Color dominance** — which color owns the most of the frame? White-dominant, dark-blue-dominant, green-dominant, balanced split, monochrome + single accent.
4. **Headline treatment** — how is the headline rendered? Single weight centered, two-tone (different words different colors), oversized scale, mixed sizes, all caps, tight kerning, generous tracking, on a color block, on a texture, framed by negative space.
5. **Mood** — calm/quiet, confident/declarative, sober/serious, contemplative, scroll-stopping/loud, editorial/restrained.

If three of those five aren't different from any of the last 5 prompts on this channel, redesign before writing the prompt.

---

## Composition Vocabulary (inspiration, not templates)

These are *patterns* — the engine combines and adapts them. Mix axes freely. Don't stick rigidly to any single one.

- **Editorial pull-quote** — centered headline on a clean field with one tiny accent
- **Asymmetric color-block split** — frame divided into two solid color regions, headline anchored in one
- **Stat hero** — a single large number or percentage carries the image; supporting text smaller
- **Typographic poster** — oversized headline that fills the frame, may bleed to the edges
- **Two-tone headline** — different words/phrases of the headline rendered in different brand colors for emphasis
- **Echoed type** — the same word/phrase appears at two different sizes or weights, creating visual rhythm
- **Vertical/horizontal band layout** — a single solid color band of varying width holds part of the composition
- **Framed document** — a thin border, like a financial memo or letterhead, surrounds the headline
- **Texture-anchored** — a real-world texture (concrete, stone, paper grain, brushed metal, raw linen) occupies a region of the frame; headline sits on the clean part
- **Layered geometry** — overlapping rectangles or squares in the brand colors create depth; headline sits within or alongside
- **Negative-space hero** — the headline is small, deliberately surrounded by empty space; the emptiness is the design
- **Color-blocked footer** — the bottom 1/3 is a solid dark blue or green block holding the subtitle and badge; headline sits on the white above
- **Diagonal split** — a clean diagonal line divides white and a brand color; headline straddles or is in one half
- **Monogram anchor** — a single oversized geometric form (circle, square, triangle, vertical bar) in green or dark blue acts as the visual anchor; headline alongside

The engine should generate at least 3 different composition ideas per post and pick the strongest, biased toward whatever has *not* been used recently on that channel.

---

## Visual Element Vocabulary (also inspiration)

When the design wants a non-typographic element:

- **Geometric primitives** — circles, squares, rectangles, triangles, vertical/horizontal bars, simple outlined shapes (the badge mark fits here)
- **Real-world textures (close-up, shallow depth)** — exposed concrete, brushed steel, matte stone, aged paper grain, raw linen, wood grain, marble
- **Subtle patterns** — fine grid, dot pattern, thin diagonal stripes, faint topographic lines (use sparingly, never busy)
- **Gradients within the palette** — soft transitions from white to a tinted near-white, or from dark blue to a slightly lighter blue (no rainbow gradients ever)
- **Negative space / paper white** — emptiness as a design element, framing the typography

---

## Per-Channel Bias (loose, not rigid)

These are tendencies, not rules. Mix when the post calls for it.

- **Facebook** tends toward more *editorial* / quieter / longer-caption-friendly compositions — text-forward, restrained, white or balanced color emphasis. Reader is more analytical, scrolls slower, can sit with a quieter image.
- **Instagram** tends toward more *graphic* / scroll-stopping / image-first compositions — bolder typography, dark or color-blocked emphasis, deliberately confident. Reader scrolls fast and the image has to earn the pause.

But both feeds need internal variety. Don't let FB become "always white centered" and IG become "always dark and bold." Surprise the reader within each feed.

---

## Image-Prompt Best Practices for Embedded Text

ChatGPT Image 2 renders text accurately and follows compositional instructions reliably. Nano Banana is more inconsistent on text — fall back if needed.

### DO
- **Quote the exact headline and subtitle text** in the prompt. Quotation marks help the model lock the literal string.
- **Specify exact colors with hex codes** every time: `#FFFFFF`, `#242E40`, `#23A85B`.
- **Specify font characteristics** — "modern sans-serif, bold weight, similar to Inter Bold or Söhne Bold."
- **Specify the composition unambiguously** — describe what's in each region of the frame, where text is positioned, what visual elements sit where.
- **Add 'render the text exactly as written, with correct spelling and punctuation.'**
- **Add 'no other text anywhere in the image except the headline and SafeTurnAdvisory.com subtitle specified above.'**
- **Specify aspect ratio at the start and end of the prompt.**

### DON'T
- Don't describe a "template" or "card" — describe THIS specific composition.
- Don't reuse the same prompt skeleton with substituted words. Write a fresh prompt structured around the design idea you chose for this post.
- Don't pile on conflicting instructions ("centered but also left-aligned"). Pick one.
- Don't use vague style words like "professional" or "modern" alone — they're noise. Be concrete.

---

## Output Structure in Each Draft File

```
<!-- VISUAL: [one-line concept summary — composition + visual centerpiece for THIS post]. 4:5 portrait. Text embedded. -->

[caption text — full, hashtags included]

---

## Image Prompt (paste into ChatGPT Image 2 — recommended — or Nano Banana)

[Full custom prompt for THIS post. No template substitutions — the prompt is written from scratch around the chosen composition idea, with exact hex codes, exact text in quotation marks, font specs, position descriptions, and a clear "no other text" constraint.]
```

Two sections only. The visual comment summarizes the design concept (so a human skimming the file knows what's coming). The image prompt is a custom paragraph for that specific post.

---

## Process for the Engine (per post)

1. Read the caption and the post's core idea.
2. Look at the last 5 prompts on this channel (drafts/ + published/). Note their compositions, color dominance, and visual centerpieces.
3. Brainstorm 3 different design directions for this post — explicitly different from the recent 5 across the variety axes above.
4. Pick the strongest direction (the one that best serves the post's specific message).
5. Write a custom paste-ready prompt for that direction with exact text, hex codes, font specs, and composition.
6. Add the one-line VISUAL concept summary at the top of the draft file.

The goal: a follower scrolling the feed should never recognize "oh, here comes another Safe Turn quote card." Every post should look freshly designed for its specific idea.
