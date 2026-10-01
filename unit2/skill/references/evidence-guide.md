# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

Where it lives: In an eval bundle, the repro report's environment
section (OS, language/runtime version, package manager, dependency
versions), read against the repo-facts block's stated target version
or platform. In live mode, the student's draft repro comment's
environment line, read against the issue body's stated version/platform
and, when the issue doesn't state one, the repo's README or
CONTRIBUTING "supported versions" section on GitHub.

What good looks like: Specific version numbers, not "latest" or
"current"; the OS/runtime named whenever this bug class is
platform-sensitive; and either a match to the issue's target or an
explicit flag of the difference ("tested on v2.3, issue reports v2.1;
noting the difference").

## Steps

Where it lives: In an eval bundle, the repro report's numbered steps
section. In live mode, the draft repro comment's steps, read against
any repro steps the issue author already gave, to see whether the
student's steps start from a comparable state.

What good looks like: Every step is a concrete, executable action (a
shell command, an exact input value, a specific UI action), and the
sequence states its starting point (a fresh clone, a specific
branch/commit, a specific input file). The triggering content does not
need to be pasted character-for-character; a precise description of
what it must contain ("a dependencies list plus an unrecognized
`category:` key") is enough for a stranger to recreate an equivalent
input. A step that says "configure the server" or "do the usual setup"
without naming the command, or describes the trigger too vaguely to
recreate ("a normal environment file"), is not followable.

## Behavior shown

Where it lives: In an eval bundle, the repro report's artifact section
(pasted output, stack trace, log, or described screenshot), read next
to the issue context's description of the bug. In live mode, the
pasted output or log in the draft, read next to the issue body and
thread highlights on GitHub.

What good looks like: When the report claims to reproduce the issue,
the artifact contains the same error message, the same stack frame, or
the same visible symptom the issue describes, not just "it crashed"
with no text, and not an error that merely resembles the issue's but is
actually a different failure (a different exception type, or a bug
already identified elsewhere in the thread as separate). When the
report honestly states it could not reproduce the issue, this family is
about whether the attempt was genuine: the artifact should show the
same trigger/scenario the issue describes being attempted, even though
the bug did not appear. A cannot-reproduce report that never actually
attempted the issue's real trigger is not a genuine attempt, whatever
it concludes; whether the stated conclusion itself is honest belongs to
the Honesty family below.

## Honesty

Where it lives: In an eval bundle, the repro report's stated
conclusion or summary line, read against its own artifact. In live
mode, the draft's closing statement ("confirmed", "could not
reproduce", "partially reproduced"), read against what was actually
pasted above it.

What good looks like: The conclusion's strength matches the evidence.
"Confirmed" only when the artifact shows the exact behavior described
in the issue. "Could not reproduce" stated plainly, with the attempted
steps shown, rather than omitted or dressed up as a confirmation.

## Comms

Where it lives: In an eval bundle, the repo-facts block (the repo's
stated bug-report template asks and contribution policy, including any
AI-use disclosure requirement), read against the claim comment and
repro comment text. In live mode, the repo's CONTRIBUTING.md, issue
template, or pinned contribution guide on GitHub, read against the
student's draft.

What good looks like: The comment addresses this specific issue
(quotes its symptom or number, references actual investigation already
done), fills in any template fields the repo asks for rather than
skipping them, and discloses AI assistance exactly as the repo's policy
requires. A repo's AI policy is one of two different things, and they
ask for opposite evidence: a disclosure requirement ("all AI usage must
be disclosed") needs an explicit sentence in the comment stating AI was
used; a well-written, thorough, or confident comment is not itself
evidence of disclosure, and the complete absence of such a sentence
always fails. A human-authorship requirement ("comments must be
written by a human in their own words," "AI-generated comments may be
hidden") needs no disclosure sentence at all; it only needs the comment
to read as ordinary human writing that doesn't claim AI wrote it. Never
silence where disclosure is required, never a disclosure sentence where
the policy instead just wants human-sounding prose. A claim comment
that could be
pasted onto any issue unchanged is not specific, however enthusiastic:
watch for flattery standing in for content ("great project, love your
work"), unverifiable guarantees ("guaranteed fix in 2 days"), or a
demand to be assigned with no stated engagement with the issue itself.
