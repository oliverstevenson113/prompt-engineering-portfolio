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
* **Gemini Evaluator Score:** **65 / 100**
* **Evaluator Feedback:** The naive prompt produced minor tweaks (like changing "helped manage" to "assisted in managing"), but it did not add metrics, scale, or a results-driven structure. It remained a passive duty description.

### Designed Version (Optimized)
* **Prompt Text:** *(Using the structured R-T-E-F prompt from `prompt.md`)*
* **Gemini Evaluator Score:** **97 / 100**
* **Evaluator Feedback:** Using few-shot examples and structured format requirements caused the AI to generate dynamic, professional variations complete with placeholder metrics (e.g., growing engagement by X%) that immediately catch a recruiter's eye.

### Conclusion
Providing clear few-shot examples combined with rigid structural constraints successfully shifted the AI from making minor vocabulary tweaks to completely re-engineering the statement into a high-impact achievement.
