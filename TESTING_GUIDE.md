# v0.4.3 Test Focus

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
13. Confirm the override and rebate condition appear in the Production Cut Sheet matrix.
14. Confirm Urban production size uses DLO +10H / +60W and Thermal uses DLO height / +70W.
15. For a 2200H × 3000W Urban final DLO, confirm the cut sheet shows 2210H × 3060W production size, 4 panels, 552.5 mm panel height, 12 muntins, 8 endcaps, 2 struts, 3.05 m strut length, 2.4 m track set, 3340 mm torsion pole and 7.8 m mohair.
16. Select insulation for that door and confirm the two insulation rows show `12 @ 748 × 535 mm` and `4 @ 803 × 535 mm`.
17. Enter Serial Number, Extra Weight and Extra Detail & Notes in Door Production Inputs; confirm all three flow into the correct door column.
18. Add ten included Urban doors. Confirm the on-screen cut sheet retains the familiar doors 1–10 comparison matrix with horizontal scrolling and no missing rows.
19. Print / Save PDF and confirm A4 landscape is selected, doors 1–5 appear in the first block, doors 6–10 start on a new page and the text remains legible.
20. Configure an Urban door requiring six panels. Confirm available cut values remain visible and Springs / Extra CBB are marked ENGINEERING REVIEW because the supplied workbook has no six-panel hardware weight.
21. Add a Thermal door and confirm its calculated fields remain on ENGINEERING REVIEW pending a Thermal parameter sheet.
22. Add an A-Series Roller Door and confirm its separate matrix includes curtain sheet mix, sheet cut length, spring selection, axle cut length and guide cut length.
23. Confirm Target Production Start defaults to today and Estimated Ready / Dispatch defaults to 21 days later.
24. Release the job and confirm the initial status is New Job Manufacture. Change it to Manufacture In Progress.
25. Enter a delay reason and confirm Delayed can be selected. Clear the reason and confirm Delayed is blocked.
26. Complete all eight factory checks and confirm status automatically changes to Quality Check.
27. Confirm QC approval is blocked until both Finished Door / Assembly and Parts / Hardware photos are captured and a Production Manager name is entered.
28. Fail QC with a reason. Confirm the job returns to Manufacture In Progress and the dimension check reopens. Complete it again to return to Quality Check.
29. Approve QC and confirm Factory Complete is selected automatically.
30. For an installed door, confirm Service Team routing is created. For supply-only/freight, confirm Dispatch routing is created.

Regression checks:
- Blank doors must not create installation pricing.
- Same-browser digital acceptance must still sync and prepare the non-account pro forma.
- Lifting equipment must remain visible on customer documents when included.
- Site and QC photo previews should appear promptly as `blob:` object previews without freezing the production document.
- A-Series 2500H × 2800W should produce 5 × A-Sheets, 2880 mm curtain cut length, 3280 mm axle and 2800 mm guides.
