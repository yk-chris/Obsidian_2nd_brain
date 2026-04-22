---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'


# Excalidraw Data

## Text Elements
Select Template ^IZAHIiat

Normal Streamer ^qTPLi3W0

Create a list of task templates ^CBedeh71

Status: Normal ^v4CEgxU2

Status: DIW ^MrEHOHOn

Status: Cost Review ^JJCed8r1

| Task ID | Task Description | FD | PCD | ACD |  task-label  | 
| 1           | xxxx                      | dd  | dd    | dd    |                      |
| 2           | xxxx                      | dd  | dd    | dd    |                      |
| 3           | xxxx                      | dd  | dd    | dd    |                      |
| 4           | xxxx                      | dd  | dd    | dd    |                      |
...
...
| 40         | xxxx                      | dd  | dd    | dd    |                      |
| 41         | xxxx                      | dd  | dd    | dd    |                      |
 ^sQLe9Gbj

Streamer is "ACTIVE".... ^Nce0SEqA

Change in PCD ^0es8Mt3h

via 
parent-child task,
test-slot manage. 
task-owner trigger ^ZX9yeX0C

Disabled/Enabled tasks ^Nf54SoFU

Complete tasks ^yzWzS4CB

Swap module ^CuWVnZmG

Adjust streamer base ^ZSo9qGLy

engine type, 
shop visit type, 
module work level, 
... ^EpyEMP5b

Select Template 
with DIW tasks ^yoqhwDgh

DIW Streamer ^pF9j7xIX

Streamer is "ACTIVE".... ^79EWHeFi

Release ^HUmUzCwx

re-induction ^nZlhV06C

via ACD ^6ftPCpT4

period of pending... ^vbTyqQWq

Completed ^MD0nwiXN

Completed ^Rfy9cCku

| Task ID | Task Description | FD | PCD | ACD |  task-label  | 
| 1           | xxxx                      | dd  | dd    | dd    |                      |
| 2           | xxxx                      | dd  | dd    | dd    |                      |
| 3           | xxxx                      | dd  | dd    | dd    |                      |
| 4           | xxxx                      | dd  | dd    | dd    |                      |
...
...
| 40         | xxxx                      | dd  | dd    | dd    |                      |
| 41         | xxxx                      | dd  | dd    | dd    |                      |
 ^Pc0PYSsm

DIW ^ZswyAk1l

DIW ^VAs1ac0f

DIW ^E2bqk6Rr

Enabled ^ucOEenQV

Disabled ^ZmEksGZr

Disabled ^ilMFZH2R

Select Template 
with Cost-review tasks ^iJ5tbYnG

DIW Streamer ^m1p0WeAH

Streamer is "ACTIVE".... ^IHGRrebl

Release ^0X1J6zph

re-induction ^PS38ojWN

period of pending... ^7ZWIcK57

Completed ^wJDUICxL

| Task ID | Task Description | FD | PCD | ACD |  task-label  | 
| 1           | xxxx                      | dd  | dd    | dd    |                      |
| 2           | xxxx                      | dd  | dd    | dd    |                      |
| 3           | xxxx                      | dd  | dd    | dd    |                      |
| 4           | xxxx                      | dd  | dd    | dd    |                      |
...
...
| 40         | xxxx                      | dd  | dd    | dd    |                      |
| 41         | xxxx                      | dd  | dd    | dd    |                      |
 ^Gii0gboR

Disabled ^voRfMMKN

Disabled ^1bw6UGyB

Cost Review ^fnILgEnw

Cost Review ^COIo1bSa

Cost Review ^RwwcReRF

Select Template  ^pRzlDAkr

Normal Streamer ^Io3cD47M

all disabled tasks and re-calculate FD/PCD  ^36qE7k3X

DIW ^4JCgA3nf

All the functions as normal does ^Cf8HUHeJ

Cost Review ^fyGQ6Rpv

All the functions as normal does ^Gyv8E1e9

DIW /Cost-review Scenario ^3D24w4YT

Choose another induction date ^NrMQ8Mlf

Choose another induction date ^CGvsNp1k

Archive all task-records during cost-review period ^N3cQ8Ebh

given the template with tasks labelled with "DIW" is selected
the planner can make a streamer with the status of "DIW" and only the tasks labelled with "DIW" would be enabled for input. once all the DIW tasks are completed, the planner can choose to input the release date but there can be a period of pending for re-induction. After the planner input -reindcution date, all the tasks disabled due to the DIW effect would be enabled and recalculated for the updated finished date (FD) and projected completion date (PCD) ^katHvyJN

Given that a template with tasks labeled “DIW” is selected, the planner can create a streamer with the status set to “DIW,” and only the tasks labeled “DIW” will be enabled for input. 
Once all DIW tasks have been completed, the planner may enter the release date, although there may be a pending period before re-induction. 
After the planner enters the re-induction date, all tasks previously disabled due to the DIW status will be enabled and recalculated based on the updated finished date (FD) and projected completion date (PCD). ^84r1vuTl

given the template with cost-review tasks is selected, the streamer would set to be "cost-review" status and only tasks labelled with cost-review would be enabled for input. once the planner release the streamer by inputting the release date but there is a period of awaiting to re-induct, the streamer would be released. After the planner input the re-induction date and select the normal template for the streamer, the task-records from cost-review period would be archived and go through the normal streamer process. ^tEP5WSlU

