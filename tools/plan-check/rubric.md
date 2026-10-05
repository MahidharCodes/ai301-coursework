# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Diagnosis | The candidate plan's diagnosis read against the repro evidence. | The plan explicitly identifies the root cause of the bug, and this stated cause logically aligns with (and does not contradict) the stack trace or behavior shown in the repro evidence. | required |
| Scope | The candidate plan's scope or proposed changes section. | The plan is safely bounded: it explicitly lists the specific components or files that will be changed (in scope) AND explicitly states what related functionalities or files will *not* be touched (out of scope). | required |
| Test | The candidate plan's test section read against the original repro steps. | The plan specifies an automated or manual test that directly maps to or re-runs the original repro steps, clearly proving that the reported bug no longer occurs. | required |
| Conventions | The candidate plan comment read against the thread highlights and repo facts. | The comment accurately summarizes the proposed fix for the maintainers without overpromising timelines, and respects any stated repository contribution policies or active thread state. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->
Output `accept` (ready) if every `required` check passes. 
Output `reject` (hold) if any `required` check fails.
If a check is `unclear` (?), it counts as a fail (`reject`). `preferred` checks never change the verdict.
