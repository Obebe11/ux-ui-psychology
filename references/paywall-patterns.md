# Paywall Patterns — Actionable Triggers

When you see a paywall or subscription screen, apply these triggers in order. Each entry has a **trigger** (what to look for) and an **action** (what to change).

## Screen-level triggers

### Trigger: Paywall appears cold (no value delivered yet)
- **Action:** Insert a value-delivery screen *before* the paywall. Show the user's personalized outcome (e.g., "You're about to reclaim 8 years of your life", "Here's your first AI-generated summary").
- **Why:** Users who haven't received value yet have no reason to pay.

### Trigger: Progress bar starts at 0%
- **Action:** Count the user's first action (account creation, first click, first input) as step 1. Show progress ≥ 20% from the first screen.
- **Never:** Start any multi-step flow at 0%.

### Trigger: Single-page paywall
- **Action:** Split into a multi-page flow. Unfold information gradually: value → social proof → pricing → CTA.
- **Why:** Users process decisions better when not forced to absorb everything at once.

### Trigger: Only one pricing option visible
- **Action:** Add a second, more expensive option (yearly next to monthly, premium tier next to base). Anchor the user to the higher price.
- **Limit:** Never show more than 2 options on the base paywall. Hide extras behind "View all plans".

## CTA triggers

### Trigger: CTA says "Subscribe" or "Continue"
- **Action:** Replace with a specific, low-commitment verb:
  - "Subscribe" → "Start my free trial"
  - "Continue" → "Start my free week"
  - "Unlock" → "Try PRO free for 14 days"

### Trigger: No "Cancel anytime" reassurance
- **Action:** Add subtitle under CTA: **"No commitment. Cancel anytime."**

### Trigger: Plain CTA button
- **Action:** Add a right chevron `›` at the end of the CTA text.

### Trigger: Cancel button next to CTA
- **Action:** Add an **exit-intent sheet** — when the user taps cancel, offer a cheaper plan (monthly instead of yearly) rather than full cancellation.

## Trial triggers

### Trigger: Free trial offered without timeline
- **Action:** Add a visible **trial timeline**: today → day-5 (reminder) → day-7 (charge). State explicitly: "We'll remind you before your trial ends".

### Trigger: Short trial (7 days or less)
- **Action:** Test extending to 14 days. Longer trials reduce perceived risk and outperform on yearly plans.

### Trigger: Trial on all plans equally
- **Action:** Restrict the trial to the **yearly plan only**. This filters for high-intent users and lifts LTV.

### Trigger: Trial starts without payment method
- **Action:** Consider requiring a credit card upfront. Sign-ups will drop, but paying-user conversion typically increases. Use this only if your funnel can tolerate lower top-of-funnel volume.

## Pricing triggers

### Trigger: Price shown as a range ("$13–17")
- **Action:** Replace with a single fixed price per tier. The brain anchors on the maximum of the range and perceives overpayment risk.

### Trigger: Price shown in isolation (no comparator)
- **Action:** Anchor against a larger number:
  - Break into weekly cost: "$3.50/week" instead of "$15/month"
  - Compare to a daily expense: "Costs less than a coffee"
  - Show struck-through old price next to current

### Trigger: Plan benefits listed as abstract features ("PRO features")
- **Action:** Show concrete side-by-side outputs of free vs PRO. For AI products: actual model responses, not feature lists.

## Framing triggers

### Trigger: Offer framed as a gain ("Get PRO features")
- **Action:** Reframe as a loss: "Without PRO, your [saved projects / trained models / history] will be [deleted / reset / unavailable] in N days."

### Trigger: No social proof
- **Action:** Add real reviews + 5★ rating near the CTA.

### Trigger: Feature described technically ("OCR engine, 99.2% accuracy")
- **Action:** Reframe as a user outcome: "Turn a PDF into Excel in 30 seconds".

## What never to do

- **Spin-the-wheel paywalls** — predetermined Lottie animation "awards" of a discount.
- **Fake countdown timers** that reset on refresh.
- **Fake reviews** or fabricated social proof.
- **Confusing trial toggles** designed to trick users into paid opt-ins.
- **Aggressive last-minute discounts** outside of Black Friday / Cyber Monday.
- **Hard-to-cancel flows** — cancellation should take the same number of steps as subscription.

## Verification

After applying patterns, check:
- [ ] Progress bar starts at ≥ 20%, never 0%.
- [ ] CTA uses a specific verb, not "Subscribe" or "Continue".
- [ ] "No commitment. Cancel anytime." subtitle is present.
- [ ] Trial timeline is visible with explicit reminder promise.
- [ ] At most 2 pricing options on the base paywall.
- [ ] Price has an anchor (weekly breakdown, comparator, or struck-through old price).
- [ ] No fake timers, fake reviews, or spin-the-wheel patterns.
