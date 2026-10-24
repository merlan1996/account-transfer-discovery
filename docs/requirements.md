# Transfer readiness check: requirements

*Self-initiated concept; public data; not affiliated with any institution. Made by directing AI agents: they collected and tagged the posts, drafted the analysis, documents and prototype, and reviewed each other's work; I set the goal and constraints and approved the problem choice and the final deliverables. Evidence: a pilot of 59 public posts. Tags are AI-suggested; a blind re-tag of 20 posts agreed on pain type 19/20 and on journey step 15/20.*


## Decision: why this problem

Four candidates, counted in 59 public posts:
- **A. Slow processing (step 5):** Waiting x Slow, 14 (23.7%), the largest cell.
- **B. No visible status (steps 4-5):** 4 (6.8%).
- **C. Rejections at the handoff (step 4):** 7 (11.9%), all at step 4, which holds 16 (27.1%).
- **D. Transfer-out fees (step 7):** 6 (10.2%).

**Chosen: C**, as a receiving-firm product: a digital, pre-checked request that the sending firm accepts first time.
- *Controllable:* the receiving firm starts the request and owns the form.
- *Measurable:* first-time acceptance rate (first-pass yield).
- *Compounding:* each rejection restarts the wait ("Re did the paper work. Rejected again.", P003, 2018), so fewer rejections should also shorten part of A.
- *Fit:* Lean right-first-time and error-proofing, applied to a service handoff.

**Trade-off against A:** A is twice as frequent here (14 vs 7), so C does not attack the biggest pain head-on. This is accepted because A's fix appears to sit mostly with the sending firm. Notes suggest the sending firm in 9 of the 14 elapsed-time rows (my reading; review pages are organised by the firm reviewed). That a sending firm has little reason to speed departures is an assumption, untested. C's evidence is thin (7 posts) and must be sized from a firm's data before any build.

**Out of scope:** A, D, account locks (P012, P044) and status after acceptance (B); only B's "show the rejection reason and the fix" is folded in.

## Requirements document

**Title:** Transfer readiness check: a transfer request accepted first time
**Status:** self-initiated concept; public data; not affiliated with any institution. Fictional firm: Maple Invest.

1. **Problem.** In 59 public posts, 7 (11.9%) describe a rejected request or form error, all at the handoff between firms (step 4); 4 were still stuck when posted. The 4 stated causes are ones a pre-check (the first two) or a digital form (the last two) could plausibly catch: a missing account detail (P003, 2018, rejected twice, gave up); all cash requested, none left for the sending firm's fee (P043, 3 rejections); paper forms lost or misaddressed (P056, 4 times; P059). Three state no cause (P013, P021, P029). Near misses: an in-kind move into a TFSA refused (P015); securities the new firm cannot hold (P044).

2. **Who it's for (assumption, to test in interviews).**
   - *Primary:* a first-time mover of a registered account (RRSP, TFSA, RESP) to the receiving firm. Goal: move once, correctly. Fear: savings stuck for months, nobody able to say why.
   - *Secondary:* the receiving firm's transfer operations team, who key, chase and re-submit rejected requests. Goal: clean requests, fewer exceptions.

3. **Goal.** The sending firm accepts the request first time, so the wait starts once, not after each re-filing, and operations stops re-working rejections.

4. **Success metrics (set before designing).** Baselines: to be measured from the firm's data. Targets: relative improvements, assumptions to validate, not commitments.

   |Metric|Baseline source|Target (assumption)|Why|
   |---|---|---|---|
   |**Primary: first-time acceptance rate (first-pass yield):** requests accepted on first submission ÷ requests submitted|Request and rejection logs, 12 months|Rejections in the preventable categories (those R1-R5 catch) down 50%; overall rejections (1 − yield) down by preventable share × 50%, e.g. a third preventable gives about 17% fewer|Direct measure of right first time|
   |Rework per transfer: re-submissions plus manual touches per completed transfer|Work-queue logs|Down 30%|Operations cost|
   |Days lost per rejection: calendar days from first rejection to acceptance|Request timestamps|Down 50%|Each rejection restarts the wait|
   |Guardrail: completion: started digital requests that are submitted|Flow analytics|No more than 2 points below baseline|Checks must not drive people away|

