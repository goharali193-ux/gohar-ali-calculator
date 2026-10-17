# User Stories with Acceptance Criteria

**Status key:** Every story is currently marked **Not implemented** because the app has not been built yet. After you build and test the app, change a story to **Implemented** only if you have checked every acceptance criterion in the running app. Stories S-9 to S-11 are future ideas and should stay Not implemented.

**Rules used across all stories (state these to the AI tool):**
- Contract value: greater than 0, up to 999,999,999,999.99, at most 2 decimal places.
- Percentages: from 0.01 to 100, at most 2 decimal places. Total must equal exactly 100.00%.
- Milestones: minimum 1, maximum 12.
- Amounts are rounded to the cent. The last milestone is calculated as the contract value minus the sum of the other milestones, so the total always matches exactly.
- No currency conversion. The currency is a display label only.

---

## S-1: Calculate milestone amounts
**Role:** Project Manager | **Serves:** J-1 | **Status:** Not implemented

As a Project Manager, I want to enter a contract value and milestone percentages and see the amount due at each milestone, so that I know what to bill at each stage.

- Given a contract value of 10,800 and milestones of 25%, 25% and 50%, when I calculate, then I see 2,700.00, 2,700.00 and 5,400.00.
- Given the contract value is empty or 0, when I calculate, then I see "Enter a contract value greater than 0" and no amounts are shown.
- Given the contract value is negative or contains letters (for example "abc"), when I calculate, then I see "Contract value must be a positive number" and no amounts are shown.
- Given the contract value is 0.01 and one milestone is 100%, when I calculate, then the amount is 0.01.
- Given the contract value is 999,999,999,999.99, when I calculate, then amounts are shown in full with thousands separators and not in scientific notation.
- Given the contract value is above 999,999,999,999.99, when I calculate, then I see "Contract value cannot be more than 999,999,999,999.99".
- Given a result is on screen, when I change the contract value or a percentage, then the old result is replaced or cleared so that I never see amounts that do not match the inputs.

## S-2: Add, name and remove milestones
**Role:** Project Manager | **Serves:** J-2 | **Status:** Not implemented

As a Project Manager, I want to add, name and remove milestones, so that the schedule matches my contract.

- Given 3 milestones are listed, when I add one, then 4 milestones are listed and the new one is empty.
- Given 3 milestones are listed, when I remove the second one, then 2 remain and they are renumbered in order.
- Given only 1 milestone is listed, when I try to remove it, then it stays and I see "At least one milestone is required".
- Given 12 milestones are listed, when I try to add another, then I see "A maximum of 12 milestones is supported" and none is added.
- Given I leave a milestone name empty, when I calculate, then it is shown as "Milestone N", where N is its position.

## S-3: Warn when percentages do not total 100%
**Role:** Finance Analyst | **Serves:** J-4 | **Status:** Not implemented

As a Finance Analyst, I want to be told when the percentages do not total exactly 100%, so that I never rely on a schedule that bills the wrong total.

- Given milestones of 25%, 25% and 40%, when I calculate, then I see "Percentages total 90%. They must total 100%. 10% still to allocate." and no final amounts are shown.
- Given milestones of 50%, 40% and 20%, when I calculate, then I see "Percentages total 110%. They must total 100%. Reduce by 10%." and no final amounts are shown.
- Given milestones of 33.33%, 33.33% and 33.34%, when I calculate, then the total is accepted as 100%.
- Given a percentage is empty, zero, negative or not a number, when I calculate, then I see "Each milestone needs a percentage between 0.01 and 100" next to that milestone.
- Given a percentage has more than 2 decimal places (for example 33.333), when I calculate, then I see "Use at most 2 decimal places" next to that milestone.
- Given an error message is showing, when I correct the percentages so they total 100%, then the message disappears and the amounts are shown.

## S-4: Amounts that always add up to the contract value
**Role:** Finance Analyst | **Serves:** J-3 | **Status:** Not implemented

As a Finance Analyst, I want amounts rounded to the cent that always add up to the contract value, so that I can raise invoices that match the contract exactly.

