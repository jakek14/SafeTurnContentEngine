# Safe Turn Advisory — Content Engine

Multi-channel organic content engine for [Safe Turn Advisory](https://safeturnadvisory.com/).

Generates one LinkedIn post, one Facebook post, and one Instagram post per day — each tailored to its platform. Single brand voice, six pillars, fresh topics daily based on current SMB debt / MCA / cash flow news.

## Structure

```
.
├── CLAUDE.md              Master prompt — voice, pillars, audience, industry facts
├── voice-guide.md         Tone, language rules, bar test
├── vista-config.md        Vista Social IDs and publishing pattern (non-secret)
├── TRIGGER_PROMPT.md      Pasteable scheduled-trigger prompt (with secret placeholders)
├── linkedin/
│   ├── CLAUDE.md          LinkedIn-specific format rules
│   ├── drafts/            Daily generated posts before approval
│   ├── published/         Posts that have shipped via Vista Social
│   └── archive/           Rejected or retired posts
├── meta/
│   ├── facebook/
│   │   ├── CLAUDE.md      Facebook-specific format rules
│   │   ├── drafts/, published/, archive/
│   └── instagram/
│       ├── CLAUDE.md      Instagram-specific format rules (line-1 hook critical)
│       ├── drafts/, published/, archive/
└── posts/                 Style reference templates across the 6 pillars
```

## Daily Flow

1. Scheduled agent runs at 8am ET
2. Reads master `CLAUDE.md` + all three channel `CLAUDE.md` files
3. Determines yesterday's pillar **per channel** from drafts/published/git log
4. Runs 3+ web searches for current SMB debt / MCA news
5. Generates three independent posts:
   - LinkedIn → `linkedin/drafts/YYYY-MM-DD.md`
   - Facebook → `meta/facebook/drafts/YYYY-MM-DD.md` (with visual direction comment)
   - Instagram → `meta/instagram/drafts/YYYY-MM-DD.md` (with visual direction comment)
6. Commits and pushes all three in a single commit
7. Creates three posts in Vista Social → "Safeturn Advisory (Brand)" profile group → "Safeturn Content Engine" approval workflow, each routed to its own channel profile
8. All three land as **Pending Review** for Jake + Peter to approve

## Approval

Nothing publishes without explicit approval. All posts go through Vista Social's approval workflow.

## Content Pillars

1. Contrarian
2. Relatable Pain
3. Educational
4. Perspective Shift
5. Authority Insight
6. Hypothetical Scenario

Never repeat the same pillar two days in a row on the same channel. Each channel maintains its own independent rotation.