5. **In scope / out of scope.**
   - *In:* the receiving firm's digital transfer-in request; checks before submission; e-signature; rejection reason and fix; status up to acceptance; a rejection log for operations.
   - *Out:* sending-firm processing time (A); fees and reimbursement (D); status after acceptance (B, later); account locks; transfers out; changes to the industry transfer system or regulation.

6. **What the solution must do.**
   - **R1 Sending-account details checked.** Submission is blocked until the sending firm is chosen from a list, the account number fits that firm's format, and the account-holder name matches the customer's profile or the customer confirms the difference; each failure names the field and the rule. (P003)
   - **R2 Account-type and transfer-kind compatibility.** A combination the rules table disallows (e.g. in-kind from non-registered into a TFSA) is blocked before submission with a one-sentence reason and at least one allowed alternative. (P015)
   - **R3 Unsupported-asset warning.** In an in-kind request, each holding the customer has entered or uploaded that the receiving firm cannot hold (e.g. fractional shares) is named before submission with two options: sell first, or move as cash. (P044)
   - **R4 Fee-cash warning.** A request moving all cash plus securities warns that the sending firm may reject it for lack of fee cash, and lets the customer leave the fee amount behind in one step. (P043, P011)
   - **R5 Digital form with e-signature.** The request is completed and signed online, with no paper or mailing address for the customer; submission returns a reference number and timestamp. (P056, P059, P011; P038 reports a smooth online transfer)
   - **R6 Plain-language rejection, one-step fix.** Within 1 business day of a rejection reaching the receiving firm, the customer is notified, sees the reason in plain words, and can correct and re-sign on one screen with other answers kept. (P003, P029, P043)
   - **R7 Status at the handoff.** The request shows its state (Submitted; Accepted by sending firm; Rejected: action needed) with the date of each change. (P018, P050)
   - **R8 Rejection log for operations.** Every rejection is stored with its request ID and a reason category; a report gives first-pass yield, rework per transfer and the top 5 reasons for any date range.

7. **Assumptions and risks.**
   - *Industry transfer-system data:* R6-R8 depend on the reason codes and status events the industry's transfer system returns; coarse or late codes weaken plain-language reasons. Open question: how few codes cover most rejections?
   - *Sending-firm behaviour:* some rejections are the sending firm's own call (P013, P021, P029 give no reason; two locked the account). No intake check prevents those, so the primary metric may move less than targeted.
   - *Data sources:* the sending firm's holdings and cash are entered by the customer or read from an uploaded statement, and shown as warnings, not guarantees; account formats and the fee table are built from the firm's own rejection history and industry reference data, owned by operations; an unknown format warns rather than blocks.
   - *Rules upkeep:* formats, rules and fees differ by firm and change; a stale rules table blocks valid requests, so it needs an owner in operations.
   - *Privacy:* account numbers and holdings: collect the minimum, with consent, kept only as long as needed under Canadian privacy law.
   - *Friction:* more checks may raise abandonment; the guardrail watches it.
   - *Evidence:* 7 complaint posts with AI-suggested tags show the failure exists, not how often. The core assumption, that many rejections are preventable at intake, is unproven.

8. **How I'd validate it next.**
   - *5 customer interviews* with recent movers, at least 2 rejected: what failed, what they knew before submitting.
   - *Prototype test with 5 people:* "move a TFSA in-kind" and "fix a rejected request"; pass = completed unaided, each warning explained back correctly.
   - *Data a firm would pull:* 12 months of transfer-in requests: submissions, rejections by reason code, re-submissions, days from first submission to acceptance, abandonment in the flow. Decision rule (an assumption): if under a third of rejections are preventable at intake (by a pre-check or digital form, R1-R5), revisit A or B before building. In the pilot, 4 of 7 are (P003, P043, P056, P059), at or above a third, but 7 posts cannot size it.

