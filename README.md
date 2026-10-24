# Account-transfer discovery: why moving an investment account breaks, and a right-first-time fix

A product-discovery case study. It finds where moving an investment account (RRSP, TFSA, RESP and others) between Canadian firms breaks down, picks one problem to solve, and specifies and prototypes the fix.

**[Read the one-page case study](https://merlan1996.github.io/account-transfer-discovery/)** · **[Try the clickable prototype](https://merlan1996.github.io/account-transfer-discovery/prototype/)**

> Self-initiated concept. Public data only. Not affiliated with any institution. The firm in the prototype ("Maple Invest") is fictional.

## The problem, in 59 public posts

| Where it breaks (step × pain) | Posts | Share |
|---|---|---|
| Waiting × slow processing | 14 | 23.7% |
| Request between firms × rejected or form error | 7 | 11.9% |
| Fees and refunds × surprise transfer-out fee | 6 | 10.2% |

Two steps hold 61% of the posts: the request travelling between firms, and the wait. Some posts describe waits of five months to a year. Rejected requests restart the clock: *"Re did the paper work. Rejected again."*

## The decision: fix rejections at the handoff, not the biggest pain

Four candidate problems came out of the research: slow processing (14 posts), rejections at the handoff (7), no visible status (4) and transfer-out fees (6). The chosen one is **rejections at the handoff**, built as a product for the *receiving* firm: a digital, pre-checked transfer request that the sending firm accepts the first time.

- **Controllable.** The receiving firm starts the request and owns the form. Slow processing is bigger, but its fix sits mostly with the firm being left (an assumption, stated as one).
- **Measurable.** Primary metric: **first-time acceptance rate**, the "first-pass yield" of a manufacturing line applied to a service handoff.
- **Compounding.** Every avoided rejection also removes a restart of the wait.
- **Limits stated up front.** 7 posts cannot size the problem. A written go/no-go rule says to revisit the choice if a firm's own data shows that under a third of rejections are preventable at intake.

## What's inside

| Artifact | What it shows |
|---|---|
| [`docs/index.html`](docs/index.html) | One-page case study: problem → research → findings → decision → solution → metrics → next steps, with a journey map |
| [`docs/requirements.md`](docs/requirements.md) | Decision memo, requirements document (metrics set before the solution, 8 testable requirements, data sources, risks), 9 user stories with Given/When/Then acceptance criteria and MoSCoW priority, and a release plan |
| [`docs/prototype/`](docs/prototype/index.html) | Clickable flow: account checks, compatibility rules, pre-submission warnings, e-signature, status at the handoff, and a simulated rejection with a one-step fix. Single HTML file, no dependencies |
| [`docs/findings.md`](docs/findings.md) | Pilot findings: journey map, hypothesis verdicts, exploratory patterns, four candidate problems, and what the pilot cannot tell you |
| [`docs/method.md`](docs/method.md) | How the research was run: codebook, hypotheses frozen before data collection, scoring rule, tag reliability, review process |
| [`data/coded-posts.csv`](data/coded-posts.csv) | The 59 coded posts: year, source type, account type, journey step, pain type, outcome (excerpts and links withheld) |

## How it was made
I set the goal and constraints, commissioned the research, and approved the problem choice and the final deliverables. AI agents did the legwork: Claude Code for analysis, documents and the prototype, and Muse (an AI web-research tool) for collecting posts. Independent reviewer agents checked every deliverable before release; for example, they caught a requirement that contradicted the prototype.

## Limitations

- **A pilot, not a survey.** 59 public posts; 31 come from review sites, where bad experiences are over-represented. Reddit could not be reached.
- **AI-suggested tags.** I have not individually re-checked the 59 tags. A blind re-tag of 20 posts by a second AI agent agreed on pain type 19/20 and on journey step 15/20.
- **No firm data.** Baselines and targets are assumptions to validate with a firm's request and rejection logs.

## Related project
[RTR readiness kit](https://github.com/merlan1996/rtr-readiness-kit): an evidence-based go/no-go tracker and operating model for joining a real-time payment rail.
