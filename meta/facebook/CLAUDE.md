# Facebook — Channel Rules

Read `../../CLAUDE.md` first for voice, pillars, audience, industry facts, and craft rules. This file covers Facebook-specific formatting only.

## Audience Note

Facebook's Safe Turn audience skews slightly older (40–60), reads longer captions, more analytical mindset, often scrolling during work hours or weekends. They're more patient than IG users with longer setups before the payoff.

## Format

- **Length:** 1,000–1,800 characters (~150–250 words)
  - FB has no aggressive truncation cliff like IG — captions display nearly in full
  - Caption can carry more setup before the reframe
- **Paragraph style:** short paragraphs, 2–3 lines each, with blank lines between
- **Emojis:** allowed sparingly, 0–2 per post, never as bullets

## The Hook

- First 1–2 lines should still be scroll-stopping, but you have more room than on IG
- Use: data drops, contrarian openers, story setups, pattern interrupts
- The hook does not need to stand alone the way an IG hook does — FB shows ~250 chars before "See more"

## Hashtags

- **2–5 hashtags** — FB's algorithm largely ignores hashtags, so don't stuff
- Place at the end of the caption
- Mix: 1–2 brand + 1–3 topical
- Brand: `#SafeTurnAdvisory`
- Topical: `#SmallBusiness` `#BusinessDebt` `#CashFlow` `#DebtRestructuring` `#MCARelief` `#BusinessOwner` `#SMB`

## Links

- Soft links to safeturnadvisory.com are tolerable on FB but still reduce reach
- **Default: no link in body.** Use a comment with the link if a CTA is needed.
- Never put a tracking link or UTM in the post body — looks salesy

## Visual Direction (Required)

Every Facebook post needs a visual. Write a one-line direction at the **very top of the file** as an HTML comment:

```
<!-- VISUAL: Branded text-card on dark background with the pull quote: "Fast cash isn't the same as affordable cash." Safe Turn brand colors. -->

[caption text starts here]
```

Visual direction principles:
- **No stock photos of people** (avoid UGC/influencer feel)
- **Branded graphics:** text cards, simple icons, charts, abstract structural imagery
- **Pull a phrase from the caption** for text-card visuals — keeps the post coherent
- FB visuals can be horizontal (1.91:1) or square (1:1) — note the format if it matters

## Hard Don'ts

- No engagement bait ("Comment YES if you agree", "Tag a friend")
- No reposting Instagram caption verbatim — FB post should be longer with more setup, different hook
- No reposting LinkedIn caption verbatim — LinkedIn is operator-to-operator B2B; FB is broader audience

## Post Structure

1. **Visual direction** (HTML comment at top of file)
2. **Hook** (1–2 lines, scroll-stopping)
3. **Setup / context** (FB tolerates 2–3 sentences here)
4. **Reframe or insight** (the "aha" moment)
5. **Light solution insight** (principle, not pitch)
6. **Soft close** (optional — "If this sounds familiar..." or nothing)
7. **Hashtags** (2–5)

## Output

Write the visual direction comment + final caption text only to `drafts/YYYY-MM-DD.md`. No PILLAR tag, no metadata beyond the visual comment.
