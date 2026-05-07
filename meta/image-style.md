# Safe Turn — Image Style Guide

Shared brand identity and creative direction for Facebook and Instagram images. **Every post gets its own custom image design — no templates, no fill-in-the-blank layouts.** The engine reads the caption, identifies a visual hook unique to that post, and writes a paste-ready prompt for **ChatGPT Image 2** (recommended) or **Nano Banana** that produces a finished, post-ready asset with text embedded directly in the image.

## North Star

The Meta feed should look like a real graphic designer makes one custom card per day, not like a content engine cranking out the same template with different words.

If two consecutive posts on the same channel look like the same design with different headlines, the engine has failed its job. Each post needs a different *composition, visual centerpiece, color emphasis,* and *mood* than the last several posts on its channel.

## Default to imagery, NOT typography

**Typography-only designs are the exception, not the rule.** Modern image generators handle text reliably so typography is the safe default — but a feed of all-typography posts looks like content-engine output, not a real brand. A scrolling viewer should see actual photography, charts, documents, textures, and material on most days; pure-text design cards on a minority.

**Quota: across any rolling 7 posts on a channel, no more than 2 should be typography-only.** The other 5+ should feature real imagery (photographic, data viz, material/texture, or document-driven).

When you brainstorm 3 design directions per post, **at least 2 of the 3 must be imagery-led** (real photography / data viz / document / texture / material), not typography-led. Pick the one that best serves the post.

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

- **Photography, charts, documents, people, and real-world imagery are ALL allowed** — they are encouraged when they serve the post better than typography alone. The goal is variety: a feed that mixes data viz, photography, abstract design, and pure typography across different posts.
- **People guidance:** Real-looking professional figures are fine. Lean toward editorial photography aesthetic over generic stock photo. Avoid "happy stock model with a clipboard giving a thumbs-up." Better directions: a business owner from behind looking at documents, hands on a contract, an over-the-shoulder shot of someone at a laptop, a candid moment in a real-feeling office. NEVER render specific real people, executives, or anyone identifiable as a Safe Turn team member (the brand uses real team photography for that — AI-generated humans must not impersonate real people).
- **Charts/graphs:** Allowed when they convey real data from the post's research. Keep them clean, minimal, brand-colored (dark blue / green / white only). Bar charts, simple line graphs, callout numbers all fine. NEVER fabricate data — every number in a chart must trace to a source cited in the commit message.
- **Documents:** Allowed. Macro shots of contracts, term sheets, statements, ledgers all work. Type on documents may be readable if it's generic legal/financial language, or kept blurred for atmospheric purposes. NEVER reproduce real client documents or recognizable brand letterhead.
- **Stock-trope avoidance (still applies):** Don't lean on the clichés — handshakes-over-the-table, generic suit-and-briefcase guy, "puzzle pieces fitting together," light-bulb-equals-idea, digital-blue-circuitry, gears, a businessman jumping with arms raised. These read as AI-template content. Aim for editorial photography quality, not corporate clip-art.
- **No metaphor literalism:** Don't draw a road with a "safe turn." Don't draw a wallet bleeding cash. The brand's visual ideas come from real-feeling environments and quality imagery, not literal illustrations of metaphors.
- **No fabricated stats inside the image.** Numbers in the image must come from a real source cited in the post.
- **No additional text beyond the headline + subtitle specified in the prompt.** No taglines, watermarks, extra labels, social handles, or stray words. The model often wants to add "trusted" or "premium" — block it explicitly.
- **Color palette is still strict:** White, dark blue `#242E40`, brand green `#23A85B`. Photographic images that include other natural colors (skin tones, paper warmth, wood grain, sky blue, sunlight) are fine — that's photography. But: no neon brights, no rainbow gradients, no off-brand accent colors layered onto graphics.
- **Aspect ratio:** 4:5 portrait (1080×1350) is the default for both FB and IG. 1:1 (1080×1080) only when there's a deliberate reason.

---

## Variety Mandate

When generating today's image prompt, the engine MUST review the **last 5 image prompts on the same channel** (read the most recent draft and published files in `meta/facebook/` or `meta/instagram/`) and ensure the new prompt differs meaningfully on at least four of these six axes:

1. **Medium type — THE MOST IMPORTANT AXIS.** What KIND of image is this? Choose from: *photographic-real* (people, environments, objects, cityscapes), *document/material* (contracts, statements, ledgers, real-world textures like concrete or paper), *data visualization* (charts, graphs, stat heroes), *abstract design* (color blocks, geometric shapes, layered forms, diagonal splits), *typography-only* (the design IS the type — no other elements). Across any 7-post rolling window, typography-only must appear at most twice. The other 5+ must use a different medium.
2. **Composition** — where does the eye go first? Centered, asymmetric, full-bleed, off-axis, framed, layered, diagonal, stacked-hierarchy, color-blocked, edge-anchored.
3. **Visual centerpiece** — what's carrying the image? Real photograph, document, chart, texture, geometric shape, color block, typography, negative space.
4. **Color dominance** — which color owns the most of the frame? White-dominant, dark-blue-dominant, green-dominant, balanced split, photographic natural tones (warm paper, neutral concrete, sky blue), monochrome + accent.
5. **Headline treatment** — how is the headline rendered? Centered, left-aligned, on a photograph, on a color block, on a texture, two-tone, oversized, framed by space, integrated into a graphic.
6. **Mood** — calm/quiet, confident/declarative, sober/serious, contemplative, scroll-stopping, editorial, documentary, atmospheric.

If four of those six aren't different from any of the last 5 prompts on this channel, redesign before writing the prompt. Medium type difference counts heaviest — if all 5 prior posts are typography-only, today MUST be a different medium.

