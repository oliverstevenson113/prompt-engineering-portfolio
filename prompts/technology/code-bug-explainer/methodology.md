# Methodology & Evaluator Results: Code Bug Explainer

## Design Choices

### 1. Structure Choice: C-A-R-E-S Framework
* **Role:** Sets the persona as a senior engineer/mentor so the tone is encouraging rather than condescending.
* **Context:** Establishes the user's skill level as beginner so the AI scales its language appropriately.
* **Task & Steps:** Enforces a Chain-of-Thought approach where the AI must explain the root cause *before* offering code.

### 2. Technique Choice: Chain-of-Thought 
* **Why:** Programming bugs require logical deduction. Forcing the AI to break down the error message and isolate the flaw step-by-step drastically reduces hallucinations or syntax shortcuts.

---

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

### Conclusion
Deliberate design transformed a quick, transactional fix into a valuable learning experience, proving that structure and Chain-of-Thought prompting yield significantly higher quality educational outputs.
