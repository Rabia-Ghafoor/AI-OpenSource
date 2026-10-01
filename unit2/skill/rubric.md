# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| environment-recorded | The repro report's environment record (OS/runtime, language version, package manager, dependency versions) read against the repo-facts block's stated target version or platform. | The record names specific versions (not "latest" or "current") and the OS/runtime where this bug class is platform-sensitive, and either matches the issue's stated target or explicitly flags the difference. | required |
| steps-followable | The repro report's numbered steps, read for whether a stranger starting from the stated initial state could execute every step without guessing. | Each step names a concrete action (an exact command, an exact input, a specific UI action) and the sequence states its starting state (fresh clone, specific branch/commit, specific input file). The triggering content does not need to be pasted verbatim as long as it is described precisely enough to recreate an equivalent input ("a dependencies list plus a category key" is precise; "a normal environment file" is not). A step that only names a goal ("set up the project", "reproduce the bug") without the means to do it fails this check. | required |
| behavior-matches-issue | The artifact in the repro report (output excerpt, stack trace, log, or screenshot description) read side by side with the issue's description of the problem. | When the report claims to have reproduced the issue, the artifact must show the same failure: same error text or symptom, same trigger. When the report honestly states it could not reproduce the behavior, this check instead passes if the artifact documents a genuine attempt at the issue's own trigger, even though the behavior did not appear. It fails when a claimed reproduction's artifact shows a different error, a different code path, or an adjacent bug passed off as the issue's own, or when a cannot-reproduce report never actually attempted the issue's real trigger. | required |
| evidenced-outcome | The report's stated conclusion (reproduced / could not reproduce / partial) read against what the attached artifact actually shows. | The stated outcome claims no more than the artifact supports. An honest "could not reproduce" backed by a described attempt passes; a "confirmed"/"reproduced" claim with no artifact, or an artifact that does not show the behavior, fails. | required |
| ai-disclosure | The claim comment and repro comment text itself, read against the repo-facts block's stated AI policy, if any. | First classify the policy, since "AI policy" covers two different asks: (1) a disclosure requirement ("all AI usage must be disclosed," "disclose assistive AI use") passes only if the comment text contains an explicit sentence stating AI was used, naming the tool/extent if the policy asks for that; the complete absence of such a sentence always fails this check, however thorough or well-written the comment is. (2) A human-authorship requirement ("comments must be written by a human in their own words," "AI-generated comments may be hidden") asks for no disclosure at all; this check passes as long as the comment reads as ordinary human writing with no claim that AI wrote it, and does not need or want a disclosure sentence. A policy that is silent on AI, or permissive with no ask of either kind, passes without further evidence. | required |
| claim-specific-and-honest | The claim comment, read against the issue's specific trigger/symptom and against generic self-promotional or over-promising language. | The comment shows it engaged with this specific issue (references the actual symptom, trigger, or investigation already done), not a template that could be pasted onto any issue. It fails if the comment relies on unverifiable guarantees ("guaranteed fix in N days"), flattery substituting for content ("great project, love your work"), or a demand to be assigned with no stated engagement with the issue. | required |

## Verdict rule

Accept only if every `required` check passes. Any check graded
`unclear` counts as `fail`: proof that cannot be verified is not proof
the package is ready to post.
