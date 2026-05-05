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
You are running the Safe Turn Advisory multi-channel content engine. Generate one LinkedIn post, one Facebook post, and one Instagram post for today, then publish all three to Vista Social as Pending Review.

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
- Read meta/facebook/CLAUDE.md
- Read meta/instagram/CLAUDE.md
- Read vista-config.md (Vista Social IDs and publishing pattern)

================================================================
STEP 3 — Determine yesterday's pillar per channel
================================================================

For EACH of the three channels, find the most recent file in drafts/ and published/, plus check git log:
- linkedin/drafts/, linkedin/published/
- meta/facebook/drafts/, meta/facebook/published/
- meta/instagram/drafts/, meta/instagram/published/

git log --oneline -20 — read commit messages for "LI: [pillar] / FB: [pillar] / IG: [pillar]"

Today's pillar must differ from yesterday's pillar ON THE SAME CHANNEL. Each channel rotates independently — they can be the same pillar on the same day if appropriate, just not yesterday's same-channel pillar.

================================================================
STEP 4 — Research current SMB debt / MCA / cash flow news
================================================================

Run AT LEAST 3 WebSearch queries. Look for:
- Recent stats (last 90 days preferred)
- Industry shifts (regulation, lender behavior, credit markets)
- Real numbers you can cite

If WebSearch results are weak, expand to general SMB financial pressure news. DO NOT invent statistics.

The same research base powers all three posts, but each post must use a different angle / hook / framing.

================================================================
STEP 5 — Generate the LinkedIn post
================================================================

Follow linkedin/CLAUDE.md (1,300–1,900 chars, hook in first 210, 3–5 hashtags, no body links).
Pick a pillar different from yesterday's LinkedIn pillar.
Write the post text only to linkedin/drafts/YYYY-MM-DD.md (no PILLAR tag, no metadata).

================================================================
STEP 6 — Generate the Facebook post
================================================================

Follow meta/facebook/CLAUDE.md (1,000–1,800 chars, less aggressive hook than IG, 2–5 hashtags).
Pick a pillar different from yesterday's Facebook pillar.
NOT a copy-paste of the LinkedIn post — different hook, different angle.

Format example for the visual comment line:
<!-- VISUAL: Branded text-card on dark background with the pull quote: "[short phrase from caption]". Safe Turn brand colors. Format: square 1:1 or horizontal 1.91:1. -->

Write visual comment + caption to meta/facebook/drafts/YYYY-MM-DD.md.

================================================================
STEP 7 — Generate the Instagram post
================================================================

Follow meta/instagram/CLAUDE.md (500–900 chars, line-1 hook MUST stand alone at ~125 chars, 5–10 hashtags, no links).
Pick a pillar different from yesterday's Instagram pillar.
NOT a copy-paste of the LinkedIn or Facebook posts — tighter, punchier, IG-native.

Format example for the visual comment line:
<!-- VISUAL: Branded square text-card (1:1) on dark background with the pull quote: "[short phrase from caption]". Safe Turn brand colors. Readable at thumbnail size. -->

Write visual comment + caption to meta/instagram/drafts/YYYY-MM-DD.md.

================================================================
STEP 8 — Commit and push (single commit, all three files)
================================================================

git add linkedin/drafts/YYYY-MM-DD.md meta/facebook/drafts/YYYY-MM-DD.md meta/instagram/drafts/YYYY-MM-DD.md
git commit -m "Daily content - LI: [pillar] / FB: [pillar] / IG: [pillar] - YYYY-MM-DD

Sources:
- [title](URL)
- [title](URL)"
git push origin main

If no external sources informed the posts, write "Sources: none (general industry knowledge)".

================================================================
STEP 9 — Publish to Vista Social (MCP primary, Python fallback)
================================================================

Vista Social IDs (from vista-config.md):
- workflow_gid: 69ca8c24d75620ecec4eb0b8 (Safeturn Content Engine approval workflow)
- LinkedIn profile_id: 703776
- Facebook profile_id: discover at runtime via listProfiles
- Instagram profile_id: discover at runtime via listProfiles
- Profile group: "Safeturn Advisory (Brand)"
- API endpoint: https://vistasocial.com/api/integration/mcp?api_key=<VISTA_API_KEY>

