# Design Methodology: Resume Bullet Point Optimizer

## Design Goal

To change vague resume bullet points into engaging and specific achievement statements optimized for modern hiring standards by providing a clear structural formula and professional persona.

---

## Design Approach: Structure and Technique

**Structure I used:** R-T-E-F Framework (Role, Task, Examples, Format).

**Why this structure fits my task:**
- **Role:** Establishes the persona of a resume writer to ensure professional terminology is used.
- **Examples & Format:** By embedding concrete "Weak vs. Strong" examples right in the prompt, the model receives a clear behavioral pattern to follow, ensuring the output directly mirrors professional resume standards across three distinct focus areas.

**Technique I used:** Few-Shot.

**Why this technique fits my task:**
Giving the AI explicit examples of how a basic task is turned into a data-driven achievement prevents the AI from guessing what a "good" bullet looks like.

---

## Part-by-Part Justification

| Part | What I put here | Why the prompt needs it |
|------|-----------------|-------------------------|
| **Role** | `You are a professional resume writer...` | It discourages conversational preamble or colloquial phrasing. |
| **Task** | `Rewrite the resume bullet point... using the Action Verb + Task + Measurable Result formula` | Establishes the objective and sets a formula that every generated bullet must follow. |
| **Examples** | `Examples of Successful Transformations (Weak vs. Strong)` | Functions as the few-shot learning anchor. It shows how to introduce estimated scale and measurable results without hallucinating unrealistic accomplishments. |
| **Format** | `Provide 3 variations... Metrics, Leadership, Efficiency` | Prevents bias by forcing the model to explore multiple professional angles. |
| **Input** | `[Insert your weak or draft resume bullet point here]` | Provides a placeholder for variable user data, making the prompt fully reusable without altering system instructions. |

---

## Testing and Iteration

**Baseline I compared against:**
```
Make this resume bullet sound better: Helped manage social media pages and posted updates.
```
| Version | Result / score | What changed |
|---------|----------------|--------------|
| Naive baseline | 10/100 | Evaluator suggested applying a structured framework (R-T-F/C-A-R-E), assigning a professional persona, and requiring specific metrics |
| Final/Version 1 | 100/100 | Established an Executive Resume Writer persona, provided concrete examples, and required 3 categorized output variations based on the target formula |

**What testing showed:** Demonstrating transformation patterns via few-shot examples is substantially more effective at constraining syntax than lengthy narrative instructions. 

**What I learned:** A structured prompt with concrete examples forces the AI to transition into a specialized, professional output format.

## Strengths and Limitations
**Works well when:** When it is given a bullet pint with at least a few specific details and when all placeholders are filled out.
**Struggles when:** The user supplies a bullet with zero context or quantifiable activity, forcing the model to estimate placeholder metrics.
**Would improve next:** Incorporate an interactive preliminary questionnaire step that prompts the user for rough estimations prior to generating final bullets.
