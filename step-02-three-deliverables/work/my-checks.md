# My checks — Step 02

- **The grand total, by hand.** Summed the `amount_open` column of `figures.csv` directly: **40,048.40**. This matches the "Grand total" cell on the xlsx's Summary sheet (`Summary!B8`, a `=SUM(...)` formula) and the total in the memo and slides.

- **Three ages, by hand**, worked out from each invoice's due date to 2 November 2026:
  | Invoice | Due date | Days to 2 Nov 2026 | Band shown |
  | --- | --- | --- | --- |
  | INV-4286 (Morning Tide Coffee) | 2026-11-29 | not yet due (−27 days) | Not yet due — agrees |
  | INV-4206 (Pocket Espresso Bar) | 2026-10-04 | 29 days overdue | 1-30 — agrees |
  | INV-4141 (Harbourline Hotels Group) | 2026-08-22 | 72 days overdue | 61-90 — agrees |

- **The payments really were applied.** INV-4240 (paid by PAY-9020) and INV-4254 (paid by PAY-9030) do not appear in `figures.csv` at all — both fully closed. Confirmed against `step-01-first-whole-job/work/claude/payment-matches.csv`: both show `result = matched`.

- **The disputed invoice is on its own line.** INV-4199 (Brickyard Bistro, 1,084.06) appears with `age_band = Disputed` and an empty `days_overdue`, and its 1,084.06 is reported separately in the memo and slides, not folded into any age band total.

- **The sheet uses formulas.** Opened `aged-receivables.xlsx` and recalculated it (I don't have Excel here, so I used LibreOffice Calc to force a recalculation and exported the result): every Summary cell — the five age-band totals, the grand total, and each customer's total and oldest days overdue (`MAXIFS`) — is a formula reading from the Invoices sheet, not a typed number. The recalculated values matched my own hand totals exactly.

- **All three agree.** The grand total (40,048.40), the overdue total (19,442.38), the disputed total (1,084.06) and the top-five customer balances are identical across `aged-receivables.xlsx`, `overdue-memo.docx` and `monday-slides.pptx`, because all three were generated from the same `figures.csv`.

- **Every policy claim in the memo is right.** Checked each citation against `copperleaf/policies/credit-and-collections-policy.md`:
  - Section 4.1: a hold triggers at more than 60 days overdue, or balance more than 10% over the credit limit. Harbourline's oldest invoice is 72 days overdue — triggers the first condition. (Its balance, 10,211.79, is well under its 25,000 limit, so only the days-overdue condition applies, which the memo doesn't overclaim.)
  - Section 4.3: a limit above 10,000 means the Owner is told the same day a hold is proposed. Harbourline's limit is 25,000 — condition applies, as the memo says.
  - Section 5: the reminder schedule's milestones are 7, 21, 35, 45 and 60 days. Pocket Espresso Bar (37 days) and Westgate College Catering (36 days) have both passed the 35-day phone-call point but not the 45-day final notice — matches what the memo says for both.
