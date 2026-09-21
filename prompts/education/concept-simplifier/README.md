Markdown

# Complex Concept Simplifier

A structured, zero-shot chain-of-thought prompt designed to transform complex academic topics or notes into easy-to-understand explanations with real-world analogies.

## Overview
When studying complex subjects, textbook definitions can often feel dry and confusing. This prompt leverages a master communicator persona and structured output formatting to break down hard topics step-by-step, making them accessible and memorable for learners.

## Use Cases 
* **Exam Preparation & AP Review:** Breaking down complex biological cycles, physics laws, or historical movements into study guides.
* **Peer Tutoring:** Providing mentors and tutors with relatable real-world analogies to explain difficult abstractions.
* **Self-Directed Learning:** Digesting dense technical documentation or scientific research notes rapidly.

## Framework & Technique Used
- **Structure:** R-T-F-C (Role, Task, Format, Constraints)
- **Technique:** Zero-Shot Chain-of-Thought

## Output Description
The generated explanation produces four distinct study sections:
1. **The Big Picture:** A clear 2-sentence synthesis capturing the core mechanism.
2. **The Real-World Analogy:** An intuitive comparison mapping abstract functions to familiar everyday systems.
3. **Step-by-Step Breakdown:** A bulleted, chronological, or procedural walkthrough of how the concept functions.
4. **Quick Test:** Three conceptual check-for-understanding questions to assess retention.

## How to Use
1. Copy the prompt text from `prompt.md`.
2. Replace the **Input Topic or Notes** section at the bottom with your own study notes or difficult topic.
3. Paste it into your LLM of choice to generate a clear breakdown complete with analogies and review questions.

## Customization Guidance
* **Adjust Reading Level:** Change the target audience in the Task line
* **Change Communicator Style:** Adapt the Role persona
* **Add Answer Keys:** Add a rule under Constraints requesting hidden spoiler answers for the Quick Test questions.

## Examples Reference
View sample inputs, naive baseline comparisons, and complete Gemini Evaluator reports in the [`examples/`](./examples/) folder:
* [`examples/naive-output.md`](./examples/naive-output.md)
* [`examples/designed-output.md`](./examples/designed-output.md)

## Technical Details
* **Recommended Models:** GPT-4o, Claude 3.5 Sonnet, or Gemini 1.5 Pro.
* **Recommended Temperature:** 0.6 – 0.7.
* **Context Requirements:** Self-contained; suitable for single-turn study generation.
