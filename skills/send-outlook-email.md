# Skill: Send Outlook Email

## Summary

Sends an email on behalf of the signed-in user through Outlook.

## Trigger examples

- "Email Priya the Q3 report summary."
- "Send an email to john@contoso.com about tomorrow's deadline."
- "Reply to the last message from Finance with an approval."

## Required connector(s) / MCP tools

| Connector | MCP tool(s) | Graph permission(s) |
| --- | --- | --- |
| microsoft-365 | `send-mail` | `Mail.Send` |

## Inputs

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `to` | string / string[] | yes | Recipient email address(es). |
| `subject` | string | yes | Email subject line. |
| `body` | string | yes | Email body (plain text or HTML). |
| `cc` | string[] | no | CC recipients. |

## Outputs

Confirmation that the email was sent, including recipient(s) and subject.

## Step-by-step behavior

1. Confirm recipient(s), subject, and body content with the user if any are ambiguous or
   missing.
2. Call the `send-mail` MCP tool with the composed message.
3. Report success (or the error returned by Microsoft Graph) back to the user.

## Example conversation

**User:** "Email Priya (priya@contoso.com) to say the deployment is complete."

**Agent:** "Sending an email to priya@contoso.com with subject 'Deployment Complete' —
confirm before I send?"

**User:** "Yes, send it."

**Agent:** "Done — email sent to priya@contoso.com."

## Edge cases / error handling

- If the MCP server isn't authenticated, prompt the user to run
  `npx @softeria/ms-365-mcp-server --org-mode --login`.
- If the recipient address is invalid/ambiguous, ask the user to clarify before sending.
- Always ask for explicit confirmation before sending, since sending mail is
  irreversible.

## Status

- [x] Draft
- [ ] Implemented
- [ ] Tested
