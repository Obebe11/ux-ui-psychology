# A/B-Test Patterns: 3 Redesigns

Three concrete UI redesigns backed by real A/B-test results. Source: [youtube.com/watch?v=zr37ibqXl1U](https://www.youtube.com/watch?v=zr37ibqXl1U).

## Meta-principle

**Every UI element poses an internal question to the user. The simpler the question, the higher the conversion.** ([2:25](https://www.youtube.com/watch?v=zr37ibqXl1U&t=145s))

Before redesigning, run every screen through this check: what internal question does this element raise, and can it be simplified?

---

## Pattern A. Paywall — Variant B won

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

For deeper paywall research (2,995 paywalls study), see [`paywall-research.md`](paywall-research.md).

---

## Pattern B. Ride Hailing — Variant B won

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

---

## Pattern C. Booking — Variant B won

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

## How to use these patterns

1. **Identify the screen type** (paywall / ride-hailing / booking / similar).
2. **Find the closest pattern** above.
3. **Identify the heaviest internal question** your current screen poses.
4. **Borrow the corresponding trick** from the winning variant.
5. **Run the same check on every element** until no heavy question remains.
