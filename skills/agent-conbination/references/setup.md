# Team setup

Use this guide when collaboration starts or when the team or its working environment changes.

## What to record

Put the following details in the project's instructions. Link to existing rules where they already cover a point.

| Topic | What the team needs to know |
|---|---|
| Ownership | Who owns each feature, artifact, or path? Who coordinates edits and integration for shared types, generated files, and specs? |
| Reviews | Which milestones need an independent check? What should the reviewer examine? Assign the owner and reviewer per request. |
| Decisions | Who can approve changes to the specification, costs, or publication? What work can continue while a decision is pending? |
| Request record | Where can everyone find the current status, owner, acceptance criteria, and results? Use the project's issue tracker or another shared record. |
| Workspaces | Do participants share a checkout or work in separate worktrees or repositories? How will they identify versions, and who will integrate the changes? |
| Handoffs | How will participants exchange requests? If one agent can launch another, record the limits of that permission and who will collect and record the result. |

Point each client's startup instructions or initial request to the same project rules and request record. If the client cannot discover the skill automatically, give it the path to these files. Before work begins, check that each participant can identify the same target, version, and request status.

## Match the setup to the team

| Team arrangement | What to agree on first |
|---|---|
| Implementer and read-only reviewer | The implementer edits and integrates. The reviewer identifies the version examined and reports observations. If the reviewer cannot write to the request record, the requester records the reply. |
| Several contributors in one working tree | Share the paths each person will change. Assign owners and an edit order for shared types, lockfiles, and files touched by bulk formatting. If requests live in one Markdown file, assign a writer or take turns editing it. |
| Separate worktrees, repositories, or machines | Keep request status somewhere everyone can reach. Identify the review target by commit, PR revision, or accessible snapshot of the diff. Share the integration target and its owner. |

If existing permissions do not settle an ownership or sequencing conflict, pause the overlapping edits. Give the decision maker the affected paths and available options. Independent work can continue.

If someone takes over formatting for only part of a change, list the same files in the handoff. Keep the remaining formatting open on the existing request.
