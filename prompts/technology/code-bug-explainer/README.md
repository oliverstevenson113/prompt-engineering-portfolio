Markdown

# Code Bug Explainer & Fixer

A structured, chain-of-thought prompt designed to help beginner programmers debug code errors, understand underlying programming concepts, and learn best practices without receiving confusing technical jargon or unexplained code dumps.

## Overview
When learning to code, encountering stack traces and cryptic error messages can be frustrating. Standard AI queries often return isolated, copy-paste code blocks without explaining *why* the bug occurred or how to prevent it. This prompt establishes a patient senior engineering mentor persona and enforces a logical, step-by-step diagnostic sequence that turns runtime exceptions into structured learning opportunities.

## Use Cases
* **Introductory Programming Support:** Assisting beginners working through foundational languages (Python, JavaScript, C++) with syntax and type errors.
* **Homework & Lab Debugging:** Helping computer science students isolate bugs independently without violating academic integrity guidelines by having AI write entire assignments.
* **Refactoring Mentorship:** Explaining subtle logic flaws, off-by-one errors, or variable scoping mistakes in plain language.

## Framework & Technique Used
* **Structure:** Custom **C-A-R-E-S** (Context, Assignment/Task, Role, Execution Steps, System Constraints).
* **Technique:** **Chain-of-Thought (CoT)**, requiring an explicit 4-stage sequential diagnostic workflow before the final corrected snippet is presented.

## Output Description
The generated debugging response delivers four distinct, labeled sections:
1. **Analyze the Error:** A jargon-free breakdown of what the compiler or interpreter error message means.
2. **Locate the Issue:** Direct identification of the exact line number, syntax element, or logic flaw triggering the issue.
3. **Explain the Why:** A conceptual deep dive into the programming rule or data-type contract that was violated.
4. **Provide the Solution:** A clean, corrected code block featuring inline comments that clearly highlight what changed.

## How to Use
1. Copy the prompt text from `prompt.md`.
2. Replace the **Input Data** section at the bottom with your specific programming language, error message, and broken code.
3. Paste it into your LLM of choice to receive a clear, educational debugging breakdown.

## Examples Reference
Review the raw baseline output, the optimized designed response, and full Gemini Evaluator grading breakdowns in the [`examples/`](./examples/) folder:
* [`examples/naive-output.md`](./examples/naive-output.md)
* [`examples/designed-output.md`](./examples/designed-output.md)

## Customization Guidance
* **Adjust Experience Level:** Change the `Context` section 
* **Enforce Frameworks/Libraries:** Add version constraints under 'Input Data'
* **Request Alternative Approaches:** Add a line under 'Steps for Your Response' asking for multiple ways to fix the issue.

## Technical Details
* **Recommended Models:** Claude 3.5 Sonnet, GPT-4o, or Gemini 1.5 Pro.
* **Recommended Temperature:** 0.2 – 0.4.
* **Context Requirements:** Completely self-contained; requires no external tools or multi-turn history.
