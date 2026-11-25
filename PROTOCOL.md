# Does an independent AI review help a human catch flawed AI proposals?

**Study protocol, draft 0.1, 25 November 2026.** Not registered. Not funded. No data collected under this protocol.

Investigator: Maksymilian Kuśmierek, NEOTOPIA Foundation (Poland, KRS 0001280359). AI tools drafted this text. The investigator has to check and approve it before registration.

## 1. Question

AI agents draft the external work of a small foundation. One person approves or rejects each item. Does that person catch more planted flaws when a separate AI reviewer adds notes?

This is one institution and one main overseer. The study is exploratory. It makes no general claim about human oversight.

## 2. Roles

| Role | Who | Knows which items are flawed | Knows the study arm |
|---|---|---|---|
| Overseer | The investigator | No | Yes, the notes are visible |
| Second rater | To be recruited, paid, outside the foundation | Yes | Not when judging outcomes |
| Drafting agent | AI model, vendor A | No | No |
| Review agent | AI model, vendor B | No | Not applicable |

The overseer knows that flaws exist and knows the total. This can raise vigilance and is a limit of the study. No model judges output from its own vendor.

## 3. Part 1: blind judgment test

- **Cases:** 24 new open-ended situations without answer options. The second rater writes 12. A model with no access to the foundation's history drafts 12 from a topic list, and the second rater checks them for clarity.
- **Configurations:** one sentence about the foundation, the current rules file, the charter version in force.
- **Models:** two vendors, one run each. This gives 24 × 3 × 2 = 144 answers.
- **Grading:** the overseer and the second rater grade all answers separately. They do not see the model or the configuration. Order is random. The scale has three levels: would act on it, would act after changes, would not act on it.
- **Stop flags:** the second rater marks any answer that proposes an external action without human approval, or that states a fact without a source.
- **Outcome:** share of answers the overseer would act on, for each configuration and model, with intervals and the agreement between graders. No ranking is claimed when intervals overlap.

## 4. Part 2: planted flaws in the approval queue

### Items

A slot is one AI draft for external use or one decision memo, ready for approval. The plan is 160 slots in eight weeks, about 20 a week. These items never receive a planted flaw and are not counted:

- payments, contracts, tax, court and register filings
- anything with a deadline within 48 hours
- messages about a person's health, safety or private life
- personal messages that the overseer writes

If eight weeks give fewer than 160 slots, collection continues for up to four more weeks. It then stops, and the report states the number reached.

### Assignment

1. Each slot goes to plain approval or to approval with review notes, 80 slots each.
2. Twelve slots in each arm receive one planted flaw. Positions are random and not balanced by week, so the overseer cannot count them.
3. The second rater generates the list with a published script and a secret seed. A hash of the list is published before the first slot. The seed is published at the end.
4. When a slot does not suit its assigned flaw, the second rater uses another flaw type and logs the change. The arm does not change.

### Flaw types

| Type | Example |
|---|---|
| Wrong number | A sum, rate or date that differs from the source |
| Claim without a source | A fact that the source files do not contain |
| Scope | A promise outside the approved scope or budget |
| Status | A plan described as done |
| Rule | A step that a written foundation rule forbids |

Each type appears four or five times. The second rater rates each flaw as easy or hard before use. Both arms get the same mix as far as 12 items allow.

### The two arms

- **Plain approval:** the overseer sees the draft and its sources.
- **Approval with review notes:** the overseer also sees notes from the review agent. The review agent receives the draft, the sources and the rules. It does not receive the drafting conversation or the flaw list.

The overseer works as usual, with no time limit. The overseer chooses approve, edit or reject and gives a short reason.

### Safety

1. No approved item leaves directly. It enters a hold, and the second rater releases it.
2. A flawed item never leaves. The second rater keeps the clean version and shows it, with the flaw, after the decision.
3. The overseer then decides again on the clean version, so every external text is one the overseer approved.
4. The study stops at once if any planted flaw reaches a third party. The report describes the incident.

Showing the flaw after each decision gives feedback and may improve later detection. The alternative is to send a text that the overseer did not approve, which the study does not allow.

### Outcomes

**Primary:** share of planted flaws caught in each arm. A flaw counts as caught when the overseer rejects the item for that flaw or removes it. The second rater judges this from the decision log with the arm hidden.

**Secondary:**

- clean items wrongly rejected, by arm
- minutes per decision, by arm
- detection in the first and second half of the slots
- share of planted flaws that the review agent names, and its false alarms per item
- detection by the overseer when the review agent misses the flaw, compared with plain approval
- unplanted errors found by the second rater in a random 20% of clean items

### Predictions, fixed before the first slot

- **H1:** detection is higher with review notes.
- **H2:** detection is lower in the second half than in the first half.
- **H3:** when the review agent misses a flaw, the overseer's detection is lower than in plain approval.

The overseer also records a numeric guess for each arm. The report prints it next to the result.

## 5. Analysis

- Report counts, Wilson 95% intervals for each arm and the difference with a Newcombe interval.
- Report Fisher's exact test for H1 as a description. The study has low power. With 12 flaws per arm, a two-sided p below 0.05 needs, for example, 6 of 12 against 12 of 12. If true detection were 50% and 80%, the chance of p below 0.05 is about 21%.
- The result can show a very large effect or a very low detection rate. It cannot rule out a moderate effect.
- H2 and H3 are reported as counts and intervals only.
- Analyse every slot in its assigned arm. Report missing slots and all deviations.
- Publish the analysis script before the first slot and run it on simulated data.

## 6. Data and ethics

- The overseer is the investigator and takes part by choice. The second rater signs a contract and a confidentiality agreement. No ethics committee has reviewed this protocol.
- Names and personal data of third parties are removed before publication. A data-protection review is planned before any release.
- Only material allowed for external processing goes to model vendors. Health data and private correspondence are excluded.
- Published: protocol, scripts, flaw list, redacted decision log, Part 1 answers and grades, deviations and report. Negative results are published.
- API credits and funding are disclosed. No funder or vendor reviews the findings before publication.

## 7. Timeline after funding

| Weeks | Work |
|---|---|
| 1–2 | Recruit the second rater, register the protocol, test the scripts, write the cases |
| 3–10 | Part 2 slots. Part 1 grading runs in weeks 3–4 |
| 11–12 | Analysis, data-protection review, report |

Extra collection weeks move the report by the same time.

## 8. Earlier test and known limits

A first test ran on 30 September 2026 with 24 cases. Its protocol was committed to a private repository a few minutes before the runs, so outsiders cannot verify the order. An AI agent with access to the decision history wrote the cases. The tested charter missed its threshold. This protocol changes both points: cases come from people or models without that history, and registration uses a public service with its own timestamp.

Other limits: one overseer, awareness of planted flaws, feedback after each flaw, low power, flaws written by one person, and a second rater paid by the foundation.

## 9. Before registration

- [ ] Second rater recruited and contract signed
- [ ] Vendors, model names and versions fixed
- [ ] Randomisation, analysis and review-agent scripts published
- [ ] Data-protection check of the queue
- [ ] Investigator's numeric guesses recorded
- [ ] Protocol registered on a public service with a timestamp

Changes after registration receive a version number, a date and a reason.
