# Methodology & Evaluator Results: Resume Bullet Point Optimizer

## Design Choices

### 1. Structure Choice: R-T-E-F Framework
* **Role:** Establishes the persona of an executive resume writer to ensure professional, impactful terminology is used.
* **Examples & Format:** By embedding concrete "Weak vs. Strong" examples right in the prompt, the model receives a clear behavioral pattern to follow, ensuring the output directly mirrors professional resume standards across three distinct focus areas.

### 2. Technique Choice: Few-Shot (Multi-Shot)
* **Why:** Giving the AI explicit examples of how a basic task is turned into a data-driven achievement guides the model much better than a text-only instruction ever could. It prevents the AI from guessing what a "good" bullet looks like.

---

## Evaluation: Designed vs. Naive Prompt

To test the effectiveness of this designed prompt, I ran a performance comparison using the Gemini Gem Prompt Evaluator.

### Naive Version (Baseline)
* **Prompt Text:** *"Make this resume bullet sound better: Helped manage social media pages and posted updates."*
* **Gemini Evaluator Score:** **10 / 100**
* **Evaluator Feedback:** To dramatically improve this prompt, apply a structured framework (such as R-T-F or C-A-R-E), assign a professional persona (e.g., Senior Resume Strategist), and require specific quantifiable metrics and action-oriented verbs.

### Designed Version (Optimized)
* **Prompt Text:** *(Using the structured R-T-E-F prompt from `prompt.md`)*
* **Gemini Evaluator Score:** **100 / 100**
* **Evaluator Feedback:** By establishing an Executive Resume Writer persona, providing concrete transformation examples, and requiring 3 categorized output variations based on the Action Verb + Task + Measurable Result formula, it guarantees a tailored, highly actionable set of professional bullet points.

### Conclusion
Providing clear few-shot examples combined with rigid structural constraints successfully shifted the AI from making minor vocabulary tweaks to completely re-engineering the statement into a high-impact achievement.
