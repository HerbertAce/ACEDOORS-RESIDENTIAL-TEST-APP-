# v0.4.7 Test Focus

## Three-client / three-address test

1. Open **Residential Jobs** and confirm the existing v0.4.6 draft appears as its own job.
2. Complete the first record as `RES-000001`, Client A, with the first site address and at least one configured door.
3. Select **New Job** and confirm `RES-000002` opens as a clean job without changing the first job.
4. Enter Client B and the second site address, then select **New Job** again.
5. Enter Client C and the third site address. Confirm the dashboard now shows three different customers and addresses.
6. Open each job from the dashboard and confirm its customer, site, doors, quote state and workflow state return correctly.
7. Search using part of Client B's name, site address and job number. Confirm only matching jobs appear.
8. Attempt to change one job number to another active job's number. Confirm the change is rejected and the original number is restored.
9. Duplicate one of the configured jobs. Confirm it receives the next job number and retains the customer and door configuration.
10. Confirm the duplicated job has a blank site address and no acceptance, PO/payment, final-measure approval, Production release, QC or handover completion.
11. Archive the duplicated job. Confirm it leaves the normal job list and does not affect the three original jobs.
12. Select **Show archived jobs**, restore the duplicated job and confirm it can be opened again.
13. As a restricted Production user, confirm New, Duplicate, Archive and Restore are unavailable, while opening a job still respects the Production-only workspace.
14. Reload the page and confirm all jobs, addresses, statuses and the last-open job remain available.
15. Reset the currently open test quote and confirm the other saved and archived jobs remain unchanged.

## Retained v0.4.6 regression checks

## Department access, dashboard and audit

1. In the Job Command Center, enter a test user and select **Department User / Restricted** with Sales assigned. Confirm only Sales is visible.
2. Repeat for Technician / Service, Production, Install, Dispatch and Accounts / Invoicing. Confirm each user sees only the relevant workspace.
3. For Technician / Service, confirm Site Measure is visible before Production. After final measure approval and Production release, confirm Install also appears with scheduling open.
4. Confirm installation date, team and notes can be entered while Production is underway, but the completion checklist remains locked until QC passes.
5. Select **Master / All Departments** and confirm all six workspaces appear and the active department selector opens each workspace.
6. Confirm the top dashboard displays Quote, Acceptance, Site Measure, Production, Install/Dispatch and Invoicing with a short waiting reason.
7. Send the job back to another department with a reason. Confirm that department's Job Status stage reopens in yellow and **Currently waiting for** remains yellow.
8. As the requested department or Master, resolve the action and confirm both request and resolution appear in the audit timeline with user, department and time.
9. Confirm a different restricted department cannot resolve the action.

## Override request and management decision

10. As a restricted Technician / Service user, select an opening, enter a reason and request an override.
11. Confirm Site Measure reopens in yellow and the management-review reason appears in the waiting summary.
12. Confirm the management decision controls are hidden and a restricted user cannot approve the override directly.
13. Switch to Master, open the same door, record the authorised manager and decision, then approve the override.
14. Confirm the request changes to approved, the technical exception is recorded and the audit shows requester and decision.
15. Repeat with a second warning and decline it. Confirm the request remains traceable but does not create an active technical override.

## Customer purchasing path and portal

16. Select **Non-account — 75% pro forma** before generating a quote. Accept in the customer portal and confirm the pro forma pathway appears.
17. Confirm the quote clearly states **Estimated quotation — subject to final site measure / inspection**.
18. Select **Approved account — customer PO** and confirm the quote explains that a PO replaces the pro forma deposit.
19. Open the customer acceptance portal. Confirm payment path is read-only, the customer can enter a PO number and can optionally attach a PDF.
20. Accept without a PO. Confirm acceptance is recorded but Production remains blocked for the PO.
21. Accept with a PO. Confirm the office view records the PO and the commercial Production gate completes without generating a pro forma.
22. Upload a non-PDF or a PDF over 2 MB and confirm the static test build rejects it with an explanation.
23. Reopen a recorded PO after Production release and confirm the Production Pack becomes out of date.

## Revised quotation after payment

