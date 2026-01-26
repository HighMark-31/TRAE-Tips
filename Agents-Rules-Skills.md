# 🚀 TRAE Core Concepts: Agents, Rules & Skills

This document explains **what Agents, Rules, and Skills are in TRAE**, how they differ, and how they work together.
It is designed to be **clear, practical, and immediately usable** inside the TRAE IDE.

---

## 🤖 1. [Agents](https://github.com/HighMark-31/TRAE-Agents)

### What an Agent Is

An **Agent** in TRAE is an AI assistant with a **specific role** in your development workflow.
Think of Agents as **active workers** that understand intent, plan actions, and execute tasks.

An Agent typically has:

*  A **defined purpose** (e.g. backend developer, reviewer, tester)
*  A **custom prompt** that defines its behavior
*  Access to **tools** (filesystem, terminal, models)
*  The ability to **reason, plan, and act autonomously**

You can create custom Agents and configure:

* The prompt they use
* Which tools they can access
* The type of tasks they should focus on

> **Agents are the primary actors in TRAE.** They do the actual work.

### Key Characteristics

* Accept **natural language requests**
* Decide **how to approach a task**
* Can follow **Rules** and load **Skills**
* Fully customizable for specific roles or workflows

---

## 📏 2. Rules

### What Rules Are

**Rules** are **persistent behavioral constraints** that guide how Agents operate across a project.
They live in the `.trae/rules/` directory and act as **non-negotiable guidelines**.

Rules do *not* perform tasks.
Instead, they **shape how tasks are performed**.

Typical Rules include:

*  Coding standards (naming, formatting, structure)
*  Security and compliance policies
*  Output style or language preferences
*  Architectural constraints

> **Rules ensure consistency and discipline across all Agents.**

### Key Characteristics

* Apply **globally** or at project scope
* Are **always active**
* Do **not trigger actions** directly
* Stored as Markdown files in `.trae/rules/`

---

## 🧩 3. [Skills](http://github.com/HighMark-31/TRAE-Skills)

### What Skills Are

**Skills** are **explicit, step-by-step procedures** that describe *how to perform a specific task*.
They are stored in the `.trae/skills/` directory and act like **SOPs or technical playbooks**.

Instead of relying on generic reasoning, Skills provide:

*  Clear instructions
*  Repeatable workflows
*  Predictable outcomes

Agents **load Skills only when relevant** to the task.

> **Skills tell an Agent exactly *how* to do something.**

### Key Characteristics

* Modular and reusable
* Focused on **one specific procedure**
* Loaded **on demand**
* Stored as Markdown files in `.trae/skills/`

---

## 🔄 4. How They Work Together

At runtime, TRAE follows this flow:

```
User Request
   ↓
Agent
├── Applies Rules (behavioral constraints)
└── Loads relevant Skills (procedures)
   ↓
Executes the task
```

Each component has a clear responsibility:

* **Agents** think and act
* **Rules** constrain behavior
* **Skills** provide instructions

---

## 📊 5. Comparative Overview

| Concept       | Role                  | Lives In            | When It Acts | Primary Function                   |
| ------------- | --------------------- | ------------------- | ------------ | ---------------------------------- |
| 🤖 **Agent**  | Active executor       | Agent configuration | Always       | Plans and performs work            |
| 📏 **Rules**  | Behavioral guardrails | `.trae/rules/`      | Always       | Enforces standards and constraints |
| 🧩 **Skills** | Procedural knowledge  | `.trae/skills/`     | On demand    | Provides step-by-step instructions |

---

## 🛠 6. Example Workflow

1. You ask: *"Refactor this API to follow security best practices."*
2. The **Agent** interprets the intent.
3. **Rules** enforce constraints (naming, security, architecture).
4. The Agent loads relevant **Skills**, such as:

   *  Secure API Authentication
   *  REST Endpoint Naming Conventions
5. The Agent executes the changes following those Skills.

This separation guarantees:

*  **Consistency** through Rules
*  **Repeatability** through Skills
*  **Flexibility and reasoning** through Agents

---

## ✅ 7. Recommended Usage

* Use **Agents** to represent roles and responsibilities
* Write **Rules** to encode standards and expectations
* Create **Skills** for precise, repeatable operations

This architecture makes TRAE-based workflows **professional, scalable, and predictable**.
