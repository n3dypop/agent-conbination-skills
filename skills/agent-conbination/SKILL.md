---
name: agent-conbination
description: Coordinate agents working on the same project. Use when choosing a shared request record, setting roles and edit boundaries, comparing design options, handing off or resuming a request, coordinating concurrent edits, reviewing changes, or applying findings.
metadata:
  version: "1.1.1"
---

# Working with other agents

Read the project's instructions and shared request record. Agree on who owns the work, what they can change, and what evidence the next person needs to accept the result. Assign roles for each task regardless of the product or model each participant uses.

- **Set up a team or change its membership.** Follow [Team setup](references/setup.md). Use the project's existing ownership rules, approval process, and issue tracker.
- **Choose an approach.** Invite the other agent to help design the solution. Work independently from the same evidence, then test the assumptions behind any disagreement. See [Design discussions](references/handoff.md#design-discussions).
- **Hand off, review, or resume work.** Follow [From request to completion](references/handoff.md#from-request-to-completion). Use [Verifying findings](references/handoff.md#verifying-findings) for corrections and removal claims, and [Interrupted requests](references/handoff.md#interrupted-requests) before retrying an operation.

## Checks for each request

1. Before starting, confirm the request ID, owner, target and version, permitted edits, and acceptance criteria. For a review-only request, inspect the target and return proposed fixes to its owner.
2. Compare active requests with the files the work will actually change. Without Git, compare shared copies of the old and current versions. For overlapping edits, agree on ownership and order. Include files that formatters or generators rewrite.
3. Tie the result to the request ID and target version. If the reviewer reports that verification was impossible, keep the request open even if the CLI exited successfully. Record the changes or findings, checks performed, and outstanding conditions. The requester or the person designated by the project decides whether to accept the result.

Use the project's existing channels to hand off work. Launch another agent only when the user's request and project rules authorize it. The receiving environment's permissions and usage limits apply. Share only the information needed for the request. Exclude credentials, private conversation history, and unrelated files.
