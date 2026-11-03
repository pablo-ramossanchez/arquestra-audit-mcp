# Arquestra Audit · MCP server

Check your own data before you publish a result from it. **Arquestra Audit** is a remote MCP server by
[Arquestra](https://arquestra.dev) that walks your AI assistant through an audit of a data file: it agrees with you
how to read each column, measures the file where it is (in the chat's audit panel or with a small script on your
computer), and shows one light per figure, red, amber or green, with the reasons.

**Your data never reaches the server and nothing is stored.** The measuring runs in your browser or on your computer;
only counts come back.

- Endpoint: `https://arquestra.dev/api/mcp/audit` (Streamable HTTP, no sign-in)
- Page: [arquestra.dev/assets/audit](https://arquestra.dev/assets/audit)

## Connect it

**Claude (claude.ai, desktop, mobile):** open Claude's connectors, search **Arquestra Audit** and press Connect.
Not in the list yet? [Add it directly](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Arquestra%20Audit&connectorUrl=https%3A%2F%2Farquestra.dev%2Fapi%2Fmcp%2Faudit).

**Claude Code:**

```bash
claude mcp add --transport http arquestra-audit https://arquestra.dev/api/mcp/audit
```

or install this repository as a plugin (Manage plugins → Install by GitHub URL → `https://github.com/pablo-ramossanchez/arquestra-audit-mcp`).

**VS Code:** [install](vscode:mcp/install?%7B%22name%22%3A%22arquestra-audit%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Farquestra.dev%2Fapi%2Fmcp%2Faudit%22%7D)

**Cursor:** [install](cursor://anysphere.cursor-deeplink/mcp/install?name=arquestra-audit&config=eyJ1cmwiOiJodHRwczovL2FycXVlc3RyYS5kZXYvYXBpL21jcC9hdWRpdCJ9)

**ChatGPT:** settings → connectors (developer mode) → add `https://arquestra.dev/api/mcp/audit`.

**Any other MCP client:** add a remote server with the URL above.

## Tools

| Tool | What it does |
|---|---|
| `start_audit` | Proposes how to read your file (the role of each column, each result written as a claim) from its column names and the results you want to publish. |
| `measure_in_app` | Opens the audit panel in the chat; the panel reads your file in your browser and measures it with the confirmed reading. |
| `prepare_script` | Returns `measure.py`, a fixed Python script (standard library, no network) that counts what each check needs and prints counts, never rows. |
| `show_audit` | Shows the lights: one per figure, with the reasons and a small chart. |
| `example_audits` | How the audit works, with worked examples. |

## About Arquestra

[Arquestra](https://arquestra.dev) builds open, checkable data assets on public procurement and AI governance:
the [Consulting Market Radar](https://arquestra.dev/assets/consulting) (public consulting tenders in Europe and who
wins them), the AI Procurement Observatory, research papers, and this audit.

Earlier versions of this repository held a plugin for a scientific-computing product; that product is now listed
as Arquestra Chem on [arquestra.dev](https://arquestra.dev).
