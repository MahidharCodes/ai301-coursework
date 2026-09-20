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

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69

**Verdict output**

```
All evidence gathered. Here's my grading.

Ranked read-out

All three issues are from the scoped repo (codepath/pathreview-ai301-fa26-s3), not archived, actively pushed (last commit 2026-09-16), and opened by Aburke225 (COLLABORATOR) — so maintainer-alive, repo-in-use, and triaged pass for all three. The contribution policy (docs/CONTRIBUTING.md) says nothing about AI/generative tooling, so policy passes (silence passes) for all. All three are labeled bug, have no assignees, and no linked/cross-referenced PRs. All three accept.

Ranked by your fit profile (Python + Git on Windows; want to grow in AI agents & automated testing; avoid front-end):

1. #69 — Output parser crashes on top-level JSON array — best fit. RAG generator code handling raw LLM output (output_parser.py) — the most directly "working with AI agents" of the three — plus a pytest fix (remove the xfail). good first issue, tier-1, and a completely clean thread (zero claims, zero coordination needed).
2. #68 — Keyword search ZeroDivisionError on empty index — RAG retriever (keyword_search.py / BM25) with the same pytest-xfail shape; also good first issue, tier-1. Ranks just under #69 only because one classmate (acordero4852, non-member) already posted a claim comment — under the Path Review house rule that doesn't block it, but #69 is friction-free.
3. #71 — Heading hierarchy test fixture is indented — cleanest, smallest task (1–2 hrs) and a pure automated-testing fix, but it's in ingestion/parsers (markdown parsing), the least AI-agent-flavored, tier-2, and no good first issue label.

Every required check passed on all three; none were rejected.

[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Issue opened 2026-09-10 by Aburke225 (author_association COLLABORATOR); last default-branch commit 2026-09-16, within 90 days of 2026-09-20 capture."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived: False; pushed_at 2026-09-16, within 180 days of capture."},
      {"name": "triaged", "grade": "pass", "evidence": "Author role COLLABORATOR and labels applied: bug, good first issue, rag, tier-1."},
      {"name": "newcomer-scope", "grade": "pass", "evidence": "Bounded bug: stated symptom (AttributeError: 'list' object has no attribute 'items' on top-level JSON array), expected behavior (fallback should handle arrays), files named, 'good first issue' label."},
      {"name": "availability", "grade": "pass", "evidence": "assignees: none; no cross-referenced/linked PRs; 0 comments, no claim."},
      {"name": "policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no statement on AI/generative tooling; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Issue opened 2026-09-10 by Aburke225 (COLLABORATOR); last default-branch commit 2026-09-16, within 90 days of capture."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived: False; pushed_at 2026-09-16, within 180 days of capture."},
      {"name": "triaged", "grade": "pass", "evidence": "Author role COLLABORATOR and labels applied: bug, good first issue, rag, tier-1."},
      {"name": "newcomer-scope", "grade": "pass", "evidence": "Bounded bug: stated symptom (ZeroDivisionError in BM25Okapi on index([])), expected behavior (index() shouldn't raise on empty corpus), files named, 'good first issue' label."},
      {"name": "availability", "grade": "pass", "evidence": "assignees: none; no linked PR; only one claim comment (acordero4852, author_association NONE) — a classmate claim, which the Path Review house rule does not treat as blocking; single claim, so no 2+-person graveyard pattern."},
      {"name": "policy", "grade": "pass", "evidence": "No AI/generative-tooling statement in docs/CONTRIBUTING.md or PR template; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/71",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Issue opened 2026-09-10 by Aburke225 (COLLABORATOR); last default-branch commit 2026-09-16, within 90 days of capture."},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived: False; pushed_at 2026-09-16, within 180 days of capture."},
      {"name": "triaged", "grade": "pass", "evidence": "Author role COLLABORATOR and labels applied: bug, ingestion, tier-2."},
      {"name": "newcomer-scope", "grade": "pass", "evidence": "Bounded bug: stated cause (fixture indented 8 spaces so Markdown treats it as a code block, no headings found), stated fix (remove the indentation), files named."},
      {"name": "availability", "grade": "pass", "evidence": "assignees: none; no cross-referenced/linked PRs; 0 comments, no claim."},
      {"name": "policy", "grade": "pass", "evidence": "No AI/generative-tooling statement in docs/CONTRIBUTING.md or PR template; silence passes."}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

15/20, 18/20, 20/20

**Issue analysis**

issue-12 (bookwyrm-social/bookwyrm#1133). Rubric decision: reject. Gold: reject.

Five of six required checks pass. The issue carries "labels: enhancement, good first
issue, UI", so `triaged` and `newcomer-scope` pass; a MEMBER (mouse-reeve) answered in
the thread within a day; the repo's last push is 2026-08-12 on a 2026-08-12 capture;
"assignees: none; linked PRs: none", and the only claim ("I've started to look at this")
is from 2024-09-19, so `availability` passes. The verdict turns on `policy`. The
contribution policy line reads: "We do not accept AI-generated code or documentation."
That matches the check's fail condition ("prohibits AI-generated code or documentation")
verbatim, and the verdict rule is "Accept if and only if every required check passes",
so the issue is rejected.

In run 1 this item was graded accept. The old policy check read "The proposed work does
not violate explicitly stated project guidelines", and the grader evaluated the
*proposed work* (a progress bar) against the policy, found nothing wrong, and passed it.


**Check rationale**

`policy` (required). Evidence: "The `contribution policy` line in `repo-facts` only.
This check is about how contributions are produced, not the issue's subject matter."
Pass condition: "Pass if the policy has no statement on AI or generative tooling, or
explicitly permits AI-assisted contributions (with or without disclosure or review
requirements, e.g. "AI tools welcome; you are responsible for reviewing the output").
Fail if the policy prohibits AI-generated code or documentation, says PRs suspected of
AI involvement will be closed, or "strongly discourages" generative AI. This workflow
produces AI-assisted contributions, so a repo that rejects them is a reject regardless
of how good the issue is."

The form is deliberate in three ways. It names a single evidence source so the grader
cannot go hunting in the issue body for a "violation". It states the reason the check
exists (the skill's output is AI-assisted) so the grader cannot reinterpret "violate
guidelines" as being about the issue's topic. And it lists three concrete fail phrasings
rather than an adjective, because run 1 showed that "does not violate" was open to a
reading that passed every issue.

**Trade-offs**

The check treats "strongly discourages" the same as a ban. tldr-pages' policy reads:
"strongly discourages generative AI for new pages (output is often inaccurate); pull
requests suspected of being made wholly or partly with generative AI or machine
translation without human review are closed". A human-reviewed page is arguably allowed
there, and the check rejects every tldr-pages issue anyway. I accept that miss: the
policy says suspected PRs are closed, and a first-time contributor has no track record
to defend against suspicion.

Nothing else changed, and here is how I know: the check reads exactly one line of
repo-facts, and the only verdict that moved from accept to reject in the policy category
between run 1 and run 2 was issue-12. issue-10 (tldr-pages) also fails this check, but
it was already a reject on `newcomer-scope` ("title contains 'megaissue'"), so its
verdict did not move. The check was left untouched between run 2 and run 3, and the
policy category held at 1/1 while the run 3 changes to `newcomer-scope` flipped
issue-01 and issue-19 from reject to accept.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. [Which issue you're claiming, and why it fits you: the language/stack you already
   know, the part of the tool you use or care about, and how many hours you have. E.g.
   "conda#16487: it's Python, I use conda daily, and a stderr/stdout JSON fix is a
   one-evening change."]

2. [What the accept verdict got right: e.g. active repo, contributor-authored bug with a
   clear symptom, unassigned, AI-friendly policy. Then what you weighed that no check
   reads: how the codebase looks when you open it, whether you can reproduce the bug
   locally, whether the maintainer's tone in other threads is one you want to work
   with, whether the fix might touch tests you don't understand.]

3. [What makes claiming it hard. Use the repo-facts: e.g. for conda, 4 of the 5 sampled
   issues show "no maintainer comment in thread", so a claim comment may sit
   unanswered and you may need to just open the PR; for zxlive, maintainer response
   ranges from 0.4 to 92.1 days, so plan for silence. Also whether the issue author is
   a CONTRIBUTOR who might intend to fix it themselves.]

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
