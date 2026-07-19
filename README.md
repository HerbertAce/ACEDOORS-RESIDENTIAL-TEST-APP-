# AceDoors Residential v0.4.4

Flat GitHub Pages review release.

## v0.4.4 changes

### Revisable pro forma invoices

- Every included door is described on the pro forma, for example `Garage 1 — Urban Sandringham 2100H × 3500W — Titania`.
- Included accessories and installation extras are listed below the relevant door.
- A generated pro forma is stored as a revision snapshot so its description and amount do not silently change afterward.
- Changes to doors, sizes, colours, options, customer/site details or pricing flag the current pro forma as out of date.
- Printing and resending are blocked until the revised pro forma is regenerated.
- Revised invoices receive a revision number and invoice suffix such as `-DEP-R2`; each revision can then be marked as sent or resent.
- Confirmed payment is retained when a later commercial change requires a revised invoice.

### Standard production process

Production status is now automatic and follows the page from top to bottom:

1. Released to Production
2. Production Sheets / Cut Sheets Created
3. Manufacture In Progress
4. Collecting Parts / Hardware
5. Quality Check
6. Rework when QC fails, or Ready for Install / Ready for Dispatch when QC passes

- Later-stage controls remain locked until the preceding stage is complete.
- Restored v0.4.3 jobs with all eight factory checks already complete are reconciled automatically to Quality Check instead of remaining stuck at Manufacture In Progress.
- QC failure records the reason, changes status to Rework and reopens the production-dimension check.
- Completing the rework returns the job to Quality Check.
- QC still requires a Production Manager, a Finished Door / Assembly photo and a Parts / Hardware photo.
- QC approval creates Service Team routing for installed doors and Dispatch routing for supply-only/freight doors.
- Delayed is an exception state requiring a reason and next action; Resume Standard Process returns the job to its calculated stage.

### Layout and cut-sheet printing

- Production cards are ordered to match the factory process and are collapsible.
- Site Measure cards and both workflow summary panels are collapsible.
- The production cut sheet is now the first factory stage rather than a document at the bottom of the page.
- Print / Save PDF uses a compact A4 landscape layout with smaller margins, header and table spacing.
- The first matrix can begin on page one instead of being pushed to a mostly blank front page.
- Up to five doors remain grouped per printed matrix; larger jobs continue on deliberate page breaks without losing fields.

## Production cut-sheet calculations retained

- `Urban SD Production Sheet(3).xlsx` drives Urban panel count and height, muntins, endcaps, struts, insulation cuts, hardware kit, extra-height kit, cable, track, torsion pole, springs, extra CBB and mohair.
- Urban production size uses final DLO +10 mm height / +60 mm width.
- Roller calculations use `RD Production Sheet (WIP)(1).xlsx`.
- Sectional and Roller doors use separate production matrices.
- Serial Number, Extra Weight and Extra Detail & Notes are factory-controlled inputs.
- Undefined workbook combinations show `ENGINEERING REVIEW` rather than an invented value.
- Thermal calculations remain on engineering review until a Thermal production parameter sheet is supplied.

## Site Measure rules retained

- Sales visits default to Sales Site — Pre-Quote Measure.
- Accepted jobs with confirmed deposit/PO automatically move to Final Production Measure.
- Rebate choices are Standard 100 × 100 × 25, accepted minimum 60 × 60 × 25, No Rebate, or Custom/Existing.
- No Rebate displays a finished-floor and possible water-ingress warning without becoming a hard blocker.
- Only the Opening photo is mandatory.
- Admin/Master or Production Manager can record a named, reasoned technical override for warnings.

Cross-device customer acceptance and real team notifications still require the shared backend/database. Photo previews remain session-only, while captured-photo records remain in the local test draft. All engineering-review results must be resolved before manufacture.
