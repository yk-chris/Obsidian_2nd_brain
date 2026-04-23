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

Task Owner feedback - mainly focus on Task-view & Notification ^5SvAvh33

## Element Links
QvpqGF5x: [[../(WORK) 工作/Projects_HAESL/proj_digital_streamer/streamer_feedback_review (Task Owner)#1) Consolidated Categories of Comments]]

%%
## Drawing
```compressed-json
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=
```
%%