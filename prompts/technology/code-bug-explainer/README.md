# Code Bug Explainer & Fixer

> *A prompt designed to help beginner programmers debug code errors, understand underlying programming concepts, and learn best practices without receiving confusing technical jargon or unexplained code dumps.*

## Overview

Standard AI queries often return isolated, copy-paste code blocks without explaining *why* the bug occurred or how to prevent it. This prompt establishes a patient senior engineering mentor persona and enforces a logical, step-by-step diagnostic sequence that helps coders learn from mistakes.

**Best for:**
- Introductory Programming Support: Assisting beginners working through foundational languages (Python, JavaScript, C++) with syntax and type errors.
- Homework & Lab Debugging: Helping computer science students isolate bugs without cheating.
- Refactoring Mentorship: Explaining subtle logic flaws, off-by-one errors, or variable scoping mistakes in plain language.

**Structure:** Custom C-A-R-E-S (Context, Assignment/Task, Role, Execution Steps, System Constraints).

**Technique:** Chain-of-Thought (CoT), requiring an explicit 4-stage sequential diagnostic workflow before the final corrected snippet is presented.

**Output:** Four distinct, labeled sections: Analyze the Error, Locate the Issue, Explain the Why, and Provide the Solution.

---

## Quick Start

1. Open [`prompt.md`](./prompt.md) and copy the template.
2. Replace the placeholders:
   - `[LANGUAGE]`: Your specific programming language or environment.
   - `[ERROR_MESSAGE]`: The exact error output or stack trace.
   - `[CODE_SNIPPET]`: The broken code block.
3. Paste it into your AI model of choice and run it.
4. Review the output and adapt it to what you need.

---

## Examples

See the [`examples/`](./examples/) folder for filled-in demonstrations showing the
prompt and the resulting output.

---

## Customization Tips

- **Adjust Experience Level:** Change the `Context` section to reflect a more advanced learner.
- **Want it shorter?** Clarify what exactly you need to be clarified.
- **Request Alternative Approaches:** Add a line under 'Steps for Your Response' asking for multiple ways to fix the issue.

---

## Technical Details

- **Structure:** C-A-R-E-S
- **Technique:** Chain-of-Thought (CoT)
- **Best models:** Claude 3.5 Sonnet, GPT-4o, or Gemini 1.5 Pro
- **Placeholders:** 3 (`[LANGUAGE]`, `[ERROR_MESSAGE]`, `[CODE_SNIPPET]`)
