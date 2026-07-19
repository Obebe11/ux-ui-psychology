---
name: ux-ui-psychology
description: "Use when designing or reviewing interfaces (onboarding, forms, pricing pages, paywalls, ride-hailing, booking) for AI or general products. Applies 6 psychological principles, 3 A/B-test patterns, and concrete paywall triggers. Each UI element should answer one simple question for the user. Load before proposing UI flows, signup funnels, or monetization screens."
version: 3.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [ux, ui, design, psychology, conversion, onboarding, pricing]
    related_skills: [popular-web-designs, design-md, sketch]
---

# UX/UI Psychology

Trigger → action rules for interface design. Apply the matching rule when its trigger fires; don't preload everything.

## When to Use

- Designing or reviewing **onboarding, signup, forms, pricing, paywalls, upsells, booking**.
- Investigating **why users drop off** a specific screen.
- Writing prompts for UI generation (`claude-design`, `sketch`, `popular-web-designs`).

**Not for:** visual aesthetics (colors, typography, grid) — that's `popular-web-designs`.

## The Six Principles — Quick Reference

| # | Trigger | Action |
|---|---------|--------|
| 1 | **Form with 3+ empty fields** | **Smart Defaults** — pre-fill with the most common answer. |
| 2 | **Multi-step flow / progress bar** | **Goal Gradient** — start at ≥ 20%, never 0%. |
| 3 | **Signup wall before value** | **Reciprocity** — give a partial result free first. |
| 4 | **Bare "Email + Password" signup** | **IKEA + Endowment** — let user customize something theirs first. |
| 5 | **Paywall framed as a gain** | **Loss Aversion** — reframe as what they'll lose. |
| 6 | **Price shown in isolation** | **Contrast Effect** — anchor against a larger number. |

**Rule:** never apply more than 2 principles to one screen.

→ Full triggers, actions, pitfalls: [`references/principles.md`](references/principles.md)

## Meta-Rule

**Every UI element poses an internal question. The simpler the question, the higher the conversion.**

Audit each element: what internal question does it raise? Can it be simplified?

→ Three concrete patterns (paywall, ride-hailing, booking): [`references/ab-test-patterns.md`](references/ab-test-patterns.md)

## Paywall Triggers (quick picks)

- **Paywall appears cold (no value delivered)** → insert a value screen before it.
- **CTA says "Subscribe" or "Continue"** → replace with "Start my free trial" / "Start my free week".
- **No "Cancel anytime" reassurance** → add subtitle: "No commitment. Cancel anytime."
- **Plain CTA button** → add right chevron `›`.
- **Free trial without timeline** → add visible timeline with day-5 reminder promise.
- **Single-page paywall** → split into multi-page flow.
- **Only one pricing option** → add a more expensive anchor option (max 2 visible).

→ Full paywall triggers and actions: [`references/paywall-patterns.md`](references/paywall-patterns.md)

## Screen Recipes (quick picks)

- **Onboarding:** Goal Gradient + Reciprocity + Smart Defaults → [`screen-recipes.md`](references/screen-recipes.md#onboarding-for-a-new-ai-product)
- **Form:** Smart Defaults + Goal Gradient → [`screen-recipes.md`](references/screen-recipes.md#data--settings-form)
- **Paywall:** Contrast Effect + Loss Aversion + Reciprocity → [`screen-recipes.md`](references/screen-recipes.md#paywall--upsell)
- **Booking:** Contrast Effect + Reciprocity → [`screen-recipes.md`](references/screen-recipes.md#booking--cart)
- **Landing page (AI):** outcome over spec → [`screen-recipes.md`](references/screen-recipes.md#landing-page-ai-product)
- **Cancellation:** Loss Aversion (truthful) → [`screen-recipes.md`](references/screen-recipes.md#cancellation--churn-screen)

Full recipes: [`references/screen-recipes.md`](references/screen-recipes.md)

## Ethical Boundary

Forbidden: fake countdown timers, fake reviews, dark patterns ("hard to cancel"), faked losses, spin-the-wheel paywalls, confusing trial toggles.

**Test:** *if the user learned how this works, would they feel cheated? If yes, don't ship it.*

→ Full ethics, 10 pitfalls, ship checklist: [`references/ethics-and-pitfalls.md`](references/ethics-and-pitfalls.md)

## Sources

- [6 Psychological Principles of UX/UI Design](https://www.youtube.com/watch?v=2TlIg3VokY8)
- [3 UX/UI Redesign Examples (A/B Tests)](https://www.youtube.com/watch?v=zr37ibqXl1U)
- [We Studied 2,995 Paywalls. Here's What Actually Converts.](https://www.youtube.com/watch?v=9ypqs_2fAl8)

## Installation

See [`README.md`](README.md) for Hermes Agent install, and [`guides/`](guides/README.md) for Claude Code, Codex, OpenCode, Cursor, Gemini CLI, Cline, Continue, Aider, Windsurf.