---

## Composition Vocabulary (organized by medium type — bias toward imagery)

The engine generates at least 3 design directions per post, **at least 2 of which must be imagery-led** (drawn from the first three groups below), with at most 1 typography-only direction.

### Imagery-led patterns (DEFAULT — prefer these)

**Photographic-real:**
- **Editorial photograph + lower text** — full-bleed real-feeling photo (office, building exterior, business owner from behind, hands on document, candid working moment) in the upper 60–70% of the frame; headline sits on a clean white lower band
- **Duotone photograph** — a real photograph rendered in dark blue + white only (no other colors); headline overlaid on the darker zone
- **Photograph with negative-space corner** — real photo fills most of the frame except one corner kept clean for typography
- **Cityscape / architecture** — modern office buildings at dusk, financial district, anonymous facade — atmospheric backdrop with overlaid headline
- **Still-life arrangement** — top-down editorial shot of objects (calculator, fountain pen, notebook, ledger, currency, eyeglasses, coffee mug) on a desk surface
- **Over-the-shoulder / hands-only** — a person from behind reviewing documents, or just hands on a contract / keyboard

**Document/material:**
- **Macro of a contract page** — close-up of legal-looking type with a pen, a highlighter mark, or a partial signature line; readable generic legal language only
- **Stack of folded papers** — overlapping cream documents at slight angles with soft natural shadows
- **Real-world texture** — close-up of exposed concrete, brushed steel, matte stone, aged paper grain, wood grain, marble — occupies a region of the frame; headline on the clean part
- **Light & shadow study** — directional raking light across a textured wall or surface, atmospheric, contemplative

**Data visualization:**
- **Stat hero** — a single huge number/percentage as the visual centerpiece; supporting label smaller; brand-colored
- **Bar chart** — clean horizontal or vertical bars with real data, brand-colored, source attributed
- **Comparison split** — two small visualizations side-by-side contrasting two states
- **Line graph / trend** — minimal trend visualization with one or two lines

### Abstract design patterns (use sometimes — not the default)

- **Asymmetric color-block split** — frame divided into solid color regions, headline anchored in one
- **Diagonal split** — clean diagonal line divides white and a brand color
- **Layered geometry** — overlapping rectangles or squares in brand colors create depth
- **Vertical/horizontal band layout** — a single solid color band of varying width holds part of the composition
- **Color-blocked footer** — bottom 1/3 is a solid dark blue or green block; headline sits on white above
- **Monogram anchor** — a single oversized geometric form (circle, square, triangle) acts as visual anchor

### Typography-only patterns (use SPARINGLY — at most 2 of every 7 posts per channel)

- **Editorial pull-quote** — centered headline on a clean field with one tiny accent
- **Typographic poster** — oversized headline that fills the frame, may bleed
- **Two-tone headline** — words of the headline rendered in different brand colors for emphasis
- **Echoed type** — the same word/phrase appears at two different sizes or weights
- **Negative-space hero** — small headline surrounded by deliberate empty space

When the engine brainstorms 3 directions, the brainstorm distribution should be roughly: 1–2 photographic, 1 data viz or document/material, 0–1 typography. Pick the strongest one. If the audit of the last 5 posts shows multiple typography-only entries, the next post **must** be imagery-led — non-negotiable.

---

## Visual Element Vocabulary (inspiration — mix freely)

**Photographic / real imagery:**
- **People in editorial business contexts** — over-the-shoulder shots, hands on documents, a figure looking out of an office window from behind, candid working moments. Editorial photography quality, not stock-photo artificial.
- **Real documents** — close-ups of contracts, term sheets, statements, ledgers; folded papers; signed pages with pen
- **Office environments** — empty desks with morning light, conference rooms, professional bookshelves, a workspace mid-task
- **Buildings and cityscapes** — modern office buildings, financial districts, architectural facades at golden hour or under overcast skies
- **Material objects** — calculators, fountain pens, leather-bound notebooks, professional desk accessories, a glass of water, eyeglasses on documents
- **Currency and financial materials** — stacks of paper currency, coin arrangements, financial publications (used tastefully, never literal "money raining down" tropes)

**Data visualization:**
- **Bar charts** — clean, minimal, brand-colored, with real data from the post's research
- **Simple line graphs** — trend visualization
- **Callout numbers / stat heroes** — a single statistic rendered massive as the focal point
- **Comparison side-by-side** — two simple visualizations contrasting two states
- **Pie / donut charts** — used sparingly, when they actually clarify
- ALWAYS attribute data to a real source. NEVER fabricate numbers.

**Abstract design:**
- **Geometric primitives** — circles, squares, rectangles, triangles, vertical/horizontal bars
- **Layered shapes** — overlapping rectangles or color blocks creating depth
- **Halftone / duotone treatments** — real photographs rendered in just dark blue + white
- **Real-world textures** — exposed concrete, brushed steel, matte stone, aged paper grain, raw linen, wood grain, marble
- **Subtle patterns** — fine grid, dot pattern, thin diagonal stripes (sparingly)
- **Light & shadow studies** — atmospheric, no objects needed
- **Gradients within the palette** — soft white-to-near-white or dark-blue-to-lighter-blue
- **Negative space** — emptiness as a deliberate design choice

**Typography-driven:**
- Pure typographic posters where the design IS the type (use occasionally, not as default)
- Two-tone headlines (different words different brand colors)
- Oversized scale, mixed weights, generous tracking

The mix matters. A feed that's all photos = generic stock-marketing brand. A feed that's all text cards = engine output. A healthy feed alternates: photo-heavy days, data-heavy days, abstract-design days, typography days.

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
