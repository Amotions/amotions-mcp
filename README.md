# Amotions AI — Remote MCP Server (`https://amotionsinc.com/mcp`)

Read-only **Model Context Protocol (MCP)** remote connector for [Amotions AI](https://amotionsinc.com), the real-time AI sales coach that privately guides customer-facing teams during live Zoom, Microsoft Teams, Google Meet, and phone calls (with no meeting bot), runs voice and text AI roleplay beforehand, and delivers MSCEIT-informed scorecards afterward.

## Quick Connect

- **Server URL:** `https://amotionsinc.com/mcp`
- **Transport:** Streamable HTTP (`streamable-http`)
- **Authentication:** OAuth 2.1 Authorization Code + PKCE (`S256`), dynamic client registration enabled
- **Scope:** `calls:read` (read-only; scoped strictly to the signed-in user's own calls)
- **Discovery Metadata:**
  - MCP Server Card: `https://amotionsinc.com/.well-known/mcp.json`
  - OAuth Protected Resource: `https://amotionsinc.com/.well-known/oauth-protected-resource`
  - OAuth Authorization Server: `https://amotionsinc.com/.well-known/oauth-authorization-server`

## Setup by AI Assistant

### ChatGPT
1. Open **Settings → Apps & Connectors** and add a custom MCP server with `https://amotionsinc.com/mcp` (OAuth).
2. Sign in to your Amotions AI account and click **Allow**.
- **Guide:** https://amotionsinc.com/docs/use-amotions-in-chatgpt
- **Workflow overview:** https://amotionsinc.com/integrations/chatgpt

### Claude (Web, Desktop, and Claude Code)
1. Open **Settings → Connectors** and add a custom connector with `https://amotionsinc.com/mcp` (or run `claude mcp add --transport http amotions https://amotionsinc.com/mcp` in Claude Code).
2. Sign in to Amotions AI and click **Allow**.
- **Guide:** https://amotionsinc.com/docs/use-amotions-in-claude
- **Workflow overview:** https://amotionsinc.com/integrations/claude

### Perplexity
1. Open **Settings → Connectors → Add custom connector** and enter `https://amotionsinc.com/mcp` (Streamable HTTP, OAuth).
2. Sign in to Amotions AI and click **Allow**.
- **Guide:** https://amotionsinc.com/docs/use-amotions-in-perplexity
- **Workflow overview:** https://amotionsinc.com/integrations/perplexity

### Grok
1. Visit `grok.com/connectors`, click **New Connector → Custom**, and enter `https://amotionsinc.com/mcp`.
2. Sign in to Amotions AI and click **Allow**.
- **Guide:** https://amotionsinc.com/docs/use-amotions-in-grok

## Exposed Read-Only Tools

| Tool | Description |
| --- | --- |
| `prepare_next_call` | Build a pre-call coaching brief from your recurring coaching focus areas and any matching prior calls with a prospect or account, plus handoff links to AI Roleplay and Live Coaching. |
| `list_recent_calls` | List your own recent coached calls, uploaded recordings, and AI roleplays with dates, scores, and outcomes. |
| `get_call_coaching` | Fetch the structured post-call coaching summary, strengths, opportunities, and next-call actions for one of your calls. |
| `get_call_transcript` | Read the speaker-attributed transcript of one of your calls to draft follow-up emails or review buyer wording. |
| `get_coaching_trends` | Inspect your score trajectory and recurring improvement themes across recent calls. |

## Security & Privacy Guarantees

- **Strictly personal & read-only:** Every tool enforces `readOnlyHint: true` and checks `data.userId === uid`. Connected assistants cannot view teammates' calls—even if you are an organization admin—and cannot modify or delete anything in Amotions AI.
- **No model training:** Customer call transcripts, audio uploads, playbooks, and chat sessions stay isolated to your organization workspace and are never used to train third-party foundation AI models.
- **Easy revocation:** Remove the connector in your AI assistant's settings at any time; refresh tokens expire automatically within 30 days.
- **Trust Center:** https://amotionsinc.com/security

## Links

- **Amotions AI:** https://amotionsinc.com
- **Real-time AI sales coach:** https://amotionsinc.com/real-time-ai-sales-coach
- **AI sales roleplay:** https://amotionsinc.com/solutions/ai-sales-roleplay
- **Free AI sales roleplay:** https://amotionsinc.com/free-ai-sales-roleplay
- **Help Center:** https://amotionsinc.com/docs
- **Pricing:** https://amotionsinc.com/pricing
- **Support:** support@amotionsinc.com
