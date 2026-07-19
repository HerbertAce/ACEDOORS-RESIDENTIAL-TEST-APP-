# AceDoors Residential v0.4.1

Flat GitHub Pages test release.

This build keeps the v0.3.0 quote, pricing and digital-acceptance fixes and restores the later workflow work recovered from TB3.4.

Review corrections in v0.4.1:
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
- Roller production parameters remain TBC pending Jamie's information.

New workflow:
- Quote and acceptance remains the first stage.
- Site Measure supports multiple doors, DLO measurements, clearances, eight site checks, seven photo prompts and final-measure approval.
- Urban production size is DLO +10 mm height / +60 mm width.
- Thermal production size is DLO height / +70 mm width.
- Roller production size remains clearly marked as a factory calculation.
- Production release is blocked until acceptance, payment/PO, technical details and all required final measures are complete.
- Only Admin/Master or Production Manager roles are presented for release.
- Factory Handover excludes customer terms and payment clutter.
- Changes to critical job information after release are flagged.

Cross-device customer acceptance still requires a shared backend/database.
Photo previews remain session-only, while the captured-photo record is retained in the local test draft.
Final spring, strut, panel, muntin and cut-sheet calculations still require approved factory rules.
