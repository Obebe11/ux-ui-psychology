# Ethics & Pitfalls

How to apply UX psychology without becoming a dark-pattern factory. Read this if you're about to ship something that feels manipulative, or if you're not sure why a "principles-based" redesign isn't converting.

## Ethical Boundary

These principles exist to **reduce confusion and build trust**, not to manipulate. Forbidden:

- **Fake countdown timers** that "reset" on refresh.
- **Fake reviews**, fabricated social proof, bot-generated testimonials.
- **Deceptive design** (dark patterns): "hard to cancel", button swaps, pre-checked paid options.
- **Faked loss** where nothing is actually deleted — e.g., "Your files will be deleted in 24h" when they won't.
- **Spin-the-wheel paywalls** with predetermined "win" outcomes.
- **Confusing trial toggles** designed to trick users into paid opt-ins (Apple started rejecting these in early 2026).

### The guiding heuristic

> **If the user learned exactly how this works, would they feel cheated?**
>
> If yes, don't ship it.

Long-term trust > short-term conversion. Retention and LTV are the metrics that matter — not trial sign-ups. See [`paywall-research.md`](paywall-research.md) for the data behind this.

### Regulatory context

- **EU DSA** (Digital Services Act) — bans dark patterns, manipulative design, and misleading interfaces. Fines up to 6% of global turnover.
- **FTC** (US Federal Trade Commission) — actively enforces against deceptive design, especially in subscription flows and cancellations.
- **Apple App Store** (early 2026) — rejects paywall patterns that rely on confusing trial toggles.

---

## Common Pitfalls

### 1. Applying all 6 principles to one screen

Overload creates chaos. Pick 1–2 relevant to the task:
- Form → Smart Defaults
- Paywall → Loss Aversion + Contrast
- Onboarding step 1 → Goal Gradient + Reciprocity

### 2. Starting onboarding at 0% progress

Even a token first step (account created = 1/5 = 20%) gives a measurable completion boost.

### 3. Asking for email/signup before the first value

The most common drop-off cause on AI-product landing pages. Always give a partial result first (Reciprocity).

### 4. Positive framing on paywalls

"Unlock PRO" is weaker than "without PRO you lose N". Loss pain is ~2× stronger than gain joy.

### 5. Price solo, with no anchor

The brain pulls out a calculator and computes the yearly cost — always show context. $5 next to $20 reads as small; $5 solo reads as expensive.

### 6. Dark patterns dressed up as psychology

Fake timers and false losses destroy trust and fall under regulation (EU DSA, FTC, Apple App Store Review).

### 7. Beautiful paywall ≠ high-converting paywall

The Mobbin study found that "ugly" paywalls with a ton of text can outperform polished ones. Don't optimize for aesthetics; optimize for clarity of the internal question.

### 8. Single-page paywall defaulting

Multi-page paywalls almost always beat single-page. Unfold information gradually.

### 9. Too many pricing options on the base paywall

Never show more than 2 options on the base paywall. Hide the rest behind "View all plans" to reduce cognitive load.

### 10. Ignoring the lifecycle

A paywall is a flow, not a screen. The decision to pay often happens before the user sees the paywall — so invest in onboarding, value delivery, and timing.

---

## Verification Checklist

Run this before shipping any UI change:

- [ ] Each screen has been checked against relevant principles (not necessarily all 6).
- [ ] No multi-step flow starts at 0% progress.
- [ ] No signup asks for email before the user has received at least partial value.
- [ ] Form fields are pre-filled where it makes sense.
- [ ] Paywall is framed with loss where appropriate and **truthful**.
- [ ] Upsell prices are shown next to an anchor.
- [ ] No fake timers, no fabricated social proof, no deceptive losses.
- [ ] No more than 2 pricing options visible on the base paywall.
- [ ] Multi-step paywall flows unfold information gradually.
- [ ] Cancellation flow is as easy as subscription (ClassPass anti-pattern: 17 screens to cancel vs <5 to subscribe).
- [ ] The guiding heuristic passes: "If the user learned how this works, would they feel cheated?" → No.
