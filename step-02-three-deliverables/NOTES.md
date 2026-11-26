# Step 02: Notes

**How this run was done.** As with Step 01, this ran in a Claude Code cloud session on branch `claude/step-02-three-deliverables`, not in a local Claude Desktop project. The model is this session's configured Sonnet model (`claude-sonnet-5`), not picked from an app's model menu. The three deliverables were built with Python (`openpyxl`, `python-docx`, `python-pptx`) and verified by recalculating the spreadsheet in LibreOffice Calc and converting all three files to PDF to confirm they open cleanly — not the same workflow as Claude Desktop's own file-creation skills, but the output format (a real .xlsx/.docx/.pptx file in `work/claude/`) is the same.

**The figures.** Started from `copperleaf/invoices.csv`, applied the 34 "matched" payments from `step-01-first-whole-job/work/claude/payment-matches.csv` (the 8 "needs a person" payments were left unapplied, as the brief requires), then built the aged receivables view as of Monday 2 November 2026:

- Total open: **40,048.40**
- Overdue (past due date, excluding the disputed invoice): **19,442.38**
- Not yet due: **19,521.96**
- Disputed, held separately: **1,084.06** (one invoice, INV-4199)
- Age bands: Not yet due 19,521.96 · 1-30 days 12,722.96 · 31-60 days 5,304.66 · 61-90 days 1,414.76 · Over 90 days 0.00

Three accounts have an invoice more than 30 days overdue: Harbourline Hotels Group (72 days — past the 60-day hold trigger in policy section 4.1), Pocket Espresso Bar (37 days) and Westgate College Catering (36 days, including the invoice tied up in last week's unresolved combined payment).

**ChatGPT run.** Not done — no ChatGPT access from this session. Transfer plan, *planned, not tested*: attach `copperleaf/invoices.csv`, `copperleaf/policies/credit-and-collections-policy.md`, and `step-01-first-whole-job/work/claude/payment-matches.csv` (or the ChatGPT-run equivalents) to a ChatGPT project, run the same four prompts (settle the figures, then the sheet, memo and slides) with `work/claude/` changed to `work/chatgpt/`, download the files, then run the same checks and compare every total.

**Second AI's review of the memo.** Also not done, for the same reason — recorded as a transfer plan in `work/memo-rounds.md`.

**Where each file would be saved:** in this session, everything was written directly into `step-02-three-deliverables/work/claude/` in the cloned repo. In Claude Desktop, the step says files are created directly in the project's folder the same way; in ChatGPT, files are made in its own workspace and must be downloaded manually into `work/chatgpt/`.

**Time:** roughly 2 hours for this run (figures, three deliverables, verifying each one, and the review round) — again faster than the 6–8 hour estimate mainly from skipping the two-app setup and reading-list overhead this run didn't need.
