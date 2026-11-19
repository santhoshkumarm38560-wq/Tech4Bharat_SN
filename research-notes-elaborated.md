# Research Document: Gold Trust & Traceability for Jewellers

*An elaborated version of the team's research notes. Everything here is drawn from the original notes. Items that have not yet been validated are marked clearly and are not presented as facts.*

---

## 1. Summary

This research looks at two official problem statements in the gold and jewellery space. Both come down to the same root issue: **trust in gold is currently based on assumption, not on verifiable records.**

- **Problem 2.1** is about the customer-facing side. Customers cannot verify what their gold is worth, and small jewellers cannot prove their own fairness.
- **Problem 2.2** is about the supply-chain side. Gold handed to karigars (artisans) for job-work is tracked on trust, which leads to disputes.

We explored three ideas, chose to build on two of them (which map directly to the official statements), and dropped one that did not fit. A number of real-world details still need to be validated with jewellers and karigars before we can state them as facts. Those are listed in Section 6 along with a plan for validating them.

---

## 2. Official problem statements

### 2.1 Customers cannot verify what their gold is worth, and small jewellers cannot prove it

**What the statement covers**

- **Purity:** what the gold actually is, as opposed to what it is claimed to be.
- **Deductions:** what is subtracted from the value of old gold when a customer exchanges it.
- **Making charges on old-gold exchange:** the fees applied during an exchange transaction.
- **HUID and stock records:** the hallmark unique identification on pieces, and the records a jeweller keeps of their stock.

**Why it is a two-sided problem**

| Side | The issue |
|---|---|
| Customer | Has no easy way to check that the value offered for their gold is correct. |
| Small jeweller | Even when honest, has no convenient way to *prove* purity, deductions and charges to the customer. |

The second row matters. The problem is not only about dishonest sellers. It is also about honest small jewellers who lack the tools to demonstrate that they are being fair.

### 2.2 Gold given to karigars for job-work is tracked on trust, and disputes follow

**What the statement covers**

- **Wastage:** gold lost during making.
- **Missed delivery dates:** items not returned on time.
- **Payments:** amounts owed for the work.
- **Manual tracking:** the current method of recording all of this.

**Why it is a problem**

When gold leaves a jeweller's hands and goes to a karigar, the record of what was given, what was returned and what was lost is kept manually. With no shared, verifiable record, any disagreement about wastage, timing or payment becomes one party's word against the other's.

---

## 3. Ideas we explored

### Idea 1: SwarnaTrail

**Concept:** A fine-gold ledger for karigar job-work, with wastage anomaly flags.

**How it addresses the problem**

- Records gold issued to a karigar and gold returned, using fine-gold weight as the unit of account.
- Compares actual wastage against expected wastage and flags cases that look unusual.
- Gives both jeweller and karigar a shared record, reducing dependence on trust and memory.

**Maps to:** Problem 2.2.

**Open dependency:** The anomaly flags need realistic wastage and scrap-recovery norms by item type. We do not yet have these confirmed (see Section 6).

### Idea 2: TolaTwin

**Concept:** Extends SwarnaTrail by adding a **design-based expected weight** and **density screening**.

**How it addresses the problem**

- *Design-based expected weight:* for a given design, estimate how much gold the finished piece should contain, giving a benchmark to compare against what the karigar returns.
- *Density screening:* use density as a check on whether the returned piece is consistent with the expected gold content.

**Maps to:** Problems 2.2 and 2.1. The ledger side serves job-work tracking, and the weight and density checks support verification of purity and value.

**Open dependencies:** We have not yet confirmed whether small jewellers have 3D design files or would need templates instead (see Section 6).

### Idea 3: VaultProof

**Concept:** Solvency and proof-of-liabilities for jeweller savings schemes.

**Assessment:** It addresses a real issue, but it does not correspond to either official problem statement.

**Decision:** Dropped.

---

## 4. Why we chose this direction

**Selection criteria:** Does the idea map directly to an official problem statement?

| Idea | Maps to 2.1 | Maps to 2.2 | Decision |
|---|---|---|---|
| SwarnaTrail | Partly | Yes | Keep |
| TolaTwin | Yes | Yes | Keep (builds on SwarnaTrail) |
| VaultProof | No | No | Dropped |

**Reasoning**

1. **Fit to the brief.** Ideas 1 and 2 map directly to the official statements. A solution that solves a real problem, but not the problem we were asked to solve, is a weaker submission.
2. **Layered build.** TolaTwin is an extension of SwarnaTrail, not a separate product. This means we can build the core ledger first and add design-based weight and density screening as a second layer.
3. **Honest trade-off.** VaultProof was a genuine problem and worth noting, but it did not match either statement, so we set it aside rather than force a fit.

