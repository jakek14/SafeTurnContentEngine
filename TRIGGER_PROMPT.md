# Scheduled Trigger Prompt

Paste this prompt into a new scheduled trigger at https://claude.ai/code/scheduled

**Schedule:** Daily at 8:00 AM ET (cron: `0 13 * * *` UTC during EST, `0 12 * * *` UTC during EDT)
**Model:** claude-sonnet-4-6
**Tools:** Bash, Read, Write, Edit, Glob, Grep, WebSearch, WebFetch
**MCP:** Vista Social connector enabled (UUID `6a082e06-34ec-493f-a78e-734cc3729f98`)

Substitute `<PAT>` with the GitHub PAT and `<VISTA_API_KEY>` with the Vista Social API key before saving the trigger.

---

## Prompt

```
You are running the Safe Turn Advisory multi-channel content engine. Generate one LinkedIn post and one Meta (Facebook + Instagram) post for today, then publish both to Vista Social as Pending Review.

================================================================
STEP 1 — Clone or pull the repo
================================================================

if [ -d /tmp/SafeTurnContentEngine ]; then
  cd /tmp/SafeTurnContentEngine && git pull
else
  git clone https://jakek14:<PAT>@github.com/jakek14/SafeTurnContentEngine.git /tmp/SafeTurnContentEngine
  cd /tmp/SafeTurnContentEngine
fi

git remote set-url origin https://jakek14:<PAT>@github.com/jakek14/SafeTurnContentEngine.git

================================================================
STEP 2 — Read the rules
================================================================

- Read CLAUDE.md (master)
- Read voice-guide.md
- Read linkedin/CLAUDE.md
- Read meta/CLAUDE.md
- Read vista-config.md (Vista Social IDs and publishing pattern)

================================================================
STEP 3 — Determine yesterday's pillar per channel
================================================================

- ls linkedin/drafts/ linkedin/published/ — find most recent file per channel
- ls meta/drafts/ meta/published/ — same
- git log --oneline -20 — read commit messages for "LinkedIn: [pillar] / Meta: [pillar]"
- Today's LinkedIn pillar must differ from yesterday's LinkedIn pillar
- Today's Meta pillar must differ from yesterday's Meta pillar

================================================================
STEP 4 — Research current SMB debt / MCA / cash flow news
================================================================

Run AT LEAST 3 WebSearch queries. Look for:
- Recent stats (last 90 days preferred)
- Industry shifts (regulation, lender behavior, credit markets)
- Real numbers you can cite

If WebSearch results are weak, expand to general SMB financial pressure news. DO NOT invent statistics.

================================================================
STEP 5 — Generate the LinkedIn post
================================================================

Follow linkedin/CLAUDE.md (1,300–1,900 chars, hook in first 210, 3–5 hashtags, no body links).
Pick a pillar different from yesterday's LinkedIn pillar.
Write the post text only to linkedin/drafts/YYYY-MM-DD.md (no PILLAR tag, no metadata).

================================================================
STEP 6 — Generate the Meta post
================================================================

Follow meta/CLAUDE.md (600–1,200 chars, IG hook in line 1, 5–10 hashtags, visual direction comment at top).
Pick a pillar different from yesterday's Meta pillar.
The Meta post must NOT be a copy-paste of the LinkedIn post — different angle, different hook, different length.

Format example for the visual comment line:
<!-- VISUAL: Branded text-card on dark background with the pull quote: "[short phrase from caption]". Safe Turn brand colors. -->

Write the visual comment + caption to meta/drafts/YYYY-MM-DD.md.

================================================================
STEP 7 — Commit and push
================================================================

git add linkedin/drafts/YYYY-MM-DD.md meta/drafts/YYYY-MM-DD.md
git commit -m "Daily content - LinkedIn: [pillar] / Meta: [pillar] - YYYY-MM-DD

Sources:
- [title](URL)
- [title](URL)"
git push origin main

If no external sources informed the post, write "Sources: none (general industry knowledge)".

================================================================
STEP 8 — Publish to Vista Social (MCP primary, curl fallback)
================================================================

Vista Social IDs (from vista-config.md):
- workflow_gid: 69ca8c24d75620ecec4eb0b8 (Safeturn Content Engine approval workflow)
- LinkedIn profile_id: 703776
- Facebook profile_id: discover at runtime (may not exist yet)
- Instagram profile_id: discover at runtime (may not exist yet)
- Profile group: "Safeturn Advisory (Brand)"
- API endpoint: https://vistasocial.com/api/integration/mcp?api_key=<VISTA_API_KEY>

------ 8a. Try MCP first ------

Attempt to use the Vista Social MCP tools (createOrUpdatePost, listProfiles, etc.) directly.

If MCP tools ARE available:
1. Call listProfiles, filter for profile group "Safeturn Advisory (Brand)"
2. Identify profile_ids by network_code: linkedin, facebook, instagram
3. Call createOrUpdatePost twice:
   - LinkedIn post → linkedin profile_ids only, content = LinkedIn caption
   - Meta post → facebook + instagram profile_ids, content = Meta caption (FB and IG share caption)
4. Both calls must include workflow_gid: 69ca8c24d75620ecec4eb0b8 → posts land as Pending Review
5. Do NOT publish directly. Do NOT skip the workflow.

If listProfiles returns no facebook or instagram profiles, that is expected during rollout. Skip the Meta publish step (the Meta draft is still committed in git for manual posting if needed) and continue.

------ 8b. Curl fallback if MCP unavailable ------

If MCP tools are NOT loaded (permitted_tools is empty, or tools/call errors), fall back to Python urllib:

import urllib.request, json

API_KEY = "<VISTA_API_KEY>"
ENDPOINT = f"https://vistasocial.com/api/integration/mcp?api_key={API_KEY}"
HEADERS = {
    "Content-Type": "application/json",
    "Accept": "application/json, text/event-stream"
}

def vista_call(method_name, arguments):
    payload = {
        "jsonrpc": "2.0",
        "id": 1,
        "method": "tools/call",
        "params": {"name": method_name, "arguments": arguments}
    }
    req = urllib.request.Request(
        ENDPOINT,
        data=json.dumps(payload).encode("utf-8"),
        headers=HEADERS,
        method="POST"
    )
    with urllib.request.urlopen(req, timeout=60) as resp:
        return json.loads(resp.read().decode("utf-8"))

# Step A: discover profile IDs
profiles_resp = vista_call("listProfiles", {})
# Parse profiles_resp to extract profile_ids by network_code, filtered to "Safeturn Advisory (Brand)" group

# Step B: post LinkedIn
linkedin_caption = open("linkedin/drafts/YYYY-MM-DD.md").read()
li_resp = vista_call("createOrUpdatePost", {
    "profile_ids": [703776],  # known LinkedIn profile_id
    "content": linkedin_caption,
    "workflow_gid": "69ca8c24d75620ecec4eb0b8"
})

# Step C: post Meta (only if FB/IG profile_ids were discovered)
meta_caption_full = open("meta/drafts/YYYY-MM-DD.md").read()
# Strip the leading <!-- VISUAL: ... --> comment before posting
meta_caption = strip_visual_comment(meta_caption_full)
if fb_id or ig_id:
    meta_resp = vista_call("createOrUpdatePost", {
        "profile_ids": [id for id in [fb_id, ig_id] if id],
        "content": meta_caption,
        "workflow_gid": "69ca8c24d75620ecec4eb0b8"
    })

The curl/urllib fallback is not optional — it is the resilience layer for known MCP-on-trigger flakiness. Always include it.

================================================================
STEP 9 — Final report
================================================================

Output a short summary:
- LinkedIn pillar + first line of the post
- Meta pillar + first line of the post
- Vista Social post IDs returned (or "skipped — Meta profiles not yet connected")
- Git commit SHA
- Whether MCP or fallback was used

If anything failed, report the exact error so it can be debugged.
```
