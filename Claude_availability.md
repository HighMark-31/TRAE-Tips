# Claude availability on TRAE

## ❌ Why Claude is not available on TRAE

Claude models are **not available inside TRAE** due to restrictions imposed by **Anthropic**, the company behind Claude.

Anthropic has decided to **block access to its models for Chinese companies** for **geopolitical and regulatory reasons**.  
Since **TRAE is developed by ByteDance**, and ByteDance is a **Chinese company**, Claude models cannot be directly integrated or exposed inside TRAE.

This is **not a technical limitation of TRAE**, but a **policy decision made by Anthropic**.

---

## ✅ How to still use Claude models

If you strongly prefer Claude (e.g. Opus), you can still use it **indirectly** by relying on external API providers, such as:

- **OpenRouter**
- Other third-party Claude API providers

In these cases, Claude runs **outside of TRAE’s native model list**, accessed via external routing or API abstraction.

---

## 🔁 Best alternative to Claude Opus 4.6

At the moment, the **best replacement for Claude Opus 4.6 inside TRAE** is:

**➡️ Gemini 3 Pro Preview**

Why Gemini 3 Pro Preview:
- Excellent reasoning and long-context handling
- Strong code understanding and generation
- Very competitive with Claude Opus for analysis and complex tasks
- Fully supported and accessible within TRAE

For most use cases where Claude Opus was preferred, **Gemini 3 Pro Preview is the closest and most reliable substitute** available today.

---

## Summary

- Claude is unavailable on TRAE due to **Anthropic restrictions on Chinese companies**
- TRAE is affected because it is owned by **ByteDance**
- Claude can still be used via **OpenRouter or external APIs**
- **Gemini 3 Pro Preview** is currently the **best native alternative** inside TRAE
