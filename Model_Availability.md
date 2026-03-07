# Model Availability on TRAE (Claude & GPT)

> 🏆 **Part of the winning workflow for the 2025 TRAE Global Best Practice Challenge**

This document explains why certain top-tier models like **Claude (Anthropic)** and **GPT (OpenAI)** are restricted or removed from the native TRAE interface and how to use them anyway.

---

## ❌ Claude Availability (Anthropic)

### Why Claude is not available natively
Claude models are **not available inside TRAE** due to restrictions imposed by **Anthropic**.

Anthropic has decided to **block access to its models for Chinese companies** for geopolitical and regulatory reasons. Since **TRAE is developed by ByteDance** (a Chinese company), Claude models cannot be directly integrated into the platform.

### How to use Claude models
If you need Claude (e.g., Claude 3.7 or Opus), you must use it **indirectly** via external API providers:
- **OpenRouter**
- **z.ai (Coding Plan)**
- Other third-party API abstractions

---

## ❌ GPT Availability (OpenAI - US Region)

### Current Situation
**TRAE has removed OpenAI (GPT) models from the US region** and from direct user access in several global zones.

### Why this happened (Strategic Risk Mitigation)
This is a **proactive "pre-policy" decision** by TRAE. The goal is to prevent sudden service disruptions if OpenAI decides to restrict or terminate access to its models due to increasing US-China tech tensions.

By removing them now, TRAE avoids a scenario where users' workflows are suddenly broken by external policy changes.

---

## ✅ Best Alternatives & Workarounds

If you are missing Claude or GPT, the following models are the **best native substitutes** currently available in TRAE:

1. **Gemini 3 Pro Preview** (Best overall replacement for reasoning and context)
2. **GLM-5** (Superior performance for coding and refactoring)
3. **DeepSeek-V3.1** (Strong open-source alternative)

### 🚀 The "Pro" Way: External API Integration
To get **unrestricted access** to any model (including Claude 3.7, GPT-5, etc.) while using TRAE's powerful interface:
1. Use **SOLO Mode**.
2. Connect an external API key (via **z.ai** or **OpenRouter**).
3. This bypasses regional restrictions and provides the best cost-to-performance ratio.

---

## Summary
- **Claude**: Blocked by Anthropic for ByteDance/TRAE.
- **GPT**: Removed by TRAE as a proactive risk-mitigation move.
- **Solution**: Use **Gemini 3 Pro** natively or connect **external APIs via SOLO** for full freedom.

---
_Last updated: March 7, 2026_