24. Complete non-account acceptance, generate the pro forma and confirm the original 75% deposit.
25. Change a priced item, quantity or final measured dimension. Confirm the quote becomes a revised quotation awaiting final customer approval.
26. Confirm Acceptance turns yellow, Production is blocked, and the customer view shows previous total, revised total, change, deposit received and revised remaining balance.
27. Confirm the customer message explicitly says no second 75% deposit is requested.
28. Approve the revised quotation through the customer link and sync it back to the office view.
29. Generate the next commercial document. Confirm it is **Variation / Updated Balance Notice**, its deposit due is zero and the paid deposit remains allocated.
30. Confirm the revised remaining balance equals revised total less the deposit already received.

## Door, accessory and travel quantities

31. Configure a door and set its quantity to 5. Confirm the quote shows `Qty 5`, while the common configuration is entered only once.
32. Confirm door, motor, installation or freight amounts multiply by 5.
33. Include two extra remotes and confirm only the remote line uses quantity 2.
34. Confirm door and option quantities appear in the customer portal, pro forma and Production Cut Sheet.
35. Select Wiri, enter a site address and open the Google Maps route. Repeat from Rolleston and confirm the route origin changes.
36. Enter 50 km one way on an installed job. Confirm travel is charged once at `(50 − 30) × 2 × 1.19`, not once per door.
37. Confirm supply-only jobs do not receive installation travel.
38. As a Department User, confirm the Master travel override reason is locked. As Master, enter a reason and confirm it is visible in the audit.

## Site Measure and production-pack reissue

39. Confirm the accepted/paid or PO-confirmed job moves from Pre-Quote Measure to Final Production Measure.
40. Complete final measure, including all checks and the Opening photo, and approve it.
41. Release the job to Production and issue the first Production Pack. Confirm Revision 1 is shown on the cut sheet.
42. Change colour, dimensions, quantity, fulfilment, approved site measure, PO, or a factory-controlled input after release.
43. Confirm a red **Production Pack is out of date** warning appears and manufacture/QC controls are blocked.
44. As Production or Master, select **Reissue Production Pack**. Confirm the revision increments and work unlocks.
45. As another restricted department, confirm pack reissue is refused.

## Automatic serial sequence

46. As Master, set a test prefix and starting number in **Override Requests & Management Review**.
47. Add a quantity-five door followed by a quantity-two door. Confirm the first receives a five-number range and the second continues with the next two numbers.
48. Confirm Production cannot type over the automatic serial and the field is labelled non-blocking.
49. Confirm a blank/test serial sequence never prevents Production release or manufacture.

## Production, Install, Dispatch and Invoicing

50. Complete cut sheets, four manufacture checks and four parts/hardware checks. Confirm automatic status changes through Sheets, Manufacture In Progress, Parts and Quality Check.
51. Confirm QC approval requires both photos and a Production Manager.
52. Fail QC with a reason. Confirm Rework and the reopened dimensions check, then complete it to return to Quality Check.
53. Pass QC for an installed door. Confirm Ready for Install and a quantity-aware Service Team route.
54. Complete all four install checks after QC. Confirm the Install handover completes.
55. Pass QC for a supply-only/freight door. Confirm Ready for Dispatch and a Dispatch route.
56. Enter dispatch date/carrier and complete all four dispatch checks. Confirm Dispatch completes.
57. For a mixed job, confirm Accounts remains blocked until both Install and Dispatch are complete.
58. Enter final invoice number/status, complete invoicing, and confirm the top dashboard shows the job complete.
59. Mark Production delayed without a reason and confirm it is blocked; add a reason, delay, then resume the calculated standard stage.

## Print and regression checks

60. Print / Save PDF from the quote. Confirm A4 portrait, compact header and spacing, readable content and substantially less blank space on the first page.
61. Print / Save PDF from Production. Confirm compact A4 landscape, Revision number, and the first matrix on page one.
62. Add ten included doors and confirm no fields are lost: screen comparison allows ten; print comparison uses doors 1–5 then 6–10.
63. Confirm Urban and Roller production calculations match the supplied workbooks and undefined/Thermal values remain `ENGINEERING REVIEW`.
64. Reload the page and confirm the v0.4.7 job list persists. Confirm an existing v0.4.6 single draft migrates into the dashboard and older v0.4.5/v0.4.4 drafts remain recoverable.
65. Confirm photo previews, Terms acceptance, commercial-document regeneration, rebate warnings and management overrides behave as described above.

## Static review-build limitation

The permission selectors are a workflow prototype, not a security boundary. Do not treat the GitHub Pages build as a production access-control system. Live release requires authenticated users, backend role policies, server-side audit history, document storage, notification delivery and a protected routing integration.
