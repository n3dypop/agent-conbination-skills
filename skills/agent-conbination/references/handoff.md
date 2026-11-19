# Handoffs and reviews

Use the project's shared request record. If the request already exists, use its ID. Link to design notes, diffs, and test output so the record shows both the current status and the criteria for completion.

Choose one field as the source of the current status. If a heading repeats that status, update both together. Keep earlier decisions in the history with their version or date. When taking over formatting or integration, confirm the file boundaries in [Team setup](setup.md).

## Design discussions

1. Before choosing an approach, share the question, target version, available evidence, constraints, and decision maker. Give each participant the same information, including anyone starting a fresh session. Ask each to propose an option independently, describe when it would be a poor fit, and name an observation that would change their choice. Exchange recommendations after both have answered.
2. Send the points of disagreement back to each other and answer the open questions. Check permissions and tool availability in the actual environment. To compare models or reasoning settings, give each the same task with the answer withheld and compare their reasoning. Use a direct check for questions such as whether two versions match.
3. When considering a tool or dependency, try both the candidate and the existing process on the same small task in an isolated workspace. Keep the roles, inputs, and acceptance criteria the same. For example, try sending a request, retrying delivery, and collecting the result both ways. Record what the candidate makes possible, what permissions, setup, or maintenance it adds, and what the trial did not cover.
4. Record the conditions under which the decision applies, the reasons for it, remaining objections, and what would justify revisiting it. Put this in the request record or link to it. Remove discarded prototypes and connection settings from the trial workspace. A decision maker can proceed within their authority when participants still disagree.

## From request to completion

| Stage | What to record or check |
|---|---|
| Request | Give the ID, requester and recipient, type of work (design, review, change, or decision), target and version, permitted edits, and verifiable acceptance criteria. Include priority and dependencies when relevant. |
| Start | Confirm the target version, owner, and active requests in the shared record. When resuming a change, compare the current work with the saved artifact to locate the next step. The requester may receive submissions and apply the accepted results. |
| Result | Return the ID, version examined, conclusion, evidence, and anything unverified. Preserve who submitted the result and who actually checked it, even after a handoff. Distinguish a visual inspection from running a parser or comparing bytes. For conditional approval, name the remaining condition and who will check it. |
| Acceptance | The requester or the person designated by the project checks the acceptance criteria. If required device or production checks remain, keep them open here or track them in a linked request. Record the reason for withdrawing a request. |

A findings-only review can close once the reviewer returns findings and evidence for the requested version, even if the findings call for changes. Keep it open if it also requires a re-review or the reviewer could not perform a required check. The requester or the person designated by the project makes a separate decision about whether the underlying work is complete. If a required check moves to a linked request, the work stays open until the check passes or someone with authority approves a change to the criteria. Record the outstanding condition and its next owner.

When several results arrive for the same request and version, the person applying them compares each with the original submission, including its author, scope, wording, and evidence. Return the existing record for a redelivery of the same result. Keep independent findings and additions separately. For a correction, preserve the earlier result and link it to the replacement identified by the submitter. If the original is missing or the relationship is unclear, keep both records, ask the submitter, and defer decisions that depend on that distinction.

If measuring how long results wait for a decision, start when each result first arrives in the shared record and stop when it is accepted or declined. A change of owner or redelivery does not restart the clock. A new finding, addition, or correction has its own arrival time. Measure delivery delay separately.

## Verifying findings

- When a review proposes a correction to a number or decision rule, the person applying it checks the source for that version and repeats the calculation or decision with the same units and scope. Record the original value, the value adopted, and the effect on the conclusion. Decide on each correction individually. Defer any correction that needs more evidence and name the missing input.
- A claim such as "removed" or "no duplicates" needs a search scope and a method that could detect the old behavior or a duplicate. For example, first show that a search finds the target in the old version, then use it on the current version. If acceptance requires a live response, verify that you reached the intended deployment and version and check the response required by the contract. File searches provide supporting evidence in that case. A regression test can demonstrate that it detects the defect by failing on the old version and passing on the fix. Mark applicable conditions you could not check as unverified, with a reason. Distinguish them from verified conditions and those outside the spec.

