# Six Psychological Principles — Details & Triggers

Deep reference for the six principles introduced in `SKILL.md`. Load this file when you need to decide *which* principle applies to a specific screen and *how* to apply it.

## Quick Recap

| # | Principle | One-line heuristic |
|---|-----------|--------------------|
| 1 | **Smart Defaults** | Don't show an empty form — pre-fill with the most common answers. |
| 2 | **Goal Gradient** | Never start a progress bar at 0%. Give "free" 20% just for starting. |
| 3 | **Reciprocity** | Give value first, then ask for email/signup. |
| 4 | **IKEA + Endowment** | Let the user customize something "theirs" before signup — attachment grows. |
| 5 | **Loss Aversion** | Show what they'll lose, not what they'll gain. Loss pain is ~2× stronger. |
| 6 | **Contrast Effect** | Show a price next to a larger one — the brain evaluates relative to context. |

---

## 1. Smart Defaults

- **Trigger:** a form with 3+ empty fields.
- **Heuristic:** pre-fill each field with the most common answer (timezone, country, currency, default privacy settings).
- **Why it works:** 70–90% of people don't change the default — they read it as an expert recommendation. An empty form = decision fatigue.
- **AI specifics:** pre-fill response style, tone, UI language by locale, default roles/use-cases by traffic source.

## 2. Goal Gradient

- **Trigger:** onboarding/questionnaire/multi-step flow with a progress bar.
- **Heuristic:** count account creation or the first click as a step. Show ≥ 20% progress from the very start. Never start at 0%.
- **Why it works:** the closer to the goal, the faster the motion. Zero demotivates.
- **AI specifics:** steps like "upload your first image" or "ask your first question" immediately advance the bar.

## 3. Reciprocity

- **Trigger:** screens where there is no value before signup ("result held hostage").
- **Heuristic:** give a partial result for free (basic report, first 3 rows of generation, preview). Then ask for email/account for the full version.
- **Why it works:** a subconscious sense of debt converts better than coercion.
- **AI specifics:** give 2–3 free model outputs, cut the watermark or cap at N messages — then ask for signup.

## 4. IKEA + Endowment

- **Trigger:** a standard "Email + Password + Button" screen with no engagement.
- **Heuristic:** before signup, let the user **make something theirs**: pick a project name, choose a theme, finish a mini-lesson, upload an avatar, configure a dashboard.
- **Why it works:** invested time and effort raise the product's subjective value. Closing the tab becomes psychologically more expensive.
- **AI specifics:** let the user create their first assistant/chat/agent before you ask for signup.

## 5. Loss Aversion

- **Trigger:** paywall/upsell framed positively ("Buy to get X").
- **Heuristic:** reframe as loss. Not "unlock PRO features", but "without PRO your files will be deleted in 7 days" / "you'll lose access to N saved projects".
- **Why it works:** psychological pain of loss ≈ 2× stronger than joy of an equivalent gain (Kahneman & Tversky).
- **AI specifics:** "your trained model will be deleted", "chat history will reset", "your prompt templates will become unavailable".

## 6. Contrast Effect

- **Trigger:** price shown in isolation.
- **Heuristic:** place the price next to a larger one (upsell insurance in the cart of an expensive item; yearly plan next to monthly; add-on next to the base tier).
- **Why it works:** the brain evaluates a number relative to what it saw a second ago. $50 against $1900 reads as "rounding error".
- **AI specifics:** "+$5/mo for priority access" next to a $20/mo base plan looks like nothing; the same $5 solo on a landing page looks expensive.

---

## Which principle applies when?

| Screen type | Primary principle | Secondary |
|-------------|-------------------|-----------|
| Onboarding step 1 | Goal Gradient | Reciprocity |
| Empty long form | Smart Defaults | Goal Gradient |
| Result behind signup | Reciprocity | — |
| New account creation | IKEA + Endowment | Reciprocity |
| Paywall / upsell | Loss Aversion | Contrast Effect |
| Pricing page | Contrast Effect | Loss Aversion |
| Booking / cart | Contrast Effect | Reciprocity (preview) |
| Cancel / churn screen | Loss Aversion | Reciprocity (last gift) |

Rule of thumb: never apply all 6 to one screen. Pick 1–2 relevant to the task. See [`ethics-and-pitfalls.md`](ethics-and-pitfalls.md) for the failure modes of over-application.