- Given a contract value of 100.00 and milestones of 33.33%, 33.33% and 33.34%, when I calculate, then amounts are 33.33, 33.33 and 33.34 and the total is 100.00.
- Given a contract value of 1,000.01 and milestones of 33.33%, 33.33% and 33.34%, when I calculate, then amounts are 333.30, 333.30 and 333.41 and the total is 1,000.01.
- Given rounding changed the last milestone, when amounts are shown, then a short note says that the last milestone includes a rounding adjustment.
- Given any valid schedule, when amounts are shown, then a total row displays the sum of all milestone amounts and it equals the contract value exactly.

## S-5: Choose the display currency
**Role:** Project Manager | **Serves:** J-1 | **Status:** Not implemented

As a Project Manager, I want to choose the currency, so that amounts are labelled correctly for contracts in different currencies.

- Given I choose USD, when amounts are shown, then they appear as "USD 2,700.00".
- Given I choose PKR, when amounts are shown, then they appear as "PKR 2,700.00".
- Given amounts are on screen, when I change the currency, then only the label changes and the numbers stay the same.
- Given the screen is open, then a note states that no currency conversion is performed.

## S-6: Apply common payment splits
**Role:** Sales Manager | **Serves:** J-5 | **Status:** Not implemented

As a Sales Manager, I want to apply common payment splits with one click, so that I can compare options quickly in a negotiation.

- Given the presets 50/50, 30/40/30 and 25/25/25/25 are available, when I choose 30/40/30, then three milestones with 30%, 40% and 30% appear.
- Given I have edited milestones and a contract value, when I choose a preset, then the milestones are replaced by the preset and the contract value is kept.
- Given a preset is applied and a contract value is entered, when I calculate, then the amounts follow the preset percentages.

## S-7: Copy a milestone's details for an invoice
**Role:** Finance Analyst | **Serves:** J-3 | **Status:** Not implemented

As a Finance Analyst, I want to copy a milestone's details, so that I can paste them into an invoice without retyping.

- Given a valid schedule is shown, when I copy milestone 1, then the clipboard contains text such as "Milestone 1 - 25% - USD 2,700.00" and I see "Copied".
- Given the browser blocks copying, when I try to copy, then I see "Copy is not available. Select the text and copy it manually."
- Given no valid schedule is shown (for example after an error), then no copy option is available.

## S-8: Clear everything and start again
**Role:** Project Manager | **Serves:** J-2 | **Status:** Not implemented

As a Project Manager, I want to clear all inputs and results, so that old values never carry over into a new contract.

- Given inputs and results are on screen, when I choose Reset, then the contract value is empty, the milestones return to their default state and no results or messages are shown.
- Given an error message is showing, when I choose Reset, then the message is cleared.

---

## Future ideas (to be kept as Not implemented)

## S-9: Compare two schedules side by side
**Role:** Sales Manager | **Serves:** J-5 | **Status:** Not implemented

As a Sales Manager, I want to see two payment splits for the same contract side by side, so that I can show a client the difference between options.

- Given two splits for the same contract value, when I compare, then I see both amounts per stage next to each other and the difference for each stage.
- Given one of the two splits does not total 100%, when I compare, then I see an error on that split and no comparison is shown.

## S-10: Download the schedule
**Role:** Finance Analyst | **Serves:** J-4 | **Status:** Not implemented

As a Finance Analyst, I want to download the schedule as a file, so that I can keep it with my records.

- Given a valid schedule, when I download it, then the file contains the milestone names, percentages, amounts, currency and total.
- Given no valid schedule is shown, then the download option is not available.

## S-11: Save a schedule and reopen it later
**Role:** Project Manager | **Serves:** J-2 | **Status:** Not implemented

As a Project Manager, I want to save a schedule and reopen it later, so that I can revise it when the plan changes.

- Given a valid schedule, when I save it with a name, then it appears in my saved list.
- Given a saved schedule, when I open it, then the contract value, milestones and currency are restored exactly as saved.
- Given I try to save without a name, then I see "Enter a name to save this schedule".
