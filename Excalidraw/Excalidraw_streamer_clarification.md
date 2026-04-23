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
test-slot manage, 
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
    BUT all the record of tasks labelled "DIW" remain unchanged

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

Select Template  ^ZnovFkYO

Archive all task-records during cost-review period ^iCPU6eRO

? ^eVn3vcUs

Help ^OFnjxibp

## Element Links
QvpqGF5x: [[../(WORK) 工作/Projects_HAESL/proj_digital_streamer/streamer_feedback_review (Task Owner)#1) Consolidated Categories of Comments]]

%%
## Drawing
```compressed-json
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=
```
%%