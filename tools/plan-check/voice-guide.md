# Voice guide: how I talk upstream

<!--
THIS IS A CARRY-OVER SLOT, not a new hole. You wrote this guide in
week 2; paste your filled week-2 voice-guide.md here, whole. It is not
re-authored and it is not graded as new work this week.

Then reread it with the plan comment in mind. Your claim and repro
comments promised and reported; a plan comment commits you to an
approach in front of the people who maintain the code. If your rules
do not cover that register (for example: how you state an approach you
are not certain of, or how you respond when a maintainer already
suggested a direction), extend the guide with what it needs. Extending
is allowed and encouraged; starting over is not required.

Live mode reads this file before your plan comment goes out and
reports any rule your draft breaks. Eval mode ignores it entirely,
because your voice is yours and carries no gold labels.
-->

## Who I am in threads

<!-- Paste your week-2 section here. -->
I am a student contributor participating in a class exercise to reproduce open-source bugs. I am here to provide clear, objective, and factual reproduction reports to save maintainers time. I document what I see; I do not guarantee fixes.

## Rules I write by

<!-- Paste your week-2 rules here, wrong/right pairs and all. Add any
rule the plan-comment register needs that your week-2 comments did
not. -->
### Rule: Promise the investigation, never the fix
Do not tell a maintainer you will solve their problem or give them a timeline for a PR. Promise only the reproduction report.
- Wrong: "I am claiming this issue and will have a PR up with a fix by tomorrow!"
- Right: "I'd like to look into this. I'll attempt to reproduce the bug and post my findings here."

### Rule: Specifics over excitement
Omit filler adjectives and robotic enthusiasm. State exactly what you are doing.
- Wrong: "Hello! This is an incredibly awesome project and I am super excited to dive in and help out!"
- Right: "Hi, I am setting up a local environment to reproduce this error."

### Rule: Explicit AI disclosure
If I used an AI tool to write or format the report, state it plainly at the end of the comment, especially if the repo requires it.
- Wrong: (Saying nothing while posting an overly-polished, structured markdown report).
- Right: "Note: The formatting of this reproduction report was assisted by an AI tool."

## Things I never post

<!-- Paste your week-2 list here; extend it if planning tempts you
toward new ones (overpromised timelines are the classic). -->
- Deadlines, ETAs, or promises of a pull request.
- Demands for maintainer attention ("Please review this soon").
- "Me too" comments that don't add new environmental data or logs.
- Apologies for being a beginner.
