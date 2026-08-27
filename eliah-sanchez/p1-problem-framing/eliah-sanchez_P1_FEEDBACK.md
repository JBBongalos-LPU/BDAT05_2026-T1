# P1 Feedback — Eliah Therrien Sanchez

**Anchor: Financial / CFO** · Graded with the P1 rubric (Assignment Sheet v2), which operationalizes CILO 1
**Scope of this review:** anchor canvas.

## Score

| Criterion | Weight | Level (of 4) | Basis |
|---|:-:|:-:|---|
| Target & unit precision | 30% | 3 · Proficient | Your unit of analysis — **"product-year: one row of the total revenue of a product for a year"** — is the crispest field 5 in the class. The row concept has landed. Held back by an inconsistency: field 1 says revenue *per product*, field 3 says revenue for *Kape Tayo as a whole* — pick one and carry it through every field. |
| Decision linkage | 25% | 3 · Proficient | The CFO's budget-planning role is clear, and field 8 is a *real* action: invest more in high-revenue products, cut spending on low ones. The prediction genuinely changes what the CFO does. |
| Success & cost of error | 25% | 2.5 | Field 10 is strong — both directions with concrete consequences (over-predict → over-spend on a product; under-predict → stockouts of its ingredients). But field 9 ("10% growth from last year") is a *goal for the business*, not a measure of *forecast quality* — a forecast can be perfectly accurate about a bad year. Separate the two. |
| Baseline & feasibility | 10% | 2 · Developing | "Last year's revenue" is the right baseline. The catch is feasibility: with ~18 months of history, a *product-year* unit gives you roughly **one row per product** — far too few rows to model. Shrink the grain (product-*month* gives you ~18 rows per product) and the same idea becomes buildable this term. |
| Clarity & reader fit | 10% | 3 · Proficient | Clean, readable, CFO-appropriate language throughout. |

**Weighted score: 2.8 / 4.0 — approaching Proficient.** Counted inside the laboratory/P1 component of your Prelim grade; revisable under the portfolio policy — and this canvas is the seed of your Week 8 case report, so the fixes below are an investment, not a correction.

## What worked — keep doing this

- **"Product-year" as one row** — you did exactly what the Studio asked: named the row. That skill is the hardest one in framing and you have it.
- **A real allocation decision** in field 8: the CFO does something different depending on the number. Many professionals never get this far.
- **Both error directions with business consequences** — over-spend versus stockout. Add pesos and a "which is worse" call and field 10 is Exemplary.
- Field 12 shows the right instinct: aggregate revenue data needs no customer names.

## Two fixes, in order

1. **Resolve the grain — and shrink it.** Decide: per product, or company-wide? (Per product matches your field 8 action, so keep that.) Then change the window from year to **month**: *"total revenue per product per month, predicted 3 months ahead"* keeps your whole framing intact while giving the model enough rows to learn from. This is the difference between a beautiful idea and a buildable one — the Case 3 lesson, in your own canvas.
2. **Split the goal from the gauge.** Keep "10% growth" as the CFO's *target*. Then add a separate line for forecast quality in money terms: e.g., *"monthly product forecasts within ±10% of actuals, so budget allocations are wrong by no more than ₱X across the year."* One number for ambition, one for accuracy — the CFO needs both, and needs to know which is which.

Watch one predictor too: "yearly sales" as an input to predicting yearly revenue is the same number wearing two hats — use *last* period's sales (a lag), never the same period's.

## Where this goes next

In Session 3 you will compute revenue-per-product-per-month from the actual sales and products tables — and discover firsthand how many rows your chosen grain really yields. That discovery *is* P2. Bring this canvas on Saturday.
