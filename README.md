
# Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer

ServiceNow System Administrator capstone project for Naan Mudhalvan (SmartBridge).

## Team

- Ramya Dheekshitha S
- Divya Dharshini K V

Team ID: SWTID-2026-3758

## Project summary

This project automates the configuration step of standard laptop procurement in ServiceNow so that approved requests no longer depend on someone remembering to raise a task. A Flow Designer flow named "Standard laptop task" is attached to the Standard Laptop catalog item (Hardware category) through its Process Engine tab. The flow uses a Service Catalog trigger and a Create Catalog Task action built on the Requested Item record. The task is created with the short description and description "Laptop need to Configured", Assignment group Hardware and Approval set to Approved, so it only applies to approved requests.

The result is shown in the project screenshots. A Standard Laptop order that is approved produces a Catalog Task (SCTASK0010001) linked to the Requested Item (RITM0010001), already described and assigned to the Hardware group. The three UAT test cases (place order, approve, verify Catalog Task) are defined but still marked Pending in the source documents.

- Instance: dev449683.service-now.com (ServiceNow Personal Developer Instance)
- Build date: 30 September 2026 (Catalog Task creation timestamp in the screenshots)
- Documentation date: 03 October 2026

## Phase-wise submission (SmartInternz format)

| Phase | File | Deliverables |
|-------|------|--------------|
| 1 | 1_Ideation_Phase_.pdf | Brainstorm and Idea Prioritization, Define Problem Statements, Empathy Map |
| 2 | 2_Requirement_Analysis.pdf | Customer Journey Map, Data Flow Diagram and User Stories, Solution Requirements, Technology Stack |
| 3 | 3_Project_Design_Phase_doc.pdf | Problem-Solution Fit, Proposed Solution, Solution Architecture |
| 4 | 4_Project_Planning_Phase.pdf | Product Backlog, Sprint Planning, Story Points, Velocity, Burndown Chart |
| 5 | 5_Project_Development_Phase.pdf | Model Performance Test, Implementation Screenshots, User Acceptance Testing (UAT) Template |
| 6 | 6_Project_Documentation.pdf | Full project report: overview, results, advantages and disadvantages, conclusion, future scope, appendix |

## Supporting evidence

- Output screenshots in `6_Project_Documentation.pdf` and `5_Project_Development_Phase.pdf` show the flow, the catalog item's Process Engine setting and the generated Catalog Task.
- Demo video: https://drive.google.com/file/d/1yuwkocNTxJAjUa95f2rkNSqutQJBPrYM/view?usp=sharing
- GitHub: https://github.com/ramyasankar22/naan_mudhalvan
- No source code or dataset is involved. The solution is configured entirely in ServiceNow Flow Designer.

## Planning snapshot

| Sprint | Epics | Story points | Planned dates |
|--------|-------|--------------|---------------|
| Sprint 1 | Flow Creation | 12 | 02 Oct 2026 to 07 Oct 2026 |
| Sprint 2 | Flow Assignment, Service Catalog Ordering and Approval | 11 | 08 Oct 2026 to 13 Oct 2026 |

Total 23 story points, planned velocity 11.5 story points per sprint.

## How to reproduce

1. Make sure the Standard Laptop catalog item (Hardware category), its approval process and a Hardware assignment group exist.
2. Open Flow Designer and create a new flow named Standard laptop task.
3. Set the flow to Global and run it as System user.
4. Add a Service Catalog trigger.
5. Add the Create Catalog Task action using the Requested Item Record from the trigger.
6. Set the short description and description to "Laptop need to Configured", the Assignment group to Hardware and Approval to Approved.
7. Save and activate the flow.
8. Open the Standard Laptop catalog item, go to the Process Engine tab, remove any remaining automations, select Standard laptop task in the Flow field and save.
9. Verify by ordering from Service Catalog, Hardware, Standard Laptop, Order Now. Open the request number, approve it under Approvers, then open the Requested Item and check Catalog Tasks for the short description and Hardware assignment group.

## Future scope

- Notifications to the Hardware team and the requester
- Approval reminders and escalation
- Task checklists for configuration steps
- Satisfaction survey after fulfilment
- Reusing the same flow pattern for desktops, monitors, accessories and other IT requests
