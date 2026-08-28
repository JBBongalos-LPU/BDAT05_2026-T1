# P1 Feedback — Angus Jullian Alcantara

**Anchor: Human Resource / HR Manager** · Graded with the P1 rubric (Assignment Sheet v2), which operationalizes CILO 1
**Scope of this review:** anchor canvas (received 28 Aug — see the late-policy note under the score).

## Score

| Criterion | Weight | Level (of 4) | Basis |
|---|:-:|:-:|---|
| Target & unit precision | 30% | 3 · Proficient | Field 4 is the best-defined target in the class: **"voluntary resign (resigned=1, stayed=0) over the next 90 days from the start of prediction"** — binary, measured, windowed. You are also the **only student who framed a classification problem**; everyone else forecast a number. Held back by field 5: "one single employee at a time" names the unit but not the row — for churn, one row = *one employee as of a prediction date*, and that snapshot idea matters the moment you build the table. Predictors: 3 named where the spec asks 4–8. |
| Decision linkage | 25% | 3 · Proficient | Field 1 is closer to a real decision than most of the class managed: *who gets the intervention* is a genuine recurring choice. Field 8 is the only one in the class with an explicit **threshold**: ≥75% likelihood → stay interview + schedule fix. That is exactly how classification predictions drive action. The register is casual ("a friendly chat"), but the mechanics are right. |
| Success & cost of error | 25% | 3 · Proficient | You are the only student who costed **both** directions *and* made the call: false alarm = manager time, miss = hire-and-train a replacement, "so miss is a huge deal." That is the complete field 10 structure the whole class missed. What's absent is the number: "a lot of money" is not defensible in a review — pesos are (see fix 1). Field 9's "stop at least 2 resignations" is a real business-unit criterion. |
| Baseline & feasibility | 10% | 2.5 | "Assume everyone stays" is the textbook **majority-class baseline** — correct, and harder to beat than it sounds (it is right most of the time, which is the class-imbalance lesson waiting for you). Feasibility is silent, though, and for your track it bites: how many employees does Kape Tayo have, and how many actually resigned in 18 months? A classifier learns from the resignations — count them before promising the model. |
| Clarity & reader fit | 10% | 2 · Developing | The thinking is sound; the language undersells it. Grammar slips ("who will likely to voluntary resign," "If the we predict") and a conversational register would make an HR Manager take this memo less seriously than it deserves. This mirrors your diagnostic profile exactly: strongest quantitative instincts in the room, business language still catching up. |

**Raw weighted score: 2.85 / 4.0.** Received six days after the 22 Aug deadline; under §IX-C the −10%/calendar-day deduction caps at 3 days (−30%): **recorded score 2.00 — Developing.** The portfolio policy still applies: this canvas is revisable, and since it seeds your Week 10 case report, every fix below pays twice. Expect a brief oral walk-through on Saturday — per the house rules, be ready to explain any field without notes.

## What worked — keep doing this

- **You framed the class's first classification problem.** Everyone else asked "how many"; you asked "which ones" — and probability, threshold, and action all line up correctly. This is the shape your P6 attrition case needs, and you found it unprompted.
- **The threshold action.** "≥75% → stay interview" is precisely how a churn score becomes a decision. Most professionals write "monitor closely"; you wrote a trigger.
- **Both error directions, with the call made.** The asymmetry argument (replacement cost ≫ interview time) is the right one for retention problems.
- **Majority-class baseline** — technically the correct dumb guess for a classifier, chosen without being taught it.

## Two fixes, in order

1. **Put pesos on the loop.** Three numbers turn this canvas from casual to defensible: what does replacing one barista cost (hiring + training + the weeks of lower productivity)? What does one stay interview cost (roughly an hour of the HR Manager's time)? And therefore the ratio — if a miss costs ~₱25–40k and a false alarm ~₱300, misses are on the order of **100× worse**, so your model should deliberately flag generously. Look at the calibration example on your own assignment sheet: its "₱18k vs ₱2.4k, ~7× worse" sentence is the pattern. Your field 9's "a lot of money" becomes a peso figure the same way.
2. **Name the law and your lawful basis.** Field 12 says "there is a law that must be obeyed" — as the HR track owner, you carry the heaviest privacy load in the class, and you need to say the words: **RA 10173 (Data Privacy Act)**, employee data is **sensitive by default**, the lawful basis is legitimate interest in workforce planning, and outputs must never expose an individual's risk score beyond the HR Manager. On Saturday your track is the worked example in the privacy clinic — this paragraph, done properly, is the exemplar the class reads.

One more row worth a sentence: **count your positives before you promise the model.** With a workforce of Kape Tayo's size, 18 months may hold only a handful of voluntary resignations — possibly too few rows-with-a-1 to train on this term. That is not a reason to abandon the framing; it is a reason to say so in field 12 (scope honesty), and to know your fallback: widen the window, or predict at an aggregate grain first. Your P2 slice — branch-month workforce — is exactly where you will find out. Also expand field 7 to 4–8 predictors (tenure, schedule volatility, wage vs market, branch, recent shift changes) and flag anything knowable only after a resignation letter as leakage.

## Where this goes next

In Session 3 you build the branch-month workforce table from the employees file and run the validation checks on it — that work *is* P2, and your lawful-basis paragraph (fix 2) is due inside it. File this canvas in your repo as `p1-problem-framing/` per the folder README (note: your submitted file was labeled "P3HR" — the framing project is P1; P3 is Week 4's EDA). Bring the canvas Saturday.