Routing rules:
- LinkedIn caption → LinkedIn profile only
- Facebook caption → Facebook profile only
- Instagram caption → Instagram profile only
- ABSOLUTELY NEVER send the same caption to multiple network types.

------ 9a. Try MCP first ------

Attempt the Vista Social MCP tools (createOrUpdatePost, listProfiles).

If MCP tools ARE available:
1. Call listProfiles, filter for profile group "Safeturn Advisory (Brand)"
2. Identify profile_id by network_code: linkedin (already known: 703776), facebook, instagram (or instagram_business)
3. Call createOrUpdatePost THREE times, each routed to a single channel:
   - LinkedIn caption → profile_ids: [703776]
   - Facebook caption → profile_ids: [<discovered FB id>]
   - Instagram caption → profile_ids: [<discovered IG id>]
4. All three calls must include workflow_gid: 69ca8c24d75620ecec4eb0b8 → posts land as Pending Review
5. Strip the leading <!-- VISUAL: ... --> comment from FB/IG captions before posting
6. Do NOT publish directly. Do NOT skip the workflow.

If listProfiles returns no facebook profile, skip the FB publish step (FB draft stays committed for manual posting).
If listProfiles returns no instagram profile, skip the IG publish step (IG draft stays committed for manual posting).
LinkedIn posts unconditionally (profile already live).

------ 9b. Python urllib fallback if MCP unavailable ------

If MCP tools are NOT loaded (permitted_tools is empty, or tools/call errors), fall back to Python urllib:

import urllib.request, json, re

API_KEY = "<VISTA_API_KEY>"
ENDPOINT = f"https://vistasocial.com/api/integration/mcp?api_key={API_KEY}"
HEADERS = {
    "Content-Type": "application/json",
    "Accept": "application/json, text/event-stream"
}
WORKFLOW_GID = "69ca8c24d75620ecec4eb0b8"
LINKEDIN_PROFILE_ID = 703776

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

def strip_visual(caption):
    return re.sub(r"^\s*<!--.*?-->\s*", "", caption, flags=re.DOTALL)

# Discover FB + IG profile IDs
profiles_resp = vista_call("listProfiles", {})
# Parse profiles_resp to find profile_ids by network_code, filtered to "Safeturn Advisory (Brand)" group
fb_id = ...   # network_code == "facebook"
ig_id = ...   # network_code in ("instagram", "instagram_business")

# Post LinkedIn (always)
linkedin_caption = open("linkedin/drafts/YYYY-MM-DD.md").read()
li_resp = vista_call("createOrUpdatePost", {
    "profile_ids": [LINKEDIN_PROFILE_ID],
    "content": linkedin_caption,
    "workflow_gid": WORKFLOW_GID
})

# Post Facebook (only if FB profile exists)
if fb_id:
    fb_caption = strip_visual(open("meta/facebook/drafts/YYYY-MM-DD.md").read())
    fb_resp = vista_call("createOrUpdatePost", {
        "profile_ids": [fb_id],
        "content": fb_caption,
        "workflow_gid": WORKFLOW_GID
    })

# Post Instagram (only if IG profile exists)
if ig_id:
    ig_caption = strip_visual(open("meta/instagram/drafts/YYYY-MM-DD.md").read())
    ig_resp = vista_call("createOrUpdatePost", {
        "profile_ids": [ig_id],
        "content": ig_caption,
        "workflow_gid": WORKFLOW_GID
    })

The Python urllib fallback is not optional — it is the resilience layer for known MCP-on-trigger flakiness. Always include it.

================================================================
STEP 10 — Final report
================================================================

Output a short summary:
- LinkedIn pillar + first line of post + Vista post ID (or error)
- Facebook pillar + first line of post + Vista post ID (or "skipped — FB profile not yet connected")
- Instagram pillar + first line of post + Vista post ID (or "skipped — IG profile not yet connected")
- Git commit SHA
- Whether MCP or fallback was used

If anything failed, report the exact error so it can be debugged.
```
