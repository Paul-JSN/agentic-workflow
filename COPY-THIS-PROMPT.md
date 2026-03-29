# Copy This Prompt

Copy the block below into the primary agent.

```text
Read `START-HERE.md`, `INTERNAL-BUNDLE-PICKER.md`, and the files in `starter-bundles/`.

Goal: choose the smallest suitable starter bundle for the current operator request.

Return:
1. recommended bundle
2. short reason for the choice
3. exact files that should be applied first
4. optional files that should stay out for now
5. one approval question before making any changes

Rules:
- prefer the smallest viable bundle
- prefer a bundle with an explicit verification lane when the task is not trivial
- do not ask the operator to choose roles manually unless truly necessary
- keep the system simple for a beginner
- do not apply anything until approval is given
- do not treat bundle recommendation as permission to execute work
```
