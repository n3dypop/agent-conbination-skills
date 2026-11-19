# agent-conbination

A skill for agents such as Codex and Claude Code that work on the same project. It helps them agree on a design, hand off work, and review each other's changes. Each request records who owns it, which version to inspect, and how to tell when the work is done. A new session can pick up where the last one stopped.

## Installation

1. Copy the entire [skill folder](skills/agent-conbination/) to `skills/agent-conbination/` in your project. Include `references/` and `LICENSE`.
2. Add the instructions below to the project's root `AGENTS.md`. Create the file if needed. Adapt the issue tracker and roles to your project.
3. If you use Claude Code, add `@AGENTS.md` on its own line in the root `CLAUDE.md`. Create that file if needed. For other agents, point their startup instructions to the same `AGENTS.md`.

```markdown
For collaborative work, read skills/agent-conbination/SKILL.md.
Track requests and results in project issues.
The requester names the version and acceptance criteria. The reviewer posts
findings in the issue, and the requester records the decision.
```

## Try a review

Open an issue, link to the exact revision, and give the reviewer a request like this.

> Review the error message in revision r2. Leave the files unchanged. Check whether the implementation displays the message under the conditions in the spec, and post your findings and evidence in this issue.

Start a fresh reviewer session and give it the issue. Check that it can open the skill and the requested revision, then find its reply in the same issue.

You can also hand off requests through a shared document. If the user and project rules allow one agent to launch another directly, check that the calling environment can find `claude` or `codex`. If the CLI is installed elsewhere, use its full path on that machine.

Read [Team setup](skills/agent-conbination/references/setup.md) to assign roles and [Handoffs and reviews](skills/agent-conbination/references/handoff.md) to work through an individual request.

## License

The skill and its documentation are available under the [MIT License](LICENSE). When redistributing the skill, include the [license in the skill folder](skills/agent-conbination/LICENSE).
