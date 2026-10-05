# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

MahidharCodes

**Plan comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69#issuecomment-5988825624

I've successfully reproduced the issue and dug into the root cause.

The crash happens because _parse_json_output in rag/generator/output_parser.py expects a dictionary and unconditionally calls .items() on the parsed data.

My Plan:
I'll add a type check inside _parse_json_output to handle list inputs gracefully, mapping the array elements to the expected FeedbackSection format. Then, I will remove the @pytest.mark.xfail marker from the test_json_array_fallback test to ensure it passes cleanly and prevents regressions.

I'll start building this change on a new branch and report back!
---

## Your branch

**Branch**

fix/69-json-array-fallback

**Evidence**

Before:
```
for key, value in data.items():
E       AttributeError: 'list' object has no attribute 'items'

rag\generator\output_parser.py:68: AttributeError
```
After:
```
tests\unit\test_output_parser.py .                                                                                                                                              [100%]

========================================================================== 1 passed, 18 deselected in 0.43s ==========================================================================
```


## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

**Package analysis**

1. 1/1 (errored out due to Windows cp1252 charmap encoding)
2. 4/4 (partial run testing packages 1-4 after fixing PYTHONUTF8=1)
3. 20/20 (final full run, saved to eval-run.txt)

**Check rationale**

`pkg-01`
My rubric graded this as `reject`, and the gold label was `reject`. It correctly failed the Diagnosis check because the plan identified an unrelated error (wrong cause) instead of the actual root cause shown in the repro evidence.

**Trade-offs**

By strictly requiring an explicit "out of scope" list, my Scope check might reject a generally safe plan that just forgot to name what it isn't touching. I accept this trade-off because I am prioritizing strict safety boundaries over a slightly faster PR process.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
