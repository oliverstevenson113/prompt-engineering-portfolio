# Complex Concept Simplifier

> *A structured, zero-shot chain-of-thought prompt designed to change complex academic topics or notes into easy-to-understand explanations with real-world analogies.*

## Overview
When studying complex subjects, textbook definitions can often feel dry and confusing. This prompt uses a master communicator persona and structured output formatting to break down hard topics step-by-step, making them easy to learn.

**Best for:**
- Exam Preparation and AP Review: Breaking down complex and confusing topics into study guides.
- Peer Tutoring: Providing mentors and tutors with real-world analogies to explain difficult topics.
- Self-Directed Learning: Digesting dense technical documentation or scientific research notes rapidly.

**Structure:** R-T-F-C (Role, Task, Format, Constraints)

**Technique:** Zero-Shot Chain-of-Thought

**Output:** Four distinct study sections (The Big Picture, The Real-World Analogy, Step-by-Step Breakdown, Quick Test).

---

## Quick Start

1. Open [`prompt.md`](./prompt.md) and copy the template.
2. Replace the placeholder:
   - `[INPUT_TOPIC]`: Insert your complex topic or notes here.
3. Paste it into your AI model of choice and run it.
4. Review the output and adapt it to what you need.

---

## Examples

See the [`examples/`](./examples/) folder for filled-in demonstrations showing the
prompt and the resulting output.

---

## Customization Tips

- **Want more detail?** Add a rule under Constraints requesting hidden spoiler answers for the Quick Test questions, or ask the AI to provide multiple real-world analogies.
- **Want it shorter?** Modify the Format section to remove the 'Quick Test' requirement, reducing the output to just the core explanation and analogy.
- **Different context?** Change the target audience in the Task line to adjust the reading level, or change the Role persona to match a different communicator style.
---

## Technical Details

- **Structure:** R-T-F-C (Role, Task, Format, Constraints)
- **Technique:** Zero-Shot Chain-of-Thought
- **Best models:** GPT-4o, Claude 3.5 Sonnet, or Gemini 1.5 Pro.
- **Placeholders:** 1 (`[INPUT_TOPIC]`)
