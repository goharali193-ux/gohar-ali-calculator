# App Roles

**App:** Milestone Payment Calculator, a browser-based tool that turns a contract value and a set of payment milestones into the amount due at each milestone.

**Note on roles:** The first version has no login. Roles describe the three kinds of people who use the app and what they need from it. The "must never" rules are enforced by how the app behaves, not by permissions.

---

## R-1 Project Manager

A **Project Manager** is a delivery lead who owns a client contract and has to turn its payment terms into a billing plan. They can enter the contract value, choose the currency, define the milestones and their percentages, and see the amount due at each milestone. They must never be shown a schedule that looks final when the milestone percentages do not total 100%.

## R-2 Finance Analyst

A **Finance Analyst** is a member of the finance team who raises invoices when a milestone is completed and checks them against the contract. They can enter the figures from a contract, check the exact amount due at each milestone, and copy a milestone's details to use in an invoice. They must never be shown amounts that fail to add up to the contract value because of rounding.

## R-3 Sales Manager

A **Sales Manager** is a commercial lead who negotiates payment terms with a client before the contract is signed. They can try different contract values and payment splits quickly and see what would be payable at each stage. They must never be given an unvalidated schedule (for example, one that does not total 100%), because they may quote it to a client.

---

## How the roles differ

| | Project Manager | Finance Analyst | Sales Manager |
|---|---|---|---|
| **When they use it** | After signing, to plan billing | At each milestone, to invoice | Before signing, to negotiate |
| **What they care about most** | A schedule that matches delivery stages | Exact, cent-accurate amounts | Speed and comparing options |
| **Typical input** | Real contract and milestones | Figures copied from the contract | Draft values and common splits |
| **Risk if the app gets it wrong** | Wrong cash-flow plan | Wrong invoice sent to the client | Wrong terms quoted to the client |
