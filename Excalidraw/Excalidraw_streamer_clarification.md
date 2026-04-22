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
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=
```
%%