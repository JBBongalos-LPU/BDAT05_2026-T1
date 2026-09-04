# P2 Feedback — Lawrence Lagdamen

**Track: P7 · Operations — branch-month order counts**
Graded with Rubric A (the Prelim rubric this work feeds into), using the three criteria P2 covers — framing, data preparation, lawful handling — re-weighted to 100%. EDA and oral defense wait for Week 5.
**What I reviewed:** your notebook, your completed lab sheet (Parts A to C), and your AI-use log.

Lawrence — let me lead with the number, because you earned the right to it: **108.** In P1 you promised a branch-month table of roughly 108 rows, and this week you built it, counted it, and printed the proof — 6 branches × 18 months, exactly as your canvas said. You are the first student in this class whose P1 promise and P2 reality match to the row. That's not luck; that's what happens when the frame was right to begin with.

## Your score

| Criterion | Weight | Level (of 4) | Why |
|---|:-:|:-:|---|
| Problem framing & decision use | 33% | 2.5 | The grain promise was kept perfectly — and your C1 sentence says exactly why the count is right. What's missing is the frame *itself*: your notebook never states the decision this table serves. Nowhere does it say "each month, the Operations Manager decides stock and staffing, and this table is how she'll know demand." I know it — because I graded your P1. But a notebook has to stand without me in the room, and right now yours opens with a mount command instead of a reason. Your classmate's opened with a frame table; steal that move shamelessly. |
| Data preparation & documentation | 42% | 3.5 | Here is where I want to stop and applaud, because **your cleaning is the best technical work anyone did this week.** You found *everything* the sales table was hiding — the 12 dateless rows, the 4,775 missing CustomerIDs, the 23 duplicate SaleIDs, and the six misspelled BranchIDs that were quietly stealing 40 rows in the join. And then you made the move that separates analysts from row-deleters: **you repaired the dirty IDs instead of dropping them** — strip, uppercase, de-hyphen — and forty real transactions walked back into the dataset. Your calendar fallback (derive the month from the sale date when the calendar has a hole) shows the same instinct: rescue the data, don't discard it. Counting orders with `nunique` so duplicates can't inflate the total? Chef's kiss. Your four-entry cleaning log has a reason on every line, and you validated twice — raw and final. What kept this from a 4: your code makes changes it never *counts*. How many rows did `drop_duplicates()` remove? How many dateless rows fell out of the slice? Your log names the decisions; your notebook must print the numbers. Nothing changes silently — including the fixes we're proud of. |
| Lawful & ethical data handling | 25% | 2.5 | Your paragraph gets the core argument right: the output is BranchID, YearMonth, OrderCount — no person is identifiable, and aggregation is the protection. Good. But Lawrence, I flagged this exact row in your P1: the law has a name — **RA 10173** — and for the second submission running, it doesn't appear. And one thing your paragraph doesn't see: the *output* is clean, but the *input* you handled contains CustomerID — pseudonymous, which our privacy drill rated amber: still personal data. One sentence acknowledges it: "the raw sales data contains customer identifiers, which are excluded from all outputs by aggregation." Say the law, name the amber, and this criterion jumps. |

**Weighted score: 2.9 / 4.0 — approaching Proficient**, and the same 2.9 as your P1, which tells a story worth hearing: your *craft* is consistently the strongest in the room, and what holds you at 2.9 both times is the *telling* — the frame, the narrative, the law's name. The gap between you and a 3.5 isn't skill. It's paragraphs.

## Your AI-use log — I read it closely, and I want you to know what I saw

Your log says "Vibe coding," names ChatGPT, declares Tier 3, and claims you "corrected the Date dtype mismatch and verified the final table had 108 rows." **I checked those claims against your notebook, and they're true** — the dtype fix is right there in your cells, and the 108 is printed twice. An honest log that matches the work: that's exactly what the policy exists to produce, and I'm genuinely pleased. Three upgrades for next time. First, the template asks for the **shared conversation link** — yours has none, and the link is what makes the log auditable rather than merely believable. Second, one blanket entry for the whole session hides your actual supervision — split it by stage (load, clean, aggregate). Third, record at least one thing you *rejected* — your notebook converts the Date column twice in two different cells, which tells me you assembled chunks from the chat without pruning; the pruning decision belongs in the log too. A log that only ever accepts is a log that isn't supervising yet.

## What I want you to keep doing forever

- **Repair before delete.** The BranchID fix recovered forty transactions someone else would have shrugged away. That habit will save a real company real money someday.
- **Verify your own promise.** 108 counted, not assumed — and re-validated after the build. This is the "count your rows" discipline, fully internalized.
- **Belt and suspenders.** Deduplicate *and* count with `nunique`. You didn't trust one safeguard to hold. Correct.
- **The resourceful load.** Your glob search for the workbook was clever problem-solving (one note: the BDAT05 class files are the CSVs on the Drive — use those going forward so your notebook runs on the canonical sources P3 will assume).

## Two fixes — and I'm asking because the hard part is already done

1. **Give your notebook its voice.** Every interesting thing you discovered lives on your *lab sheet* — in your handwriting, in your own words, and they're good words ("they may have formatting issues" was the correct diagnosis before you'd even confirmed it). But the repo record — the thing the Prelim panel reads — is currently a script with one paragraph at the end. Bring the Discussion → Code → Reading rhythm in: a sentence of *why* before each cell, a sentence of *what the output says* after. You already did the thinking. Now let the notebook show it. P3 will be graded as analysis, not as code — I'm telling you now so nothing surprises you.
2. **Print what you change, and name the law.** Add `before/after` row counts around your deduplication and your date exclusion — your cleaning log promises it, so make the code deliver it. Then rewrite the privacy paragraph with three additions: RA 10173 by name, the CustomerID-in-the-raw acknowledgment, and one line on retention. Ten minutes, and your weakest criterion becomes a strength.

And your gift for next week, because your table is already whispering it: your OrderCount runs from **34 to 182** — a five-fold spread between your quietest and busiest branch-months. Somewhere in that spread is the answer to the question your whole P1 was built on: *is demand predictable enough to staff against?* And here's the part I love — the baseline you promised in field 11, the 3-month moving average, **you can compute it right now** from this very table, before we've taught you a single model. Walk into Week 4 with your baseline already drawn on a chart, and you'll be the first student in BDAT05 history to arrive at EDA with the score-to-beat in hand.

## Where this goes

This table is the direct input to P3, and it is the spine of your Week 11 operations forecast — the branch-month demand series, already clean, already counted. Make the two fixes as a revision commit ("P2 v2 — narrative & counts") and bring the moving-average chart on Saturday if you take the dare.

Fine work, Lawrence. Now make the notebook talk the way your lab sheet does.
