# v0.4.1 Test Focus

1. Open the build and confirm Customer Acceptance is empty on a fresh quote.
2. Complete one installed Urban door, generate the quote and mark it sent.
3. Use Preview Customer Acceptance and confirm the customer portal opens.
4. Accept in the portal, return to the office view and confirm acceptance syncs. Confirm View Client Portal and Reset Acceptance Test are available afterward.
5. Before payment, open Site Measure and confirm Visit Type shows Sales Site — Pre-Quote Measure.
6. Confirm payment/PO, return to Site Measure and confirm Visit Type automatically changes to Final Production Measure and is locked to the workflow stage.
7. Confirm Backroom is absent and the four rebate choices are available.
8. Select No Rebate and confirm the finished-floor/water-ingress warning appears but does not create a hard blocker.
9. Enter technician/date, dimensions, fixing type and all eight checks. Confirm approval remains blocked until an Opening photo is captured.
10. Capture Opening only. Confirm optional photos remain incomplete but Overall Completion can reach 100%.
11. Click Approve Final Measure for Production and confirm the door becomes approved and Production unlocks when the other gates are complete.
12. Create a short-sideroom/headroom warning. Confirm an override requires an authorised name and reason, then allows final approval without bypassing acceptance, payment, site checks or Opening photo.
13. Confirm the override and rebate condition appear in Factory Handover.
14. Confirm Urban production size uses DLO +10H / +60W and Thermal uses DLO height / +70W.
15. Confirm Roller production parameters remain marked TBC.

Regression checks:
- Blank doors must not create installation pricing.
- Same-browser digital acceptance must still sync and prepare the non-account pro forma.
- Lifting equipment must remain visible on customer documents when included.
