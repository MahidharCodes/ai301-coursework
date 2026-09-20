# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | In `repo-facts`: the maintainer first-response sample and the last 5 default-branch commits. In the issue: author role, comment authors and dates. | Pass if ANY of: (a) an OWNER, MEMBER, or COLLABORATOR opened this issue or commented in its thread within 180 days of the capture date; (b) the first-response sample shows at least one maintainer response within 30 days; (c) at least one of the last 5 default-branch commits is a merged pull request (message contains "Merge pull request" or a "(#NNNN)" reference) dated within 90 days of capture. Fail if none hold. | required |
| repo-in-use | `repo-facts`: the `archived` flag and the last 5 default-branch commit dates. | `archived: no` AND at least one default-branch commit within 180 days of the capture date. | required |
| triaged | Issue author role, applied labels, and comment authors. | Pass if ANY of: the author's role is OWNER, MEMBER, COLLABORATOR, or CONTRIBUTOR; at least one label is applied; an OWNER/MEMBER/COLLABORATOR has commented in the thread without declining the request. Fail if none hold: an unlabeled request from an outsider or from a bot account (login ending in `[bot]`) that no maintainer has touched is untriaged, and a newcomer cannot know whether the project wants it. | required |
| newcomer-scope | Issue title, body, labels, and any maintainer comments. | Pass if the issue is a bounded unit of work: a reader can tell what "done" looks like without making design decisions the project has not made. This includes a bug with a stated observable symptom and the conditions that produce it; a specific feature/UI change with stated expected behavior; or a docs task that names the pages to add or change and what they should say. Multi-file or multi-step work is still bounded when the issue itself enumerates the steps: a fully specified five-page docs update is one unit of work, not five. Causes, fixes, or suggestions listed by the author or a maintainer are guidance already given, not decisions left open; "additional suggestions", "consider", and "lower priority" items are optional extras that do not enlarge the required scope. An implementation approach is NOT required; a clear symptom or clear expected behavior is enough. A beginner label (`good first issue`, `help wanted`, `easy`, `beginner`, `starter`) satisfies this on its own for a bounded issue. Never fail on technical difficulty or subject matter (threading, multi-processing, concurrency, performance, parsing, packaging), and never fail on a `Priority: High` or `critical` label; priority describes the project's urgency, not the contributor's skill. Fail if ANY of: (a) it is an umbrella, tracking, or meta issue: the title contains "megaissue", "tracking", "epic", "umbrella", or "meta", or the body is primarily a list of links to other issues/PRs; labels do not rescue this; (b) it is an open question, design discussion, or RFC: the body asks what to do rather than stating what to do, or presents competing designs with no maintainer picking one; (c) the author or a maintainer explicitly says the work is large, needs an RFC or design doc, or should be split before anyone starts; (d) the request serves only the reporter's own organization or deployment (e.g. "our company logo") rather than the project's general users; (e) it was filed by a `[bot]` account and no human maintainer has endorsed it in the thread. | required |
| availability | Assignee field, linked PRs, and the comment thread with dates. | Pass if: assignees is none; no linked PR is open (closed or merged PRs do not block); and no comment within 30 days of capture claims the issue ("I'll take this", "working on this", "can I be assigned") without a maintainer reply releasing or redirecting it. Fail on a graveyard pattern: 2 or more separate people have claimed the issue and gone silent, even if those claims are old. Generic "how do I contribute?" comments are not claims. | required |
| policy | The `contribution policy` line in `repo-facts` only. This check is about how contributions are produced, not the issue's subject matter. | Pass if the policy has no statement on AI or generative tooling, or explicitly permits AI-assisted contributions (with or without disclosure or review requirements, e.g. "AI tools welcome; you are responsible for reviewing the output"). Fail if the policy prohibits AI-generated code or documentation, says PRs suspected of AI involvement will be closed, or "strongly discourages" generative AI. This workflow produces AI-assisted contributions, so a repo that rejects them is a reject regardless of how good the issue is. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

Accept if and only if every required check passes. Any required check graded fail or unclear rejects the issue. There are no preferred checks; if any are added later they rank accepted issues and never change the verdict.
