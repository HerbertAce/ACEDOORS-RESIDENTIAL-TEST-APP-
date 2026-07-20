# v0.4.8 Test Focus

## Three-client / three-address test

1. Open **Home Dashboard · Residential Jobs** and confirm existing v0.4.7 jobs appear separately with summary counts.
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

## v0.4.8 Service Coordination, technician visibility and Settings

1. As Master, open **Service Coordination** and allocate the first job to `Tech A`, including client contacted, ready site and a scheduled measure date.
2. Switch to a Department user assigned to Technician / Service with the exact test user name `Tech A`. Confirm the allocated job is visible.
3. Change the test user to `Tech B`. Confirm Tech A's job disappears and only jobs specifically allocated to Tech B are shown.
4. Switch to Service Coordination. Confirm it sees only the coordination workspace and can save client/site readiness, proposed dates and technician-support notes.
5. Confirm Installation Coordination stays locked until Final Measure is approved and the job is released to Production.
6. During Production, complete an installation proposal. Confirm it remains yellow/in progress and cannot be finally booked yet.
7. Confirm the Admin/Cost card is no longer in Sales. Open **Settings** as Master and confirm Roller cost controls and the missing-pricing-information checklist are present.
8. Switch to any Department user. Confirm Settings is hidden and a direct cost-change attempt is refused.
9. Complete a quote card and confirm it auto-collapses. Reopen it and confirm the information is retained.
10. Confirm every department tab uses green **Complete** or yellow missing/in-progress wording.

## Department access, dashboard and audit

1. In the Job Command Center, enter a test user and select **Department User / Restricted** with Sales assigned. Confirm only Sales is visible.
2. Repeat for Service Coordination, Technician / Service, Production, Install, Dispatch and Accounts / Invoicing. Confirm each user sees only the relevant workspace.
3. For Technician / Service, confirm Site Measure is visible before Production. After final measure approval and Production release, confirm Install also appears for the allocated technician.
4. Confirm Service Coordination can record a proposed installation date while Production is underway, but final booking and the Install checklist remain locked until QC and the remaining-balance gate are complete.
5. Select **Master / All Departments** and confirm all eight workspaces appear, including Service Coordination and Settings.
6. Confirm the top dashboard displays Quote, Acceptance, Service Coordination, Site Measure, Production, Install/Dispatch and Invoicing with a short waiting reason.
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
33. Include extra remotes, use the visible minus/plus controls to set quantity 6, and confirm only the remote line uses quantity 6.
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
54. For a non-account installed job, confirm Install remains blocked after QC until Accounts records the remaining 25% invoice (including any approved additions).
55. Complete the Service Coordination proposal, record the balance invoice as issued, and confirm the installation booking. Confirm the Install checklist now unlocks.
56. Complete all four install checks and confirm the Install handover completes.
57. Pass QC for a supply-only/freight door. Confirm Ready for Dispatch and a Dispatch route, but confirm release is blocked until the remaining balance invoice is issued.
58. Enter dispatch date/carrier and complete all four dispatch checks. Confirm Dispatch completes.
59. For a mixed job, confirm final Accounts close-out remains blocked until both Install and Dispatch are complete.
60. Enter final invoice number/status, complete invoicing, and confirm the top dashboard shows the job complete.
61. Mark Production delayed without a reason and confirm it is blocked; add a reason, delay, then resume the calculated standard stage.

## Print and regression checks

62. Print / Save PDF from the quote. Confirm A4 portrait, compact header and spacing, readable content and substantially less blank space on the first page.
63. Print / Save PDF from Production. Confirm compact A4 landscape, Revision number, and the first matrix on page one.
64. Add ten included doors and confirm no fields are lost: screen comparison allows ten; print comparison uses doors 1–5 then 6–10.
65. Confirm Urban and Roller production calculations match the supplied workbooks and undefined/Thermal values remain `ENGINEERING REVIEW`.
66. Reload the page and confirm the v0.4.8 job list persists. Confirm an existing v0.4.7 multi-job store migrates with all jobs and older single-job drafts remain recoverable.
67. Confirm photo previews, Terms acceptance, commercial-document regeneration, rebate warnings and management overrides behave as described above.

## Static review-build limitation

The permission selectors are a workflow prototype, not a security boundary. Do not treat the GitHub Pages build as a production access-control system. Live release requires authenticated users, backend role policies, server-side audit history, document storage, notification delivery and a protected routing integration.
