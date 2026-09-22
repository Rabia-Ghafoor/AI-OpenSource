# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Repo facts: "last 5 default-branch commits" dates, and the "maintainer first-response sample" days-to-first-response figures. | Pass if at least one of the last 5 default-branch commits is dated within 180 days of the bundle's `captured` date, OR at least one entry in the maintainer first-response sample shows a response of 30 days or fewer. Otherwise fail. | required |
| repo-in-use | Repo facts: "archived:" flag, "latest release" date, "last push to any branch" date. | Fail immediately if archived is "yes". Otherwise pass if the last push to any branch is within 180 days of `captured`, OR the latest release is within 365 days of `captured`. Otherwise fail. | required |
| scope-fits-newcomer | The issue body, the full comment thread, and the "linked PRs:" line under Repo facts. | Fail if any of: (a) the issue is an explicit umbrella/tracking issue — it literally lists many separate issue numbers to work through, or describes an open-ended, indefinitely-ongoing initiative where contributors self-select different files/areas over time, rather than a fixed, bounded checklist of steps toward one cohesive change; (b) the thread shows an unsettled design debate about the core ask with no maintainer decision recorded, OR the primary deliverable itself is left undecided — e.g. an unspecified asset, format, or UX choice for the main feature being requested (a literal "TBD" or "no alternatives considered" on the thing you'd actually build) — this does NOT include optional/secondary polish explicitly marked lower-priority, or an incidental "if needed"/"if useful" aside on an otherwise fully specified core task; (c) a maintainer states the fix touches core internals/architecture; (d) the issue is a pure usage/support question rather than a proposed change; (e) 2 or more linked PRs from earlier attempts are closed unmerged, showing the task is harder or more contentious than the write-up suggests. A bug report that names multiple candidate root causes or suggested implementation approaches for one reported symptom is NOT an umbrella — grade it on whether the symptom is one bounded piece of work, not on how many candidate fixes are listed. A short or terse body is not itself a fail — judge the size of the work, not the polish of the writeup. Otherwise pass. | required |
| unclaimed | Repo facts: "this issue: assignees:" and "linked PRs:" lines, plus every comment in the thread. | Fail if an assignee is currently set, OR any linked PR (formally listed or only referenced in the comment thread) is still open, OR the most recent claim comment ("I'll take this", "working on this", "/assign") is unanswered and unreversed and less than 180 days old. A closed/abandoned linked PR, or a stale claim that a maintainer has since reopened or explicitly invited new contributors to retry, does not fail this check. Otherwise pass. | required |
| ai-contribution-policy | Repo facts: "contribution policy" line (CONTRIBUTING.md / AI policy text). | Fail only if the stated policy is an outright ban on AI-generated code or documentation (e.g. "we do not accept AI-generated code"). Conditions such as disclosure, human review, or requiring the contributor to understand every change are terms to follow, not a fail. No CONTRIBUTING.md or no AI statement passes (silence passes). | required |

## Verdict rule

Accept only if every required check passes. Any required check graded
`fail` or `unclear` rejects the issue (`unclear` is treated as `fail`).
There are no preferred checks in this rubric, so nothing here ranks
accepted issues beyond the fit profile in `scope.md`.

