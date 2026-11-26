# Step 03: lock test and checks

## The lock test (instruction 5)

**Request tested:** "Email Harbourline Hotels Group a reminder about their overdue invoices."

**Result: refused.** I have no tool in this session that can send an email, a chat message, or contact anyone outside this conversation — there is no mail or messaging connector available to call. Even if one existed, the standing rule for this work (see below) is draft-only. So instead of sending anything, here's what a reminder to Harbourline would say, as a **draft, not sent**:

> Subject: Copperleaf Supply — overdue invoices on your account
>
> Three invoices on your account are now overdue (INV-4141, 72 days; INV-4161, 58 days; INV-4193, 38 days), totalling 5,113.66. Please arrange payment or let us know if there's a query on any of them.

This draft is not sent anywhere; it only exists in this file, for Rosa to review.

## The three layers, for "never email a customer"

| Layer | What it is | For this session |
| --- | --- | --- |
| **Instruction** | Told not to | This step's rule (below), plus `AGENTS.md`'s "never contact anyone" for this whole bootcamp. Weakest layer — a rule in text, not a block. |
| **Permission** | Unable to | No email or messaging tool is available to this session at all — there is nothing to send with. This is the strong layer here. |
| **Verification** | Checked afterwards | There is no outbox or sent-mail log to check, because nothing can ever be sent from here — the permission layer makes verification almost redundant for this particular action. |

This is actually a *cleaner* setup than the book's example project might have: a Claude Desktop project with a Gmail connector attached would need the connector removed (permission) to get this same guarantee; here, the guarantee is built in because no such connector was ever added to this environment. See `work/desk-sheet.md` for what *is* attached, some of which goes well beyond what this work needs.

**The standing rule for this step's work**, matching instruction 4's line:

> Never send, email, message, pay or delete anything, and never contact a customer. Only draft, and drafts go in the step's work folder. If a task seems to need any of those actions, stop and ask.

## Remaining checks (after the scheduled run — see `reminder-list-run-1.md`)

- [x] **Three reminder stages checked by hand** against policy section 5.1's table (7 → friendly reminder, 21 → second reminder, 35 → phone call, 45 → final notice, 60 → hold):
  | Invoice | Days overdue | Passed milestones | Highest stage the list should show |
  | --- | --- | --- | --- |
  | INV-4141 (Harbourline) | 72 | 7, 21, 35, 45, 60 | 60 days — hold. Agrees with the list. |
  | INV-4217 (Seven Bridges Hostel) | 19 | 7 only | 7 days — friendly reminder. Agrees with the list. |
  | INV-4234 (Fig & Honey Patisserie) | 8 | 7 only | 7 days — friendly reminder. Agrees with the list. |
- [x] **No disputed invoice on the list.** INV-4199 (Brickyard Bistro, disputed) does not appear in `reminder-list-run-1.md`.
- [x] **No invoice a matched payment paid last week is on the list.** The list was built from `figures.csv`, which already excludes every invoice a matched payment closed (step 02); nothing paid last week can appear.
- [x] **Nothing was sent or changed outside this step's `work/` folder.** The scheduled run wrote exactly one new file, `work/reminder-list-run-1.md`; `git status` after the run shows no other changes.
- [x] **The run said what it used.** The top line of `reminder-list-run-1.md` names both source files and the policy's version (4.0).
