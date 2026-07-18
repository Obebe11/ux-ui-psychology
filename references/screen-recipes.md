# Screen Recipes

Ready-to-use sequences for the most common UI screens. Each recipe picks 1–2 principles from [`principles.md`](principles.md) and incorporates patterns from [`ab-test-patterns.md`](ab-test-patterns.md) and [`paywall-research.md`](paywall-research.md).

## Onboarding for a new AI product

1. Don't start the progress bar at 0% (Goal Gradient).
2. On step one, give an action with value: create the first assistant / generate a preview (Reciprocity + IKEA).
3. Pre-fill defaults from locale/source (Smart Defaults).
4. Ask for email only after the first result (Reciprocity).

## Data / settings form

1. Pre-fill every field that can be pre-filled (Smart Defaults).
2. Split into 2–3 field steps, progress starts at >0% (Goal Gradient).
3. On the final step, show what the user gets right after submit (Reciprocity).

## Paywall / upsell

1. Place a more expensive plan or add-on next to the main price (Contrast Effect).
2. Frame with loss: what disappears without the subscription (Loss Aversion).
3. A free tier with a partial result as the entry point (Reciprocity).
4. **Add "No commitment. Cancel anytime." subtitle** — reliably lifts conversion (Mobbin study).
5. **Use multi-page flow** — outperforms single-page; unfolds information gradually.
6. **Preselect yearly + 14-day trial** — best LTV + lowest perceived risk (Headspace A/B winner).
7. **Consider credit-card-required trial** — sign-ups drop, but paying users can more than double (Outsider: 5× conversion).

## Booking / cart

1. Show the total (with fees) upfront — transparency removes fear (Reciprocity).
2. Display the struck-through old price next to the current one (Contrast Effect).
3. Use emotional copy and a hero image — sell the feeling, not the spec sheet.
4. Replace calendar dates with weekdays when it helps visualization (Goal Gradient: feels closer).

## Landing page (AI product)

1. Lead with a concrete outcome, not a model spec — "Turn a PDF into Excel in 30 seconds" beats "OCR engine with 99.2% accuracy".
2. Give a partial free result before asking for signup (Reciprocity).
3. Anchor the price against a more expensive option or a daily cost (Contrast Effect).
4. Show real output examples side-by-side: free vs PRO (transparency).

## Cancellation / churn screen

1. Offer a downgraded plan (monthly instead of yearly) via exit-intent sheet (Loss Aversion + Reciprocity).
2. Remind the user what they lose — concretely: saved projects, trained models, history (Loss Aversion).
3. Avoid dark patterns: no "hard to cancel" navigation, no pre-checked options. Trust > short-term retention.

## Empty state / first-run

1. Show a partial result or sample content immediately (Reciprocity).
2. Pre-fill the first input or seed the account with defaults (Smart Defaults).
3. Count this first run as step 1 of onboarding — progress > 0% (Goal Gradient).

## Notification / email subject line

1. Frame opening as preventing a loss ("Your X will expire in 24h") over gaining ("New feature available") (Loss Aversion).
2. Be specific about what's inside — "3 new matches waiting" beats "You have updates" (Reciprocity).
3. Avoid fake urgency words ("URGENT", "LAST CHANCE") unless literally true — trust erosion is permanent.

## How to combine recipes

- For complex screens (e.g., a paywall reached after onboarding), chain recipes: Onboarding → Paywall.
- Each recipe should add at most 1–2 principles to the screen. More is overload.
- When two principles conflict (e.g., Reciprocity vs. Loss Aversion), pick the one that matches the user's emotional state at that step.
