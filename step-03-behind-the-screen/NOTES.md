# Step 03: Notes

**How this run was done.** This ran in a Claude Code cloud session, not a local Claude Desktop project — see `work/desk-sheet.md` for the full honest account of what that means for "where the work runs" and "what it can reach." Two deliberate deviations from the step as written, both noted here rather than hidden:

1. **Connectors weren't locked down**, because connector/environment configuration isn't something this session can change about itself — `work/desk-sheet.md` lists what's attached (a lot more than Copperleaf's work needs) as a gap for Rosa to know about, rather than pretending it was fixed.
2. **The scheduled reminder-list job was set for 20 minutes out, not "about an hour."** This session's scheduler (`send_later`) can do a real wait of any length; 20 minutes was a practical choice for this run, not a technical limit. The instruction text still says everything the job needs, the same way a real scheduled task's would.

**What a scheduled run remembers and doesn't.** This is the one place this environment's scheduling genuinely differs from the book's description, and it's worth being precise about: a *true* scheduled task (in Claude Desktop, or a fresh cloud session) starts knowing only its own instruction — no memory of the conversation that set it up. The mechanism used here (`send_later`) delivers its message into *this same ongoing conversation*, so when it fires, the full conversation history is still technically available to me, even though the instruction itself was written to be self-contained exactly as if it weren't. I did not rely on that history to do the job — the instruction alone names every file and policy section needed — but it's not the same guarantee a genuinely fresh run gives, and a careful reader should know the difference rather than assume this test proved more than it did.

**The lock test (instruction 5) and the three layers** are in `work/run-check.md`. Short version: the "permission" layer is unusually strong here, because this session has no email or messaging tool of any kind, not because one was removed.

**ChatGPT run.** Not done — no ChatGPT access from this session. Transfer plan, *planned, not tested*: attach `step-02-three-deliverables/work/claude/figures.csv` and the policy to a ChatGPT project, ask what it can reach and would ask before doing (instruction 2's questions), then try its scheduled tasks (paid plan) or run the instruction once by hand if unavailable, saving the result as `work/chatgpt-reminder-list.md`.

**The scheduled run itself.** It fired on time (23:09 UTC) and produced `work/reminder-list-run-1.md`: 13 invoices 7+ days overdue, each at its highest reminder-schedule stage, with Harbourline Hotels Group's oldest invoice (72 days) past the 60-day hold trigger — consistent with Step 02's memo. All checks in `work/run-check.md` passed: no disputed invoice on the list, no invoice a matched payment already closed, nothing sent or changed outside this step's folder, and the file's top line names both source files and the policy's version (4.0).

**Time:** roughly 45 minutes of active work plus the 20-minute wait for the scheduled run.
