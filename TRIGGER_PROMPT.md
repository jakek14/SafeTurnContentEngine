# Scheduled Trigger Prompt

Paste this prompt into a new scheduled trigger at https://claude.ai/code/scheduled

**Schedule:** Daily at 8:00 AM ET (cron: `0 13 * * *` UTC, or `0 12 * * *` UTC during EDT)
**Model:** claude-sonnet-4-6
**Tools:** Bash, Read, Write, Edit, Glob, Grep, WebSearch, WebFetch
**MCP:** Vista Social connector enabled (UUID `6a082e06-34ec-493f-a78e-734cc3729f98`)

---

## Prompt

```
You are running the Safe Turn Advisory multi-channel content engine. Generate one LinkedIn post and one Meta (Facebook + Instagram) post for today.

## Setup

1. Clone the repo (or pull if it exists):
   ```
   if [ -d /tmp/SafeTurnContentEngine ]; then
     cd /tmp/SafeTurnContentEngine && git pull
   else
     git clone https://jakek14:<PAT>@github.com/jakek14/SafeTurnContentEngine.git /tmp/SafeTurnContentEngine
     cd /tmp/SafeTurnContentEngine
   fi
   ```

2. Set git remote with auth for push (replace `<PAT>` with the GitHub PAT, kept in the trigger prompt only — not in this repo):
   ```
   git remote set-url origin https://jakek14:<PAT>@github.com/jakek14/SafeTurnContentEngine.git
   ```

## Read the rules

- Read `CLAUDE.md` (master)
- Read `voice-guide.md`
- Read `linkedin/CLAUDE.md`
- Read `meta/CLAUDE.md`

## Determine yesterday's pillar per channel

- Check `linkedin/drafts/` and `linkedin/published/` for the most recent file
- Check `meta/drafts/` and `meta/published/` for the most recent file
- Run `git log --oneline -20` to see recent pillar tags from commit messages
- Identify yesterday's pillar for each channel — today's pillar must be different on the same channel

## Research

Run at least 3 WebSearch queries for current SMB debt / MCA / cash flow / business credit news. Look for:
- Recent stats (last 90 days preferred)
- Industry shifts (regulation, lender behavior, credit markets)
- Real numbers you can cite

If WebSearch results are weak, expand to general SMB financial pressure news. Do NOT invent statistics.

## Generate the LinkedIn post

- Follow `linkedin/CLAUDE.md` rules (1,300–1,900 chars, hook in first 210, 3–5 hashtags, no body links)
- Pick a pillar different from yesterday's LinkedIn pillar
- Write the post text only to `linkedin/drafts/YYYY-MM-DD.md`
- No PILLAR tag, no metadata in the file

## Generate the Meta post

- Follow `meta/CLAUDE.md` rules (600–1,200 chars, IG hook in line 1, 5–10 hashtags allowed, visual direction comment at top)
- Pick a pillar different from yesterday's Meta pillar (can be same or different from today's LinkedIn pillar)
- The Meta post must NOT be a copy-paste of the LinkedIn post — different angle, different hook, different length
- Write the visual comment + caption only to `meta/drafts/YYYY-MM-DD.md`
- Format example for the visual comment line:
  ```
  <!-- VISUAL: Branded text-card on dark background with the pull quote: "[short phrase from caption]". Safe Turn brand colors. -->
  ```

## Commit and push

```
git add linkedin/drafts/YYYY-MM-DD.md meta/drafts/YYYY-MM-DD.md
git commit -m "Daily content - LinkedIn: [pillar] / Meta: [pillar] - YYYY-MM-DD

Sources:
- [title](URL)
- [title](URL)"
git push origin main
```

If no external sources informed the post, write "Sources: none (general industry knowledge)".

## Publish to Vista Social

Use the Vista Social MCP. For BOTH posts:
- Target profile group: "Safeturn Advisory (Brand)"
- Approval workflow: "Safeturn Content Engine"
- Status: Pending Review (do NOT publish directly)
- LinkedIn post → LinkedIn profiles in the group only
- Meta post → Facebook and Instagram profiles in the group only (FB and IG share the same caption)

Note: if the Meta profiles are not yet added to the group, the FB/IG portion may fail or skip — that is expected during the rollout. Continue with LinkedIn regardless.

## Reporting

After both are queued, output a short summary:
- LinkedIn pillar + first line of post
- Meta pillar + first line of post
- Vista Social post IDs (or error messages if any failed)
- Git commit SHA
```
