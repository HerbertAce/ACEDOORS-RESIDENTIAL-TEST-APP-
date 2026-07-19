# AceDoors Residential v0.4.2

Flat GitHub Pages test release.

This build keeps the v0.3.0 quote, pricing and digital-acceptance fixes and restores the later workflow work recovered from TB3.4.

Production and QC corrections in v0.4.2:
- Site and QC photos now use fast browser object previews instead of slow base64 conversion and full production rerenders.
- Released By Role is read-only in this prototype and ready to be populated from the signed-in user/department.
- Target Production Start defaults to today and Estimated Ready / Dispatch defaults to 21 days later.
- Production statuses are New Job Manufacture, Manufacture In Progress, Quality Check, Factory Complete and Delayed.
- Completing all eight factory checks automatically moves the job to Quality Check.
- QC requires a Production Manager, a Finished Door / Assembly photo and a Parts / Hardware photo.
- QC approval automatically selects Factory Complete.
- QC failure records the reason, returns the job to Manufacture In Progress and reopens the dimension check.
- Factory Complete creates a Service Team routing record for installed doors and a Dispatch routing record for supply-only/freight doors.
- Delayed status requires a reason and next action.
- The Production Cut Sheet now shows every requested Sectional production field.
- Roller A-Series and B-Series sheets, curtain cut length, axle, guides and spring lookup use `RD Production Sheet (WIP)(1).xlsx`.
- Sectional panel, muntin, endcap, strut, insulation, hardware-kit, extra-height-kit, cable, torsion, spring and mohair results remain on hold until the Urban SD production parameter sheet is supplied.

Review corrections retained from v0.4.1:
- New test quotes no longer import stale acceptance data from an earlier build or quote link.
- The client portal can be reopened after acceptance and acceptance can be reset for testing.
- Sales visits default to Sales Site — Pre-Quote Measure.
- Accepted jobs with confirmed deposit/PO automatically pass to the technician as Final Production Measure.
- Backroom has been removed from the current measure form.
- Rebate choices are Standard 100 × 100 × 25, accepted minimum 60 × 60 × 25, No Rebate, or Custom/Existing.
- No Rebate creates a prominent finished-floor and possible water-ingress warning without blocking approval.
- Only the Opening photo is mandatory; the other six photo prompts are optional.
- Final-measure approval now uses a reliable button and the measurement-state bug that prevented approval has been fixed.
- Admin/Master or Production Manager can record a named, reasoned technical override for dimension or clearance warnings.
- Overrides remain visible in the Factory Handover.
- Technical overrides remain the current v0.4.1 prototype pending operational feedback.

New workflow:
- Quote and acceptance remains the first stage.
- Site Measure supports multiple doors, DLO measurements, clearances, eight site checks, seven photo prompts and final-measure approval.
- Urban production size is DLO +10 mm height / +60 mm width.
- Thermal production size is DLO height / +70 mm width.
- Roller production calculations use the supplied WIP lookup charts within the current A-Series and B-Series limits.
- Production release is blocked until acceptance, payment/PO, technical details and all required final measures are complete.
- Only Admin/Master or Production Manager roles are presented for release.
- The Production Cut Sheet excludes customer terms and payment clutter.
- Changes to critical job information after release are flagged.

Cross-device customer acceptance still requires a shared backend/database.
Photo previews remain session-only, while the captured-photo record is retained in the local test draft.
Roller spring selections are sourced from the supplied WIP chart. Final Sectional calculations still require the approved Urban SD production rules.
