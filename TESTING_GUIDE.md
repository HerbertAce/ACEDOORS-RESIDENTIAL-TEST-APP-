# v0.4.2 Test Focus

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
13. Confirm the override and rebate condition appear in the Production Cut Sheet.
14. Confirm Urban production size uses DLO +10H / +60W and Thermal uses DLO height / +70W.
15. Add an A-Series Roller Door and confirm the cut sheet includes curtain sheet mix, sheet cut length, spring selection, axle cut length and guide cut length.
16. Confirm Target Production Start defaults to today and Estimated Ready / Dispatch defaults to 21 days later.
17. Release the job and confirm the initial status is New Job Manufacture. Change it to Manufacture In Progress.
18. Enter a delay reason and confirm Delayed can be selected. Clear the reason and confirm Delayed is blocked.
19. Complete all eight factory checks and confirm status automatically changes to Quality Check.
20. Confirm QC approval is blocked until both Finished Door / Assembly and Parts / Hardware photos are captured and a Production Manager name is entered.
21. Fail QC with a reason. Confirm the job returns to Manufacture In Progress and the dimension check reopens. Complete it again to return to Quality Check.
22. Approve QC and confirm Factory Complete is selected automatically.
23. For an installed door, confirm Service Team routing is created. For supply-only/freight, confirm Dispatch routing is created.
24. Confirm the Sectional cut sheet contains every requested field and clearly holds its calculated values for the missing Urban SD parameter sheet.

Regression checks:
- Blank doors must not create installation pricing.
- Same-browser digital acceptance must still sync and prepare the non-account pro forma.
- Lifting equipment must remain visible on customer documents when included.
- Site and QC photo previews should appear promptly as `blob:` object previews without freezing the production document.
- A-Series 2500H × 2800W should produce 5 × A-Sheets, 2880 mm curtain cut length, 3280 mm axle and 2800 mm guides.
