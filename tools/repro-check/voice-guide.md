# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->
I am a student contributor participating in a class exercise to reproduce open-source bugs. I am here to provide clear, objective, and factual reproduction reports to save maintainers time. I document what I see; I do not guarantee fixes.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->
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

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->
- Deadlines, ETAs, or promises of a pull request.
- Demands for maintainer attention ("Please review this soon").
- "Me too" comments that don't add new environmental data or logs.
- Apologies for being a beginner.