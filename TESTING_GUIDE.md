# v0.4.0 Test Focus

1. Complete one installed Urban door through quote generation, send, acceptance and payment confirmation.
2. Open Site Measure and confirm the quoted door and DLO values carry through.
3. Select Final Production Measure, enter technician/date, opening clearances and fixing type, then complete all eight checks.
4. Confirm approval remains blocked until every required measure item is complete.
5. Approve the measure and apply it to the quote door. Confirm Urban production size uses DLO +10H / +60W.
6. Add an installed Thermal door and confirm production size uses DLO height / +70W.
7. Confirm each installed door requires its own approved final measure before production release.
8. Confirm supply-only doors do not require a final measure.
9. Open Production & Handover. Confirm release remains blocked until acceptance, payment/PO, technical details and final measures are complete.
10. Enter an authorised name, release the job, and confirm Factory Handover contains production details but no T&Cs or payment content.
11. Change a critical door detail after release and confirm the production-change warning appears.
12. Confirm Factory Complete cannot be selected until all eight factory checks are complete.

Regression checks:
- Blank doors must not create installation pricing.
- Same-browser digital acceptance must still sync and prepare the non-account pro forma.
- Lifting equipment must remain visible on customer documents when included.
