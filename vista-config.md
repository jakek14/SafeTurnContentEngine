# Vista Social Configuration

Non-secret reference for Vista Social IDs used by this engine. The API key and connector UUID are kept out of the repo and live only in the scheduled trigger prompt.

## Profile Group

- **Name:** `Safeturn Advisory (Brand)`
- All Safe Turn social profiles (LinkedIn + Facebook + Instagram) belong to this group

## Approval Workflow

- **Name:** `Safeturn Content Engine`
- **workflow_gid:** `69ca8c24d75620ecec4eb0b8`
- Posts created by this engine are assigned to this workflow → land as **Pending Review** for Jake + Peter to approve before publishing

## Profiles (verified 2026-05-05 via findProfiles)

| Channel | profile_id | Vista profile name |
|---|---|---|
| LinkedIn | `703776` | Safe Turn Advisory (LinkedIn Company Page) |
| Facebook | `703765` | SafeTurn Advisory (Facebook Page) |
| Instagram | `724863` | safeturnadvisory (Instagram Profile) |

(Note: Vista also has profile `703768 HFMNJ (Facebook Page)` — that's a different brand. Do NOT post to it.)

## Posting Modes (per channel)

Vista's `createOrUpdatePost` has two routing patterns. Each Safe Turn channel uses a different one:

| Channel | Mode | API call |
|---|---|---|
| LinkedIn | **Pending Review** (Approve/Reject) | `profile_id: 703776, workflow_gid: "69ca8c24d75620ecec4eb0b8"` |
| Facebook | **Editable Draft** | `profile_id: 703765, draft: true` (omit workflow_gid) |
| Instagram | **Editable Draft** | `profile_id: 724863, draft: true` (omit workflow_gid) |

### Why the split

- **LinkedIn is text-only** — no image to add — so Pending Review (approve/reject only, no editing) is appropriate. Caption ships as-is once Jake/Peter approve.
- **Facebook + Instagram require images** — Jake creates the visual after the caption is generated. Editable Draft mode lets him edit the caption, attach the image, and publish manually from Vista.

### Critical rule

- `workflow_gid` and `draft: true` are **mutually exclusive** code paths in Vista. Never combine them.
- Never pass `workflow_gid: null` — omit the field entirely if not using a workflow.
- Each caption posts to exactly ONE profile_id — never post the same caption across multiple network types.

## MCP Endpoint

- **Endpoint:** `https://vistasocial.com/api/integration/mcp?api_key={API_KEY}`
- **Required header:** `Accept: application/json, text/event-stream` — without this you get a "Not Acceptable" error
- **JSON-RPC format:**
  ```json
  {
    "jsonrpc": "2.0",
    "id": 1,
    "method": "tools/call",
    "params": {
      "name": "schedulePost",
      "arguments": { ... }
    }
  }
  ```

## Known Issue: MCP on Scheduled Triggers

Vista Social MCP tools work reliably in local Claude Code sessions but **intermittently fail to load in remote scheduled agents**. The connector UUID and URL config can look correct while `permitted_tools` shows as empty.

**The trigger prompt must include a Python `urllib` fallback** that calls the MCP HTTP endpoint directly via JSON-RPC if the MCP tools aren't available. Use Python (not raw curl) to handle JSON escaping of post text properly.

## Publishing Pattern

1. Try MCP tools first (`createOrUpdatePost`, etc.)
2. If MCP tools aren't loaded, fall back to Python urllib JSON-RPC call
3. Always assign `workflow_gid` so posts land as Pending Review (never publish directly)
4. Always include source profile_ids per channel (LinkedIn vs Meta)
