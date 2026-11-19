# Hack4Bharath
# Jewellers Promise

Making every gram of gold verifiable.

Hack for Bharat | Theme: Jeweltech | Problem Statement 2.1 (supported by 2.2)

Team: [SHADOW NINJAS] | Members: [SANTHOSH KUMAR M, GOWRAV MADIVALAR, DEEPTHI H P ]

## Problem

- **2.1:** Customers cannot verify purity, deductions or making charges on old-gold exchange. Small jewellers struggle to prove their numbers and to keep HUID (hallmark) and stock records in order.
- **2.2 (supporting):** Gold given to karigars (artisans) for job-work is tracked in notebooks, which leads to disputes over wastage, delivery dates and payments.
- **Root cause:** the promise between jeweller, karigar and customer has no shared record that anyone can check.

## Solution

A web app with two connected parts on one tamper-evident ledger.

**Transparent exchange and stock (2.1)**
- Jeweller records weight, tested purity, melting-loss deduction, rate and making charge.
- Customer gets an itemised receipt with a QR code: value = weight x purity x (1 - melting loss) x rate - agreed charges.
- Density screening (weigh in air and in water) flags purity that looks inconsistent. It is a screen beside the proper purity test, not a replacement.
- Every item is linked to its HUID with a status: in stock, with karigar, sold.

**Verified job-work (2.2)**
- A digital job card fixes the terms before work starts: design, gold issued, due date, labour rate, wastage allowance. Jeweller and karigar both confirm with PINs.
- Digital twin: the design gives an expected weight band. For a closed 3D mesh, volume = sum over triangles of (v1 . (v2 x v3)) / 6, and expected weight = volume x alloy density plus a casting and finishing allowance. Without a 3D file, use a simple template or the karigar's own history.
- Recovered scrap (filings and dust) is logged so the loss figure is realistic.
- On return, the app compares the piece and scrap with the band, the allowance and the artisan's history, then produces a settlement statement.

**Tamper-evident ledger**
Every issue, return, payment and receipt is linked to the previous record with a SHA-256 hash. Editing an old record breaks every record after it.

## Worked example (illustrative numbers)

Issued 20.0 g of 22K gold. The design says the piece should weigh about 18.5 g (band 18.2 to 18.8 g) with about 1.2 g of normal scrap. Returned: 17.1 g piece and 1.3 g scrap, so 1.6 g is unaccounted for and the app flags it.

## Diagrams

See the `diagrams/` folder: solution overview, exchange receipt flow, job-work flow, gold flow example, tamper-evident ledger, architecture.

## Planned tech stack

React or Next.js PWA (offline-first, regional language), three.js for the 3D viewer, Supabase or Firebase, browser WebCrypto for hashing.

## Prototype plan

Exchange receipt with QR code, density screening calculator, HUID and stock register, job card with issue and return flows, expected-weight calculator and 3D viewer, settlement statement, hash-chained ledger with a tamper demo, and a dashboard with seeded demo data.

## Honest limits

- Expected weight depends on the design and alloy; hollow pieces need the cavity modelled.
- Wastage terms vary by trade and are set by the jeweller and karigar.
- Density is a screening step, not a final purity test.
- BIS hallmarking and HUID rules must be checked against current official guidance.

See `docs/research-notes.md` for how the idea was chosen and what still needs validating.

