# A/B-Test Patterns — Trigger → Action

Three concrete UI patterns derived from real A/B tests. Each has a **trigger** (when to apply) and **actions** (what to change). Apply them when the screen type matches.

## Meta-rule

**Every UI element poses an internal question to the user. The simpler the question, the higher the conversion.**

Before redesigning any screen, audit each element: what internal question does it raise? Can it be simplified?

---

## Pattern A. Paywall

**Trigger:** Subscription / paywall screen.

**Actions:**
1. **Reframe the core question.** Replace "Is this worth $19?" with "Do I want to try it free?". Achieve this by:
   - Leading with the free trial, not the price.
   - CTA: "Start my free trial" instead of "Subscribe".
2. **Add a trial timeline.** Show: today → day 5 (we'll remind you) → day 7 (charge). State the reminder promise explicitly.
3. **Replace abstract graphics with real screenshots.** Show actual content the user will get.
4. **For AI products:** show concrete free-vs-PRO output examples side-by-side, not "premium features" lists.

For deeper paywall triggers, see [`paywall-patterns.md`](paywall-patterns.md).

---

## Pattern B. Ride Hailing (and any price-range screen)

**Trigger:** Price displayed as a range, OR price shown without context.

**Actions:**
1. **Replace price ranges with a single fixed price per tier.** The brain anchors on the maximum of the range and sees overpayment risk.
2. **Add convenience context next to the price:** pickup time ("2 min away"), delivery estimate, availability status. This shifts focus from cost to convenience.
3. **Add a decision-making badge:** "Cheaper", "Fastest", "Best value" — takes the decision off the user's shoulders.

**AI specifics:** Don't show "$0.05–0.50 per request" — the user anchors on the max. Use a fixed package price or the average cost of a typical session.

---

## Pattern C. Booking (and any emotional-decision screen)

**Trigger:** Booking, travel, experience, or any screen where the user makes an emotional (not purely transactional) decision.

**Actions:**
1. **Make the hero visual dominant.** Photo on half the screen or larger. Small thumbnails kill emotion.
2. **Replace factual titles with emotional copy.** Not "Beach house with garden" → "Coastal escape, steps from the sand". Sell the feeling, not the spec sheet.
3. **Show the struck-through old price** next to the current one (visible saving).
4. **Replace calendar dates with weekdays** when it helps visualization: "Friday – Wednesday" beats "Jul 12–15".
5. **Show the full total upfront** — no hidden fees. Transparency removes the fear of being nickeled-and-dimed.

**AI specifics:** An AI product landing often reads like API documentation. Reframe as a concrete user outcome: "Turn a PDF into Excel in 30 seconds" beats "OCR engine with 99.2% accuracy".

---

## How to apply these patterns

1. **Identify the screen type:** paywall / price display / emotional decision / something else.
2. **Find the matching pattern above.**
3. **For each element on the screen, ask:** what internal question does this raise? Can it be simplified?
4. **Apply the corresponding actions** until no heavy question remains.
5. **Cross-check with [`principles.md`](principles.md)** to confirm the underlying principle (Loss Aversion, Contrast Effect, Reciprocity) is correctly applied.
