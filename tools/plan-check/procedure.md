# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

<!-- What gets read, in what order, before any check is graded, and
what to note down from each part while reading. A complete procedure
decides the order (issue first? repro evidence first?) and says why
the order matters for the checks that come later. -->
1. **Read the Issue and Repro Evidence first:** Before looking at the plan, read the original issue to understand the user's report, and carefully read the Repro Evidence. Note down the exact file, line number, or behavior where the bug was proven to occur. This is your "ground truth".
2. **Read the Candidate Plan:** Read the proposed plan, specifically noting the sections for Diagnosis, Scope, and Test Plan.
3. **Read the Repo Facts and Thread Highlights:** Note any specific contribution rules (e.g., no timelines, AI disclosure requirements) and the current state of the conversation.
4. **Read the Candidate Comment:** Review the draft comment the author intends to post to the thread.

## Evidence gathering

<!-- For each evidence family your rubric's checks name, the concrete
gathering move: which part of the package (or, live, which page or
thread location per your evidence guide) to pull the fact from, and
what to record. A complete procedure leaves no check whose evidence an
executor would have to hunt for. -->
Gather evidence for the four rubric checks as follows:
- **For Diagnosis:** Pull the root cause stated in the plan's diagnosis and hold it directly against the stack trace or failing behavior recorded in the Repro Evidence. 
- **For Scope:** Search the plan explicitly for two lists: the specific components/files that *will* be changed, and the specific components/files that *will not* be touched. 
- **For Test:** Pull the testing procedure described in the plan's test section and compare it side-by-side with the reproduction steps from the Repro Evidence. 
- **For Conventions:** Pull the candidate comment and compare its promises against the Thread Highlights and Repo Facts.

## Check execution

<!-- How one check runs against gathered evidence: in what order the
checks execute, what an executor does when evidence for a check is
genuinely absent, and when a check may be graded without re-reading
the whole package. A complete procedure makes two executors grade the
same package the same way. -->
1. Grade each check in the exact order they appear in `rubric.md` (Diagnosis, Scope, Test, Conventions).
2. Compare the gathered evidence strictly against the "Pass condition" for that check. 
3. If the plan explicitly meets the pass condition, grade the check as `pass`.
4. If required information is missing entirely (e.g., the plan fails to state what is out of scope, or omits a test plan), immediately grade the check as `fail`.
5. If the evidence is present but ambiguous, contradictory, or requires you to guess the author's intent, grade the check as `unclear`.

## Verdict assembly

<!-- How the per-check grades become the final accept or reject:
apply your rubric's verdict rule, state how unclear grades enter it,
and say what gets quoted in the output for the deciding check. A
complete procedure produces the same verdict from the same grades,
every time. -->
1. Apply the verdict rule defined in `rubric.md`.
2. Evaluate the required checks:
   - If ALL `required` checks are graded `pass`, the final verdict is `accept`.
   - If ANY `required` check is graded `fail` or `unclear`, the final verdict is `reject`.
3. Output the result as a strict JSON block containing the `item` (the URL or package ID), an array of `checks` (each containing the `name`, `grade`, and a brief quote of the `evidence` used), and the final `verdict`. Do not output any markdown outside the JSON block.
