# AceDoors Residential v0.4.6

Flat GitHub Pages review release for automatic serials, management overrides, revised customer approval and paid-deposit variations, alongside the department workflow introduced in v0.4.5.

## Department workflow and permissions

The top **Job Command Center** shows the job’s current position, the reason it is waiting, any open inter-department action, and the audit timeline.

| Department | Normal workspace | Release condition |
|---|---|---|
| Sales | Quote, acceptance and commercial setup | Customer acceptance plus deposit or PO pathway |
| Technician / Service | Final Site Measure, then installation scheduling | Install scheduling appears after final measure approval and Production release; completion unlocks after QC |
| Production | Release, cut sheets, manufacture, parts and QC | Ready for Install and/or Ready for Dispatch |
| Install | Installation handover | Available only for jobs containing installed doors after QC |
| Dispatch | Dispatch handover | Available only for supply-only/freight doors after QC |
| Accounts / Invoicing | Final invoice and close-out | Available after all required Install/Dispatch handovers |

- Department users see only their authorised workspace; Master users can open every department and change the active workspace.
- Any department can request action from another department, including a reason. The target Job Status stage reopens in yellow until the requested department or Master resolves it.
- Auditable workflow events record the time, test user, department, action and detail.
- The current GitHub Pages build simulates users and permissions. Real enforcement, tamper-resistant audit history, remote uploads and notifications require authenticated backend roles and database policies.

## Job status dashboard

The at-a-glance path is:

**Quote → Acceptance → Site Measure → Production → Install / Dispatch → Invoicing**

Each stage shows complete, active or blocked state and a short explanation of what the job is waiting for. Mixed jobs require both Install and Dispatch completion before final invoicing.

The waiting panel remains yellow while work, missing information, a send-back or a management override request is open. It turns green only when the full workflow is complete.

## Account and non-account customers

Customer type is selected near the start of the Sales workflow:

- **Non-account customer:** acceptance creates the 75% pro forma pathway.
- **Approved account customer:** customer PO replaces pro forma/deposit confirmation.

Account customers can accept in the customer portal, enter their PO number and optionally attach a PDF. Acceptance may be completed without a PO, but Production stays blocked until the PO number is recorded. The office can also record or reopen the PO. In this static review build, attached PDFs are stored locally and limited to 2 MB.

## Revised quote and paid-deposit treatment

- Quotes state that pricing is estimated and subject to final site measure / inspection.
- A price or specification change after acceptance creates a revised quotation approval requirement and blocks Production until the customer approves it.
- The customer review shows the previous total, revised total, change and any deposit already received.
- If the 75% deposit has already been paid, AceDoors does **not** request another 75%. After revised approval, Accounts generates a **Variation / Updated Balance Notice** and carries the approved change into the remaining balance.
- The approval and commercial-document actions are recorded in the audit timeline.

## Quantities and travel

- Identical doors can use a door quantity from 1–99 instead of duplicating the full configuration.
- Accessory and installation-extra quantities are independent, so extra remotes or other parts can be quoted accurately.
- Door, motor, installation and freight prices multiply by door quantity; each option multiplies by its own quantity.
- Travel kilometres are entered once per job, not once per door.
- The selected Wiri or Rolleston branch is the route origin. **Open Route in Google Maps** opens directions to the site for review.
- The first 30 km remains free and travel pricing is applied once to an installed job. Master can record an override reason.
- Automatic kilometre retrieval remains deferred until a protected Maps/Routes integration is available; no unrestricted API key is embedded in the public page.

## Production safeguards and handover

Production follows the standard automatic sequence:

1. Released to Production
2. Production Sheets / Cut Sheets Created
3. Manufacture In Progress
4. Collecting Parts / Hardware
5. Quality Check
6. Rework when QC fails, or Ready for Install / Ready for Dispatch when QC passes

- The issued Production Pack has a revision number.
- Serial numbers are generated automatically by door quantity. A quantity line receives a serial range, the next included door continues the sequence, and serials never block Production.
- Master / Management can set the temporary prefix and starting number; the live starting sequence can be entered at go-live.
- Quote, site-measure, PO or factory-input changes after release mark the pack out of date and block manufacture/QC.
- Production or Master must explicitly **Reissue Production Pack** before work continues.
- QC still requires a Production Manager, Finished Door / Assembly photo and Parts / Hardware photo.
- QC approval creates quantity-aware Service or Dispatch routing.
- Install and Dispatch have their own required handover checklists. Accounts cannot finish invoicing until every required route is complete.

## Override requests

- Department users can select the affected door and request an override with a reason.
- The request reopens Site Measure in yellow and appears in the current-waiting summary.
- Only Master / Management can review technical warnings, approve or decline the request, and clear an existing override.
- The request, decision, named authoriser and reason are retained in the audit trail and production information.

## Documents and calculations

- Quote Print / Save PDF uses a compact A4 portrait layout with smaller margins, spacing and headers to reduce dead space.
- Production Print / Save PDF remains a compact A4 landscape cut sheet with up to five doors per printed comparison block.
- Door and accessory quantities appear on quotes, acceptance views, pro formas and production sheets.
- Pro formas retain revision snapshots and regeneration safeguards; paid jobs use a variation / updated-balance document after revised customer approval.
- `Urban SD Production Sheet(3).xlsx` continues to drive Urban production calculations.
- `RD Production Sheet (WIP)(1).xlsx` continues to drive Roller calculations.
- Undefined combinations show `ENGINEERING REVIEW`; Thermal remains on review until its production parameter sheet is supplied.

## Retained Site Measure rules

- Sales visits default to Sales Site — Pre-Quote Measure.
- Accepted jobs with confirmed deposit/PO move automatically to Final Production Measure.
- Rebate options remain Standard 100 × 100 × 25, accepted minimum 60 × 60 × 25, No Rebate, or Custom/Existing.
- No Rebate gives the finished-floor/water-ingress warning without becoming a hard blocker.
- Only the Opening photo is mandatory.
- Only Master / Management can approve or clear a named, reasoned technical override. Departments request review from the same management card.
