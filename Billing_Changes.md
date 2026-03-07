# TRAE Billing & Token Economy — Official Info & FAQ 📊

> 🏆 **Part of the winning workflow for the 2025 TRAE Global Best Practice Challenge**

This document explains the transition from the request-based system to the token-based model, supported by official team images and FAQ.

---

## 🚀 The Transition: From Requests to Tokens

TRAE is moving from a **request-based system** to a **token-based system**. This affects **everyone**, not just Pro users.

### Official Team Documentation:

**Blog** : [https://www.trae.ai/blog/trae_membership_0213](https://www.trae.ai/blog/trae_membership_0213)

---

# 🔁 Before vs Now

## Before (Request-Based Model)
- Fixed number of Fast Requests.
- 1 request = 1 premium model call.
- Context size didn’t directly impact quota.
- Simple and predictable.

## Now (Token-Based Model)
- Each plan gives a monthly **$ basic usage balance + bonus usage**.
- Every interaction consumes tokens based on input/output size, context window, and model choice.
- **1 interaction ≠ 1 unit.** Heavy sessions cost more tokens.

---

## 📊 Real Usage Stats
For a detailed technical breakdown of costs, model efficiency, and token burn from intensive professional usage, please refer to:

👉 **[NEW BILLING STATS REPORT](./New_Billing_Stats.md)**

---

## 💡 Official Bonus & Subsidy (Pro Users)

According to the TRAE Team, the transition is supported by a subsidy:

- **Officially, the Bonus Usage for Pro users is $130.**
- This is a dynamic subsidy to ensure total usable conversations remain aligned with the previous request-based system.

---

## ❓ FAQ Bonus Usage – Clear Explanation

### 1️⃣ What is Bonus Usage?
Bonus Usage is **not an extra gift package**. It is a dynamic subsidy that TRAE provides after your Basic Usage is consumed, in order to ensure that your total usable conversations remain roughly aligned with the previous request-based system.

### 2️⃣ Is Bonus Usage predictable?
At the moment, Bonus Usage is calculated dynamically based on your subscription plan and usage behavior. TRAE is working on improving transparency regarding the fixed "cap".

### 3️⃣ Will my card be charged automatically when Bonus Usage runs out?
**No.** Your card will only be charged if your subscription renews, OR you manually activate “On-Demand Usage”. No additional automatic billing occurs otherwise.

### 4️⃣ Why does the new billing feel more expensive?
Because individual request unit cost is now visible in dollars and larger context windows consume more tokens. Previously, cost was abstracted behind “requests”.

### 5️⃣ Will I get the same amount of conversations as before?
TRAE’s internal calculation aims for: **Basic Usage + Bonus Usage combined ≈ similar total conversation capacity** compared to the old plan. 

In real-world testing, we demonstrated that **500 high-intensity sessions** under the new system are effectively equivalent to the **600 requests** of the old system. While the number seems slightly lower, this is due to high-consumption usage on complex repositories (both frontend and backend) involving **more than 200 files** and massive context. For standard usage, the capacity remains virtually identical.

---

## 📢 Personal Opinion & Insights (Marco N. - AI Architect)

In these months, I have collaborated closely with the TRAE team, providing continuous feedback on the challenges posed by this new billing system. 

As an **AI Architect**, I am proud of this change. Technically, it is the best possible choice: it removes the abstraction of "requests" and introduces a transparent, usage-based model that reflects the actual compute resources consumed. It enables the use of massive context windows and complex multi-agent workflows that were previously impossible or poorly managed.

The problem, as I have consistently informed the team, was **not the technical implementation of the new billing**, but rather **how it was communicated** and the initial **lack of predictability**. For a long time, users were left in the dark about how their tokens were actually being consumed, until someone could provide a comprehensive report with real usage data and technical breakdowns.

Transparency and predictability are the keys to a professional tool. Now that we have the data, we can see that the system is technically superior, even if its introduction could have been more user-centric.

---
_Last updated: March 7, 2026_
_Data source: TRAE Official Blog & HighMark Marco N. Internal Data_
