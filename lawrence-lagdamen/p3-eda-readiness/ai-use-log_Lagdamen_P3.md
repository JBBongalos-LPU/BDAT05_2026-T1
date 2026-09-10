# AI Use Log — Lawrence Lagdamen

Every graded submission carries its entries here. Honest logs are never penalised; absent or false logs are. Tier definitions are in the syllabus (Section X-A).

| Date | Tool | Purpose | What was produced | How I verified / changed it | Tier |
|---|---|---|---|---|---|
| 2026-09-03 | ChatGPT | Vibe coding | Colab/Pandas code for the Session 3 lab, including data inspection, joins, validation, cleaning, branch-month aggregation, and CSV export. | Ran the code in Colab, checked the outputs and errors, corrected the Date dtype mismatch, and verified the final branch-month table had 108 rows. | Tier 3 |
| 2026-09-10 | ChatGPT | P3 exploratory analysis | Colab/Pandas code for reloading the P2 slice, checking the OrderCount distribution, monthly patterns, IQR extremes, and branch-level differences. | Ran each code block in Colab and checked the outputs. Verified 108 rows, mean OrderCount of 97.72, December average of 129 orders, and B01 as the highest-average branch at 142.89 orders. | Tier 3 |
| 2026-09-10 | ChatGPT | Leakage audit | Code and explanations for applying the day-1 calendar test to the supplied leak dataset and my P7 candidate predictors. | Reviewed each predictor based on whether it could actually be known before the prediction month. Corrected the file path for `hunt_the_leak.csv` after the first path produced a FileNotFoundError. | Tier 3 |
| 2026-09-10 | ChatGPT | Base rate and signal memo | Code for the quietest-to-busiest branch-month ratio and wording for the five-sentence predictive-signal memo. | Verified B06 July 2025 had 34 orders and B01 December 2025 had 182 orders, giving a quietest-to-busiest ratio of 18.7%. | Tier 3 |

**P3 ChatGPT conversation:**

## P3 AI Assistance Summary — Lawrence M. Lagdamen

For my **BDAT05 P3 — Exploratory Data Analysis** activity under **P7 Operations**, I used ChatGPT as a Tier 3 coding and analysis assistant while completing the work myself in Google Colab.

ChatGPT helped me draft and explain Python/Pandas/Matplotlib code for reloading my validated P2 branch-month dataset, checking the distribution of `OrderCount`, measuring mean, median, and skewness, examining monthly demand patterns, applying the IQR rule for extreme values, comparing average demand across branches, conducting leakage audits, calculating the quietest-to-busiest base-rate ratio, and drafting the required five-sentence predictive-signal memo.

I ran the code myself in Colab and checked the outputs before using them. Key verified results included **108 branch-month rows**, mean `OrderCount` of **97.72**, median of **94.50**, skewness of **0.10**, a December average of **129 orders**, B01 averaging **142.89 orders per month**, B06 averaging **49.33**, and a quietest-to-busiest ratio of **18.7%**.

For the leakage exercise, ChatGPT helped apply the question **“Could Kape Tayo actually know this value on day 1?”** to each predictor. I reviewed the classifications myself and retained only predictors that would be available before the target month.

I also corrected AI-generated work when necessary. In particular, an initial path for `hunt_the_leak.csv` caused a `FileNotFoundError`, so I located the file in Google Drive, corrected the path, and reran the code successfully. A later Colab runtime reset also required me to reload the P2 dataset and re-import Matplotlib before rerunning the histogram.

The final interpretations, charts, leakage decisions, base-rate calculation, and signal memo were based on the outputs I personally ran and verified in Colab.

