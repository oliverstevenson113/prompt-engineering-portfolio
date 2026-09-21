# Methodology & Evaluator Results: Resume Bullet Point Optimizer

## Design Choices

### 1. Structure Choice: R-T-E-F Framework
* **Role:** Establishes the persona of an executive resume writer to ensure professional, impactful terminology is used.
* **Examples & Format:** By embedding concrete "Weak vs. Strong" examples right in the prompt, the model receives a clear behavioral pattern to follow, ensuring the output directly mirrors professional resume standards across three distinct focus areas.

### 2. Technique Choice: Few-Shot (Multi-Shot)
* **Why:** Giving the AI explicit examples of how a basic task is turned into a data-driven achievement guides the model much better than a text-only instruction ever could. It prevents the AI from guessing what a "good" bullet looks like.

---

## Part-by-Part Justification
* **Role (`You are a professional executive resume writer...`):**
  * *Contribution:* It discourages conversational preamble or colloquial phrasing.
* **Task (`Rewrite the resume bullet point... using the Action Verb + Task + Measurable Result formula`):**
  * *Contribution:* Establishes the clear, actionable objective and sets a syntactic formula that every generated bullet must follow.
* **Examples of Successful Transformations (`Weak vs. Strong`):**
  * *Contribution:* Functions as the few-shot learning anchor. It shows how to introduce estimated scale and measurable results without hallucinating unrealistic accomplishments.
* **Format (`Provide 3 variations... Metrics, Leadership, Efficiency`):**
  * *Contribution:* Prevents bias by forcing the model to explore multiple professional angles, giving versatility for different job applications.
* **Input Resume Bullet (`[Insert your weak or draft resume bullet point here]`):**
  * *Contribution:* Provides a placeholder for variable user data, making the prompt fully reusable without altering system instructions.

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

### Reflection

* **Key Takeaway from Testing:** Demonstrating transformation patterns via few-shot examples is substantially more effective at constraining syntax than lengthy narrative instructions.
* **Strengths:** Produces three genuinely distinct, actionable options per query, eliminating passive resume language and speeding up application prep.
* **Limitations:** If the user supplies a bullet with zero context or quantifiable activity, the model must estimate placeholder metrics (e.g., "[X]%") that the user has to fill in manually.
* **Next Improvement:** Incorporate an interactive preliminary questionnaire step that prompts the user for rough estimations prior to generating final bullets.
