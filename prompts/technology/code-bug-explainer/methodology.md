# Methodology & Evaluator Results: Code Bug Explainer

## Design Choices

### 1. Structure Choice: C-A-R-E-S Framework
* **Rationale:** Debugging assistance requires setting clear boundaries so the AI acts as a tutor rather than a passive code generator. The C-A-R-E-S (Context, Assignment/Task, Role, Execution Steps, System Constraints) framework establishes user background, sets strict diagnostic phases, and enforces language constraints tailored to learners

### 2. Technique Choice: Chain-of-Thought 
* **Why:** Programming bugs require logical deduction. Forcing the AI to break down the error message and isolate the flaw step-by-step drastically reduces hallucinations or syntax shortcuts.

---

## Part-by-Part Justification

* **Role (`You are a senior software engineer and a patient computer science mentor`):**
  * *Contribution:* Dictates the conversational register, preventing condescending, overly academic, or terse replies and establishing an encouraging coaching tone.
* **Context (`I am a beginner programmer who ran into a bug...`):**
  * *Contribution:* Sets the user baseline so the model scales vocabulary appropriately, avoiding advanced abstractions that confuse novice developers.
* **Task (`Analyze the provided error message... explain it in plain, beginner-friendly English, and provide the corrected code`):**
  * *Contribution:* Establishes the clear, primary objective and defines the non-transactional goal: understanding the error rather than blindly patching it.
* **Steps for Your Response (Chain-of-Thought) (`Analyze the Error, Locate the Issue, Explain the Why, Provide the Solution`):**
  * *Contribution:* Enforces sequential reasoning. By requiring the AI to explain the mechanism *before* printing the solution, it ensures the educational tutorial is front and center.
* **Constraints (`Avoid overly dense technical jargon... Keep the tone encouraging`):**
  * *Contribution:* Acts as a strict negative constraint filter to eliminate unexplained technical terms (e.g., "implicit type coercion") that derail beginner comprehension.
* **Input Data (`Language/Environment, Error Message, Code Snippet`):**
  * *Contribution:* Provides structured, dedicated placeholders that separate compiler diagnostics from program source code, making the prompt reusable across any language.

## Evaluation: Designed vs. Naive Prompt

To test the effectiveness of this designed prompt, I ran a performance comparison using the Gemini Gem Prompt Evaluator.

### Naive Version 
* **Prompt Text:** *"Fix this error for me in Python: TypeError: can only concatenate str (not int) to str. Code: message = 'I am' + age + 'years old.' print(message) where age = 25"*
* **Gemini Evaluator Score:** **10 / 100**
* **Evaluator Feedback:** This is a naive, unstructured prompt that relies on basic query-style input rather than deliberate prompt design. While supplying the error message and code snippet gives the AI minimal material to diagnose the bug, the prompt lacks a clear framework, defined constraints, or explicit output formatting instructions. Incorporating a designated persona, requesting a step-by-step explanation, and specifying the desired fix format will significantly improve performance.

### Designed Version 
* **Prompt Text:** *(Using the structured C-A-R-E-S prompt from `prompt.md`)*
* **Gemini Evaluator Score:** **100 / 100**
* **Evaluator Feedback:** This designed prompt is exceptional compared to a naive "fix my code" request. By defining a patient mentor persona, outlining a specific 4-step reasoning process, and requiring plain-English explanations with commented code, it ensures the LLM delivers an educational tutorial rather than just a raw code fix.

---

## Reflection
* **Key Takeaway from Testing:** Structuring the Chain-of-Thought sequence chronologically dramatically changes how the AI approaches the problem, shifting the model from an automated code generator to an interactive teaching assistant.
* **Strengths:** Eliminates the cognitive overload of cryptic compiler errors by breaking them down into manageable pieces, reinforcing retention with commented code solutions.
* **Limitations:** If a student provides a large codebase (>100 lines) with multiple interacting runtime bugs, the prompt may attempt to fix all issues simultaneously rather than tackling them one at a time.
* **Next Improvement:** Add an optional conditional directive: "If multiple independent errors are present, identify only the primary blocking error first and guide the user through testing that fix before proceeding.
