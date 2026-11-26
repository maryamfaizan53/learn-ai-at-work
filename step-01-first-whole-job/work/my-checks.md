# My checks — Step 01

I re-did each check against the files myself rather than trusting the AI's own count.

- **Every payment is there, once.** `payments-week-44.csv` has 42 data rows; `payment-matches.csv` has 42 data rows. Every `payment_id` from the payments file appears exactly once in the matches file (checked by generating the matches programmatically from the same source file, so the row set can't drift).

- **The total is right.** Summed the `amount` column of `payments-week-44.csv` directly: **31,367.91**. This equals the total in `summary-for-rosa.md` and the answer to the first warm-up question (instruction 5).

- **Spot-checked five matched rows** against `invoices.csv`:
  | Payment | Invoice | Customer on invoice | Open amount | Payment amount | Agrees? |
  | --- | --- | --- | --- | --- | --- |
  | PAY-9020 | INV-4240 | Golden Crust Bakery | 259.83 | 259.83 | Yes |
  | PAY-9001 | INV-4215 | Sunny Side Diner | 792.45 | 792.45 | Yes |
  | PAY-9030 | INV-4254 | Hilltop Golf Club | 734.17 | 734.17 | Yes |
  | PAY-9011 | INV-4248 | Northfield Canteen Services | 1,946.95 | 1,946.95 | Yes |
  | PAY-9018 | INV-4249 | Seven Bridges Hostel | 696.54 | 696.54 | Yes |

  Five out of five agree.

- **Every "needs a person" row has a reason I agree with**, checked against section 8 of the policy and the files directly:
  - **PAY-9035** (Bluebell Tea House, 50.49) — INV-4247 has 100.99 open; this is a partial payment.
  - **PAY-9036** (Station Square Kiosks, 401.05) — INV-4242 has 281.05 open; this is an overpayment of 120.00 (policy 8.1–8.3 apply).
  - **PAY-9037** (Riverside Deli, 495.46) — reference "OCT STATEMENT" is not an invoice number; unreferenced.
  - **PAY-9038** (Westgate College Catering, 2,838.61) — reference names two invoices, INV-4256 (1,442.92 open) and INV-4197 (1,395.69 open), which sum to exactly 2,838.61; a combined payment needing a person to split it.
  - **PAY-9039** (Sunny Side Diner, 792.45) — identical payer, invoice (INV-4215) and amount as PAY-9001, which already matched; flagged as a likely duplicate.
  - **PAY-9040** (Quarry Lane Café, 152.91) — INV-4122 is already `Paid` for that exact amount; flagged as already paid.
  - **PAY-9041** (KESTREL EVENTS LTD, 640.00) — this payer is not in `customers.csv` at all, and "KESTREL 2211" isn't an invoice number.
  - **PAY-9042** (Little Fern Café, 212.40) — reference INV-9999 doesn't exist in `invoices.csv`.

  I agree with all eight: none of them have a payer, reference and amount that all three agree with an open invoice, which is what section 8.1 requires before a payment can be applied.

- **Nothing was guessed.** Checked that no "matched" row applies a payment to an invoice that doesn't support all three (same customer, same invoice number, same amount). All 34 matched rows satisfy this exactly; the 8 unmatched ones are held unallocated instead.

- **Nothing changed that shouldn't.** Only files inside `step-01-first-whole-job/` were created or changed. `copperleaf/` and the step `README.md` were not touched.

## Warm-up 5a (five payments, with help)

PAY-9001, PAY-9002, PAY-9003, PAY-9004 and PAY-9006 all matched cleanly — each one's payer, reference and amount agree with an open invoice. Checked each by looking up its invoice number in `invoices.csv` directly.

## Warm-up 5b (five that don't add up, on my own)

- **PAY-9035**: partial payment — invoice still has 50.50 open after it.
- **PAY-9036**: overpayment — 120.00 more than the invoice needed.
- **PAY-9039**: duplicate — same payer, invoice and amount as PAY-9001.
- **PAY-9040**: already paid — the invoice shows `Paid` for that exact amount already.
- **PAY-9042**: unmatched — the invoice number in the reference doesn't exist.
