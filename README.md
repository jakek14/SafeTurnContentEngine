# Safe Turn Advisory — Content Engine

Multi-channel organic content engine for [Safe Turn Advisory](https://safeturnadvisory.com/).

Generates one LinkedIn post and one Meta (Facebook + Instagram) post per day. Single brand voice, six pillars, fresh topics daily based on current SMB debt / MCA / cash flow news.

## Structure

```
.
├── CLAUDE.md              Master prompt — voice, pillars, audience, industry facts
├── voice-guide.md         Tone, language rules, bar test
├── linkedin/
│   ├── CLAUDE.md          LinkedIn-specific format rules
│   ├── drafts/            Daily generated posts before approval
│   ├── published/         Posts that have shipped via Vista Social
│   └── archive/           Rejected or retired posts
├── meta/
│   ├── CLAUDE.md          Meta-specific format rules (FB + IG share caption)
│   ├── drafts/
│   ├── published/
│   └── archive/
└── posts/                 Style reference templates across the 6 pillars
```

## Daily Flow

1. Scheduled agent runs at 8am ET
2. Reads master `CLAUDE.md` + channel `CLAUDE.md` files
3. Determines yesterday's pillar **per channel** from drafts/published/git log
4. Runs 3+ web searches for current SMB debt / MCA news
5. Generates one LinkedIn post → `linkedin/drafts/YYYY-MM-DD.md`
6. Generates one Meta post (with visual direction comment) → `meta/drafts/YYYY-MM-DD.md`
7. Commits and pushes both in a single commit
8. Creates both posts in Vista Social → "Safeturn Advisory (Brand)" profile group → "Safeturn Content Engine" approval workflow
9. Posts land as **Pending Review** for Jake + Peter to approve

## Approval

Nothing publishes without explicit approval. All posts go through Vista Social's approval workflow.

## Content Pillars

1. Contrarian
2. Relatable Pain
3. Educational
4. Perspective Shift
5. Authority Insight
6. Hypothetical Scenario

Never repeat the same pillar two days in a row on the same channel.
