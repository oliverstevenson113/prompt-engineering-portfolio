Markdown

# Resume Bullet Point Optimizer

> *A structured, few-shot prompt designed to make vague resume bullet points into results-oriented achievement statements optimized for modern hiring standards.

## Overview
Many job seekers write resume bullets that sound like passive job descriptions rather than active accomplishments. This prompt uses a professional career coach persona and a few-shot examples pattern to teach the AI the exact transformation style required to highlight metrics and impact.

**Best for:**
- Career Transitions: reframing work done from a previous industry into universally valued achievements.
- Internship and Early-Career Resumes: Elevating club involvement, class projects, or entry-level roles into professional statements.
- Targeted Resume Polishing: Generating distinct angles tailored to match specific job descriptions.

**Structure:** R-T-E-F (Role, Task, Examples, Format)
**Technique:** Few-Shot (Multi-shot learning via provided examples)
**Output:** Three categorized bullet points (Metrics-Focused, Leadership-Focused, Efficiency-Focused) adhering to an Action Verb + Core Task/Context + Measurable Result/Impact format.

---

## Quick Start
1. Open [`prompt.md`](./prompt.md) and copy the template.
2. Replace the placeholders:
- `[PLACEHOLDER_1]`: [what to put here]
- `[PLACEHOLDER_2]`: [what to put here]
3. Paste it into your AI model of choice and run it.
4. Review the output and adapt it to what you need.
---
## Examples
## Output Description
The prompt yields three categorized, ready-to-use bullet points:
1. **Metrics-Focused:** Prioritizes quantifiable numbers, percentages, and scale of impact.
2. **Leadership-Focused:** Highlights initiative, cross-functional collaboration, ownership, or mentorship.
3. **Efficiency-Focused:** Emphasizes workflow optimization, time savings, procedural improvements, or resource management.

All bullets strictly adhere to the `[Action Verb] + [Core Task/Context] + [Measurable Result/Impact]` structure.

## Examples Reference
Review raw baseline outputs, optimized results, and evaluator score breakdowns in the [`examples/`](./examples/) directory:
* [`examples/naive-output.md`](./examples/naive-output.md)
* [`examples/designed-output.md`](./examples/designed-output.md)

## How to Use
1. Copy the prompt text from `prompt.md`.
2. Replace the **Input Resume Bullet** section at the bottom with your own draft resume bullet.
3. Paste it into your LLM of choice to get multiple professional variations of your achievement.

## Customization Guidance
* **Add Target Industry/Keywords:** Append a line beneath the input: `Target Industry/Role: [e.g., Software Engineering / Sales Operations]`.
* **Insert Known Numbers:** If you have exact figures, add them as notes

## Technical Details
* **Recommended Models:** Claude 3.5 Sonnet, GPT-4o, or Gemini 1.5 Pro.
* **Recommended Temperature:** 0.3 – 0.5 
* **Context Requirements:** Zero external dependencies; self-contained in a single prompt execution.


