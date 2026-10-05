# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

<!-- Where the plan states its cause, and where the repro evidence
pins down the behavior that cause must explain. What it means for a
diagnosis to follow from the evidence rather than contradict or
ignore it. -->
- **Where it lives:** In an eval bundle, look at the `Candidate plan` (specifically the Diagnosis section) and hold it against the `Repro evidence` block. In live mode, look at the `plan.md` Diagnosis section and hold it against the reproduction comment the student previously posted on the live GitHub issue.
- **What good looks like:** The stated root cause directly references the specific error, stack trace, file, or line captured in the reproduction evidence. The diagnosis logically follows from the evidence rather than inventing a cause the evidence doesn't support.

## Scope

<!-- Where the plan bounds itself: the in-scope statement, the
not-in-scope line, the files or areas named. What one bounded change
looks like next to a drive-by rewrite. -->
- **Where it lives:** Look at the Scope section of the `Candidate plan` (in eval bundles) or `plan.md` (in live mode).
- **What good looks like:** The plan strictly bounds itself. It explicitly lists the files, components, or lines that *will* be changed, AND explicitly names adjacent areas, files, or functionalities that *will not* be touched. It proposes a targeted fix, not a sprawling rewrite.

## Executability

<!-- Where the plan says what will actually be done: files or areas,
approach, order of work. What it means for a stranger to be able to
start executing without asking the author anything. -->
- **Where it lives:** Look at the Approach or Implementation section of the `Candidate plan` (in eval bundles) or `plan.md` (in live mode).
- **What good looks like:** A stranger could read the proposed steps and know exactly what logic to change without having to ask the author for clarification. It specifies the actual code changes (e.g., "Add a check to gracefully handle JSON arrays in `output_parser.py`") rather than vague intentions (e.g., "Fix the parsing bug").

## Test plan

<!-- Where the plan says how success will be observed, and how that
maps onto the repro evidence's steps and artifacts. What a decisive
test plan names that a vague one does not. -->
- **Where it lives:** Look at the "Risks and Unknowns" and "Deviations" sections of the `Candidate plan` or `plan.md`.
- **What good looks like:** The author openly acknowledges what they don't know yet or what might break as a result of their change. If the plan was built and deviated from the original idea, the Deviations section accurately records what changed and why, rather than covering it up.

## Honesty

<!-- Where claims meet uncertainty: risks, unknowns, and deviations.
How to tell stated unknowns from false confidence, and where an
honest mid-build deviation gets recorded. -->
- **Where it lives:** Look at the "Risks and Unknowns" and "Deviations" sections of the `Candidate plan` or `plan.md`.
- **What good looks like:** The author openly acknowledges what they don't know yet or what might break as a result of their change. If the plan was built and deviated from the original idea, the Deviations section accurately records what changed and why, rather than covering it up.

## Comms

<!-- Where the words meet the thread and the repo: the plan comment
read against the issue's maintainer signals (thread highlights, or
the live thread) and against the repo-facts block's stated templates,
contributing asks, and contribution policy (including AI-use
disclosure requirements). What thread-aware looks like next to
boilerplate. -->
- **Where it lives:** Look at the candidate plan comment (in `comment.md` or the eval package) and hold it against the `Thread highlights` and `Repo facts` blocks. 
- **What good looks like:** The comment concisely summarizes the approach for the maintainers, doesn't promise a strict timeline, explicitly respects any guidance a maintainer has already dropped in the thread, and adheres to any contribution or AI-disclosure policies stated in the repo facts. It sounds like a helpful collaborator, not an automated bot.
