> there are three scenario for off-module swap
> 1. pre-condition introduction
> 2. off-module without module streamer swapped into engine streamer
> 3. module swapped between two engine streamer

#### Question 1: how to select the module template by engine type and visit type?
**solution:**
Visit type = "**Swap**" for module streamer template?

#### Question 2: which tasks would be transferred from module streamer to engine streamer?
**solution:**
> A module without module streamer cannot be nominated.

in case of off-module swapped into a specific engine streamer, only module tasks on the module streamer would be merged into the engine streamer.


![473](assets/MoM_2026-04-15%20streamer_off-module/file-20260417082339910.jpg)
![](assets/MoM_2026-04-15%20streamer_off-module/file-20260417082339914.jpg)


#### Question 3: swap module between two engine streamer
**solution:** pending
![](assets/MoM_2026-04-15%20streamer_off-module/file-20260417082339916.jpg)

---
==Reminder for bug: module is not on the off-module list once it is created on Streamer page==
#### When the input type is "module", it still need to put into the off-module list

![](assets/MoM_2026-04-15%20streamer_off-module/file-20260417082339933.jpg)

