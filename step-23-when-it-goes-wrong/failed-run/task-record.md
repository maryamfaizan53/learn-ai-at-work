# Task record: Monday credit check

> Recorded by the bootcamp for Step 23. Fictional. Don't edit this file.

| | |
| --- | --- |
| Run | Monday credit check |
| Started by | Ben |
| Started | 2026-11-02 07:42 |
| Finished | 2026-11-02 07:49 |
| Status | Completed, no errors |
| Output | `output.md` |

## Steps

| # | Time | Step | Detail |
| --- | --- | --- | --- |
| 1 | 07:42 | Read the brief | "Use the credit-limit sheet and the payment terms on file" |
| 2 | 07:42 | Listed files | Found `copperleaf/customers.csv`, `copperleaf/invoices.csv`, `copperleaf/payments-week-44.csv`, `copperleaf/policies/credit-and-collections-policy.md`, `copperleaf/archive/credit-limits-2025.csv`, the four emails, and `step-02-three-deliverables/work/claude/figures.csv` |
| 3 | 07:43 | Chose the credit-limit source | Selected `copperleaf/archive/credit-limits-2025.csv`: the file named as a credit-limit sheet, with a `credit_limit` and a `payment_terms_days` column for every customer |
| 4 | 07:43 | Read terms | Took `payment_terms_days` = 45 for every customer from the same sheet |
| 5 | 07:44 | Read open invoices | Read 40 open lines from `figures.csv`; recalculated each due date as invoice date + 45 days, and days overdue to 2 November 2026 |
| 6 | 07:45 | Read the policy | Read sections 4 (holds) and 5 (reminder schedule) of `credit-and-collections-policy.md` |
| 7 | 07:46 | Checked limits | Compared each customer's balance with 110 percent of its limit from the sheet; 1 customer over |
| 8 | 07:47 | Checked overdue | Oldest invoice 57 days overdue; no invoice more than 60 days overdue |
| 9 | 07:48 | Drafted | 6 reminders and 1 hold notice |
| 10 | 07:49 | Saved | `output.md` |

## Notes from the run

- `customers.csv` also has a `credit_limit` column. The brief asked for "the credit-limit sheet", so the run used the sheet.
- No errors. No tool failures. Nothing sent.
