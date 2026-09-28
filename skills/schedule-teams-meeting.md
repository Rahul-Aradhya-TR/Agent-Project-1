# Skill: Schedule Teams Meeting

## Summary

Creates a Microsoft Teams online meeting and sends invites to the specified attendees.

## Trigger examples

- "Schedule a Teams call with the design team tomorrow at 3pm."
- "Set up a 30-minute Teams meeting with Alex and Sam on Friday morning."
- "Book a Teams meeting titled 'Sprint Review' for next Monday at 10am."

## Required connector(s) / MCP tools

| Connector | MCP tool(s) | Graph permission(s) |
| --- | --- | --- |
| microsoft-365 | `create-calendar-event` / `create-online-meeting` | `Calendars.ReadWrite`, `OnlineMeetings.ReadWrite` |

## Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `subject` | string | yes | Meeting title. |
| `start` | datetime | yes | Meeting start time (with timezone). |
| `end` | datetime | yes | Meeting end time (with timezone). |
| `attendees` | string[] | no | Attendee email addresses. |
| `body` | string | no | Meeting description/agenda. |

## Outputs

Confirmation of the scheduled meeting, including the generated Teams join link.

## Step-by-step behavior

1. Resolve/confirm subject, date/time (with timezone), duration, and attendees with the
   user if any are ambiguous or missing.
2. Call the calendar/online-meeting MCP tool to create the event with Teams meeting
   details enabled.
3. Return the meeting time and Teams join link to the user.

## Example conversation

**User:** "Schedule a Teams meeting with Alex (alex@contoso.com) tomorrow at 3pm for 30
minutes, title 'Design Sync'."

**Agent:** "Scheduling 'Design Sync' for tomorrow 3:00–3:30 PM with alex@contoso.com —
confirm?"

**User:** "Yes."

**Agent:** "Done — 'Design Sync' is on the calendar with a Teams join link sent to
alex@contoso.com."

## Edge cases / error handling

- If the MCP server isn't authenticated, prompt the user to run
  `npx @softeria/ms-365-mcp-server --org-mode --login`.
- If no timezone is given, ask for one or use the user's default calendar timezone.
- If an attendee's free/busy status conflicts, surface the conflict and ask whether to
  proceed anyway or pick another time.

## Status

- [x] Draft
- [ ] Implemented
- [ ] Tested