## Identifying the version under review

- For committed changes, record the base and target commit IDs. For uncommitted work, record the base commit and a copy of the diff. Without Git, use snapshots of both versions or version history the recipient can open. For a first version, review the whole artifact. If the baseline is gone, report what you could verify in the current version and what remains unknown about the change.
- The recipient states which version they read and whether they independently verified its identity. If reviewing a shared tree, check whether anyone plans to edit it during the review. Supply a frozen snapshot when concurrent edits are possible. Before applying findings, the requester compares the version sent, the version in the reply, and the current artifact. Record who checked each one.
- If the recipient cannot obtain the target version, provide it through an authorized shared location or record why verification was impossible.
- Reuse the request ID for a re-review. Identify the new version and the changes. Determine which parts of an earlier approval still apply. If that cannot be established, review the new version.
- When handing work to another worktree, include the snapshot's identifier and a location the recipient can open. File a late reply about an older version under that version's history.
- Track review milestones separately from individual request IDs. Make any expansion of a request's scope explicit. Create a linked request when the added work has a separate responsibility or acceptance criterion.

## Interrupted requests

- Transfer responsibility for applying results through the authorized decision maker or the team's agreed process. Verify that the previous owner has stopped writing or that the shared system rejects their updates. Record the new owner, target version, and pending proposals. If ownership changes while the artifact stays at the same version, use the handoff record to distinguish results from before and after the transfer.
- From their own workspace, the new owner reopens the shared record and the instructions needed for acceptance. If a reference fails, obtain a working link or a copy of the same version. Preserve the proposals and evidence while the current state or decision criteria are unknown. Defer decisions that depend on them.
- For a late reply from before the transfer, compare each proposal with existing decisions. Return the existing result for duplicates. The current owner evaluates new proposals and records their source and disposition.
- If a result never arrives, keep the request open and record the reason and conditions for resuming. Track delivery of a stop request and termination of the run separately, with evidence for each. Check the target diff before retrying. If the environment assigns a run ID per attempt, record each one on the same request.
- If a run attempted an external action, such as sending an order or publishing an artifact, check the receiving system's final record. Never repeat an action it has accepted. A local log or clean working tree cannot establish that the receiver got nothing. If the receiver may accept an action after the run ends, ask for its final status and hold that retry until the outcome is known. Other actions confirmed to be outstanding may proceed within the original authorization. Check where a restarted run begins and which items it will process. If the default includes accepted or uncertain items, restrict the run to the remaining items. Hold that run until they can be isolated.
- Whoever delivers a request to another agent links its delivery and receipt to the request ID and version. If the recipient cannot list a directory, provide a direct path or link to each artifact or finding. Ask the sender for a usable location if an item is missing. On resumption, retrieve the result of a request already received. If delivery is uncertain, check the delivery record or ask the recipient. If redelivery is necessary, use the same ID and version so the recipient can recognize the duplicate.
- Resume an agent session only if you can identify it as the session reserved for this request. Otherwise, reopen the shared record and continue from there. When one agent hands off to another in turn, keep track of who issued the request and who applies the result.
- Read-only participants return their findings with the request ID. The person authorized to update the record checks the result and its target version before writing it back.

## Example

**Request #18.** The implementer asks for a read-only review of the send queue and its regression tests at the recorded base and head commits of PR #24. Use a test double to interrupt the connection, retry immediately, and check that the history contains only one entry.

**Result #18.** The reviewer tested the requested revision. The test double interrupted the response, and the immediate retry left one history entry. A live service interruption remains unverified. The requester closes #18 because its acceptance criteria covered the simulated interruption, and tracks the live check in linked request #19.
