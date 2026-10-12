# Resume Bullet Point Optimizer

> *A structured, few-shot prompt designed to make vague resume bullet points into results-oriented achievement statements optimized for modern hiring standards.*

## Overview
Many job seekers write resume bullets that sound like passive job descriptions rather than active accomplishments. This prompt uses a professional career coach persona and a few-shot examples pattern to teach the AI the exact transformation style required to highlight metrics and impact.

**Best for:**
- Career Transitions: reframing work done from a previous industry into universally valued achievements.
- Internship and Early-Career Resumes: Elevating club involvement, class projects, or entry-level roles into professional statements.
- Targeted Resume Polishing: Generating distinct angles tailored to match specific job descriptions.

**Structure:** R-T-E-F (Role, Task, Examples, Format).

**Technique:** Few-Shot (Multi-shot learning via provided examples).

**Output:** Three categorized bullet points (Metrics-Focused, Leadership-Focused, Efficiency-Focused) adhering to an Action Verb + Core Task/Context + Measurable Result/Impact format.

---

## Quick Start
1. Open [`prompt.md`](./prompt.md) and copy the template.
2. Replace the placeholders:
   - `[INPUT_BULLET]`: Paste your draft resume bullet here.
   - `[TARGET_INDUSTRY]`: (Optional) Paste the job title or industry you are applying for.
3. Paste it into your AI model of choice and run it.
4. Review the output and adapt it to what you need.
  
---

## Examples
See the [`examples/`](./examples/) folder for filled-in demonstrations showing the
prompt and the resulting output.

---

## Customization Tips
- **Want more detail?** Add a constraint to the prompt asking the AI to add on to the contextual scope.
- **Want it shorter?** Add a constraint limiting the output to a specific word count.
- **Different context?** Adjust the `[TARGET_INDUSTRY]` placeholder to force the AI to use more specific vocabulary for the targeted industry.

---

## Technical Details
- **Structure:** R-T-E-F (Role, Task, Examples, Format)
- **Technique:** Few-Shot
- **Best models:** Claude 3.5 Sonnet, GPT-4o, or Gemini 1.5 Pro
- **Placeholders:** 2 (`[INPUT_BULLET]`, `[TARGET_INDUSTRY]`)



