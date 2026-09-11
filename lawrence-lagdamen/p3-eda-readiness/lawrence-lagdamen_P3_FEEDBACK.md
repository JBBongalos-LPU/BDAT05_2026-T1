# P3 Feedback — Lawrence Lagdamen

**Track: P7 · Operations — EDA on the branch-month order counts**
Graded with Rubric A's *Exploratory analysis & leakage audit* criterion, opened into the four P3 deliverables (charts 35 · leakage audit 25 · base rates 15 · signal memo 25). Oral defense is tomorrow; this letter is your last input before it.
**What I reviewed:** your P3 notebook, your completed lab sheet, and your AI-use log — four entries, checked line by line.

Lawrence — twice I've written you the same sentence: *your craft is the strongest in the room, and the telling holds you back.* 2.9 on P1. 2.9 on P2. I asked you to give your notebook its voice, and this week you did — Discussion before every cell, a Reading after every output, twenty-six cells that read like analysis instead of a script. And the number moved: **3.6.** Not because the code got better — it was always good — but because for the first time, the thinking is *on the record where the panel can see it.* That plateau you were standing on for a month? You just stepped off it, upward.

## Your score

| Deliverable | Weight | Level (of 4) | Why |
|---|:-:|:-:|---|
| Purposeful exploration & annotated charts | 35% | 3.5 | Three charts — histogram, branch time-series, branch comparison — every one titled, labeled, and honestly read. Your univariate reading is quietly excellent: skewness 0.10, so "the mean is a reasonable summary — but predicting only the average would still miss the 34-to-182 spread." That is precisely the right two-sided verdict, and I verified your numbers: 97.72 × 108 = 10,554 — your mean reconciles *exactly* with the clean transaction count. What holds this at 3.5 is one rigor gap you'll want to fix before the panel finds it: your headline seasonal claim — "December runs 32% above average" — rests on **a single December**. Your data spans Jan 2025–Jun 2026, so December appears once; a pattern seen once is a *candidate* for seasonality, not yet a "repeating" one. And there's a circle hiding in your outlier ruling: you kept B01-December-182 *because* "December already shows a seasonal increase" — but that December average is itself partly *made of* this very row. The KEEP verdict is right; the reasoning chases its own tail. Say "consistent with a promising but once-observed pattern — confirm when the second December arrives" and both problems dissolve. |
| Leakage audit | 25% | 3.5 | Your Part B hunt went **10 for 10** — all five liars caught, all five keepers kept, every reason correct and in your own words. Your own-predictor audit is the more interesting one: you didn't just recycle your P1 list, you *added the predictors your EDA discovered* — BranchID, MonthNo, PrevMonthOrders — which is exactly how an audit and an exploration are supposed to feed each other. Two soft spots: an audit where **all six candidates pass** never stress-tested a temptation (your P1's real danger — same-month staffing or stockout actuals — never appeared in the dock), and your "sneakiest leak" pick (QuarterRevenueTotal) is defensible but wasn't the designed answer: **AvgTicket, correlating at just 0.05 with the target**, was the trap built to prove that leakage has nothing to do with correlation strength. You reasoned about sneakiness correctly — you just never ran the correlation matrix that would have shown you which leak *looks* most innocent. |
| Base rate & imbalance | 15% | 4 · Exemplary | Textbook. The exact assigned metric (quietest ÷ busiest = 34/182 = **18.7%**), both rows named (B06 July 2025; B01 December 2025), and the implication stated the way an operations manager needs it: a flat forecast would smear a five-fold demand gap into one number. Nothing to add. |
| Predictive-signal memo | 25% | 3.5 | The best-constructed memo in the class, and I want you to know why: **your slot 5 uses only predictors your own audit approved** — BranchID, MonthNo, PrevMonthOrders — predicting a target that actually exists in your data, one month ahead. Audit convicted, plan obeyed. That coherence is rarer than you'd think (ask no one in particular). Numbers in all five slots, the trap named with its reason, the reader addressed. Half a point back for slot 4: the sheet asks what your model must *beat*, and "account for the 18.7% ratio" is a spread to explain, not a floor to beat. Your actual floor was sitting in your P2 letter, dared and waiting: the **3-month moving average** per branch. You never computed it. Naive last-month, or that moving average, is the number your Week 6 model gets measured against — walk into the Prelim with it and slot 4 completes itself. |

**Weighted score: 3.6 / 4.0 — the highest P3 in the class.** Arc: 2.9 → 2.9 → 3.6. The craft was never the question, Lawrence. The telling was — and this notebook answers it.

## Your AI-use log — audited, and it's the best log I've received

Four entries, one per stage — exactly the granularity I asked for. Two *corrections* on the record: the `FileNotFoundError` you diagnosed and fixed, and the runtime reset you recovered from. And every claimed number — 108 rows, 97.72, the December 129, B01's 142.89, the 18.7% — **checks true against your notebook**. This is what supervised AI use looks like when it grows up. One item still missing, and I'll keep asking: the **shared conversation link**. Your prose summary is honest and useful, but a summary is your account of the conversation; the link *is* the conversation. AJ's log carries one — match him next time and your log is complete.

## What I want you to keep doing forever

- **The voice.** Twenty-six cells, every output read. Your notebook finally sounds like the analyst who wrote your lab sheets all along.
- **EDA feeding the audit feeding the plan.** Discover BranchID matters → audit it → model with it. That closed loop is the whole predictive workflow in miniature, and you ran it without being told to.
- **Verifiable numbers.** Your mean reconciled to the transaction count to the row. When a grader can re-derive your figures, trust compounds.
- **Recovering in public.** The path error and the runtime reset are *in the log*, not hidden. Professionals document their stumbles; students hide them. You chose right.

## Two fixes — both are Prelim armor

1. **Soften the single-December claim before the panel does it for you.** Reword slot 2 and your A3 answer: *"December 2025 ran 32% above the overall average — a promising seasonal candidate, observed once; the second December confirms or kills it."* And untangle the outlier circle: keep B01-Dec-182 because it's *plausible and consequential*, not because December is "already seasonal." Ten minutes of editing, and the two most attackable sentences in your submission become two demonstrations of statistical maturity.
2. **Compute your floor tonight.** Three lines: `p3.groupby("BranchID")["OrderCount"].rolling(3).mean()` (shifted one month) — the moving-average baseline you promised in P1 field 11 and were dared to bring in your P2 letter. Put its error next to naive-last-month. Then slot 4 says something no one else's will: *"my model must beat a 3-month moving average that is already within X orders on a typical branch-month."* You'd be the first student in the course's history to arrive at modeling week with the baseline already scored.

## Tomorrow

Your oral story is coherence: *one slice, promised in P1, built and counted in P2, interrogated in P3 — and a model plan that uses only what survived the audit.* If the panel presses you anywhere, it will be December — so disarm it first, on your own terms, using fix 1. Reread your three letters tonight; rehearse "my decision, my reason" through your cleaning log once, aloud.

2.9, 2.9, 3.6. The plateau is behind you. See you tomorrow — bring the moving average.