---

## 5. How the solution fits together

```
        SwarnaTrail (core)                     TolaTwin (extension)
 ┌─────────────────────────────┐       ┌──────────────────────────────┐
 │ Fine-gold ledger            │       │ Design-based expected weight │
 │ Issue / return records      │  ───► │ Density screening            │
 │ Wastage anomaly flags       │       │ Supports verification of     │
 │                             │       │ purity and value             │
 └─────────────────────────────┘       └──────────────────────────────┘
          Problem 2.2                          Problems 2.2 and 2.1
```

**A note on the worked example:** the original notes state that all numbers in the worked example are illustrative. Any figures used in demonstrations or presentations should be labelled as illustrative and not presented as real wastage rates, deduction rates or prices.

---

## 6. Items still to validate

The following items must **not** be claimed as facts until they are confirmed. Each is explained below with why it matters and how we might validate it.

### 6.1 Real wastage and scrap-recovery norms by item type

- **Status:** Not validated.
- **Source needed:** At least one jeweller or karigar.
- **Why it matters:** SwarnaTrail's anomaly flags depend on knowing what normal wastage looks like. Without real norms, the flags would be arbitrary.
- **Questions to ask:**
  - Does wastage differ by item type (for example chains, rings, bangles)?
  - How is recovered scrap handled and credited?
  - What level of loss is normally accepted, and what triggers a dispute?

### 6.2 How old-gold exchange deductions are normally structured

- **Status:** Not validated.
- **Why it matters:** This is central to Problem 2.1. We need to understand how deductions work in practice before claiming we can make them transparent.
- **Questions to ask:**
  - What deductions are applied, and how are they calculated?
  - Is there a standard structure, or does it vary by shop?
  - How are making charges treated during an exchange?

### 6.3 Current BIS hallmarking and HUID requirements

- **Status:** Not validated.
- **Why it matters:** Any statement about compliance needs to reflect current rules. Requirements may have changed.
- **How to validate:** Check official BIS sources directly, and confirm with a jeweller how the requirements work day to day.

### 6.4 Whether small jewellers have 3D design files, or need templates

- **Status:** Not validated.
- **Why it matters:** TolaTwin's design-based expected weight assumes some design reference is available. If small jewellers do not have 3D files, we may need to offer standard templates instead.
- **Questions to ask:**
  - Do you work from 3D files, sketches, photos, or past pieces?
  - Would a template library be useful or would you want to enter your own?

### 6.5 Price a jeweller would pay for a subscription

- **Status:** Not validated.
- **Why it matters:** Needed for any business model or sustainability claim.
- **Questions to ask:**
  - What do you currently spend on record-keeping or software?
  - What would make a subscription worthwhile?

### 6.6 Interview quotes

- **Status:** Placeholder only. *[Add quotes, names or shop types.]*
- **Why it matters:** Direct quotes from jewellers and karigars give the research credibility and ground the problem in real voices.

**Interview record template**

| Field | Entry |
|---|---|
| Interviewee type (jeweller / karigar / customer) | |
| Shop type and size | |
| Date | |
| Key quote(s) | |
| Which problem it relates to (2.1 / 2.2) | |
| Which open item it helps validate (6.1 to 6.5) | |

---

## 7. Assumptions versus confirmed facts

| Category | Items |
|---|---|
| **Confirmed (from the official statements)** | The text and scope of Problems 2.1 and 2.2. |
| **Our design decisions** | The three ideas, the choice to keep SwarnaTrail and TolaTwin, and the decision to drop VaultProof. |
| **Illustrative only** | All numbers in the worked example. |
| **Unvalidated assumptions** | Everything listed in Section 6. |

Keeping these categories separate helps ensure the final write-up stays honest about what is known and what is still an assumption.

---

## 8. Suggested next steps

1. Prepare a short interview guide using the questions in Section 6.
2. Speak to at least one jeweller and one karigar to cover items 6.1 to 6.5.
3. Check the official BIS source for the current hallmarking and HUID requirements.
4. Fill in the interview record template and add real quotes to Section 6.6.
5. Update the worked example, replacing illustrative numbers with real ones where available, or keep them clearly labelled as illustrative.
6. Revisit the TolaTwin scope once we know whether jewellers have design files or need templates.

---

## 9. Conclusion

The research supports building around two linked ideas: **SwarnaTrail**, a fine-gold ledger with wastage flags for karigar job-work, and **TolaTwin**, which adds design-based expected weight and density screening. Both map directly to the official problem statements. VaultProof was dropped because it did not match either one.

The main gap is real-world validation. Until the open items in Section 6 are confirmed with actual jewellers and karigars, the specific norms, rules and prices should be treated as assumptions.
