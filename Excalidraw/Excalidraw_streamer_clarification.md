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

all disabled tasks and re-calculate FD/PCD  ^MzLT0DiT

Archive all task-records during cost-review period ^SrgkqID8

Choose another induction date ^TdXScOJt

%%
## Drawing
```compressed-json
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

AiYEM4gCwEAA
```
%%