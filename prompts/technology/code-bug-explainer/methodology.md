# Design Methodology: Code Bug Explainer & Fixer

## Design Goal

To help beginner programmers debug code errors, understand underlying programming concepts, and learn best practices without receiving confusing technical jargon or unexplained code dumps.

---

## Design Approach: Structure and Technique

**Structure I used:** Custom C-A-R-E-S (Context, Assignment/Task, Role, Execution Steps, System Constraints).

**Why this structure fits my task:**
- Debugging assistance requires setting clear boundaries so the AI acts as a tutor rather than a passive code generator.
- The C-A-R-E-S framework establishes user background, sets strict diagnostic phases, and enforces language constraints tailored to learners.

**Technique I used:** Chain-of-Thought (CoT).

**Why this technique fits my task:**
Programming bugs require logical deduction. Forcing the AI to break down the error message and isolate the flaw step-by-step drastically reduces hallucinations or syntax shortcuts.

---

## Part-by-Part Justification

| Part | What I put here | Why the prompt needs it |
|------|-----------------|-------------------------|
| Role | "You are a senior software engineer and a patient computer science mentor." | Dictates the tone, preventing overly academic or terse replies and establishing an encouraging coaching tone. |
| Context | "I am a beginner programmer who ran into a bug..." | Sets the user baseline so the model scales vocabulary appropriately, avoiding advanced topics that confuse novice developers. |
| Assignment/Task | "Analyze the provided error message... explain it in plain, beginner-friendly English, and provide the corrected code." | Establishes the primary objective and tells it the goal is to understand the error rather than blindly patching it. |
| Execution Steps | "1. Analyze the Error... 2. Locate the Issue... 3. Explain the Why... 4. Provide the Solution..." | Enforces sequential reasoning. By requiring the AI to explain the mechanism before printing the solution, it ensures the educational tutorial is prioritized. |
| System Constraints | "Avoid overly dense technical jargon without defining it first. Keep the tone encouraging and supportive." | Acts as a strict constraint filter to eliminate unexplained technical terms that hurt beginner comprehension. |
| Input Data | "Language/Environment, Error Message, Code Snippet." | Provides structured placeholders that separate compiler diagnostics from program source code, making the prompt reusable across any language. |

---

## Testing and Iteration

**Baseline I compared against:**
```
Fix this error for me in Python: TypeError: can only concatenate str (not int) to str. Code: message = 'I am' + age + 'years old.' print(message) where age = 25
```
| Version | Result / score | What changed |
|---------|----------------|--------------|
| Naive baseline | 10/100 | This naive prompt lacked a clear framework, defined constraints, or explicit output formatting instructions. |
| Final/Version 1 | 100/100 | Defined a mentor persona, outlined a specific 4-step reasoning process, and required plain-English explanations with commented code, ensuring an educational tutorial. |

**What testing showed:** Structuring the Chain-of-Thought sequence chronologically makes the AI more of a teacher than a problem solver.
**What I learned:** Forcing an explanation before code generation prevents the AI from just giving the answer, allowing the user to actually learn.
---
## Strengths and Limitations
**Works well when:** Eliminating the overload of information by breaking down errors and code into manageable pieces.
**Struggles when:** A large codebase of over 100 lines is input with multiple runtime bugs; the prompt may attempt to fix all issues simultaneously rather than tackling them one at a time.
**Would improve next:** Add an optional conditional directive for if there is multiple independent errors then it will identify the primary blocking error first and guide the user through testing that fix before proceeding.
