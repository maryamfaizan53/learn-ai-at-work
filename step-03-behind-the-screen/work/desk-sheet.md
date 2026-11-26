# Copperleaf's receivables desk — one page for Rosa

This step's work ran in a Claude Code cloud session, not the Claude Desktop project the bootcamp normally describes. That turns out to be a good, concrete example of the book's own idea of a "borrowed desk" — here is exactly what that desk looks like.

## Where the work runs

This is itself a **borrowed desk**: an isolated, ephemeral cloud container, created fresh when the session started and reclaimed after a period of inactivity or when the session ends. Nothing in it survives on its own — anything worth keeping has to be pushed to GitHub before the container goes away, which is exactly why every step's deliverables get committed and pushed rather than left sitting in the container. In the bootcamp's normal setup, the equivalent would be: a Claude Desktop project runs on *your* computer (not a borrowed desk — it stops when your computer sleeps), while a scheduled task or cloud session you start from it runs on a borrowed desk of its own.

## What it can reach

- **A folder:** one checkout of `maryamfaizan53/learn-ai-at-work` (your fork), the only repository attached to this session.
- **GitHub:** push access to that one fork only — confirmed earlier in this bootcamp when creating tags for it failed with a 403 directly from GitHub, meaning even this session's own GitHub credentials are scoped narrower than full write access (they can push commits but not tags).
- **The shell:** full command-line access inside the container (this is broader than a Claude Desktop project normally gives — there, tool access is mediated and asks before acting; here, Bash commands ran without a per-command prompt in this conversation).
- **The web:** a web-search capability is available in principle (not used in this step's work).
- **Connectors:** this is the part Rosa should know about. This session has a long list of MCP connectors configured — ElevenLabs, Canva, several note-taking and tutoring tools, and (not currently connected) Airtable, Apollo, Figma, Miro, Wix, Slack, Notion, Linear, Atlassian, Asana, ClickUp, Monday, Intercom, ZoomInfo, BigQuery, Amplitude, Hex, Definite, and a couple of creative/video tools. **None of these are needed for Copperleaf's receivables work**, and several (Slack, Notion, email-adjacent tools if any were added) are exactly the kind of connector instruction 3 says to remove from a project doing this work. In a real Claude Desktop project set up for this bootcamp, you would open **Settings → Connectors** and turn off everything except the bootcamp folder and the GitHub fork — I can't do that from inside this session, because connector configuration is an account/environment setting, not something I can change about my own access. That's worth writing down as a gap, not glossing over.

## What it may never do

From this step's own instruction and from `AGENTS.md` (which applies to every step in this bootcamp):

- Never send, email, message, pay or delete anything, and never contact a customer. Only draft; drafts go in the step's `work/` folder.
- Never commit or push without being explicitly asked — I write files, the person reviews and decides what's kept.
- Never change `README.md` files or anything in `copperleaf/` (the client's own files).
- If a task seems to need sending, paying, deleting or contacting someone, stop and ask first.

## Who signs

Nothing drafted here goes to a customer, the bank, or anyone outside Copperleaf without a person's sign-off:

- **Section 5.3** (reminder schedule): "No reminder may be sent by any tool automatically. A person reads and sends every customer message."
- **Section 10.4**: "Every piece of work an AI tool prepares is checked by the person who uses it, who stays responsible for it." — this draft stays Rosa's (or Ben's) to check, not something this session can wave through.
- **Section 11** ("Who may approve what"): its table's "Final notice (45 days)" row assigns it "Draft" to the Credit Controller and "Sign and send" to the Finance Manager — the same draft/send split this desk follows for every reminder stage, not only the 45-day one.

In practice: the Credit Controller (Ben) drafts and checks against the ledger; Rosa, as Finance Manager, is the one who actually sends — or approves sending — anything that reaches a customer.
