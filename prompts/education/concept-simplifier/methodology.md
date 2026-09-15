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

### Naive Version 
* **Prompt Text:** *"Explain photosynthesis based on these notes: Plants take in sunlight, water, and carbon dioxide to make glucose and oxygen. It happens in the chloroplasts. There are light-dependent reactions and the Calvin cycle."*
* **Gemini Evaluator Score:** **35 / 100**
* **Evaluator Feedback:** This is a basic, naive prompt that provides good source notes but fails to set output boundaries, structural frameworks, or persona constraints.

### Designed Version 
* **Prompt Text:** *(Using the structured R-T-F-C prompt from `prompt.md`)*
* **Gemini Evaluator Score:** **100 / 100**
* **Evaluator Feedback:** This designed prompt scores significantly higher than the naive baseline prompt. By establishing an expert communicator role (Feynman/Nye persona), requiring step-by-step reasoning, and enforcing a rigid 4-part output format (including a real-world analogy and review questions), the prompt ensures a clear, engaging explanation tailored for high school students.

### Conclusion
Structuring the request with a communication persona and zero-shot chain-of-thought turned a boring textbook summary into an engaging, multi-layered study tool.
