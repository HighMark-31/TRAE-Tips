# Billing & Token Optimization Guide 📉

> 🏆 **Part of the winning workflow for the 2025 TRAE Global Best Practice Challenge**
>
> Learn how to minimize token consumption, slash costs, and maximize your session count in TRAE.

---

## 💡 The Token Economy Mindset

In the new TRAE billing system, every token counts. Optimization isn't just about saving money; it's about making the model faster, more accurate, and extending your project's life cycle.

### 1. The Golden Rule: Context Management
The largest driver of cost is **Input Tokens**. Every time you send a message, TRAE often sends back the preceding context.

- **Selective File Indexing**: Don't index your entire node_modules or build folders. Use `.gitignore` and TRAE's indexing settings to focus only on source code.
- **Fresh Sessions**: If you are switching from a Backend task to a Frontend task, **start a new session**. Carrying 8,000 tokens of backend logic into a frontend UI task is a waste of credits.
- **Limit File References**: Use `@file` or `#file` only for the specific files needed for the current task. Don't let the agent read 20 files if the fix is only in 2.

---

## 🛠️ Tactical Strategies for Token Savings

### 2. Model Tiering (Pro vs. Flash)
Not every task requires a "Pro" model.
- **Use Flash Models for**: Simple refactors, documentation, unit tests, and repetitive boilerplate.
- **Use Pro Models for**: Architectural decisions, complex debugging, and multi-file logic changes.
- **Saving**: Switching to Gemini-3-Flash can be **3-5x cheaper** per interaction.

### 3. Prompt Engineering for Efficiency
- **Be Precise**: Instead of "Refactor this whole file," use "Refactor the `validateUser` function on lines 45-60."
- **JSON Input/Output**: As mentioned in our [10 Best Tips](./10BestTips.md), models process structured data faster and with fewer hallucinations, leading to fewer "retry" attempts that burn tokens.
- **Stop Hallucinations Early**: Use strict [Rulesets](./RULESETS.md) like `BEH-RULE-1: If unsure, ask.` This prevents the model from generating 2,000 tokens of incorrect code that you then have to pay to fix.

### 4. Efficient Code Modification
- **Diff-Only Requests**: Ask the agent to "Show only the lines that changed" or "Provide a patch" instead of rewriting the entire file.
- **Incremental Changes**: Break large tasks into smaller sub-tasks. It's better to have 5 short, precise interactions than 1 massive interaction that fails and wastes 10k tokens.

---

## 👥 Community Pro Tips & Insights

Valuable insights from the TRAE community to further refine your token management.

### The 5-Item Cost Breakdown
Understand that a single call's cost isn't just tokens. It's a sum of:
`Total Cost = Input Tokens + Output Tokens + Tool Call Costs + Retry Costs + Manual Rework Costs`

- **Hidden Output Tokens**: Output costs include tokens generated during the model's **reasoning process** (Chain-of-Thought).
- **Tool Call Billing**: Tools like *Web Search* or *File Search* are billed separately from model tokens.

**Optimal Cost Reduction Sequence:**
1. **Reduce ineffective input** (Context management).
2. **Limit output length and format** (Precise prompts).
3. **Compress the number of tool calls** (Avoid unnecessary searches).
4. **Switch to a cheaper model** (Model tiering).

### Lean Prompts & Structured Development
Focus on a "lean" workflow to maximize results within limits:

- **Short & Structured**: Keep prompts concise and specify the exact output format (e.g., "bullet points only" or "short code snippet").
- **One Function at a Time**: Don't ask to solve a whole project. Break tasks down to solve one function or one bug per interaction.
- **Leverage System Prompts & Memory**: Use system prompts for permanent rules and memory for repeating project context to avoid re-sending it.
- **Reuse & Cache**: Reuse previously generated code or cached answers instead of re-prompting the model for the same thing.

---

## 📊 Real-World Cost Benchmarks

Based on our [New Billing Stats](./New_Billing_Stats.md), here is how optimization changes your projected spend:

| Usage Style | Avg. Tokens/Session | Projected Monthly Cost |
| :--- | :--- | :--- |
| **Unoptimized** (Full context, Pro only) | 15,000+ | $400+ |
| **Optimized** (Selective context, Tiered models) | 3,000 - 5,000 | **$80 - $120** |

---

## 🚀 The "Pro" Workflow: External APIs via SOLO

The ultimate way to save is using the **SOLO + GLM-5 Combo**.
- By connecting your own API key (via **z.ai** or **OpenRouter**), you pay wholesale prices.
- **Cost Difference**: A task that costs $0.50 in TRAE credits can cost **$0.005** via external API.
- Read the full guide here: **[SOLO + GLM-5 Best Combo](./SOLO_BestCombo.md)**.

---

## ✅ Optimization Checklist

- [ ] Is this a new task? **Start a new session.**
- [ ] Do I need the full file? **Use line ranges if possible.**
- [ ] Is this a complex task? **If not, switch to a Flash model.**
- [ ] Are tool calls (Web Search/File Search) necessary? **Compress tool usage.**
- [ ] Is my prompt "lean" and structured? **Specify exact output format.**
- [ ] Are my Rulesets active? **Prevent expensive hallucinations.**
- [ ] Am I using the right architecture? **Use SOLO for heavy refactoring.**

---
_Last updated: March 7, 2026_
_Created by: Marco (HighMark-31)_
