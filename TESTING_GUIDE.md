# v0.4.4 Test Focus

## Pro forma revisions

1. Build an accepted non-account quote containing:
   - Garage 1: Urban Sandringham, 2100H × 3500W, Titania.
   - Garage 2: Urban Sandringham, 2590H × 4100W, Lignite.
2. Generate the 75% pro forma and confirm both descriptions appear under **What you are purchasing**.
3. Confirm included accessories or installation extras appear below the relevant door.
4. Mark the pro forma sent, then change a colour, size or included option.
5. Confirm the status changes to **Regeneration Required**, the previous revision remains visible, and Print / Resend are disabled.
6. Regenerate and confirm the new document shows Revision 2 and an invoice number ending `-DEP-R2`.
7. Mark the revision sent, add another included part and repeat. Confirm Revision 3 can be generated and resent.
8. If the deposit was already confirmed, confirm that payment confirmation remains recorded after regeneration.

## Site Measure

9. Before payment, confirm Visit Type is **Sales Site — Pre-Quote Measure**.
10. After acceptance and payment/PO, confirm it changes automatically to **Final Production Measure**.
11. Confirm Backroom is absent and the four rebate choices remain available.
12. Select No Rebate and confirm the finished-floor/water-ingress warning appears without blocking approval.
13. Enter technician/date, dimensions, fixing type and all eight checks. Confirm only the Opening photo is mandatory.
14. Approve the final measure and confirm Production unlocks when the other release gates are complete.
15. Confirm every Site Measure card and the Site Measure Summary can be collapsed and reopened without losing data.

## Production sequence

16. Release a ready job and confirm the status is **Released to Production**.
17. Confirm manufacture and parts controls are locked until **Production sheets / cut sheets created and issued to factory** is checked.
18. Check that milestone and confirm status becomes **Production Sheets / Cut Sheets Created**.
19. Start a door-manufacture check and confirm status becomes **Manufacture In Progress**.
20. Complete all four manufacture checks and confirm status becomes **Collecting Parts / Hardware**.
21. Complete all four parts/hardware checks and confirm status becomes **Quality Check**.
22. Confirm QC approval is blocked until both required photos and a Production Manager name are present.
23. Fail QC with a reason and confirm status becomes **Rework** and Production dimensions checked reopens.
24. Complete the reopened check and confirm the job returns to **Quality Check**.
25. Pass QC on an installed door and confirm status becomes **Ready for Install** with Service Team routing.
26. Repeat with a supply-only/freight door and confirm **Ready for Dispatch** with Dispatch routing.
27. Enter a delay reason, mark the job Delayed, then resume. Confirm it returns to the correct calculated stage.
28. Confirm each Production card and Production Control can be collapsed and reopened.
29. Load a saved v0.4.3 job with all eight checks complete. Confirm it reconciles to Quality Check rather than remaining at Manufacture In Progress.

## Cut-sheet print layout

30. Open the Production Sheets / Cut Sheets card and select Print / Save PDF.
31. Confirm A4 landscape is selected with a compact header and the first production matrix begins on page one.
32. Confirm a two-door job no longer produces a mostly blank front page.
33. Add ten included doors and confirm doors 1–5 print in the first matrix and doors 6–10 start on the next deliberate page block.
34. Confirm no production fields are lost and table text remains readable.

## Calculation and regression checks

35. For a 2200H × 3000W Urban final DLO, confirm 2210H × 3060W production size, 4 panels, 552.5 mm panel height, 12 muntins, 8 endcaps, 2 struts, 3.05 m strut length, 2.4 m track set, 3340 mm torsion pole and 7.8 m mohair.
36. With insulation selected, confirm `12 @ 748 × 535 mm` and `4 @ 803 × 535 mm`.
37. Confirm undefined six-panel spring combinations remain marked `ENGINEERING REVIEW`.
38. Confirm Thermal remains on engineering review pending its parameter sheet.
39. For an A-Series Roller Door at 2500H × 2800W, confirm 2880 mm curtain cut length, 3280 mm axle and 2800 mm guides.
40. Confirm blank doors do not create installation pricing, acceptance still syncs, lifting equipment remains on customer documents, and photo previews appear promptly.
