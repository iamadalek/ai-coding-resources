---
description: Create a well-structured issue in your tracker
args:
  platform:
    description: "Issue tracker: github, linear, jira, asana"
    required: true
  description:
    description: "Text describing the issue (problem, feature, or task)"
    required: true
---

Use the issue-writer skill to transform this into a well-structured issue:

{{description}}

Then create the issue on **{{platform}}** using the appropriate method:

| Platform | Method | Command/Tool |
|----------|--------|--------------|
| github | CLI | `gh issue create` |
| linear | CLI | `linear issue create` |
| jira | MCP | Use Jira MCP tool if available, otherwise guide user to create manually |
| asana | MCP | Use Asana MCP tool if available, otherwise guide user to create manually |

Return the issue URL when complete.
