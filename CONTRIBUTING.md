# Contributing to BehindTheMusicTree

## Open an issue

Search for an existing issue and choose the repository responsible for the outcome. Give the issue a precise title, the context someone needs to act, and an observable closure criterion. Use the bug, feature, tracking or follow-up form when it fits. Choose a blank issue for ordinary tasks.

One work issue owns an outcome that can be verified and closed in a single decision. File count, repository count, PR count and elapsed days help estimate complexity. Decide whether to split based on which outcomes can be accepted, deferred, assigned or delivered independently.

- Handle a small correction in the current PR when it fits its objective and can be finished there. Open an issue when the work needs separate tracking.
- Keep implementation, tests and documentation together when they are all needed to verify one outcome. Use a short checklist if it helps execution.
- Open one issue per independent outcome. If someone owns the combined outcome, open a tracking parent with its overall success criterion and attach the native sub-issues. Cross-reference issues that only share a theme. A sub-issue should make sense on its own and record any dependency that actually blocks its start.
- If work must wait for a later event, open a follow-up with the original issue or PR, the action, its owner, the event that triggers it, and the result to record.
- If the problem is known and the solution needs investigation, state the investigation's deliverable. For example, reproduce the problem and identify its cause. Open implementation issues once the work is identified.

For example, fixing an import that creates duplicates and adding its regression test are one issue. Repairing historical duplicates is a second issue when that work can be scheduled and verified separately. Checking the first production import is a follow-up when it must wait for deployment. A tracking parent is appropriate if someone is responsible for verifying that both current imports and historical data are free of duplicates.

## Type and triage

Set the actual issue type when creating an issue, including from the CLI. A deferred fix can use Bug with `follow-up`. Give every issue a type by the end of triage. Find open untyped issues with advanced search: `gh api -X GET search/issues -f 'q=org:BehindTheMusicTree is:issue is:open no:type' -F advanced_search=true`.

GitHub only enforces required form fields on public repositories; on private repositories, check the issue contains the information needed during triage.

| Label | When to use it |
| --- | --- |
| `needs-triage` | Awaiting the initial maintainer decision. Remove it after the decision. Replace it with `needs-info` if an answer is required. |
| `needs-info` | Waiting for an answer to a specific question. Post the question and remove the label once a sufficient answer arrives. |
| `tracking` | Coordinates sub-issues toward a shared outcome. Keep it on the parent after verifying the outcome and closing the parent. |
| `follow-up` | Tracks a concrete action arising from earlier work. Record the result before closing and keep the label after closure. |

A triaged issue can have zero labels.

## Link pull requests

Use `Closes #123` when a PR targeting the default branch fully resolves the issue; for another repository use `Closes owner/repo#123`. Reference a tracking parent or a check that must happen after merge without a closing keyword while its outcome is still pending. Close a follow-up only after recording the observed result and evidence.
