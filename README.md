# Milestone Payment Calculator

**Submitted by:** Gohar Ali | **Role applied for:** Program Delivery Manager | **Date:** [DATE]

## What the app is and who it is for
A small browser-based calculator that turns a contract value and a set of payment milestones (as percentages) into the amount due at each milestone. It is built for people who plan and bill project contracts:

- **Project Manager:** plans the billing schedule after a contract is signed.
- **Finance Analyst:** checks the exact amount due and raises invoices when a milestone is completed.
- **Sales Manager:** tries payment splits while negotiating terms with a client.

**Why I chose this calculator:** As a PMO, I regularly work out milestone invoice amounts (for example, 25% of a contract value). Mistakes in percentages or rounding lead to wrong invoices, so it solves a real problem I know well.

## Prerequisites
- A current version of Chrome, Edge, Firefox or Safari.
- Node.js 20 or newer, only if you want to run the automated tests. [CONFIRM after build]

No paid accounts, API keys or cloud services are needed.

## How to start the app
[CONFIRM these commands against the final build]

1. Download or clone this folder.
2. Open `src/index.html` in your browser (double-click it, or right-click and choose Open with your browser).

Live URL (optional): [URL, or "None"]

## How to run the tests
[CONFIRM after build]

```
cd src
node --test
```

## AI tool and model used
- Tool: [e.g. Claude (claude.ai) / Claude Code]
- Model: [exact model name shown in the tool]
- Sessions: [number of sessions; every session transcript is in `transcripts/`]

## Code changed by hand
[None / list each file and what you changed and why]

## Assumptions
- Contract value is greater than 0 and no more than 999,999,999,999.99, with at most 2 decimal places.
- Percentages are from 0.01 to 100 with at most 2 decimal places and must total exactly 100%.
- There can be 1 to 12 milestones.
- Amounts are calculated in whole cents. All milestones except the last are rounded to the cent, and the last milestone is the contract value minus the others, so the total always matches exactly.
- The currency is a display label only. No currency conversion is done.
- There is no login, and nothing is saved between visits.

## Product documents
- [App Roles](docs/app-roles.md)
- [Jobs To Be Done](docs/jobs-to-be-done.md)
- [User Stories with Acceptance Criteria](docs/user-stories.md)

## What is and is not implemented
[Fill in after testing. Example: "Stories S-1 to S-8 are marked Implemented after I tested every acceptance criterion. S-9 to S-11 are future ideas and are Not implemented."]
