# Vista Social Configuration

Non-secret reference for Vista Social IDs used by this engine. The API key and connector UUID are kept out of the repo and live only in the scheduled trigger prompt.

## Profile Group

- **Name:** `Safeturn Advisory (Brand)`
- All Safe Turn social profiles (LinkedIn + Facebook + Instagram) belong to this group

## Approval Workflow

- **Name:** `Safeturn Content Engine`
- **workflow_gid:** `69ca8c24d75620ecec4eb0b8`
- Posts created by this engine are assigned to this workflow → land as **Pending Review** for Jake + Peter to approve before publishing

## Profiles

| Channel | network_code | profile_id | Status |
|---|---|---|---|
| LinkedIn (Safe Turn Advisory) | `linkedin` | `703776` | Live in v1 engine |
| Facebook (Safe Turn Advisory) | `facebook` | TBD — pending Jake/Peter to add | |
| Instagram (Safe Turn Advisory) | `instagram` | TBD — pending Jake/Peter to add | |

The agent **must dynamically discover** Facebook + Instagram profile IDs at runtime (via `listProfiles`) rather than hard-coding them, since they aren't connected yet. Once added, this file can be updated for documentation but the agent should keep using runtime discovery so a profile change doesn't break the engine.

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
