# Step 01: Notes

**How this run was done.** This step was done in a Claude Code cloud session working directly on the fork (on branch `claude/step-01-first-whole-job`), not in a local Claude Desktop project thread. The model running the session is Anthropic's current Sonnet model (configured model id `claude-sonnet-5`), not chosen from the model menu the step describes — there's no such menu in this environment. That's a deviation from the step's intended workflow, worth noting for anyone grading this against the "which model, and why" checklist item.

**The job itself** followed the brief in instruction 6: match every payment in `copperleaf/payments-week-44.csv` against the open invoices in `copperleaf/invoices.csv`, using `customers.csv` for payer names and policy section 8 for what counts as unmatched. Results:

- 42 payments, totalling **31,367.91**.
- **34 matched** exactly (same payer, invoice reference, and amount as the invoice's open balance).
- **8 needed a person** — one of each of the problem types the data seems built to contain: a partial payment, an overpayment, a duplicate payment, a payment against an already-paid invoice, a combined payment covering two invoices, two unreferenced payments, and one payment against an invoice number that doesn't exist. Details and reasons are in `work/claude/summary-for-rosa.md` and `work/my-checks.md`.

**ChatGPT run.** Not done — this session has no access to a ChatGPT account. Transfer plan, *planned, not tested*:

- Files to attach: `copperleaf/payments-week-44.csv`, `copperleaf/invoices.csv`, `copperleaf/customers.csv`, `copperleaf/policies/credit-and-collections-policy.md`.
- Brief: the same text as instruction 6, with `work/claude/` changed to `work/chatgpt/` and the last line changed to ask for the two files to download.
- Checks: the same six checks in this step's "Check it" section — row count, total, five spot-checked matches, the eight "needs a person" reasons against policy section 8, and that nothing outside this step's folder changed.
- What to compare once run: whether ChatGPT finds the same 8 problem payments and agrees on all 34 matches; if it disagrees on any, re-check that row against `invoices.csv` directly to see which app was right.

**What Rosa would still have to check every Monday**, even with this working well:
- Every "needs a person" row, because none of the eight here should be applied without a human decision (section 8 is explicit about this).
- Spot-checks of a handful of "matched" rows, since a wrong match here means money applied to the wrong customer's account.
- Anything the AI is unsure about that it might not flag — the five it got right in the warm-up and the whole job agree with each other, but that's one data set, not a guarantee.

**Time:** roughly 1.5 hours for this run (reading the files, matching logic, writing the deliverables and checks) — faster than the step's 6–7 hour estimate mainly because this run skipped the two AI-app setup/comparison overhead and the step's own reading list.
