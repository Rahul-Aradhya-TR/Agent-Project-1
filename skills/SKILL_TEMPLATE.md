# Skill: <Short Skill Name>

> Copy this file to `skills/<kebab-case-skill-name>.md`, fill in every section, and
> remove this blockquote before committing.

## Summary

One or two sentences describing what the agent does for the user in this skill.

## Trigger examples

List a few natural-language phrasings that should invoke this skill.

- "..."
- "..."
- "..."

## Required connector(s) / MCP tools

Which MCP server and tool(s) this skill relies on (see [`.mcp.json`](../.mcp.json)).

| Connector | MCP tool(s) | Graph permission(s) |
| --- | --- | --- |
| microsoft-365 | `tool-name-here` | `Permission.Scope` |

## Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `input_name` | string | yes | What it represents. |

## Outputs

Describe what the agent returns or does as a result (e.g. confirmation message, created
item ID, summary text).

## Step-by-step behavior

1. Step one.
2. Step two.
3. Step three.

## Example conversation

**User:** "..."

**Agent:** "..."

## Edge cases / error handling

- What happens if authentication is missing or expired?
- What happens if the target resource (mailbox, chat, meeting) doesn't exist?
- Any confirmation required before a destructive/irreversible action (e.g. sending mail)?

## Status

- [ ] Draft
- [ ] Implemented
- [ ] Tested
