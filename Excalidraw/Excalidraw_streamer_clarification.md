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

all disabled tasks and re-calculate FD/PCD  ^MzLT0DiT

%%
## Drawing
```compressed-json
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
```
%%