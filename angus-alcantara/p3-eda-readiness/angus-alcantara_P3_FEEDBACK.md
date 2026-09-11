# P3 Feedback — Angus Jullian Alcantara

**Track: P6 · Human Resource — EDA on the branch-month workforce slice**
Graded with Rubric A's *Exploratory analysis & leakage audit* criterion, opened into the four P3 deliverables (charts 35 · leakage audit 25 · base rates & imbalance 15 · signal memo 25). Oral defense is tomorrow; this letter is your last input before it.
**What I reviewed:** your P2+P3 notebook, your completed lab sheet, and your AI-use log — link included, claims checked.

AJ — look at your own trajectory before you read anything else: **2.85 → 3.1 → and now 3.4.** Three submissions, three climbs. And this one did something I've been waiting for since your first feedback letter: I asked you to "show me the zero," and you wrote a cell literally titled **"Show the Zero"** — status counted, claim evidenced. I asked you to validate before minimizing, and your range check walked straight into the −₱950 daily rate waiting in that column. You didn't just read your feedback. You *executed* it. That is the single most professional habit a data analyst can own, and you now demonstrably have it.

## Your score

| Deliverable | Weight | Level (of 4) | Why |
|---|:-:|:-:|---|
| Purposeful exploration & annotated charts | 35% | 4 · Exemplary | This is the best analytical sequence any student has produced this term. You didn't just *say* B07's low tenure was structural — you **proved it with arithmetic**: the month-over-month table showing tenure drifting up by +0.082 to +0.085 per quiet month, which is exactly 1/12 of a year — the calendar itself, aging your proxy. Then you read the negative dips correctly as *hiring events, not resignations*. And your final chart openly tests the naive ranking and overturns it: the retention priority isn't B07 (young), it's **B02 — mature yet sitting at 1.56 years**. You took the question I left in your P2 letter and answered it with evidence. Three charts, all titled, all labeled, all genuinely *read*. Even your empty outlier result is read honestly — "zero rows breach the fences" stated as a finding, not hidden as a disappointment. |
| Leakage audit | 25% | 3.5 | Your Part B hunt went **10 for 10** — all five planted leaks caught, all five clean columns kept, every reason correct. Your own-predictor audit (C2) is systematic and thoughtful, with privacy woven through it. Half a point off for one factual slip: you crowned **RefundsProcessed** the sneakiest for its "near-zero correlation" — but Refunds correlates at 0.61; the near-zero one was **AvgTicket** (r ≈ 0.05). Your *reasoning* about why a low-correlation leak is dangerous was exactly right — you just pinned the medal on the wrong specimen. Precision matters when the panel is listening. |
| Base rates & imbalance | 15% | 3.5 | Both numbers, both correct: B07 at **3.36%** of headcount as your track's imbalance base rate, and the 1.938-year global mean as the floor to beat. Your implication is genuinely sophisticated — small denominators mean noisy rates, so branch size should weight the *confidence* of an alert, and the intervention threshold should follow expected business loss, not a flat cutoff. That sentence carries your P1 threshold and your P2 letter's peso logic forward in one motion. Held from a 4 only because the 1.938 "baseline" is a floor for predicting *tenure* — while your memo says you'll predict *turnover*, which has no measurable target in this data yet. The floor and the target don't point at the same thing. |
| Predictive-signal memo | 25% | 2.5 | Five slots, a number in every one — the discipline held. But slot 5 contains the one real defect of this submission, and I want you to find it yourself before you read on. …Found it? **Your modeling plan lists current-month sick leaves and current-month overtime — the exact two variables your own audit, three cells earlier, excluded as leakage.** Slot 3 even *names* current-month sick leaves as the trap you disqualified. An audit only counts if its verdicts govern the plan; yours convicted two variables and then hired them anyway. One more quiet issue: all five proposed predictors are hypothetical — none exist in the current data — while the one predictor your entire analysis just *proved* matters, **branch age**, sits in `branches.csv` (`OpenedDate`), real and ready, and appears nowhere in your list. |

**Weighted score: 3.4 / 4.0 — Proficient, at the door of Exemplary.** Your strongest submission, on your steepest curve.

## Your AI-use log — audited, and it passed

You gave me the conversation link this time — asked, delivered. I checked your log's claims against the notebook: "No IQR tenure outliers were found" matches your empty result cell exactly, and "kept and flagged B07 as a new-branch master-data anomaly" matches your reading. Your note that you "confirmed privacy review is separate from leakage testing" is the kind of judgment record I want more of — that's a real distinction, correctly drawn. Two upgrades remain for P4 onward: split the session into per-stage entries, and record at least one thing you *rejected* from the model's suggestions. You're one habit away from a textbook log.

## What I want you to keep doing forever

- **Answering feedback in code.** "Show the Zero" as a cell title is the most satisfying thing I've graded this term.
- **Proving structure with arithmetic.** The 1/12-per-month drift calculation turns an intuition into a demonstration. That's the difference between suspecting and knowing.
- **Overturning your own chart.** Your bar chart says B07; your reading says B02, and explains why the chart misleads. A chart plus the honesty about its blind spot is worth ten charts.
- **The honest empty result.** Zero outliers, reported as a finding. Most students would have quietly deleted that cell.

## Two fixes — small hands, big consequences

1. **Make the audit govern the plan.** Rewrite memo slot 5 with your three *keepers* (branch-average commute, prev-month sick leaves, prev-month overtime) — and add the predictor your own analysis crowned: **branch age, computed from `OpenedDate`**, which is real, in hand, and the strongest driver you demonstrated. While you're there, restate the target as something this data can measure (headcount change, or tenure at the branch-month grain) — "turnover" has no rows to learn from yet, by your own famous pivot. Five minutes, and slot 5 stops contradicting slot 3.
2. **Close the loops you opened.** Three threads dangle: the **−₱950 daily rate** you found never entered the cleaning log — found but unrecorded is only half the job (log it: issue → refer to payroll → reason); the **5 NaN EmploymentStatus** values are shown but never read (who are they? say one sentence); and the `dropna()` before your cross-join still doesn't print how many employees survived — the last silent change in an otherwise loud notebook. And fix one typo before tomorrow: your lab sheet says the drift is "+0.85 years per month" — it's **+0.085**. Ten times smaller. Say the wrong one aloud at the Prelim and the panel will pounce.

## Tomorrow

The Prelim oral is where this notebook pays you back. You are walking in with the strongest story in the class: *"My chart says B07 is the priority. It's wrong, and I can prove why — the real risk is B02."* If the panel asks you nothing else, they will ask you to defend that reversal — and you already have, in writing, with arithmetic. Reread your three feedback letters tonight, rehearse "my decision, my reason" once through your cleaning log, and fix slot 5 before you commit.

2.85, 3.1, 3.4. Keep the slope, AJ. See you tomorrow — bring the zero.
