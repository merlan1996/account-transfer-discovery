# Method

## Research question
Where does moving an investment account between Canadian institutions break down, and which breakdown can one firm's product team fix?

## Data
- **Sources:** 59 public, customer-written posts (October 2026 collection): 27 from personal-finance forums, 31 from review and complaint sites, 1 app-store review. Reddit was unreachable.
- **Collection rules:**
  - each row links to the specific post;
  - each excerpt is copied verbatim, 15–80 words;
  - institution names in excerpts are masked;
  - no more than 10 posts about any one institution and no more than 3 per thread;
  - no usernames.
- **Not published:** excerpts and links stay out of this repo; [`data/coded-posts.csv`](../data/coded-posts.csv) holds the coded fields.

## Codebook
- **8 journey steps:** choosing a firm → opening the new account → submitting the request → request between firms → waiting → assets moving → fees and refunds → after arrival. "Unclear" is a ninth code.
- **10 pain types:** slow · no status · rejected or form error · partial or wrong transfer · fee surprise · support hard to reach · confusing instructions · tax or registered-account worry · positive · other.
- **Checked against public guides.** Before coding, the steps were checked against two firms' public "transfer your account" guides. Steps 2–7 matched; the guides do not cover steps 1 and 8.

## Hypotheses, frozen before any post was read

| # | Hypothesis | Pilot verdict |
|---|---|---|
| H1 | Slow + no status is the largest pain group | Confirmed by one post (30.5% against a 30% bar): fragile |
| H2 | Rejections come mostly from eligibility or data mismatches, at the handoff | Unclear: share and step hold (7, all at step 4); causes are mixed (1 data omission, 3 firm-side, 3 unstated) |
| H3 | In-kind transfers go partially wrong more often than cash transfers | Wrong, on very few rows |
| H4 | Fee surprises are rarer than slowness and sit at the fee step | Confirmed, small n |
| H5 | Registered accounts are slower and cause more worry | Unclear: no non-registered posts |

**Scoring rule.** It was written before scoring: frozen wording, read literally, with the count and n shown for every verdict, and "unclear" where a comparison group has no rows.

## Reliability
- **Who tagged.** An AI tagger suggested the step and pain for every post.
- **Blind re-tag.** A second AI agent re-tagged 20 posts without seeing the first tags (no human re-check); it agreed on pain type 19/20 and on journey step 15/20. Treat step-level counts with more caution than pain-level counts.

## Review process
Every deliverable passed adversarial review by independent reviewer agents before release.
- **Lenses:** claim-checking, honesty, ranking logic, design, hiring-manager reality.
- **Fluff gate.** Each blocking finding was ruled real or fluff on the record, and only real findings forced a fix.
- **Example catches:**
  - a candidate problem that counted 18 posts when only 4 supported it;
  - a hypothesis marked "confirmed" when only part of it was tested;
  - a dropped caveat that made an average wait look shorter than it was;
  - a requirement that contradicted the prototype.

## What this pilot cannot tell you
- **How common any problem is:** there is no count of uneventful transfers.
- **Anything about individual firms:** posts were capped per firm.
- **Causes or fault:** rejection logs from a firm would be needed.
