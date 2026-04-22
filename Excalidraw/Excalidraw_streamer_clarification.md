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
```
%%