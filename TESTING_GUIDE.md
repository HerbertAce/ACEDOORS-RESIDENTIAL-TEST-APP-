# v0.4.5 Test Focus

## Department access, dashboard and audit

1. In the Job Command Center, enter a test user and select **Department User / Restricted** with Sales assigned. Confirm only Sales is visible.
2. Repeat for Technician / Service, Production, Install, Dispatch and Accounts / Invoicing. Confirm each user sees only the relevant workspace.
3. For Technician / Service, confirm Site Measure is visible before Production and Install becomes visible only after QC passes for an installed job.
4. Select **Master / All Departments** and confirm all six workspaces appear and the active department selector opens each workspace.
5. Confirm the top dashboard displays Quote, Acceptance, Site Measure, Production, Install/Dispatch and Invoicing with a short waiting reason.
6. Send the job back to another department with a reason. Confirm the open action appears at the top.
7. As the requested department or Master, resolve the action and confirm both request and resolution appear in the audit timeline with user, department and time.
8. Confirm a different restricted department cannot resolve the action.

## Customer purchasing path and portal

9. Select **Non-account — 75% pro forma** before generating a quote. Accept in the customer portal and confirm the pro forma pathway appears.
10. Select **Approved account — customer PO** and confirm the quote explains that a PO replaces the pro forma deposit.
11. Open the customer acceptance portal. Confirm payment path is read-only, the customer can enter a PO number and can optionally attach a PDF.
12. Accept without a PO. Confirm acceptance is recorded but Production remains blocked for the PO.
13. Accept with a PO. Confirm the office view records the PO and the commercial Production gate completes without generating a pro forma.
14. Upload a non-PDF or a PDF over 2 MB and confirm the static test build rejects it with an explanation.
15. Reopen a recorded PO after Production release and confirm the Production Pack becomes out of date.
16. For a non-account customer, generate, send, revise and regenerate the pro forma. Confirm revision numbers and the v0.4.4 stale-document safeguards still work.

## Door, accessory and travel quantities

17. Configure a door and set its quantity to 5. Confirm the quote shows `Qty 5`, while the common configuration is entered only once.
18. Confirm door, motor, installation or freight amounts multiply by 5.
19. Include two extra remotes and confirm only the remote line uses quantity 2.
20. Confirm door and option quantities appear in the customer portal, pro forma and Production Cut Sheet.
21. Select Wiri, enter a site address and open the Google Maps route. Repeat from Rolleston and confirm the route origin changes.
22. Enter 50 km one way on an installed job. Confirm travel is charged once at `(50 − 30) × 2 × 1.19`, not once per door.
23. Confirm supply-only jobs do not receive installation travel.
24. As a Department User, confirm the Master override reason is locked. As Master, enter a reason and confirm it is visible in the audit.

## Site Measure and production-pack reissue

25. Confirm the accepted/paid or PO-confirmed job moves from Pre-Quote Measure to Final Production Measure.
26. Complete final measure, including all checks and the Opening photo, and approve it.
27. Release the job to Production and issue the first Production Pack. Confirm Revision 1 is shown on the cut sheet.
28. Change colour, dimensions, quantity, fulfilment, approved site measure, PO, or a factory-controlled input after release.
29. Confirm a red **Production Pack is out of date** warning appears and manufacture/QC controls are blocked.
30. As Production or Master, select **Reissue Production Pack**. Confirm the revision increments and work unlocks.
31. As another restricted department, confirm pack reissue is refused.

## Production, Install, Dispatch and Invoicing

32. Complete cut sheets, four manufacture checks and four parts/hardware checks. Confirm automatic status changes through Sheets, Manufacture In Progress, Parts and Quality Check.
33. Confirm QC approval requires both photos and a Production Manager.
34. Fail QC with a reason. Confirm Rework and the reopened dimensions check, then complete it to return to Quality Check.
35. Pass QC for an installed door. Confirm Ready for Install and a quantity-aware Service Team route.
36. Enter install date/team and complete all four install checks. Confirm the Install handover completes.
37. Pass QC for a supply-only/freight door. Confirm Ready for Dispatch and a Dispatch route.
38. Enter dispatch date/carrier and complete all four dispatch checks. Confirm Dispatch completes.
39. For a mixed job, confirm Accounts remains blocked until both Install and Dispatch are complete.
40. Enter final invoice number/status, complete invoicing, and confirm the top dashboard shows the job complete.
41. Mark Production delayed without a reason and confirm it is blocked; add a reason, delay, then resume the calculated standard stage.

## Print and regression checks

42. Print / Save PDF from the quote. Confirm A4 portrait, compact header and spacing, readable content and substantially less blank space on the first page.
43. Print / Save PDF from Production. Confirm compact A4 landscape, Revision number, and the first matrix on page one.
44. Add ten included doors and confirm no fields are lost: screen comparison allows ten; print comparison uses doors 1–5 then 6–10.
45. Confirm Urban and Roller production calculations match the supplied workbooks and undefined/Thermal values remain `ENGINEERING REVIEW`.
46. Reload the page and confirm the v0.4.5 draft persists. Confirm an existing v0.4.4 local draft still migrates.
47. Confirm photo previews, Terms acceptance, quote/pro forma regeneration, rebate warnings and technical overrides still behave as in v0.4.4.

## Static review-build limitation

The permission selectors are a workflow prototype, not a security boundary. Do not treat the GitHub Pages build as a production access-control system. Live release requires authenticated users, backend role policies, server-side audit history, document storage, notification delivery and a protected routing integration.
