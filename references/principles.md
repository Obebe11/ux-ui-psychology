# Six Principles — Trigger → Action Reference

Apply each principle **only when its trigger fires**. Don't preload all six on every screen — pick the 1–2 that match the current UI element.

## 1. Smart Defaults

**Trigger:** Form with 3+ empty fields.
**Action:** Pre-fill each field with the most common answer:
- Locale-derived: timezone, country, currency, language.
- Product-derived: default role, default use-case, default style/tone.
- Privacy-safe defaults: opt-in unchecked, sharing off.

**AI specifics:** Pre-fill response style, tone, UI language, default roles/use-cases by traffic source.

**Pitfall:** Pre-selecting paid or privacy-sensitive options. Defaults must be reversible and clearly optional.

---

## 2. Goal Gradient

**Trigger:** Multi-step flow with a progress bar (onboarding, questionnaire, wizard).
**Action:** Count the user's first action as step 1. Show ≥ 20% progress from the first screen. Never start at 0%.

**AI specifics:** Steps like "upload your first image" or "ask your first question" immediately advance the bar.

**Pitfall:** Starting at 0% — even a token first step gives a measurable completion boost.

---

## 3. Reciprocity

**Trigger:** Signup wall before any value delivered ("result held hostage").
**Action:** Give a partial result for free first:
- Basic report with full version behind signup.
- First 3 rows of a table, blurred or truncated beyond that.
- 2–3 free AI outputs before requiring account.
- Watermark-free preview, paid version for full export.

**AI specifics:** Let the user run 2–3 model outputs or see a partial result before asking for signup.

**Pitfall:** Asking for email before any value. This is the most common drop-off cause on AI-product landings.

---

## 4. IKEA + Endowment

**Trigger:** Standard "Email + Password + Button" signup screen with no engagement.
**Action:** Before signup, let the user **make something theirs**:
- Pick a project name.
- Choose a theme or avatar.
- Finish a 30-second mini-lesson.
- Configure a dashboard.
- Create their first assistant/chat/agent.

**AI specifics:** Let the user create and name their first assistant before the signup step.

**Pitfall:** Forcing account creation before any customization. The customization *is* the hook.

---

## 5. Loss Aversion

**Trigger:** Paywall or upsell framed as a gain ("Buy to get X", "Unlock PRO features").
**Action:** Reframe as a loss:
- "Without PRO, your saved projects expire in 7 days."
- "You'll lose access to N trained models."
- "Your chat history resets on the free plan."

**AI specifics:** "Your trained model will be deleted", "Chat history resets", "Prompt templates become unavailable".

**Pitfall:** Faking a loss (claiming deletion that won't happen). This is a dark pattern and destroys trust.

---

## 6. Contrast Effect

**Trigger:** Price shown in isolation, no nearby anchor.
**Action:** Place the price next to a larger one:
- Upsell insurance next to a $1900 cart → $50 reads as "rounding error".
- Yearly plan next to monthly → monthly looks expensive.
- Add-on next to base tier → add-on looks small.

**AI specifics:** "+$5/mo for priority access" next to a $20/mo base looks negligible; the same $5 solo looks expensive.

**Pitfall:** Showing a price solo. The brain pulls out a calculator and computes the yearly cost.

---

## Which principle applies when?

| Screen / element | Primary | Secondary |
|------------------|---------|-----------|
| Onboarding step 1 | Goal Gradient | Reciprocity |
| Empty long form | Smart Defaults | Goal Gradient |
| Result behind signup | Reciprocity | — |
| New account creation | IKEA + Endowment | Reciprocity |
| Paywall / upsell | Loss Aversion | Contrast Effect |
| Pricing page | Contrast Effect | Loss Aversion |
| Booking / cart | Contrast Effect | Reciprocity (preview) |
| Cancel / churn screen | Loss Aversion | Reciprocity (last gift) |

**Rule:** Never apply more than 2 principles to one screen.
