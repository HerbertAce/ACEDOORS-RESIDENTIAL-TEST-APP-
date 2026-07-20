# AceDoors Residential v0.4.5

Flat GitHub Pages review release for department workflow, account-customer purchasing, quantities, travel and compact documents.

## Department workflow and permissions

The top **Job Command Center** shows the job’s current position, the reason it is waiting, any open inter-department action, and the audit timeline.

| Department | Normal workspace | Release condition |
|---|---|---|
| Sales | Quote, acceptance and commercial setup | Customer acceptance plus deposit or PO pathway |
| Technician / Service | Final Site Measure | Install workspace appears after Production QC passes |
| Production | Release, cut sheets, manufacture, parts and QC | Ready for Install and/or Ready for Dispatch |
| Install | Installation handover | Available only for jobs containing installed doors after QC |
| Dispatch | Dispatch handover | Available only for supply-only/freight doors after QC |
| Accounts / Invoicing | Final invoice and close-out | Available after all required Install/Dispatch handovers |

- Department users see only their authorised workspace; Master users can open every department and change the active workspace.
- Any department can request action from another department, including a reason. The requested department or Master can resolve it.
- Auditable workflow events record the time, test user, department, action and detail.
- The current GitHub Pages build simulates users and permissions. Real enforcement, tamper-resistant audit history, remote uploads and notifications require authenticated backend roles and database policies.

## Job status dashboard

The at-a-glance path is:

**Quote → Acceptance → Site Measure → Production → Install / Dispatch → Invoicing**

Each stage shows complete, active or blocked state and a short explanation of what the job is waiting for. Mixed jobs require both Install and Dispatch completion before final invoicing.

## Account and non-account customers

Customer type is selected near the start of the Sales workflow:

- **Non-account customer:** acceptance creates the 75% pro forma pathway.
- **Approved account customer:** customer PO replaces pro forma/deposit confirmation.

Account customers can accept in the customer portal, enter their PO number and optionally attach a PDF. Acceptance may be completed without a PO, but Production stays blocked until the PO number is recorded. The office can also record or reopen the PO. In this static review build, attached PDFs are stored locally and limited to 2 MB.

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
- Quote, site-measure, PO or factory-input changes after release mark the pack out of date and block manufacture/QC.
- Production or Master must explicitly **Reissue Production Pack** before work continues.
- QC still requires a Production Manager, Finished Door / Assembly photo and Parts / Hardware photo.
- QC approval creates quantity-aware Service or Dispatch routing.
- Install and Dispatch have their own required handover checklists. Accounts cannot finish invoicing until every required route is complete.

## Documents and calculations

- Quote Print / Save PDF uses a compact A4 portrait layout with smaller margins, spacing and headers to reduce dead space.
- Production Print / Save PDF remains a compact A4 landscape cut sheet with up to five doors per printed comparison block.
- Door and accessory quantities appear on quotes, acceptance views, pro formas and production sheets.
- Pro formas retain the v0.4.4 revision snapshot and regeneration safeguards.
- `Urban SD Production Sheet(3).xlsx` continues to drive Urban production calculations.
- `RD Production Sheet (WIP)(1).xlsx` continues to drive Roller calculations.
- Undefined combinations show `ENGINEERING REVIEW`; Thermal remains on review until its production parameter sheet is supplied.

## Retained Site Measure rules

- Sales visits default to Sales Site — Pre-Quote Measure.
- Accepted jobs with confirmed deposit/PO move automatically to Final Production Measure.
- Rebate options remain Standard 100 × 100 × 25, accepted minimum 60 × 60 × 25, No Rebate, or Custom/Existing.
- No Rebate gives the finished-floor/water-ingress warning without becoming a hard blocker.
- Only the Opening photo is mandatory.
- Admin/Master or Production Manager can record a named, reasoned technical override.