Given that a template with tasks labeled as “cost-review” is selected, the streamer will be set to the “cost-review” status, and only the tasks labeled as cost-review will be enabled for input. Once the planner releases the streamer by entering the release date, even if there is a waiting period before re-induction, the streamer will remain in the released status. 
After the planner enters the re-induction date and selects the normal template for the streamer, the task records from the cost-review period will be archived, and the streamer will then proceed through the normal process. ^URrfjGOz

Feature: Streamer transition from cost-review to normal process
  To manage streamer progression from a cost-review stage to the normal process after re-induction,
  the system must control status changes, task input availability, and record archiving accordingly.

# ── Happy Path Scenarios ──────────────────────────

Scenario: Set streamer to cost-review when a cost-review template is selected
  GIVEN a template with tasks labeled as "cost-review" is selected
  WHEN the planner creates the streamer
  THEN the streamer is set to "cost-review" status
  AND only tasks labeled as "cost-review" are enabled for input

Scenario: Release streamer during the waiting period before re-induction
  GIVEN the streamer is in "cost-review" status
  AND the planner inputs the release date
  AND there is a waiting period before re-induction
  WHEN the planner releases the streamer
  THEN the streamer is released

Scenario: Archive cost-review task records and continue with the normal process after re-induction
  GIVEN the streamer has been released from the "cost-review" period
  AND the planner inputs the re-induction date
  AND the planner selects the normal template for the streamer
  WHEN the streamer is updated for re-induction
  THEN the task records from the cost-review period are archived
  AND the streamer proceeds through the normal streamer process
 ^yruDuiwz

Feature: DIW Streamer Progression and Task Enablement
  Ensure that a streamer created from a DIW-labeled template follows the correct task enablement flow,
  and that task availability and date recalculation behave correctly after re-induction.

  # ── Happy Path Scenarios ──────────────────────────

  Scenario: Create a streamer with DIW status from a DIW-labeled template
    GIVEN a template with tasks labeled "DIW" is selected
    WHEN the planner creates a streamer
    THEN the streamer status is set to "DIW"
    AND only the tasks labeled "DIW" are enabled for input

  Scenario: Enable previously disabled tasks after re-induction date is entered
    GIVEN a streamer was created with the status set to "DIW"
    AND all tasks labeled "DIW" have been completed
    AND the planner has entered the release date
    WHEN the planner enters the re-induction date
    THEN all tasks previously disabled due to the "DIW" status are enabled
    AND those tasks are recalculated based on the updated finished date (FD)
    AND those tasks are recalculated based on the projected completion date (PCD)

  # ── Non-Scenario Rules ────────────────────────────
  - Once all DIW tasks have been completed, the planner may enter the release date.
  - There may be a pending period before re-induction. ^D8ASxgNx

Feature: DIW Streamer Progression and Task Enablement
  Ensure that a streamer created from a DIW-labeled template follows the correct task enablement flow,
  and that task availability and date recalculation behave correctly after re-induction.

  # ── Happy Path Scenarios ──────────────────────────

  Scenario: Create a streamer with DIW status from a DIW-labeled template
    GIVEN a template with tasks labeled "DIW" is selected
    WHEN the planner creates a streamer
    THEN the streamer status is set to "DIW"
    AND only the tasks labeled "DIW" are enabled for input

  Scenario: Enable previously disabled tasks after re-induction date is entered
    GIVEN a streamer was created with the status set to "DIW"
    AND all tasks labeled "DIW" have been completed
    AND the planner has entered the release date
    WHEN the planner enters the re-induction date
    THEN all tasks previously disabled due to the "DIW" status are enabled
    AND those tasks are recalculated based on the updated finished date (FD)
    AND those tasks are recalculated based on the projected completion date (PCD)

  # ── Non-Scenario Rules ────────────────────────────
  - Once all DIW tasks have been completed, the planner may enter the release date.
  - There may be a pending period before re-induction. ^yxxyb2lr

Feature: Streamer transition from cost-review to normal process
  To manage streamer progression from a cost-review stage to the normal process after re-induction,
  the system must control status changes, task input availability, and record archiving accordingly.

# ── Happy Path Scenarios ──────────────────────────

Scenario: Set streamer to cost-review when a cost-review template is selected
  GIVEN a template with tasks labeled as "cost-review" is selected
  WHEN the planner creates the streamer
  THEN the streamer is set to "cost-review" status
  AND only tasks labeled as "cost-review" are enabled for input

Scenario: Release streamer during the waiting period before re-induction
  GIVEN the streamer is in "cost-review" status
  AND the planner inputs the release date
  AND there is a waiting period before re-induction
  WHEN the planner releases the streamer
  THEN the streamer is released

Scenario: Archive cost-review task records and continue with the normal process after re-induction
  GIVEN the streamer has been released from the "cost-review" period
  AND the planner inputs the re-induction date
  AND the planner selects the normal template for the streamer
  WHEN the streamer is updated for re-induction
  THEN the task records from the cost-review period are archived
  AND the streamer proceeds through the normal streamer process
 ^yWOJs3d1

%%
## Drawing
```compressed-json
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
```
%%