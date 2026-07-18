---
name: ux-ui-psychology
description: "Use when designing or reviewing interfaces (onboarding, forms, pricing pages, paywalls, ride-hailing, booking) for AI or general products. Applies 6 psychological principles + proven A/B-test redesign patterns (trial paywalls, fixed pricing, immersive booking). Each UI element should answer one simple question for the user. Load before proposing UI flows, signup funnels, or monetization screens."
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [ux, ui, design, psychology, conversion, onboarding, pricing]
    related_skills: [popular-web-designs, design-md, sketch]
---

# UX/UI Psychology: Principles + A/B-Test Patterns for Conversion & Retention

## Overview

A successful interface is not built on "pretty pictures" but on understanding how people make decisions. This skill encodes six proven psychological principles that reduce confusion and increase conversion and retention — **without manipulation**.

Goal: for any interface design/review request, automatically run the screen through these six lenses and propose concrete edits.

## When to Use

- Designing onboarding, signup, forms, pricing, paywalls, or upsells.
- Reviewing an existing screen for "why do users drop off?"
- Explaining to a client/team why "just add a button" won't work.
- Writing a prompt for UI generation (claude-design, sketch, popular-web-designs).

**Not for:** visual aesthetics (colors, typography, grid) — that's `popular-web-designs`. Here we cover only behavioral psychology.

## Six Principles — Quick Reference

| # | Principle | One-line heuristic |
|---|-----------|--------------------|
| 1 | **Smart Defaults** | Don't show an empty form — pre-fill with the most common answers. |
| 2 | **Goal Gradient** | Never start a progress bar at 0%. Give "free" 20% just for starting. |
| 3 | **Reciprocity** | Give value first, then ask for email/signup. |
| 4 | **IKEA + Endowment** | Let the user customize something "theirs" before creating an account — attachment grows. |
| 5 | **Loss Aversion** | Show what they'll lose, not what they'll gain. Loss pain is ~2× stronger than gain joy. |
| 6 | **Contrast Effect** | Show a price next to a larger one — the brain evaluates relative to context. |

## Details & Triggers

### 1. Smart Defaults
- **Trigger:** a form with 3+ empty fields.
- **Heuristic:** pre-fill each field with the most common answer (timezone, country, currency, default privacy settings).
- **Why it works:** 70–90% of people don't change the default — they read it as an expert recommendation. An empty form = decision fatigue.
- **AI specifics:** pre-fill response style, tone, UI language by locale, default roles/use-cases by traffic source.

### 2. Goal Gradient
- **Trigger:** onboarding/questionnaire/multi-step flow with a progress bar.
- **Heuristic:** count account creation or the first click as a step. Show ≥ 20% progress from the very start. Never start at 0%.
- **Why it works:** the closer to the goal, the faster the motion. Zero demotivates.
- **AI specifics:** steps like "upload your first image" or "ask your first question" immediately advance the bar.

### 3. Reciprocity
- **Trigger:** screens where there is no value before signup ("result held hostage").
- **Heuristic:** give a partial result for free (basic report, first 3 rows of generation, preview). Then ask for email/account for the full version.
- **Why it works:** a subconscious sense of debt converts better than coercion.
- **AI specifics:** give 2–3 free model outputs, cut the watermark or cap at N messages — then ask for signup.

### 4. IKEA + Endowment
- **Trigger:** a standard "Email + Password + Button" screen with no engagement.
- **Heuristic:** before signup, let the user **make something theirs**: pick a project name, choose a theme, finish a mini-lesson, upload an avatar, configure a dashboard.
- **Why it works:** invested time and effort raise the product's subjective value. Closing the tab becomes psychologically more expensive.
- **AI specifics:** let the user create their first assistant/chat/agent before you ask for signup.

### 5. Loss Aversion
- **Trigger:** paywall/upsell framed positively ("Buy to get X").
- **Heuristic:** reframe as loss. Not "unlock PRO features", but "without PRO your files will be deleted in 7 days" / "you'll lose access to N saved projects".
- **Why it works:** psychological pain of loss ≈ 2× stronger than joy of an equivalent gain (Kahneman & Tversky).
- **AI specifics:** "your trained model will be deleted", "chat history will reset", "your prompt templates will become unavailable".

### 6. Contrast Effect
- **Trigger:** price shown in isolation.
- **Heuristic:** place the price next to a larger one (upsell insurance in the cart of an expensive item; yearly plan next to monthly; add-on next to the base tier).
- **Why it works:** the brain evaluates a number relative to what it saw a second ago. $50 against $1900 reads as "rounding error".
- **AI specifics:** "+$5/mo for priority access" next to a $20/mo base plan looks like nothing; the same $5 solo on a landing page looks expensive.

## A/B-Test Patterns: 3 Redesigns

