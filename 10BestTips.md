# 10 Best Tips for TRAE Mastery

> 🏆 **Part of the winning workflow for the 2025 TRAE Global Best Practice Challenge**
>
> Quick, actionable tips for maximizing your TRAE workflow. Reference before each session.

---

## 1. Use Specialized Agents, Not Generic Models

Do NOT use TRAE like a generic chatbot. Create role-specific agents:
- **Architect Agent** → System design, refactoring decisions
- **Backend Agent** → API design, database schemas
- **Frontend Agent** → UI flows, component patterns
- **Debugger Agent** → Error analysis, root cause investigation

**Result:** 3-5× better accuracy and context retention.

---

## 2. Benchmark Models Before Assignment

Before assigning a task:
1. Visit [aicompar.com](https://aicompar.com) or [llmarena.ai](https://llmarena.ai)
2. Test top 3-5 models on your specific task
3. Choose the best performer, not the "popular" one

**Pro tip:** **GLM-5** consistently beats GPT-5.3 and Claude 4.0 for code generation at a fraction of the cost.

---

## 3. Use SOLO Architecture for Long Workflows

When using TRAE:
- **Short tasks (<1000 tokens)** → Standard mode
- **Long workflows (>2000 tokens)** → Use **SOLO architecture**
- **Multi-step projects** → SOLO + external model API (z.ai / OpenRouter)

**Benefit:** Stable output formatting, significantly better context preservation.

---

## 4. Implement Strict Rules for Determinism

Create a rule system to prevent hallucinations:
```
RULE-1: Output formatting (always use JSON when requested)
RULE-2: Code validation (test before suggesting)
RULE-3: Uncertainty policy (ask if unclear, don't guess)
RULE-4: No rewriting (only modify what's needed)
```

**Effect:** Consistent, predictable agent behavior. Reference our [Rulesets Template](./RULESETS.md).

---

## 5. Use External API Models to Avoid Credit Burn

TRAE's internal credit system is expensive. Instead:

```
┌─────────────────┬──────────┬────────┐
│ Approach        │ Cost/100K│ Speed  │
├─────────────────┼──────────┼────────┤
│ TRAE Credits    │ $200-300 │ Medium │
│ GLM-5 API (z.ai)│ $10-20   │ Ultra  │
│ Claude 4.0 API  │ $30-50   │ Fast   │
└─────────────────┴──────────┴────────┘
```

**Action:** Integrate **GLM-5 API** into TRAE for 10×-100× cost savings.

---

## 6. Never Trust Agent Output Without Validation

Always add a validation step:
1. **Code generation** → Run linter + test suite
2. **Architecture** → Review against design principles
3. **Documentation** → Check for completeness + clarity
4. **Refactoring** → Diff against original, verify no logic changes

**Tool:** Use a **Validator Agent** as a mandatory second-pass.

---

## 7. Chain Agents for Complex Tasks

Example workflow:
```
User Request
    ↓
[Architect Agent] → Design document
    ↓
[Backend Agent] → Implementation
    ↓
[Debugger Agent] → Validation
    ↓
[Docs Agent] → README + comments
    ↓
Final Output
```

**Time saved:** 60-70% compared to sequential manual reviews.

---

## 8. Keep Context Windows Fresh

Don't let conversations get too long:
- **Optimal (GLM-5):** 2000-8000 tokens of context
- **Maximum:** 16384 tokens (accuracy degrades beyond this point)
- **Reset:** Start new conversation when switching domains

**Pro tip:** Use file references instead of copying large code blocks to save tokens.

---

## 9. Version Your Rulesets

Maintain a ruleset library with versions:
```
Security Ruleset v2.0
├─ Input validation rules
├─ Output sanitization rules
└─ Audit logging rules

Quality Ruleset v3.1
├─ Code style enforcements
├─ Documentation requirements
└─ Testing thresholds
```

**Benefit:** Consistent behavior across all agents + easy updates.

---

## 10. Measure and Iterate

Track these metrics per agent:
- **Accuracy:** % of outputs requiring zero edits
- **Speed:** Avg tokens/second
- **Cost:** Cost per task completed
- **Context retention:** Consistency over 10+ turns

**Cadence:** Review monthly, adjust rules/models quarterly.

---

## 11. Convert Prompts to JSON for Better Model Understanding

If a model seems to struggle understanding or following your instructions:

1. **Take your natural language prompt** and send it to an assistant.
2. **Ask to convert it to JSON format** - this structures your intent clearly.
3. **Use the JSON version in TRAE** - modern models (especially GLM-5) process structured data far better.

**Why it works:**
JSON formatting forces explicit structure, removing ambiguity and making the model's execution more predictable.

---

## Quick Checklist Before Each Session

- [ ] Selected correct specialized agent for task
- [ ] Model choice justified by recent benchmarks (Gemini 3.1 vs GLM-5)
- [ ] Rulesets loaded and up-to-date
- [ ] Context window is fresh (<8000 tokens)
- [ ] Validator agent will check output
- [ ] Cost tracking enabled via z.ai dashboard
- [ ] Using external API (not internal credits) for large tasks

---

## Next Steps

- 📖 Read [SOLO + GLM-5 Best Combo](./SOLO_BestCombo.md) for deep cost optimization
- 📋 Use [Rulesets Template](./RULESETS.md) to create your own rule systems
- 📄 Full context in [Main Whitepaper](./WHITEPAPER.md)

---

_Last updated: March 7, 2026_
_Created by: Marco (HighMark-31)_
