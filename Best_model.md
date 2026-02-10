# Best models for IDE usage (TRAE)

This document explains which model works best for specific IDE workflows in TRAE and highlights their main weaknesses.  
The goal is to help you quickly choose the right model for development tasks. 🧠💻

---

## ✅ Quick advice

- Working on large or complex projects → **Gemini-3-Pro-Preview**
- Heavy refactoring and backend logic → **GPT-5.2-Codex**
- Fast autocomplete and quick edits → **Gemini Flash models**
- Simple or lightweight tasks → **Kimi-K2** or **GPT-5-medium**

--- 

## Model comparison

| Model | 🥰​ Best use in IDE | 😵‍💫​ Bad / Limitations |
|------|------------------|-------------------|
| Gemini-3-Pro-Preview | Frontend, backend, full-stack development, complex reasoning, large projects | Can hallucinate in edge cases, higher latency than lightweight models |
| Gemini-2.5-Pro | General development, balanced coding and reasoning | Less powerful than Gemini-3 on complex logic |
| Kimi-K2-0905 | Simple tasks, fast suggestions, lightweight coding | Poor performance on complex reasoning and large codebases |
| GPT-5.2-Codex | Backend development, refactoring, clean and structured code | Weak with very large context and multi-file projects |
| GPT-5.2 | Balanced coding and text generation, documentation + code | Less specialized for refactoring compared to Codex |
| GPT-5.1 | General assistance, medium-complexity coding | Weaker reasoning than GPT-5.2 and Gemini-3 |
| GPT-5-high | Medium to advanced tasks, improved reasoning over medium | Still behind top-tier models for complex projects |
| GPT-5-medium | Basic code completion, small scripts | Not suitable for advanced or large-scale development |
| DeepSeek-V3.1 | Generic assistance, fallback usage | Not competitive for serious IDE workflows |
| Gemini-3-Flash-Preview | Very fast responses, quick edits, low-latency workflows | Limited depth, not suited for complex reasoning |
| Gemini-2.5-Flash | Lightweight tasks, speed-focused development | Weak on deep reasoning and large projects |

---

## 🏆 Best overall model 

Based on current benchmarks and real-world IDE usage, **Gemini-3-Pro-Preview** is the **best overall model for TRAE**.

Why it stands out:
- Excellent balance between reasoning and code generation 
- Handles complex, multi-step logic reliably 
- Strong performance on large and full-stack projects 

If you want **one single model** that performs well in almost every IDE scenario, **Gemini-3-Pro-Preview** is currently the safest and most powerful choice.

