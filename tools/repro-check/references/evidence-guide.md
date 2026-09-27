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

<!-- Where the environment record lives, and what a sufficient one
looks like against the issue's stated target. -->
- **Where it lives:** In the "Environment" or "Setup" header of the draft repro report.
- **What good looks like:** Lists concrete version numbers (e.g., `Node v18.16.0`, `macOS 13.4`) rather than vague statements like "latest version."

## Steps

<!-- Where the reproduction steps live, and what makes them followable
by a stranger, starting state to trigger. -->
- **Where it lives:** In the "Steps to Reproduce" section of the report.
- **What good looks like:** A numbered list of exact terminal commands or UI clicks, starting from cloning the repo or a blank project state, leading directly to the error.

## Behavior shown

<!-- Where the artifacts live (output excerpts, logs, screenshots),
and what it means for an artifact to show the issue's behavior rather
than an adjacent one. -->
- **Where it lives:** Inside markdown code blocks, blockquotes, or linked screenshots immediately following the reproduction steps.
- **What good looks like:** The stack trace or terminal output visibly contains the exact exception name, error code, or broken output described by the original issue author.

## Honesty

<!-- Where claims and their backing meet: how to tell a report that
says exactly what happened (including an honest cannot-reproduce) from
one that claims more than its evidence shows. -->
- **Where it lives:** The concluding sentence of the report or the opening summary.
- **What good looks like:** The written conclusion strictly matches the provided logs. It says "I successfully reproduced the bug" ONLY when the logs show the failure. It says "I could not reproduce the bug" if the logs show a successful run.

## Comms

<!-- Where the words meet the repo: the claim comment against the
issue, the comments against the repo's stated templates and
contribution policy (including AI-use disclosure requirements), and
what specific-and-honest looks like next to boilerplate. -->
- **Where it lives:** The draft claim comment and the report's introductory text, compared against the `repo-facts` block's contribution policy.
- **What good looks like:** The text does not overpromise a fix. If the repo requires AI disclosure, a sentence like "Drafted with the assistance of Claude" is explicitly present in the draft comment.
