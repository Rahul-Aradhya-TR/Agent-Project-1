# Skills

Each Markdown file in this folder documents one capability ("skill") the
**Agent-Project-1** agent exposes to users, backed by the Outlook/Teams MCP connector
configured in [`.mcp.json`](../.mcp.json).

## Adding a new skill

1. Copy [`SKILL_TEMPLATE.md`](./SKILL_TEMPLATE.md) to `skills/<kebab-case-name>.md`.
2. Fill in every section: summary, trigger phrases, required MCP tool(s)/Graph
   permissions, inputs/outputs, step-by-step behavior, an example conversation, and edge
   cases.
3. Update the **Status** checklist as the skill moves from draft → implemented → tested.

## Existing skills (examples)

- [`send-outlook-email.md`](./send-outlook-email.md) — send an email via Outlook.
- [`schedule-teams-meeting.md`](./schedule-teams-meeting.md) — schedule a Microsoft
  Teams meeting.

These two are provided as filled-in examples of the template — use them as a reference
when writing new skill pages.
