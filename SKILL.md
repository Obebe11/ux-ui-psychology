---
name: ux-ui-psychology
description: "Use when designing or reviewing interfaces (onboarding, forms, pricing pages, paywalls, ride-hailing, booking) for AI or general products. Applies 6 psychological principles, proven A/B-test redesign patterns, and research from 2,995 paywalls (Mobbin study). Each UI element should answer one simple question for the user. Load before proposing UI flows, signup funnels, or monetization screens."
version: 2.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [ux, ui, design, psychology, conversion, onboarding, pricing]
    related_skills: [popular-web-designs, design-md, sketch]
---

# UX/UI Psychology

A successful interface is built on understanding how people make decisions — not on "pretty pictures". This skill encodes six proven psychological principles, three A/B-test redesign patterns, and findings from a study of 2,995 paywalls.

**Goal:** for any interface design/review request, run the screen through the right lens and propose concrete edits — **without manipulation**.

## When to Use

- Designing **onboarding, signup, forms, pricing, paywalls, upsells**.
- Reviewing a screen for *"why do users drop off?"*
- Explaining to a client/team why *"just add a button"* won't fix conversion.
- Writing prompts for UI generation (`claude-design`, `sketch`, `popular-web-designs`).

**Not for:** visual aesthetics (colors, typography, grid) — that's `popular-web-designs`. Here we cover only behavioral psychology.

## The Six Principles — Quick Reference

| # | Principle | One-line heuristic |
|---|-----------|--------------------|
| 1 | **Smart Defaults** | Don't show an empty form — pre-fill with the most common answers. |
| 2 | **Goal Gradient** | Never start a progress bar at 0%. Give "free" 20% just for starting. |
| 3 | **Reciprocity** | Give value first, then ask for email/signup. |
| 4 | **IKEA + Endowment** | Let the user customize something "theirs" before signup — attachment grows. |
| 5 | **Loss Aversion** | Show what they'll lose, not what they'll gain. Loss pain is ~2× stronger. |
| 6 | **Contrast Effect** | Show a price next to a larger one — the brain evaluates relative to context. |

**Rule of thumb:** never apply all 6 to one screen. Pick 1–2 relevant to the task.

→ Full details, triggers, and AI-specifics: [`references/principles.md`](references/principles.md)

## Meta-Principle (from A/B tests)

**Every UI element poses an internal question to the user. The simpler the question, the higher the conversion.**

Before redesigning, run every screen through this check: what internal question does this element raise, and can it be simplified?

→ Three concrete redesign patterns (paywall, ride-hailing, booking): [`references/ab-test-patterns.md`](references/ab-test-patterns.md)

## Paywall Research (Mobbin study, 2,995 paywalls)

Three counterintuitive findings:

| Paradox | Intuition | Reality |
|---------|-----------|---------|
| Design | Beautiful paywalls convert better | An "ugly" paywall with a ton of text can outperform a polished one |
| Friction | Fewer steps = higher conversion | Extra friction (card-required trial, multi-page) can 5× conversion |
| Structure | Single-page is simpler = better | Multi-page paywalls almost always beat single-page |

**Most reliable conversion bumps:**
- "No commitment. Cancel anytime." subtitle
- Specific CTA ("Start my free week") over generic ("Continue")
- Right chevron `›` on the CTA button
- Multi-page flow, unfolded gradually
- Preselect yearly + 14-day trial (Headspace A/B winner)

→ Full case studies (Opal, Blinkist, Tipstop, Slopes, Outsider, Headspace) with numbers, pricing patterns, framing techniques: [`references/paywall-research.md`](references/paywall-research.md)

## Screen Recipes (quick picks)

- **Onboarding:** Goal Gradient + Reciprocity + Smart Defaults → [`recipes.md`](references/screen-recipes.md#onboarding-for-a-new-ai-product)
- **Form:** Smart Defaults + Goal Gradient → [`recipes.md`](references/screen-recipes.md#data--settings-form)
- **Paywall:** Contrast Effect + Loss Aversion + Reciprocity (7 steps) → [`recipes.md`](references/screen-recipes.md#paywall--upsell)
- **Booking / cart:** Contrast Effect + Reciprocity → [`recipes.md`](references/screen-recipes.md#booking--cart)
- **Landing page (AI product):** outcome over spec → [`recipes.md`](references/screen-recipes.md#landing-page-ai-product)
- **Cancellation / churn:** Loss Aversion (truthful) → [`recipes.md`](references/screen-recipes.md#cancellation--churn-screen)

Full recipes with step-by-step instructions: [`references/screen-recipes.md`](references/screen-recipes.md)

## Ethical Boundary

These principles are for **reducing confusion and building trust**, not for manipulation. Forbidden: fake countdown timers, fake reviews, dark patterns ("hard to cancel"), faked losses, spin-the-wheel paywalls, confusing trial toggles.

**Guiding heuristic:** *if the user learned exactly how this works, would they feel cheated? If yes, don't ship it.*

→ Full ethics, pitfalls (10 failure modes), and ship checklist: [`references/ethics-and-pitfalls.md`](references/ethics-and-pitfalls.md)

## Sources

- **Video 1:** [6 Psychological Principles of UX/UI Design](https://www.youtube.com/watch?v=2TlIg3VokY8) — six principles, 70–90% default acceptance, 2× loss aversion, $50 vs $1900.
- **Video 2:** [3 UX/UI Redesign Examples (A/B Tests)](https://www.youtube.com/watch?v=zr37ibqXl1U) — paywall, ride-hailing, booking patterns, "simple question" meta-principle.
- **Video 3:** [We Studied 2,995 Paywalls. Here's What Actually Converts.](https://www.youtube.com/watch?v=9ypqs_2fAl8) — Mobbin study. Opal 7→17%, Blinkist timeline, Tipstop 3×, Slopes +25%, Outsider 5×, Headspace 14-day winner, spin-the-wheel warnings.

## Installation

See [`README.md`](README.md) for Hermes Agent installation, and [`guides/`](guides/README.md) for Claude Code, Codex, OpenCode, Cursor, Gemini CLI, Cline, Continue, Aider, Windsurf.
