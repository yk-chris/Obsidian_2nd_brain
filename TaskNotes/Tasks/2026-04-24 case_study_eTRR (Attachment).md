---
title: 2026-04-24 case_study_eTRR
status: done
priority: normal
scheduled: 2026-04-24
dateCreated: 2026-04-24T10:05:48.814+08:00
dateModified: 2026-04-24T21:25:04.215+08:00
tags:
  - bug-fix
  - task
completedDate: 2026-04-24
---

# (bug-fix) Attachment card during re-submission
![](assets/2026-04-24%20case_study_eTRR%20(Attachment)/file-20260424150057416.jpg)
>Hi Chris, I thought there was a requirement that PMO/WSO changes must include an attachment. Could you please help confirm?


![](assets/2026-04-24%20case_study_eTRR%20(Attachment)/file-20260424150057419.jpg)
![](assets/2026-04-24%20case_study_eTRR%20(Attachment)/file-20260424150057421.jpg)

---

### No issue on Form page
#### Required on Attachments Card
![](assets/2026-04-24%20case_study_eTRR%20(Attachment)/file-20260424150057427.jpg)
>And(RadioGroup1.Selected.Value <> "I would like to borrow the following records for the purpose of technical information review.", RadioGroup3.Selected.Value <> "Other changes")
#### Type of Reasons
Value: "I would like to borrow the following records for the purpose of technical information review."
Value: "I would like to revise the following maintenance records due to the reason stated as:"
#### Type of Changes
- PMO/WSO changes
- Other Changes

#### Attachment required:
 Type 1 of Reason && <> Other changes

### issue found on Pending Actions
![](assets/2026-04-24%20case_study_eTRR%20(Attachment)/file-20260424150057425.jpg)

## Attachment Card > Required

**— original**
> false

**— change**
> And(_RadioGroup1_1_.Selected.Value <> "I would like to borrow the following records for the purpose of technical information review.", _RadioGroup3_1_.Selected.Value <> "Other changes")

## Submit button > OnSelect

 **-- original
> Set(varStatus, "Resubmitted");
> 
> SubmitForm(Form1_1); Launch("[https://orgd9f4c4b6.crm5.dynamics.com/main.aspx?appid=899f5362-1a41-f011-877a-000d3aa36b25&pagetype=custom&name=cr1da_mysubmission_499a1](https://orgd9f4c4b6.crm5.dynamics.com/main.aspx?appid=899f5362-1a41-f011-877a-000d3aa36b25&pagetype=custom&name=cr1da_mysubmission_499a1)", {}, LaunchTarget.Replace )

**--- Change to**
> Set(varStatus, "Resubmitted");
> 
> If(IsError(SubmitForm(Form1_1)), Set(submitError, true), ResetForm(Form1_1); Launch("[https://orgd9f4c4b6.crm5.dynamics.com/main.aspx?appid=899f5362-1a41-f011-877a-000d3aa36b25&pagetype=custom&name=cr1da_mysubmission_499a1](https://orgd9f4c4b6.crm5.dynamics.com/main.aspx?appid=899f5362-1a41-f011-877a-000d3aa36b25&pagetype=custom&name=cr1da_mysubmission_499a1)", {}, LaunchTarget.Replace );)
