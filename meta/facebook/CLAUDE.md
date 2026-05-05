# Facebook — Channel Rules

Read `../../CLAUDE.md` first for voice, pillars, audience, industry facts, and craft rules. This file covers Facebook-specific formatting only — based on 2026 algorithm behavior, not 2018-era advice.

## Audience Note

Facebook's Safe Turn audience skews 35–60, scrolls during research/lunch windows, more analytical than IG. They tolerate slightly longer captions than IG but the same scroll fatigue applies — earn the click to expand.

## Format

- **Length:** 400–1,000 characters (~70–180 words)
  - Sweet spot for B2B authority + readability
  - Posts under 80 chars often outperform on engagement, but feel thin for Safe Turn's authority play
  - Going longer than 1,000 chars dilutes — split into multiple posts instead
- **Paragraph style:** very short paragraphs, 1–3 lines each, blank lines between
- **Bullets:** **no bullet symbols (•, –, ✓).** Facebook strips them ugly. Use line breaks to separate items instead.
- **Emojis:** 0–2 max per post, never as bullets, never as decoration

## The Hook (Critical — Mobile Fold ≈ 125 chars)

- **The "See more" cut on FB mobile is ~125 characters** — same brutal truncation as Instagram
- **First line must be scroll-stopping AND stand alone at 125 chars**
- Desktop fold is ~477 chars (more forgiving), but mobile is the dominant surface
- Front-load the hook. Do not bury the lede behind a setup sentence.

### Hook patterns that work on FB (B2B 35–60)
- **Specific number:** "3 things I wish I knew before taking my first MCA"
- **Contrarian claim:** "Most owners think more revenue fixes this. It doesn't."
- **Named scenario:** "Imagine a $4M HVAC company with 4 daily MCA pulls."
- **Direct stakes:** "If you've stacked two advances, your next 6 months matter more than the last 6."

### Hook patterns that **fail** on FB (algorithm penalty)
- **No IG-style cliffhangers:** "Wait till you see #3" → punished as engagement bait
- **No curiosity-gap clickbait:** "You won't believe what one lender did" → demoted
- **No "LIKE if you agree" / "COMMENT YES" / "TAG a friend"** → 20–95% reach reduction + page-level penalty for repeat use

## Hashtags

- **1–2 niche hashtags MAX.** Facebook's algorithm relies on engagement signals + AI recommendations, NOT hashtag discovery.
- Stuffing 5+ hashtags **suppresses reach.**
- Place at the very end. Pick from: `#SafeTurnAdvisory` `#BusinessDebt` `#MCARelief` `#CashFlow` `#DebtRestructuring` — pick the ONE or TWO most relevant to today's post, not a kitchen sink.

## Links

- **NEVER put links in the caption body.** Link posts get ~0.03% engagement — roughly half of non-link posts. Only ~2% of top-viewed FB posts contain links.
- Plain-text URLs and hyperlinked previews both trigger the penalty.
- **If a CTA link is essential, put it in the first comment** (this engine doesn't auto-create first comments — Jake adds the link manually after publish if needed).
- Default: no link anywhere. CTA = "Learn more at the link in our bio" or just no CTA. Trust the brand recall.

## Visual Direction + Image Prompt (Required)

Every Facebook post needs a visual. **Read `../image-style.md` for the full brand guide and prompt templates.** Each draft file must include two things:

1. A one-line `<!-- VISUAL: ... -->` HTML comment at the top (human-readable brief)
2. A full **`## Image Prompt`** block (paste-ready for ChatGPT Image 2 or Nano Banana)

The image prompt embeds the headline and subtitle text directly in the generated image — **no post-production editing in Canva or Figma is needed**. Paste the prompt into ChatGPT Image 2 (recommended) and the output is post-ready.

**Aspect ratio for Facebook:** 4:5 portrait (1080×1350) preferred — 33% more mobile screen real estate. 1:1 (1080×1080) acceptable second choice. Never 1.91:1 horizontal for organic.

See `../image-style.md` Template A (Pull-Quote Card) for default prompt structure. ~90% of FB posts use Template A; Template B (Architectural Texture) only when the core idea is genuinely structural.

The "20% text rule" is dead. Meta's current "Image Text Rating" (OK/Low/Med/High) throttles distribution as text density rises — keep the overlay to one short pull-quote, not a paragraph.

## Algorithm Signals

The 2026 FB algorithm rewards (in priority order):
1. **Comments — long comments and back-and-forth threads weighted highest**
2. **Shares**
3. **Saves** (signal value to the reader)
4. **Watch time** (on video posts — irrelevant to text posts)
5. **Reactions** (lowest weight)
6. **Likes** (lowest weight)

A soft, genuine question at the close invites comments without triggering engagement-bait penalties. Do NOT use "comment YES below" framing — use "Curious how others handle this — what's worked for you?" or similar real questions.

**Originality is rewarded.** Reposted or aggregator content is downranked. Every Safe Turn post must be original — never recycled from other sources.

## Hard Don'ts

- **No bullet symbols** (•, –, ✓) — line breaks only
- **No engagement bait** ("LIKE if…", "COMMENT YES", "SHARE with…", "TAG a friend who…") — algorithm penalty 20–95%
- **No links in caption body** — kills reach
- **No reposting Instagram caption verbatim** — FB tolerates 100–200 more chars and supports a softer hook setup; treat as a different post
- **No reposting LinkedIn caption verbatim** — LinkedIn is professional B2B with hashtags; FB is conversational with minimal hashtags
- **No ALL CAPS for emphasis** — looks like spam
- **No cliffhanger hooks** ("Wait till you see…") — penalized

## Post Structure

1. **Visual direction** (HTML comment at top of file, with 4:5 or 1:1 spec)
2. **Hook** (line 1, ≤125 chars, stands alone, no clickbait)
3. **Body** (2–4 short paragraphs, plain text, line breaks not bullets)
4. **Tactical takeaway or insight** (1–2 sentences)
5. **Soft genuine question** (optional close — invites comments without baiting)
6. **Hashtags** (1–2 niche only)

### Skeleton

```
<!-- VISUAL: ... 4:5 portrait ... -->

[Hook ≤125 chars: specific claim, number, or named scenario]

[2–3 sentence story/insight in plain text]

[Tactical takeaway: principle, framework, or reframe]

[Soft genuine question — optional, only if natural]

#SafeTurnAdvisory #BusinessDebt
```

## Output

Write the visual direction comment + final caption text only to `drafts/YYYY-MM-DD.md`. No PILLAR tag, no metadata beyond the visual comment.
