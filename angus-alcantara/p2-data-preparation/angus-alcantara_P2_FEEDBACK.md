# P2 Feedback — Angus Jullian Alcantara

**Track: P6 · Human Resource — branch-month workforce table**
Graded with Rubric A (the Prelim rubric this work feeds into), using the three criteria P2 covers — framing, data preparation, lawful handling — re-weighted to 100%. EDA and oral defense wait for Week 5.
**What I reviewed:** your notebook + your completed lab sheet, Parts A to C.

AJ — I want to start by telling you plainly: **this is the best work you have produced in this course, and it isn't close.** Two weeks ago I was reading a canvas with strong instincts buried under rushed language. This week I read a notebook that thinks out loud, doubts itself in the right places, and treats other people's data with real respect. That's not a small jump. That's the jump.

## Your score

| Criterion | Weight | Level (of 4) | Why |
|---|:-:|:-:|---|
| Problem framing & decision use | 33% | 3 · Proficient | Your pivot is the most mature analytical act I've seen from this class all term. You went looking for resignations, found none recorded, and instead of forcing a classifier onto data that couldn't carry one, you stopped, said so in writing, and built the honest descriptive baseline instead. That is *exactly* what a professional does. Two things kept this from a 4, and I want you to see both — because they're within your reach. First: the claim your whole pivot rests on ("zero resignations recorded") is never actually *shown* in a cell. I believe you — but belief isn't the standard we hold; evidence is. Second: your frame still promises to catch "thinning headcounts," and here's the catch your own "standing water" sentence almost caught — under a continuous-employment proxy, headcount *cannot* thin. You were one sentence away from seeing it yourself. |
| Data preparation & documentation | 42% | 3 · Proficient | The `header=4` recovery made me smile — you diagnosed before you fixed, exactly the order we practiced. And your **B07 catch is the finding of the week, full stop**: you found an entire branch missing from the master list, investigated it with privacy-safe logic, and then made the *right* call for the right reason — deleting those employees would have quietly erased real people from the headcount. Your data dictionary is complete, your cleaning log has four reasoned entries, and you *counted* your 126 rows instead of estimating them. So why not a 4? Because your raw-column validation had a blind spot, and it cost you: you dropped `DailyRate` before ever range-checking it — and I'll let you in on something: there is a value in that column no payroll on earth produces. One line of code would have caught it. It was waiting for you, and you were *so close*. Also, your `dropna()` removed rows without printing how many — and I know you know better, because your own notebook says "nothing changes silently." Hold yourself to your own sentence; it's a good one. |
| Lawful & ethical data handling | 25% | 3.5 | AJ, this is where you shine now. In P1 I asked you to name the law — and you didn't just name it, you *practiced* it: RA 10173 cited, names and wages stripped with reasons stated, employee data treated as sensitive by default, aggregation argued as protection, and not one individual visible in any output. Even your validation cells were designed privacy-safe. Your lawful-basis statement is the one I want your classmates to read. Half a level from perfect only because the rubric also asks about retention and disposal of the data — one paragraph you haven't written yet. |

**Weighted score: 3.1 / 4.0 — Proficient**, and trending up fast. One more thing that matters to me as much as the score: your AI-use log's *kept/changed* line matches what the notebook actually shows, and your lab-sheet answers are correct and unmistakably in your own voice. You used the machine the way we teach it — as a junior you supervised. I noticed. Keep that.

## What I want you to keep doing forever

- **Stopping when the data says stop.** "Knowing when the data cannot yet carry the model is not a failure of analytics — it *is* analytics." You didn't quote that idea. You lived it, at the exact moment it cost you your original plan. Most professionals never learn this.
- **Investigating before deciding.** B07 could have been silently dropped in one careless line. Instead you asked *who is this?*, kept them, and wrote down why.
- **Privacy as a habit, not a paragraph.** It ran through the whole notebook, not just the statement at the end.
- **The Discussion → Code → Reading rhythm** — you held it for all fifteen steps. Your notebook reads like analysis, not like a script. That was the goal.

## Two fixes — and I'm asking for them because you're ready

1. **Show me the zero.** One small cell: `emp["EmploymentStatus"].value_counts()`, plus a one-line note that no exit-date column exists. That's it — five minutes. If it confirms no leavers, your pivot becomes bulletproof; if it surprises you, even better — you'll have caught it yourself. Remember the line from the prompt deck: *fluency is not evidence* — and that applies to our own claims most of all. Yours included. Mine included.
2. **Validate first, minimize second.** Your privacy instinct is excellent — now put it in the right *order*. Check every raw column (type, range, completeness) **before** you strip what the purpose doesn't need. Minimization protects people; it must never protect errors — and this time it protected one. Go back to the raw `DailyRate`, run the range check, and come tell me what you find. And print your row counts before and after that `dropna()` — make your own rule true everywhere.

And one gift for next week, because you've earned a head start: **look hard at your tenure chart.** B07 sits at the top as your "retention priority" — but B07 is also your *newest* branch, and a new branch cannot have long-tenured staff no matter how happy its people are. Is that signal, or is that structure? Compare tenure against each branch's opening date and find out. That question is precisely what EDA exists to answer, and you have already built the exact table that answers it. You're standing at the door of P3 with the key in your hand.

## Where this goes

This table feeds P3 next Saturday, and it is the seed of your Week 10 attrition case — where exit data *will* exist, and the classification framing you were the first in this class to write comes back to life with everything P2 just taught you. Make the two fixes as a revision commit ("P2 v2 — evidence & raw validation") and this record walks into the Prelim ready.

I'm proud of this one, AJ. Now show me the zero.