Meta-principle: **every UI element poses an internal question to the user. The simpler the question, the higher the conversion.** ([2:25](https://www.youtube.com/watch?v=zr37ibqXl1U&t=145s))

Before redesigning, run every screen through this check: what internal question does this element raise, and can it be simplified?

### Pattern A. Paywall — Variant B won

| Element | Variant A (lost) | Variant B (won) |
|---------|------------------|-----------------|
| Core question | "Is this worth $19?" (heavy — product not yet valued) | "Do I want to try it free?" (light) |
| CTA button | "Subscribe" (heavy word) | "Start my free trial" |
| Graphics | Abstract illustrations | Real content screenshots |
| Trial transparency | None | Timeline: today → day 5 (reminder) → day 7 (charge) |

**Stealable UX tricks:**
- **Trial timeline** with an explicit "We'll remind you on day 5 before it ends" — removes fear of hidden charges (transparency effect).
- **CTA verb swap**: "subscribe" → "start free". Fewer commitments — less resistance.
- **Real screenshots** instead of abstract art — the user sees what they're paying for before deciding.

**AI specifics:** AI-product paywalls often stall on "will the model actually be better?". Fix: show concrete side-by-side outputs of free vs PRO, not abstract "premium features".

### Pattern B. Ride Hailing — Variant B won

| Element | Variant A (lost) | Variant B (won) |
|---------|------------------|-----------------|
| Price | Range "$13–17" (brain anchors on $17, the max loss) | One fixed price per tier |
| Extra info | Price only | Price + pickup time ("2 min") — focus shifts to convenience |
| Hint | None | Green "Cheaper" badge makes the decision for the user |

**Why a range loses to a fixed price:**
- **Anchoring**: the brain locks onto the top of the range as the "real" price and sees overpayment risk.
- A range feels "more honest" but is psychologically scarier.
- A fixed price removes cognitive load: the user thinks "ride or not?", not "how much will I overpay?".

**AI specifics:** don't show a range "$0.05–0.50 per request" — the user anchors on the max. Better: a fixed package price or the average cost of a typical session.

### Pattern C. Booking — Variant B won

| Element | Variant A (lost) | Variant B (won) |
|---------|------------------|-----------------|
| Overall logic | "Document form" — no emotion | "Immersive escape into the trip atmosphere" |
| Photo | Small rectangle | Half-screen hero |
| Title | "Beach house with a garden" (dry description) | "Coastal escape, steps from the sand" (emotional trigger) |
| Price | Plain | Old price struck through (visible saving) |
| Dates | "Jul 12–15" | "Friday – Wednesday" (helps visualize the trip) |
| Total | May hide fees | Full total with no hidden fees upfront |

**UX tricks:**
- **Hero photo** on half the screen — emotional entry, not utilitarian info.
- **Emotional copy** over factual labels: sells not "what this is", but "what you'll feel".
- **Struck-through price** → visible win (contrast effect + anchoring on the old price).
- **Weekdays instead of dates** → the user visualizes their vacation instead of parsing a calendar.
- **Total with no fees** → removes fear of "hidden charges" (same transparency effect as in the paywall).

**AI specifics:** an AI product landing often reads like "API documentation". Fix: sell a concrete result, not a model spec — "Turn a PDF into Excel in 30 seconds" beats "OCR engine with 99.2% accuracy".

---

## Screen Recipes

### Onboarding for a new AI product
1. Don't start the progress bar at 0% (Goal Gradient).
2. On step one, give an action with value: create the first assistant / generate a preview (Reciprocity + IKEA).
3. Pre-fill defaults from locale/source (Smart Defaults).
4. Ask for email only after the first result (Reciprocity).

### Data / settings form
1. Pre-fill every field that can be pre-filled (Smart Defaults).
2. Split into 2–3 field steps, progress starts at >0% (Goal Gradient).
3. On the final step, show what the user gets right after submit (Reciprocity).

### Paywall / upsell
1. Place a more expensive plan or add-on next to the main price (Contrast Effect).
2. Frame with loss: what disappears without the subscription (Loss Aversion).
3. A free tier with a partial result as the entry point (Reciprocity).

## Ethical Boundary

These principles are for **reducing confusion and building trust**, not for manipulation. Forbidden:
- Fake countdown timers that "reset".
- Fake reviews, fabricated social proof.
- Deceptive design (dark patterns): "hard to cancel", button swaps, pre-checked paid options.
- Faked loss where nothing is actually deleted.

Heuristic: **if the user learned how this works, would they feel cheated? If yes, don't ship it.**

## Common Pitfalls

1. **Applying all 6 principles to one screen.** Overload creates chaos. Pick 1–2 relevant to the task (form → Smart Defaults; paywall → Loss Aversion + Contrast).
2. **Starting onboarding at 0% progress.** Even a token first step (account created = 1/5 = 20%) gives a measurable completion boost.
3. **Asking for email/signup before the first value.** The most common drop-off cause on AI-product landing pages.
4. **Positive framing on paywalls.** "Unlock PRO" is weaker than "without PRO you lose N".
5. **Price solo, with no anchor.** The brain pulls out a calculator and computes the yearly cost — always show context.
6. **Dark patterns dressed up as psychology.** Fake timers and false losses destroy trust and fall under regulation (EU DSA, FTC).

## Verification Checklist

- [ ] Each screen has been checked against relevant principles (not necessarily all 6).
- [ ] No multi-step flow starts at 0% progress.
- [ ] No signup asks for email before the user has received at least partial value.
- [ ] Form fields are pre-filled where it makes sense.
- [ ] Paywall is framed with loss where appropriate and **truthful**.
- [ ] Upsell prices are shown next to an anchor.
- [ ] No fake timers, no fabricated social proof, no deceptive losses.

## Sources

- **Video 1:** "6 Psychological Principles of UX/UI Design" — youtube.com/watch?v=2TlIg3VokY8. Timestamps and specific figures (70–90%, 2× loss aversion, $50 vs $1900) are from the original video.
- **Video 2:** "3 UX/UI Redesign Examples (A/B Tests)" — youtube.com/watch?v=zr37ibqXl1U. All three redesign patterns and the "simple question" meta-principle come from this video.
