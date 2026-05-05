# Meta (Facebook + Instagram) — Channel Rules

Read `../CLAUDE.md` first for voice, pillars, audience, and industry facts. This file covers Meta-specific formatting only.

**Single caption shared across Facebook and Instagram.** Vista Social posts the same text to both profiles.

## Format

- **Length:** 600–1,200 characters (~100–200 words)
  - Instagram caption limit is 2,200 chars but readers drop off fast — keep it tight
  - Facebook can take longer captions, but using one shorter caption for both keeps tone consistent
- **Paragraph style:** short paragraphs, 1–3 lines each, with blank lines between
- **Emojis:** allowed, but sparingly (0–2 per post). Never as bullet points.

## The Hook (Critical for Instagram)

- **First line is everything on Instagram** — IG truncates after ~125 characters with "... more"
- The first line must work as a standalone hook even if no one taps to expand
- Use: short declarative statements, data drops, contrarian one-liners, pattern interrupts
- Avoid burying the lede behind a setup sentence

## Hashtags

- **5–10 hashtags** acceptable on Meta (Instagram tolerates more than LinkedIn)
- Place at the end of the caption
- Mix: 3–4 broad + 2–4 niche + 1–2 brand
- Brand: `#SafeTurnAdvisory` `#SafeTurn`
- Broad: `#SmallBusiness` `#SmallBusinessOwner` `#Entrepreneur` `#BusinessOwner` `#CashFlow`
- Niche: `#BusinessDebt` `#DebtRestructuring` `#MCARelief` `#CashFlowManagement` `#SMB` `#FinancialLiteracy` `#BusinessFinance`

## Visual Direction (Required)

Every Meta post needs a visual. The agent does NOT generate the image — it writes a one-line direction at the **very top of the file** as an HTML comment, so the social media manager / designer knows what to create:

```
<!-- VISUAL: Branded text-card on dark background with the pull quote: "Fast cash isn't the same as affordable cash." Safe Turn brand colors. -->

[caption text starts here]
```

Visual direction principles:
- **No stock photos of people** (avoid UGC/influencer feel)
- **Branded graphics:** text cards, simple icons, charts, abstract structural imagery
- **Pull a phrase from the caption** for text-card visuals — keeps the post coherent
- Match Safe Turn's brand identity (clean, professional, business-first)

## Hard Don'ts

- **No links in caption body** — Meta deprioritizes link-in-caption posts. CTAs go to "link in bio."
- No engagement bait ("Double tap if…", "Tag a friend who…")
- No reposting LinkedIn copy verbatim — Meta posts must be shorter and IG-hook-aware

## Post Structure

1. **Visual direction** (HTML comment at top of file)
2. **Hook** (line 1 — works standalone)
3. **Relatable problem or observation** (1–2 short paragraphs)
4. **Reframe or insight** (the "aha" moment)
5. **Soft close** (no hard CTA)
6. **Hashtags** (5–10)

## Output

Write the visual direction comment + final caption text only to `drafts/YYYY-MM-DD.md`. No PILLAR tag, no metadata beyond the visual comment.
