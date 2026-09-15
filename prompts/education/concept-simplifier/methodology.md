# Methodology & Evaluator Results: Complex Concept Simplifier

## Design Choices

### 1. Structure Choice: R-T-F-C Framework
* **Role:** Establishes a communicator persona (Feynman/Bill Nye) to dictate a friendly, engaging tone.
* **Task & Format:** Forces the AI to output specific sections (The Big Picture, Analogy, Step-by-Step, and Quick Check) so the response is immediately structured for studying.

### 2. Technique Choice: Zero-Shot Chain-of-Thought
* **Why:** By adding the instruction *"Think through this step by step before writing your final explanation,"* the model sequences the logic from foundational rules to analogies before formatting the output, which prevents scattered or superficial summaries.

---

## Evaluation: Designed vs. Naive Prompt

To test the effectiveness of this designed prompt, I ran a performance comparison using the Gemini Gem Prompt Evaluator.

### Naive Version (Baseline)
* **Prompt Text:** *"Explain photosynthesis based on these notes: Plants take in sunlight, water, and carbon dioxide to make glucose and oxygen. It happens in the chloroplasts. There are light-dependent reactions and the Calvin cycle."*
* **Gemini Evaluator Score:** **68 / 100**
* **Evaluator Feedback:** The naive prompt generated a textbook-style definition. While factually accurate, it was dry, poorly structured, and failed to make the biochemical process intuitive or engaging for a student trying to study.

### Designed Version (Optimized)
* **Prompt Text:** *(Using the structured R-T-F-C prompt from `prompt.md`)*
* **Gemini Evaluator Score:** **95 / 100**
* **Evaluator Feedback:** The structured constraints and persona dramatically improved the output. The AI created a vivid real-world analogy (treating the chloroplast like a solar-powered kitchen), broke down the light and dark reactions logically, and added practice check questions.

### Conclusion
Structuring the request with a communication persona and zero-shot chain-of-thought turned a boring textbook summary into an engaging, multi-layered study tool.
