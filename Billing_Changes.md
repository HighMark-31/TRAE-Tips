# TRAE Membership Update — What Actually Changes 🔍

TRAE is moving from a **request-based system** to a **token-based system**.

This affects **everyone**, not just Pro users.

Let’s break it down clearly.

Image and Link reference :
<img width="2770" height="1144" alt="image" src="https://github.com/user-attachments/assets/fcb9c79f-1dd0-4fff-b050-237840735363" />

<img width="2652" height="1126" alt="image" src="https://github.com/user-attachments/assets/3171a6ff-9a66-47e3-af37-1cd94e1b1965" />

https://www.trae.ai/blog/trae_membership_0213
---

# 🔁 Before vs Now

## Before (Request-Based Model)
- You had a fixed number of Fast Requests.
- 1 request = 1 premium model call.
- Context size didn’t directly impact quota.
- Simple and predictable.

If you had 600 requests → you could make 600 premium calls.

---

## Now (Token-Based Model)
- Each plan gives a monthly **$ basic usage balance + bonus usage**.
- Every interaction consumes tokens based on:
  - Input size
  - Output size
  - Context window
  - Tool calls
  - Model choice
  - Mode (Regular vs Max)

Now:

> 1 interaction ≠ 1 unit.  
> Heavy sessions cost more tokens.

---

## ✅ Advantages of the New System

### Larger Context Windows
- Regular Mode: up to ~272K tokens  
- Max Mode: up to 1M tokens  
- Up to 200 tool calls per session  

This is a major upgrade for:
- Large repositories
- Long agent workflows
- Complex automation tasks

## ❌ Disadvantages / Trade-Offs

### Less Predictable Usage
Before:
- You knew exactly how many calls you had left.

Now:
- You must monitor token burn.
- Large contexts consume budget faster.

---

### Heavy Users May Consume Faster
If you:
- Use massive repo contexts
- Run Max mode often
- Perform long agent sessions

Your monthly allowance may drain faster than expected.

---

# ⚠️ Focus: What Changes If You Are a Pro User ⚠️

If you are currently Pro:

## 👍 What Improves
- Larger context windows
- More technical flexibility
- Potentially more usable sessions (depending on usage pattern)
- Stronger SOLO mode capability

## 👎 What Becomes Riskier
- Token burn replaces fixed request predictability
- Heavy sessions may consume allowance faster
- Early Access model access may require upgrading to Ultra

---

# 🎯 Final Take

Technically → the system is more powerful.  
Economically → it becomes usage-dependent.

If you:
- Use moderate prompts → you likely benefit.
- Run large repo-level workflows daily → monitor token usage carefully.

The key is simple:

Track your real monthly token consumption after transition.  
Then decide whether your current tier is still optimal.