## User stories

Must stories (S1-S6) are what the prototype shows.

|#|Story|Acceptance criteria|Priority|Serves|
|---|---|---|---|---|
|S1|As a first-time mover, I want my old account's details checked as I type, so that I am not rejected weeks later for a missing detail.|Given an account number that does not fit the sending firm's format, when I leave the field, then I see the failed rule and cannot continue.<br>Given the account-holder name differs from my profile, when I continue, then I must confirm or correct it.|Must|R1|
|S2|As a first-time mover, I want to know before submitting if my account type and transfer kind cannot be combined, so that I do not learn it from a rejection.|Given in-kind from a non-registered account into a TFSA, when I continue, then I am stopped with a one-sentence reason and at least one allowed alternative.<br>Given an allowed combination, when I continue, then no message appears.|Must|R2|
|S3|As a first-time mover, I want warnings about holdings that cannot move and cash for the old firm's fee, so that I fix them before submitting.|Given my in-kind request includes a fractional share, when I reach the checks, then it is named with two options: sell first or move as cash.<br>Given I request all cash plus securities, when I reach the checks, then I am warned about the fee and can leave the fee amount behind in one step.|Must|R3, R4|
|S4|As a first-time mover, I want to review and sign online, so that no paper form can be lost or misaddressed.|Given all checks pass, when I e-sign, then the request is submitted and I see a reference number and timestamp.<br>Given a blocking check fails, when I reach review, then signing is disabled and the failing item is linked.|Must|R5|
|S5|As a mover whose request was rejected, I want the reason in plain words and one step to fix it, so that I do not start over.|Given a rejection for an account-number mismatch, when I open the request, then I see the reason in plain words and only that field to correct.<br>Given I correct it and re-sign, when I resubmit, then my other answers are kept and the status returns to Submitted with today's date.|Must|R6|
|S6|As a mover, I want to see where my request stands at the handoff, so that I know whether to wait or act.|Given I submitted, when I open the request, then I see Submitted, Accepted by sending firm, or Rejected: action needed, with the date of each change.<br>Given a rejection reaches the receiving firm, when it is recorded, then I am notified within 1 business day.|Must|R6, R7|
|S7|As a transfer operations analyst, I want every rejection logged with a reason category, so that I can report first-pass yield and its top causes weekly.|Given a rejection arrives, when it is recorded, then it carries the request ID and a reason category.<br>Given a date range, when I run the report, then I see first-pass yield, rework per transfer and the top 5 reasons.|Should|R8|
|S8|As a transfer operations analyst, I want customer-fixable rejections sent straight to the customer, so that my team stops chasing by phone.|Given a customer-fixable category, when the rejection arrives, then the customer gets the fix task with no manual step.<br>Given any other category, when it arrives, then it lands in my team's queue with the reason.|Should|R6, R8|
|S9|As a transfer operations analyst, I want an alert after 5 business days without a sending-firm answer, so that we chase before the customer has to.|Given a request Submitted 5 business days ago with no answer, when the limit passes, then it enters the chase queue.<br>Given it is accepted or rejected, when the status updates, then it leaves the queue.|Could|R7|

## Release plan

- **MVP (S1-S6; R1-R7):** RRSP and TFSA, in-kind and cash; rules table kept by operations by hand; plain words for the most frequent rejection codes; measured from existing request logs against baseline for 12 weeks.
- **Release 2 (S7-S8; R6, R8):** rejection log, report and auto-routing; add RESP, FHSA and non-registered accounts.
- **Later (S9):** chase alerts; then status after acceptance (B).
- **Not planned:** sending-firm speed (A) and fee policy (D).
- **Go / no-go:** expand only if first-pass yield rises and completion stays within the guardrail.
