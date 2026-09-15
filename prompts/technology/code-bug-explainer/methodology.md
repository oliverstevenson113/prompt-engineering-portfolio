# Methodology & Evaluator Results: Code Bug Explainer

## Design Choices

### 1. Structure Choice: C-A-R-E-S Framework
* **Role:** Sets the persona as a senior engineer/mentor so the tone is encouraging rather than condescending.
* **Context:** Establishes the user's skill level (beginner) so the AI scales its language appropriately.
* **Task & Steps:** Enforces a Chain-of-Thought approach where the AI must explain the root cause *before* offering code.

### 2. Technique Choice: Chain-of-Thought (CoT)
* **Why:** Programming bugs require logical deduction. Forcing the AI to break down the error message and isolate the flaw step-by-step drastically reduces hallucinations or syntax shortcuts.

---

## Evaluation: Designed vs. Naive Prompt

To test the effectiveness of this designed prompt, I ran a performance comparison using the Gemini Gem Prompt Evaluator.

### Naive Version (Baseline)
* **Prompt Text:** *"Fix this error for me in Python: TypeError: can only concatenate str (not int) to str. Code: message = 'I am ' + age + ' years old.' where age = 25"*
* **Gemini Evaluator Score:** **62 / 100**
* **Evaluator Feedback:** The output gave the correct code immediately, but provided zero explanation of *why* Python throws type errors or how string concatenation works. It solved the immediate syntax bug without teaching the underlying concept.

### Designed Version (Optimized)
* **Prompt Text:** *(Using the structured C-A-R-E-S prompt from `prompt.md`)*
* **Gemini Evaluator Score:** **96 / 100**
* **Evaluator Feedback:** The structured role, explicit step-by-step breakdown, and constraints forced the model to act like a true teacher. It broke down the literal meaning of the error, explained data types clearly, and provided a well-commented code snippet. 

### Conclusion
Deliberate design transformed a quick, transactional fix into a valuable learning experience, proving that structure and Chain-of-Thought prompting yield significantly higher quality educational outputs.
