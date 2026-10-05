## Diagnosis
The issue states that the output parser crashes when the LLM returns a top-level JSON array. My reproduction confirmed this: `rag/generator/output_parser.py` blindly calls `for key, value in data.items():` inside `_parse_json_output`. Because `data` is a `list` rather than a `dict`, this triggers an `AttributeError`.

## Scope
**In scope:**
- Adding a type-check or list-handling fallback path in `_parse_json_output` within `rag/generator/output_parser.py`.
- Removing the `@pytest.mark.xfail` marker referencing manifest id H-02 from `tests/unit/test_output_parser.py` so the test runs normally.

**Out of scope:**
- Adjusting the upstream LLM prompts to stop it from generating arrays.
- Refactoring the rest of the parsing logic or other fallback paths.

## Approach
1. Open `rag/generator/output_parser.py`.
2. Inside `_parse_json_output(data: dict)`, add a check at the top: `if isinstance(data, list):`.
3. If it's a list, process the array elements into the expected `FeedbackSection` list format instead of calling `.items()`.
4. Open `tests/unit/test_output_parser.py` and remove the `@pytest.mark.xfail` decorator from the `test_json_array_fallback` function.

## Test Plan
I will run my exact repro command from Unit 2:
`.venv/Scripts/pytest tests/unit/test_output_parser.py -k test_json_array_fallback`

**Expected behavior:** Instead of an `AttributeError`, the test will explicitly report `1 passed` (or pass alongside the rest of the unit tests).

## Risks and Unknowns
I need to check how the JSON array is structured. If the array contains strings instead of dictionaries, I may need to map them properly to the `FeedbackSection` schema so the rest of the app doesn't break downstream.

## Deviations
During the build, I discovered `FeedbackSection` requires `section_name` and `confidence` instead of `title`. I updated the implementation to match the exact schema used elsewhere in the file.