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

DIW ^4JCgA3nf

All the functions as normal does ^Cf8HUHeJ

Cost Review ^fyGQ6Rpv

All the functions as normal does ^Gyv8E1e9

DIW /Cost-review Scenario ^3D24w4YT

Choose another induction date ^NrMQ8Mlf

given the template with tasks labelled with "DIW" is selected
the planner can make a streamer with the status of "DIW" and only the tasks labelled with "DIW" would be enabled for input. once all the DIW tasks are completed, the planner can choose to input the release date but there can be a period of pending for re-induction. After the planner input -reindcution date, all the tasks disabled due to the DIW effect would be enabled and recalculated for the updated finished date (FD) and projected completion date (PCD) ^katHvyJN

Given that a template with tasks labeled “DIW” is selected, the planner can create a streamer with the status set to “DIW,” and only the tasks labeled “DIW” will be enabled for input. 
Once all DIW tasks have been completed, the planner may enter the release date, although there may be a pending period before re-induction. 
After the planner enters the re-induction date, all tasks previously disabled due to the DIW status will be enabled and recalculated the updated finished date (FD) and projected completion date (PCD) based on the new induction. ^84r1vuTl

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
    AND those tasks are recalculated the updated finished date (FD) based on the new induction
    AND those tasks are recalculated based on the projected completion date (PCD)  based on the new induction

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
    AND those tasks are recalculated the updated finished date (FD) based on the new induction
    AND those tasks are recalculated based on the projected completion date (PCD)  based on the new induction

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

all disabled tasks and re-calculate FD/PCD  ^MzLT0DiT

Archive all task-records during cost-review period ^SrgkqID8

Choose another induction date ^TdXScOJt

%%
## Drawing
```compressed-json
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
```
%%