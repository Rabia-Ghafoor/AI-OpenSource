# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/36

**Verdict output**

Live mode was run against three candidates from the Path Review repo (issues #36, #69,
#68). All three were graded `accept`; issue #36 ranked first by fit. Full output below,
in rank order, ending with the fenced JSON verdict block:

~~~
## Summary

All three issues are course-seeded first issues in codepath/pathreview-ai301-fa26-s3 (in scope). Repo-level checks are shared and pass for all: the last default-branch commit is from Sep 16, 2026 (7 days ago) → maintainer-alive and repo-in-use both pass; not archived; docs/CONTRIBUTING.md exists but says nothing about AI-assisted code → ai-contribution-policy passes (silence passes). No comments, no assignees, and no linked PRs on any of the three → unclaimed passes across the board. Each issue is a single bounded bug-fix-or-test task with a named file, clear expected behavior, and an effort estimate → scope-fits-newcomer passes for all three.

Verdict: accept all three.

Ranked by fit (full-stack/infra/dev-tooling background, Python among known languages):

1. #36 — API test coverage for POST /reviews (labels: api, devops, tests). Closest match to full-stack/dev-tooling/testing interests; simplest, most self-contained task.
2. #69 — Output parser crash on JSON array fallback. General-purpose parsing/API-shape bug, approachable without deep RAG-domain knowledge.
3. #68 — ZeroDivisionError in BM25 keyword search on empty index. Still a clean bounded fix, but requires touching retrieval/BM25-specific logic, a narrower domain fit than the other two.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/36",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Most recent default-branch commit is dated Sep 16, 2026, 7 days before today (2026-09-23)."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Not archived; last push to any branch (Sep 16, 2026) is within 180 days of today."},
      {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Single bounded task: add missing test for POST /reviews with no ingested documents in tests/unit/test_review_routes.py, 2-3hr estimate, no umbrella/design debate/core-internals language."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, no linked PRs, no comments in thread."},
      {"name": "ai-contribution-policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md exists but contains no mention of AI-generated code or AI policy (silence passes)."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Most recent default-branch commit is dated Sep 16, 2026, 7 days before today."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Not archived; last push (Sep 16, 2026) within 180 days."},
      {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Single bounded bug fix in rag/generator/output_parser.py to handle top-level JSON array fallback, with named test to unmark (xfail H-02), 2-4hr estimate."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, no linked PRs, no comments in thread."},
      {"name": "ai-contribution-policy", "grade": "pass", "evidence": "CONTRIBUTING.md silent on AI usage (silence passes)."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Most recent default-branch commit is dated Sep 16, 2026, 7 days before today."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Not archived; last push (Sep 16, 2026) within 180 days."},
      {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Single bounded bug fix: KeywordSearcher.index() should handle empty corpus like search() already does, in rag/retriever/keyword_search.py, with xfail test H-01 to unmark, 2-4hr estimate."},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, no linked PRs, no comments in thread."},
      {"name": "ai-contribution-policy", "grade": "pass", "evidence": "CONTRIBUTING.md silent on AI usage (silence passes)."}
    ],
    "verdict": "accept"
  }
]
```
~~~

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

Run 1 (final, saved as `eval-run.txt`): 20/20 scored items agree (bar: 18/20: PASS).
Only one full run was needed — the rubric matched all 20 gold labels the first time
`--save-run eval-run.txt` was used, so no `--only` re-runs were required to reach the
bar.

**Issue analysis**

`issue-07` (source: `wting/autojump#727`, category `dead-repo`). My rubric's verdict:
`reject`. Gold label: `reject`. Agree.

The issue itself is a clean, reproducible bug report (an `AttributeError` when jumping
to a directory name containing underscores, with steps to reproduce and a full stack
trace) — on the merits of the bug alone it looks like a fine first issue. But the
repo-facts block shows the last of the 5 most recent default-branch commits is dated
2025-02-10 and the last push to any branch is 2025-02-27, both well over 180 days
before the bundle's 2026-08-05 capture date, so `repo-in-use` fails. The `maintainer
first-response sample` is even more telling: all 5 recently-updated issues sampled,
including ones opened in 2026, show "no maintainer comment in thread" — so
`maintainer-alive` also fails, since no commit is within 180 days and no sampled
response is within 30 days. My rubric rejects on either failure alone; here both
required checks fail, so the issue is rejected regardless of how well-scoped or
well-written it is. This is exactly the `dead-repo` category the eval set is built to
test: a good-looking bug in a repo nobody is maintaining anymore.

**Check rationale**

The `unclaimed` check, quoted as currently written in `rubric.md`:

> Fail if an assignee is currently set, OR any linked PR (formally listed or only
> referenced in the comment thread) is still open, OR the most recent claim comment
> ("I'll take this", "working on this", "/assign") is unanswered and unreversed and
> less than 180 days old. A closed/abandoned linked PR, or a stale claim that a
> maintainer has since reopened or explicitly invited new contributors to retry, does
> not fail this check. Otherwise pass.

It's written this way to separate a genuinely active claim from an abandoned one,
rather than treating any claim signal as a permanent block. An assignee, an open
linked PR, or a fresh unanswered claim comment means someone is plausibly still
working on it right now, so those fail the check. But a *closed* unmerged PR, or an
old claim comment the maintainer has since reopened or invited others to retry (as in
`issue-09`, a 2022 claim the maintainer later waved off), means the earlier attempt
died — the issue is available again, so it should not be rejected just because someone
once said they'd take it.

**Trade-offs**

The check gives up any staleness threshold on *open* linked PRs: unlike claim
comments, which only fail the check if they are unanswered and under 180 days old, an
open linked PR fails the check no matter how old or inactive it is. So an issue with a
linked PR that has been open and untouched for a year, whose author has effectively
vanished, still rejects today exactly as it would if the PR were opened yesterday. I
accept this as a case the check will miss (a genuinely available issue rejected as
"claimed" because of a zombie PR) — the eval set's `claimed` category issues
(`issue-03`, `issue-08`, `issue-13`, `issue-18`) all have PRs and/or claims recent
enough that this gap never fires in the scored set, so nothing in `eval-run.txt`
changed because of it, but it is a limitation the current wording carries forward
into live mode.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. I picked issue #36 (`POST /reviews` has no test for a profile with no ingested
   documents) because it's a bounded API/testing task — write one test in
   `tests/unit/test_review_routes.py` confirming the endpoint returns a proper error
   instead of crashing — which sits squarely in my full-stack/dev-tooling interests
   and fits easily in the 2-3 hour estimate the issue itself gives, without requiring
   me to first learn RAG-specific internals like BM25 scoring.
2. The verdict correctly identified that all three candidates clear every required
   check — active repo, no archived/dead signal, no design debate, no assignee, no
   open linked PR, and a silent CONTRIBUTING.md that doesn't restrict AI-assisted
   work. What the rubric can't weigh is task shape relative to my own background: #36
   is a testing/API task I can execute confidently end to end, while #68 and #69 both
   require reading into the RAG retrieval/generation pipeline first just to
   understand the failure mode. Fit only ranks the accepted list; picking the one
   requiring the least unfamiliar-domain ramp-up was my judgment on top of that
   ranking.
3. I expect the main difficulty to be less about the fix itself and more about
   getting the test environment running correctly (seeding a profile with zero
   ingested documents, mocking whatever the endpoint depends on) so the new test
   actually exercises the no-documents path rather than passing for the wrong
   reason.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.


