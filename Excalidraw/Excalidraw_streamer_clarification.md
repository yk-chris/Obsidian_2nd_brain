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
N4KAkARALgngDgUwgLgAQQQDwMYEMA2AlgCYBOuA7hADTgQBuCpAzoQPYB2KqATLZMzYBXUtiRoIACyhQ4zZAHoFAc0JRJQgEYA6bGwC2CgF7N6hbEcK4OCtptbErHALRY8RMpWdx8Q1TdIEfARcZgRmBShcZQUebR44gAYaOiCEfQQOKGZuAG1wMFAwYogSbghEgHVNABYAeQBlAFkAZhTiyFhEcsDsKI5lYPaSzG5nGoB2Gu0JgDYeCZaAVgBO

AA4JgEZEuf4SmDGWtZbtRJXEtdnztaWJtcm9yAoSdW4Fze1lnhWazc25yaJJaPKQIQjKaTcXYFSDWQbiVCJEHMKCkNgAawQAGE2Pg2KRygBiTYIEkk4aQTS4bDo5RooQcYg4vEEiSo6zMOC4QJZCkQABmhHw+AasCGEkEHj5KLRmMqL0k3E2yNRGIQopg4vQkrKIPpEI44RyaCRMIgbC52DUBzQ21NHQgdOEcAAksRjahcgBdEH88gZN3lSoATWY

LX0ABUAFIAMT5hEZWHKuB4fPpjMNzA9RQdXQRLRhAF9kQgEMQlWtNjdNkcHmbGCx2FxbRM+PWmKxOAA5ThiJUrBbzC48FogwjMAAiaSgZe4/IIYRBmmEjIAosEMlkPfkOoUYSU8+UZ5goBSSmUJC6AFoAQQAEi6rKf98X9zmHRf0F2AGpGBpYpZEgAaTPTp4ARCBuTRKgX0ePdd0gT8IDgAAlCc7xvABFF1RjgsDugkKC2Bg3dCxhH0zSEOBiFwG

dyxbOY1h4GseAuFZZhBIgOHRbgOCEYVOLYGlZzQed8DCApX2Kd9Sno9Br3vR9aL5Q82SwU8QVGNBxk2JJLirFZthqAcJkSUczRtVBnGWCZtFWC4rguW57gmEFnmIV5bRqJZtBWPyXN+ZiziOEFJDBCFTzQHhgTNOEtXtEoZTVZl8SJMlSSQJdqVpdMmVxVK2XIDhOW5TINLNQVhQ1LUIB1csVVlBB5Q8xUooatVqoguq02EA0jSVEELWpa0lUSBL

ICdKi3W3CiHT9XAAzkiAQzDSNY3jRMtPQXA2j1FdiEzD0+IEs0whE1BdJadipm+GKHQbTtm14MyQQepsew4Ps0BqWZVlmI4WmVM1xynYI6LnBcECXfb13SMqjv4/AQSomjwYY2YmJYtiOLNPFhLksTFzNY9IvQBo0j6VAI3SHxaMys1yAoamT3Kcngkp6n9Fpmc+X5TgoAaQgjARVjfX5mMFqFSycdzdSbyIZQnogMQsiYPkGygcwCHl8Elf0Ehi

CGEE9CyXAEyYQMJCqWpGlaPl8XBBMCGZ0mIDZhAOZp/A6b5XAhCgNgUPCIWEVRIQodx8273CyFbXiO6SkkUIXYAGQTHjRMhyS9hkpClmIbA6ivGMAAUU5U8Ceg9/p4T5LbnG2E4ajOCYfkrRJ/q2EFLOs45TmuRybjuOsHXczzeC2T4lm+X5/lmQEE8gMLwVj1BoQdOKEXG2rVUxFLWXQYkMvJLKaUmxl96PIqSp5cq5qFEUxS63FdVO3emoVAa3

8azrym6va/CSEOtwbeQ0rSwFGtvSarp3R5FmiUeai0gyhnDNGOMY5NrJhqD1BkB1+poHfPhfMRYSznV0n9eYawzivQ7E2JUfwaGNm7L2BEGMVhLG8hsFYY5JzTnOoTCODply4NhpubIeQ3z7iIUedSoFZLlAAI4RjLoQFolRkiwUkQheREhiATEqEsTCUYlgAHE5GqW2qQaCEBNG7kIYhJaP4/wAWAuYyuhErHERsaRciyNqJ0zkv8RizEWisTWO

xTi6deKI0EvjCG4kEDZwKLnJaSiVFqOSCCCx0BZGaTGN5OyLRQk1CKYBSs6xNgy32IcW4dkB7XGciPEoY9WoXSWD5VY6wjjRQxssH4oUY6k2iiCTeID2p73ygfCAR90p8ipGfXKl9Coci5LfXmD9f4ShfvVb+apmrjyBg6JKmJNnam2TgvqWYxlmjASNW0Y0QTQOmnA30/oECW3QCtVB60MHECTIRGoawcEZnwagY6SNTqljkrMSpbdNhLEOSUN6

nAlTfEYY9D6X1UD3B4N5YKrlga8LBvwyG0MREbnhtEk6DoUYBKVBMYJNZNg1G+Nw3GQlMQE1JcTWREgeykH0AQVAopAgLTVnqSgLtyj8sFfgYVqIQgZAJGLLIgthZvG3nzLIEt9b4GllkuWCslYqxnMq9spBNbuB1orco+tiCG3pg6E2URzakA+RAfOhdi5l3tqQR2HBna8q/PiWV8rRVKt9v7QOwd1VoDDoIkoXEEDRxXqTD4wyzRJ2YKnKJmcE

lJOksDRxv5/yARAlk9xljrF5O0psFYtlzj1rhR3FoXcLKHAKXWhyDTh4EtHp/NA4SBmpuuRvAY8VxnYkmWlY+jqSjzJyvtJZ6B2TFVWWVdZVUn5/3OZO/ZrTEUCHfqc2qu6Ga9SAaC0Blo7kXQeWaJ5sC0DeleWK91Xy1roOBpgwiSxgV4KuWgcFpDAlFOZSUuYfakW0JRbaZl6L3osP7CU+4Hd608NBggNGqABFkrXBSrcVKIU0v8dhoJGMQlhI

iZHbiRHYmcviUTB0cA2AJnEc+/cO5dzjWKIkfc8DihcY6EOqRfHdxel8W/bkUAABCCZHADG4IQjABGoDuutvUZou19wQH0GwP55R8SaDUGeAUhBMBlhLqx3kHGEIfESKxHgGMqHtOMksFoNQ8KJG0MZS4OLtjT3+vC+4/GSFmkyMQOTjIEzKCUzptIYj3WeqLqXcucFdP6YgkZkz6XBQWeIFZtjEiELOG8w5hzzmgQcPYUUlYRSvM+fWBjFlAWnO

AyWCF8TYWjlRAtTeTxFAwq4DksB8LjJ+vQSG0tIiVAQRBGXBQc68bfTmbLOTZQYiEbUsSr1tTzAGiICtAQOjY3iAun24dqw+AiMFvgueJayg6sAH04DfmIOxAAVqub8+AJhPZk3UFYXYJyrgrgRdAvQa5GzNPXGsTE7I8CHgOWYdx3jdzGK2bQda6sTFWAyjzswMZuQHagFD2gYVzGZYBbYhPh0RW4KsJu/wFjsRuIjzzsVx1b0ncu6ZHmWi4Gbn

M7K588osiJGIYgNQaKbsfpqCCSdsAaECNKd++6v49Z/turZUoAGXI9Ne4aED7lQPpDAmar6kESA/WgjafytqQVmP+4BBCdMWILB0KSiUoX9hZ05trCHYOoFKYHjgmLWFViYnixepQiVYZJQkvDxBRGUtsx0ex0BK05JZnhHR6AsQybLAgSQWxvGe7ghnpCKcoAmJLiY/kV59BuPB5BAbZfihe8LdopCkgS6aCWFiAXJdm8QRm+3sAne7sfiWqhdC

WEcIj+TG3l8kmSOozIQyijWNwlVMgFxDOYKYnsriXmpjidk7qTTrR0/iSO85yLeUAvReS+bDBxBEmdcxhY1OOE0yswzh1bRQc4OiWT/ArB2RnBtaXDTw1bAHNIk6AwnCLBNaVjzwdwZoOjLz05oDnAjJc6jo7aNS86Ej86C6ZJmgLqi686ro3wborZbry47q667Jygk6Ho7xa6ME66vwOj6iXqAaIiDQ3rG53qm7OjPLPoCYChvLvooKfp27/LbQ

TDO6gqjZHI+5RSJB/A3BLD/Rsr3QwZPStrbzIph5IZoBbAwo/QU4YZ8JcqJ4UEwyqYW6USkYb6MR1ocK4qVL0YJ5n6dBBoQBYiiozioC4CoBEAoioBsD8ioBRDMDogAA6qsXM3sM4OQEqTMgRwRIQoR4RkRUA0RsR8R6IcRXsdMGRFU/Maq+Yu+Ao4skseq3AdRJM1qxqZU4q5qlq2sRqtqBs0OTq/MZshobqD2z2r272swX2P2f2AOQOIOvq/qg

aLMEgORdMYRER44hRMRcRoQpRM4qRFRkaAcQcrAsacRpA4ckShoKa2BF08coUF+J4V+B+Ait2KS5QeiBiRipib+S+1aMO9KTcJSzK/0v0xwHm6O2kHmPkXalwPaLkxOLU9ClS8cawxwrYtwTK5kmBgySo8cV0P0CKMKhOjOeBtcJoPO06EgMyGUwuCyS61JK61866vI9BcuNU/8LBH8yJbU3JJ6NEzAYUOyvBF6LughNywhoB96Doj6Lhc0MhS0N

uPy369uyYKwKhAhah3u506w3wLQ88vwoe3A/Ooe4eUIxk6wQIL0hKmG2GuGjh5KcMhGQGR+a+dK6MmMgMzc7m1xB+2pe+HKfhCakALGbG24nGomXm/GcEQmxQ7SawWO+pfmywrau+vGMZkZCECZSZdWKZ7m68u4DcBJPwv0lSlSv0dWmZu4cZYAfwqJ0U6Jra0UWwiBeExZ0UhJZZJJlZHuHQEm/ZKo0mUWCmsWruu4KmzpamS0yW3qaWOmemBmE

g2Wd898+WhWNmnoUi9mjmlWrmsBDWvmzWQUgW7WnW/Z3WJQEWI5MWcWE5CWZU7qKcq4NQ9APAN4HAf66Wi5WWpAxmq5CCq2BW1mpMtZpWpwaZDm/wRwhOLKxw8GomjWdWlSgMQ4iwvwKwoW5eUmfWA2U2J2DoEWE2xE+FHiAJhF+AC2S2lxIZZm+W62m2BFO20m52B2HsV2TFkAEWrFl2x2rpwo7xD+Eg9ANQWIq4ygmAAAqqmBWi3h/jWlZLcNM

A5gkH5DsD9EylCVZK3B8KZKgY5EFncEiePEAZ8FsDUBZaZMxIChZXTqvE0rCPgZSdycQelCfBQSLoskydACyaVGyRVBstrmcswZrnsmwZOielyaKYAuKYbuAtKWIVNE+p6FIYgu8ktFALjk0IQFeN+FwL8ooZBFiJqVtsRjqXJFaexO0miuao9G8AkGaeYRdOcHiq3AsLYcSvYf4RAMIvhlOaVX4uvoEpvpjGZHML9L4V1bRR/hIKKLREIPIKgDK

sdpkVKrNVEFAAtWgMtddiqgLCHCabZHUVqlADqlLM0QaieG0eUMEPyABQwEwN0fgNdWyBaHyM6sMRbCNm6SUA7P4Msa7HNZtYtTtccdGmcaHDRdccmniXHBgeftmpfrmjhlnHfskkJegE0KQKuHeHULjflcTFnvJYCdpLcD5K3CjiOIsN8P/jHqAc3OTpWPzjWBRosMZa0qxLZN5IZNPAkJUq3FBkvLDaToLZBE5RKaFRMuLjSW5XOpSJ5YydLcy

Ssn5fdZVByc/CFYQWFbyRdBFUFaelrZAHwbFUIUbglY8mbhISlZbuleUBOJgDUPgFiFsJoAoQ7rgBOCVZxbVBoXeuEhwpWMcMaWgC0DsI1Z9AiAyhZVaW2h+HHvadykIk4f1S8q4UNfSoyh5gkNQsfgxjfpdYDRtVtagBOC6JUGmJKoEUDSXWXRXXtTUYdeTntWdU0WgC0YarrDdQgHderI9VrM9b0a9XAO9UMa6h8gGeaH6v9fgGtWTMXYtXXWD

acQdXGlDTRjDSOnDTHlmjmtfijfmmjV3vduUFGFGFiGWGsKQK/rJe/rkiTYpa3NoFHuEuUlWGze2oOqiQFvCoClWH8A5RAC0iaUcL5ICvWj9PijvcLYA6Ms5ZLVOkrdMrLfSYurgtQb5WsuyZFWegg+rraPrVwcFTwSUCbVembfFZApbeIclS+hVIqeUB9jGDAEsC6CnE0MoQVR7aDgAiClqT9QIH7dsJWO5hcB/QYUwkYaEhHVigaR1tVRsB1fH

lNUnini6TbenR6RdCNSEt5LpPoYmkGSozyisfPfNYtTiFEUHGYAgLNgzFXaY27AvWgJY4UdY4QLY7zNUavcHkdS3Y0fqiY1AC9egLdfdRrAPSE9AG9cbGPSMRPQI1PUsbPdXc46gK46gO454yMlGiveccthvbcavOmjvU8VAC8YxrfhPvftPn/JhCnAgCsCYpoB9n8WpDng/eMP9IUqEloQThsIDKLT3AsNMGBjChcFdNVewcA2gO5nEFdAOIZH5

MxBsNA1vbwIBOSROi5d5SQSUmQag1Qd5TQayWrYFUQ4bSQ0eo1Pg3rfyQbVFaQ2KeQ5KebVQw+lbbQ6lQw9bnIbblw8mF+tFXwwNZCmQr8ExIsCHrVXQu3a3DI6wh1uiZMDieeAncGao84T7bSmRjo0yiyn5JNZU4XeUAAD5Ux7GoAugTioDksRiUtTjMDYB+pwCaycC0uoAxg0vkslxYjcuoA3h8scu7EJHODeyaBBCoAcvJHkubBSvysKtSvku

YAquYCKvqsasKvkv2pKuoA6vyvavEBauasmuKuksyu8CmscuqtqtWumuGu6v6uOtGsGt2v2sWstBWvKuqtusmsOsctOsBsuu6u+savmscDks1BeuoA2uhtht6suv+vOvGtxtmvJHaAZvpuZsRuk6JB+sxs+upvGv6tJtBsptFtKsWu/D5uxsVvJtluuuBvkt1u0vJGV1ZGON0uUvUscv0sJGl3hDMuECstNgctcscu8v8uCv8sivohiu4AStyrSs

5tyv2sFsqstsNulvbubvhvks8DRu1t1v+s7tNu7seuHuFvHsJv1u3vCvHtVuXsbstsns3uNvBv3sVvhsZvaBZu/s5vNw1tXtftvunsfvNsPsAervxtHsgcltvt3sQdfttsN0+OixVHaoBMXVBNRNhN90WqRND0roxNmgfXj3fXbaQB/VOwpOdsUv9s9tdv9uMtDsjvsvkvjs8tCvkvTvCslHzuLu6sWvQeavevPvXvwdntnsvsWsHtruwdFuvtSf

gfns5uevyfAeKegcIcNshuQeRtPu2sSeJs6c7syccA/t/tVt5uifrtGdwcmfKflvIdQdAficOeIemeqfL0xqQ1XGFPC0lOPGI3PHI1vFH1T554QBdhiCJANCrgKI3htMrr30OhbR1q2RmTHBNrnBTBaFtggGHDRR2RBYGlh3ubsT9JmgzO8A1h2QZf/5MrHCrBwFC3rPw2OUUkS3a1S0FSHx+aNNO6nxoMXzHOYN0EBUMGcm4M9c8kHKEPTdG0QB

kMCFxW3p2jUNJXykII/OfJ/Mqkfg/rbRmK8MAagvqHnSsSAQU5aEx6mFvCVgItKh6GJAlJmSouITovGPJ1OmMX8VlWQA4vuFb6tph0IUOh4z50H3dUzXz3hpMCoDjioCJEQCCsRgujfirgo8/vaDttz1OPw+kCI/MDI+o9Yjo+Y/Y8/teOqpoeaoNG6qBOyxXVEcQB4eMJPVRMBwj2xOmzkc+3UcBq0dF2E/E+k9o8Y9Y8QA48+cQ3cAFMQ9RyBc

PGZplMVM36CW1MSDBiVD8g3hNAIDfgyWE0t5j4KWhInDQUGl+SGS02Qmf1WQeaJlbBaHsK6ThJOa6Hs34ngm9Lek1ahIFeJzC0zyfDfBmQBZjQYyi1wPdfXPJS7MDfsSHNeVIMnOq2y44NLfHJzcHoLcQSCnCkXL8EG4UPrcyklBylp0KlvpKn7dAvnhHeQR3je3jm5iVo8CXmCPnTFJjS6EGOQD3eh0jhPc4HrCVimTwpKOJ0OE/d9V/dbl2JSK

Z5yWpcTlIRXgAAaKwMACAm/iQxVK+g5mjuLWdpk08awfpPtkPGLZoYZ6jcZtZPGYAYmx/NZUixZvvEJzKAfDVH/ofoSc4IDGtIdwNgWFYoFIRRDDl5Mt5f7nNkZA3lFMbfK8qpndTNAsQQgF0B9hMQalvymWQzH+Ryw6Y8slmECsVm4wQEtCeETYOAOqY4VgmeFEIBRwB4YBxsjA4bP8S8RzZKKxEW/g6D0yMBsqwFcMvKHUBqNSY4XOgcfQcTlA

t+O/Pfgf2S7Z57q6XXSOTlxxXBdCcwOZhNQd7OAOEswGYK3DQxAEbgIUarmwSuDxAroVCLYIjnODzA1mdxDbpzi67bwc+xBJPkNw8oMl0GY3FWlg0m4a0mCVzDgjrXm73MLmhfWcHrhL4EEqOUpd5rKU+bbdIAaVWQqtH+aqlCquAO8Cd3PS4JxSk9M6HJEuCU5AIgMEOhdF0ESMMUTVRAuiXmDoZbSdhYlo6Xn6p5D8lHCAED2GpZ0gQYJIlgXS

CblAzA4RZIqc2cBK4hQRrEotQGSLpEoAzgZgHiEKKCoA0ygBANoGR6mxRWxEEYhcXBCbCzUvBBxq7DGE7DJh0w/ALML2LzDVYKIZYasNQDrDogWwnYfx32EI9UQRwzonNG8bnF0O/wzDoz2w7M9gmrPE1H8OgwEcrUrPO1A6lHp894mS0HXnrwN5G9FiM9fHhcImGq0phkgGYbO3uGLCnhbANYdYDeHbCFhexZwF8KJ4/DlAxw2Xj4wV6Jole6zI

LqrxC7lMwuqNKQZFyQjoDMB2A3ASbwgiQ5RkClJzMpTGhQVGuywHwnoL0qFIBwTmf4OEnYRB8ngbBZlGAxKQIodgWwALJf0zTC1/8WzbnDsyQaEgvBKfRWn1x8oBCJu98KbprVCE59bm7BHPgKVCBF9YhptV5pQxNybdzc1fHbrX2QSZCDujfNUoRHLQFCQWd5dvuDj7ICju+0KQZh1jqx3dDCJpP/rUMQyR16EqFBlJzWn58D50KdBfnGQzzZJi

a3eJaIkHCBrAmgUAFoIqFsTp5l+SENEfr0N7G9tE2SMfEfwgGDUtG5GL0uf0RxX84BedYMprxPpWwWxbYjsUoIbEjA3gcwU4LpFxQAwqwWhVrhAB7imQTgFXBIBTk1HTxveOBbzEswcEkkgoVXXEus02auDtmCDTwRjEG72i/Bafcbv5VdHBDuCIpWbl6Pz6fE/RMQgofrniHmhEhIYj5jQ1SHSFIxvzaMQ30QhN9cA85YFmdx9olDRolwUsewSH

7B4R+MLZhMWKijbBWUtwFHBWO+5VjfunQyer0Mzog9pxpoiHkYzaHgjH8ScAYAgER4cBkik7PHtkUEmbCRJqAcSah0BH08QR51duoXSiZQiThMIznvCP6Jy1lYcTL6qzCaAYCsBOArETR3x5YgpJwkhMLJL5Ysj8m69RXjcWV4dcpAavPkYfQFEfEJALQCEBQHRAtAywXYdEC6FXBrBMIFASSliBTj6BfJSgs3g/WnjTB6JFwS4FcGZQMotK1kYy

J8CoT3AXMFQ4yDeNQDgEEUdwIcBwiBDW8agCAZwNxOD6cifgPmVsJoKbS4pdCdRWPu4Pfhfi1gP44bkc3/HOjAJgFN0SENAnx9WCutb0cegNrRCJpy3Z5qtzL4iEXByQ5CeGLSG7dlo9fd2smDqCt9UAymCxJ32woXc5IMBH6EHQ+4PVJG3AbyDdNMLmlbQ6wH0kxBqFos7SlYykNWM6F0N3Sp/TiZ3G1Fs9kak9G/kxNDIgUIy7/BCM/1f5jisy

u4UqRqIqk+lqptU+qR0AbhNTJgTmdhG1O8iE5aBkA3bIgLHJdCWB15GAUgKOnxZUBS0SMB9k37LC4AygHgGwBgApxN+q4DgJIAaCbA6g+AK8KZh/IED/ypmEgcIM3JP9KBh6YoDQK6xnTmKuFSbEwJ9pEV2B02NvNwKoqQyMsggkgBuWyCiDJA4gviQjT3qvF+RXubyegCZkszOQ7MzmdzN5n8zBZwspQZKPwIKUQSMwM4GIy0JTAGJeg+YHECrC

EkaweKb4CDJq5VgfIVwDGPPF0jzBGIR4rAqvExzHAzI9aYAVMA2DsEupVJG0XaIGmp9HR6fQIUBKz4ei1c4VSITVHmnF9AxDoW5KtIr4TQUhm01CVbj24YS9phETCIdOOmVo0xneX2mQguBzx5glQyiU9AsomFDCz0i6I3ECxjQB+seL6frN6rJ4sWaeaQQeCJpr8teX4fkBwgaBsAYwklcfJPkrxLRfJkgfyYFOIDBTQp4UyKdFNimxZc8w45fD

4jf4lB2JnpEJHMGbKzjKZQw6HrRV3pI196kg22RjWi5nyagF8q+euOPkQAtoFlaYITkpy6QSk6U7yFlPGYzBo+LKNhL9EBTFT4U4BBlBUi0HdJKwIMjOaTDfFjo3Bxcx0baO/HJ8y5DoqZJXJdGjTgJxDBaZ6PrkINfRQpaCdFVgnwNfqCE0QqGOtr/SIxvcnaf3IBaEQUIh04oUIxUqg83MVQyYKRKXlNVQSNNV7uI0+mtDhhc/XeanUkLjjAZU

44GZAodL8SJAE4ccAu2CDEAFAvM3xWWBpEJFKipwjtq7G8XMAgl/iwJZoD8WzswlCCAESLEUmnUsOKknDpCI6IaTB+/dOEV3QkAIiBiJQMjiiNtQRhmZrM52VzJ5l8yBZQskWYNGnrmTAiUSmJQEoDTxKywiS+yX51opJoimaaFXpgXclwKbZNTJcegEkAtA7wDQBRBMHRA1BMAdQZQE0EqAYQGgN4fQJvxdBflxRVcPoFKIfq/RvMWg9hCNXWDN

DCupNKsL5B+B/BCcMKdzFPwsHTSbg5OVnMnP9xpy7KpMC0e+KtGfjE+PC7wUIgVp/iK5AEs5mNJAmq4bmEi2blIv9EwS4h8ihIW80QnrStu3c9IXX00XZCPaDQYeW7lHld8J5F0qeYTkq7GKqFc85ebRKBAJBQkotEGLYqgWYtHFi/bsUOKPkdNGx5QGAEYEqB/hRKMmG+RXh7FLRPy+gYMMGFmD6ADgP8rPCOP/mIyAZwPL0lQmWAx5981/XiXY

stmwLrZnkhBSfOPHCrRVBedBfys3FwsTg/+eeP/jzJOR2CPcanI1lnhPL4U7WahVdHJx1oh4dwPKS1z+VvAY8Rc60VwtLk+CRuYuKFcNJhUiLLmYiuudNIgm6IoJC0lbqXyDHl9EqYYpxfQzQl9zvkmE0oNhIjC6LEmhEryDih2D6NjFhkUfmvBhS293MMeNlZ1Qtk/SWJD/KQkAu0ZZ1tV7SdxUnQPDZEDAPgePL0tWqTrUiM6kokkrSEpKNU/j

UEZkvBFqScl+HLSYUvtk6SkRLqcpRIBmVzKFlSylZWso2U3gtlOyvZWZKF4WSp1xKWdbFFya+d5ejk9kc5M5EjKjVoXcZaasmUyCJAMquVQqqVUHKyKXAh+lMGmDMRcUQavBUeJ7iKisckwX6M5H/yLAsZQDEnN5kWB3BFgycwyKEgYRmjORDmT4D9EgarNvImUwFXBI8Egq+pvC2NYNITVroM+2DB5jN0mm58NcSKuaVmubkvNW5iitaZXy7lFq

a+6i5UuWvkw5Dr5p3cUiPPBynSIuGYisAsB2AB0qhuKI8U9PMXLA9NEfdgl2uUY9qeqv0h/lognL1jj5UyiALMDuq8s4AEYbBKOLAADq3CfQkHiOt1VgzEmEM6zff3YzcrBMUZUTNWQ6BgVCNraAZqRpYgUaSstEmjU6rEYcJbgEwEmUOQtTkyNZCAmmRTOUwPksg7qM9fMsWXLLVl6yzZdst2X7KJyYs5coQIAppCgKxs8gR0DOVjR5ZdZWgePK

gGqySK6sucYRTYFqyOBMGuxhRT1nWaBBCAIQcbOYCmzzZGvCLnbJc1uasQHm7BLfRkS2rIAWCjGD5mWBUJDx1lMyHTXyTbBcp88YkjoXKl1EauiwZ+tjmAFh0FgHmdOSHwjXi1upRBVjf1I43lypkhISXNLlwCZ8DaiuZXLpPEW60QZPokTdIuzVLTc1EmzFUoqQk4rZNaiu2uhLLUDzto34atd0NrXYpyyY0VuI9LzGzMQZxm6iRdCcweFg6LQ7

tYat7UdD1GbEvzRxK9IDCDSY62fhOscYXDp2EkiXVYAFZ2T5JqS9dcpNQAd0We+65WDuo56Ed1dxS3SWUoMlgalgsq+VYqsfUA1RhsuqXTkxOKfq16/nJyZvWcH/ql4Yyk1RJC22IK6gMAFCOiCaAfZe8bABoJhEqA3hnAKEdhLMHwA1Am8h2iQN7NrgKV0StkBFAaIPFWLdIxCn6Fjjy6OCxonvPDXHI+WJzLggUVOc1jDXt1t4ka4FSXNBW/jR

uQ07jVXOEU1zU1CK9NQ3IL6iaAx4mhRTjqk2dyNpBOraSWo0Uk6tF20TfiSoc1krlZ2mwdC1zODMp6dd09uo93pUmbWIRSFnDdMs0z9uqO88QTDJ5Uz7V+x25zRgMqB5VG8ZiLsQfNA3oB+QmID7HeDYCzBsALQTCH9hThAQsQUAMwCsG/AHTlVpvP+Z7lXyAKBdwCuHJhu3h6qJthjE/Byu5FWzKmi4h/UESEBX6OAN+m1SoO4CGREyOwdnDYIt

43BiFiOdQc3Fz0VYOs1C3FHZFbhcI5g6lZiBvJYXhrLRzGnqSDvY3grfBDerjbQRGmdbYVoi+FeELz6d7IJ6OsTctLzXtyC1Ki75qPoU2k7IIwYCnSwKp3/AWUvwI0bmNX1rwiFG+lnRsBWYsGN5e+76TZr7URbVFgPKA0OoC2wHRdMPauhQFwBwAXh+mfiLpMZj48Ggnh7w4uT8M099qCkpXW3RV2qTslqsXJbdL3U2oilh63nseoN3oAvdPuv3

QHqD0h6w9EeqPTHpuQtKn1Hhrwz4eIBhHrd4NVkd+r3wcindrkmBYBrd1VMzVzmp/QgBf1v6P9X+p7D/r/0AGgD8UnWQ/StIzA6sBpSmh7xnF6DTNz9X7UhuDWDC3l48bzM3BHA4oikvvJyH9va7fBFj7ENMtdpWZcH0VYQ3rhDpjX8G41GDRNbDouaPMBN4E6Q5mtkM975D2O4MbjuxWFqNGcmonaWvkIT7IITSxMfhOQHSIoo5KnQ1iS2DuYOd

hYoPJhpbXMo5RzK3fV92s2H695AJyAxnWgO1gWD4C8GQauQPMZoZPWsAE/2jLiZYyH/DYw5lrAjg5GlwPY+2VUpHHO48wdEyszy30DCtCBrisVuiy0yytDM8oFkd93+6rMeR0PeHt0JFHRZ+AtrRLNyxdayB+83jHLOoFDb8tDA6bcwPgHEBiKg2cbVWlg3zbeB+spbStuhnrbVM1mlo7yKA3u6vJiCxINgCxAUBvwUYIwNgBkyb9SAdQGTMoBLg

RhQzygF0IqFj0Q5q4xytLqNHaTxB54rZVYFiRMM3LtK08fuITjlFMQgQA4ahUXq+Wl7Bw9wCvSrqr2A7OF1xuvXwshUCLoVjxxbrXPb0RDJFaOlFbIrRVx94J/ejuY6Bk34mR98m3aaCdwAw7VNoKdTcQjn0UqdNA4L4K5LIm44mdZilnRHKsJYkrD2J7nbYd532H7NKYu+ufowNXgL5KwBRCYhTgHA79U+ZzRGBjDOB9AkgGTB9lwARgWgE4D7J

JRgBPZMAQR+LipuX6/zrE3m3zYSecNel0TvpGjP6RC3kmPFAG1020fQNRdLzbAa87eag2nmjt+B+5LjhmAjgqamMPMkMwxyTA8z/+MaIWdWCxy2CFlIwfQpRyMKM9lGu4mwpKDV7ZuvU0Hbcc43NmHjvGp4/xsuOCaCGbx9AE3M+NY6+9PxgfcOaH2jme5QJsfSCcJXJg3aM5/hpTr9oYxu0jgqodWDRMVlOE2ORiTids32GoLE4vFt6SqluHpqg

RG8MQA+wLVCiMoRVEwGSJUgwg0u12G5Y8tRFvLYqInv5d0knVG6mhKI0z3F0Qj1d6k3ddruSMHr7UJSyAPrtGLlAvTPpv0wGaDMhmwzEZqMzGbN3C9ygwVzy6gDCtKpUAkVvpV+vt0/rHdxTZ3W5J5Hq8oFGFpCM+dfPvnPz3538/+cAvAXVwoF/C7Ns/xwZczr3GOXQp2DZ0sp6G40e5iuDZ1cFMeGricHymHjqD/+crnUQ4Oh0PMz9G4C2gylt

UAdHCqNfWbY1gr50EKwQ8Jab1CLRDya54xJdeNdmoh3e1FS3IUv5rlFXzW2hkPH1aXCI2AafVNd4Cwm/aAdKhD8GuUwi6qszBFGibVEjhLSe5redZbsPH779K/M8x1owOrg4AMAVcE0BLhLA3akF5xZqpCRwWbp8BiBfOP1nhbCbNJ6LXDNi1RaSsu1wFPtY7iHWBh7ZIpNMHRLXdvSdC6KAKZ6zQCxTFMyetTKVvJiUBU5dTN6d9P+nAzwZqM6V

bDPlW8BS5dACuUlmamis2pl/rqe3L6n6BZp0imzcm2mmtZnAubSgIW0Hm7TRsh02oDNlOmDzLp7q/ApA1RdyblN6m7TbwMzW14r3bPcAOIPwoAGWU3Qs7ypqI4o8g4UWnHIZSfAMuw8FlIwqrNKXeLAm/i3waesCH41EOqHTLlEs1R4dIgRHWms7PCa/rHxgG73oxWKWhzVfYfWpfBuaXDucY7aBjsKGqEa1CN24OgRHCmKjDfwDc5I2XktdlmKL

KywedxNcr+d0FycSEmF11FQtB52HqwP8DCS8w1AHYUKQtCoAzArAQohfZ2GhHggqACgPiFKLBBGASMHYdTznWONMgZ9uIuBEvvJFr73hu+2oCAeIAQHHAZ+8JLfukAP7CAL+zA9/sYcIjiu9B63XisBE1daVjXfEZSsFL8Huuo9Z9RysSB+rb5j81+Z/N/mALQFigCBYqv48AH5sKB1DCvuSAb7EDh+8A6fu+GX7CDpByg5/sZsmrdugZY0favNH

XdaBj3eapqCYRgwHATAC0DgDOAjA/ITYAlxgBRgZMmAUgFiGwAt84zy3BMz7M6a6FpgVVZCvcEJx1pUNW45PfCSWtbBX6G8mru8Cngzw/gAIc/lWcLKdcPxfF3Zig0bMvWr4IloIa3okNTS27Am2J3JbgltyLaeO/4w4cHv4qIbI9nIf4f2hqbSVqY+G2QnOCdI7Q89tG81SM2bmsUTKCjDnI3sUnmJR5rm3WL5Wk2ouMANgAokfkTgIQEqk885u

ry1568jeRfNNfpsn9GbLEfcqSaQtIGULLurqx5PdMdGMD3T3pxQH6exnoNKXY7ZgrGCARJbfkVtK3AensI8NlkcPnZFcdEaDIImftNNIRTxBA1RSVtJsd+1VnuLwToFaE5tHhOwd/CqJ29ZENmYxDKauJ5Jd4AZrxDyTqS98eBvpPlDYN7J8PdjE5D+QWhkDL7lbBmCgQBmllGidxTh954rk6w9vJssoTB1k4utP/lQJwHkL463B4DQpiFFOY3MY

SckWeDqBS65dN9eEsCNsuqY5RUIty/9t8vKgAr5JbT0iNYOMlMRrJUlc11dFUresVI6R30kUP0ASjlR2o40daOdHCiPRwY6McmOWH1dYVxy7SJcuOAPLyQJK+lewgP1cvSR9DSGX4lZHKzt0+0bDtIRcAKEO8JgAmAlwJgUAO8BQEAj0AjJmEZwIrHGBeyLHCezpgeJmDkJSyLOIAZRaij3AIKLvc8fWlQLFTvHXwB5XPAXiBPOptZu6zOlmQROa

7IL4Q0mqSfckfr7dts+PbkX9nUnSQ6TSpcyd4r7ajtZ2q7XUPRAYbh84pwubhPMQ5gA4I0nPLeA1gW1nZdpK2Fzrx08bm9ql9Sfadn7OnSEOADGBWAfYJgmAF0FPofN3zygQEGAPQAnAUBY3iQZRwojYATA4Axr1ZfoAnA88wLKqsA1psfMYHcARgXAGsHRCrgKAy6yd6PgA8T4IDjh3ew5ZZSsQN5rNsk4s+ZedXUDm2j0+aqPcnuz3F7mOwpQb

j3blgtNQCKZAcw3A6ilkMOqVNbQBYro3wO4EqKecHIw65OGwUOFppXS8NJ1jZucf7MsaAXs6evQ2+WSgvm3fG7Pq3akO/WO3ch+Sz3aRd/GUXxa9RQ7Sdou1NgOlyG9tF2d4SihU99wjsEqkLvkTT0EcIYbqEs72ExBtO6yv3PNOedDimsXZZcW6Mc6aHpl2LpZf21+XIqHywkYCNtKgvCqcK+EZivPQ4rYIhK9usIda7iH6rjK3rq1fuoA3QbkN

2G4jdRuY3cblwAdpKPJN8eddMNCF4kcXEWrDR39U0dKbev0LCj5zbe/vePvSsL7t9x+5gBfuf3ox8inaqsgLAfIiGlrqnLUqtotK5G3yEx6qmLNUcxUx5w1LuI1nbrNerhYC8Evg7G3pzVs+6Lb2SGhNiT2T6EJzUpPJNfdkcwO+2naeR3ensd4QGxdgsKqRotj6LTImoeW1uOZuOc/+BNOlnh59z39M88zPs6n3hC/qsw/+fkIVJ7U7SZi30mkZ

wmAfhmSVnqqVZsmErUVsixY+oTk5RLNNkDfBvQ34byN4kGjdYhY38b4ry1tVNm32tFt9clqci3FBwK5WJzOiSqxuZas9WRCkeX8xMqgsHWGoPbYVujbzTM2521eSm1jbJfreAb1xR4GLY5IbIzrfRQQAbZWJNa3bDxXYp8UpfIps7Bdj1/XZhT2H41fI7w/ObW4q4DZQgBjCPezHG4k7UqBedzMo+7SKqUTKm+6FTgjkLLe7yoFrGOadXBFPWgVE

RzQ1nF1eK5LLsSWK7j1+WtXfuPSe9v40qF22+O9iWluZ3i4z26xV9v8dqlwd8TvRdYTR7kEYo8Z8nv6XzoWJeCkcFs+wtScBY1G0WKxT4z/oxwGFP96w9b2PPDN/zYWde5BJ2CR91z8oNZiRf6rSPFHhL0p7S80Hgr1JqL1n9k8KeUvGXgrrXXyuN1irrdaz3Z6quUvR4EjoMWREZHJ6gvc3etVX8k85/5PSXlT3Ec1G8m/S91y5Ia84eerzXjAx

OHIA68zYli5mO8eplaHOtoL9DxAE/EFA04+Mk45RQ7EHm4IoHmKAKAQXvMH5KgoDKWQo488AHQ44x1sLQvONvBHL1oCQJ754acfqJ4be4nvW7EEjTB7A90afnCp7oiKln5Ke8Lt24XeShqDaae6lrd66e+nrk4e0v7tX4CEc5iaQlO0KMjbHAEJAZrbALaoDD1or3D969+0Pv35/SQztCb7OB7ktB3gklPoCSURgD6ajAV7lKrJgoHuB6Qe0HloH

y+XiKYECq1uFmB1AQEBMBNAQKCAaweEFmqo+ag/oLree4Pk5KIW3QuP6h26NOap6BBgUYEUAuEHs6T+ClNjinA1pBAzMm7EIAz0eZwIUj5uLHoW7TMJOJPA42VNB3BAgP0Owb/awnkDoJ8YnnW5AuTZhLhlg0OkwHTK1IAjoZ+rARJbIqMik8wxU3dgOa923AShIl+6APwGjuk5q9hPe50vdJlCQdEVKLuUULigtq/0FdA2QVwKoEH6O7mb40uyH

j57OWJLBIBBwwQKED+GZwuUD7BIQAFbb+sVrv7K6quolb4OyVsl49EOuhq7n+6Rtq4QA//rgCABjAc0qlegRKcGHBVXqr6gydXjI5f+Fvrh7rOUXCB5geEHlB79eVpoN6IB6JgTiB0QthxbZm03jjjMe83pWBHiNXIThh8gEIZAzwjgs0bC0ZWGeR56wjI2j3AhctW7reEOpt5V2dxv4Kp+Ddvt6tBHeop4chHAWtyKGINgME3ew7gIFjuCiOMHl

U9KGQGg8ywAZoXAxLl2jWkgDBS742rTtixOGe9lHLbBEPmb4hBWHpzbUm8PrzaI+sMruAEhoSESH6MP0NFAdcOphHwdYVIWxBnAtIfLYY+QpnTL3kkptorZeJPnl7k+BXtT4qmptlPTqmxApbYyy25KcC7knPvuTuYrXDqb8+LWIL7tYSwKL7S+OPmrZ4+5WtOT20AAeojfBC5HT7BhRAhORSy3WtbZs+UYQVLc+SwR9zxhKBImGnk8KCmFo+6Yj

vDSYjthaYq2MvhL7ayCviphe21XrRRSyDFFr6U6Ovsb5HYpvgb6sCRvmxSThN2L/5dO/IEGZ1AKcOiDkEsNuY5HKljkmazMGwGAyI465qiFXQWlDTRmUYjIDCXAiGjnZsEHCK84LM8KE0KBYpQa+IfAxAdlytgQBCja/O3BsDpVBdJLQG7M/IPyAewfkI0GQuLAVyHtuPIV3ZfGQNvyHIuPAYCbuowwfd6TmoXgU6zmRTvOZaai5nBhMQHWEcDfh

t0lU6sQlTu34Igv9CLZmCznlu4T+6gXZpL8vKvu5yISEDgb4AkgN+Adwh/KRCSqDgZ8hOBLgW4ETOlpiRBz6QHlFxAQH2DJicgCAJoBRgIkbYFiRgHte4SAdQIkDBglSO5h4Wp+p4F2B3gSD5D+/gRu4/qQQSwK6hwGmEHOa7EZxHcRJHicr3afwGvYs0DgiDLpB4BBsCvcZZK2AoBjFtNIZBNwFcqto4/Ijjohy3jH43WITuXZhONATUGRONJHX

bTmMTnDrNBzdpyEJO7Qd2adBxtJjrneg5v0G4qQoTp4jBBnq3jk6uludwShtoPZAWUQdE35B4YSGiZWKFHieGc6Vmtu4E2aoUh5Z0KHiZGBkUPu4aOMgQM4DyYQgH0B0If9q7DDRo0eNEooFwbF5XB0RjcGJepqEQ6PBJDs8GlKGXktAwAy4Zvyrh64Ra5DRtUjNFssBNBvAuudRjV7AhbVsMpeu3/qEHSCUXJUCCRrge4GxBCUruHB4OwKcAWUh

lrgo3QbkfmJvhScjcC/A1Bq2B4hJOAsC2QZYhpRgEZwESRVm3mO859IdCgaSsQVwNYo/hFxlQGMhsUVt7AuUnk27gRX1kjoZRqOh3Y9mXQV258haTup5IRhOihHChJUUIHJgy6otIT2eltoZ+0lXM6oY2swbwCKMphlihlSvNAyi0R7KgD4MRx5kxG6RBFqxFLQ9AJoARgMAAojB6YoVM4aqRkZqEBBpkZD5Q8APvqFw+PNtxh823NghAwxRgrig

woCMaWSLwOpqjF44dOrx65yLoUeiK2o5OraK+mtktAfBXwcAEFhQYebYamTPlbYs+dZJGEVY0YdVjuYk3nz71hJ5G1hNhqYYb5uhEpr7GCqe0QdEbh/AoWEhxoYWHHhhJWGViVhXPrASpkh5InGtYQvs2EXk07rtgdhkvl2Gu2Rpu7Z8g82DabNWQ4UBQjhfOtr4sUE4RxRm+3FEPH6+4KL1ZKxKsWrEax9kV9F9IUAdsBaRBLB5huqJpBkH/Q61

qIwfOUeNQrvarKHcA/Ah4dsDPi4UUMiRRfztFG16D1hJ7EEiUeBFN2KuJBEmUsLhACyWsESp69BanoX4ZOKhlp4sxaEaVGhA5URCYmetfhVS3QehKsBVCJ8WiZMK/wBUIWaLntLHrB04ZsE9RWoTxIDRLlo4yIAfqPphFEqAIgBK2S/qQzHBEgHgnsARrDsTEJo5KQkrqsrpg7Ai6Snv7LRcRqtEPBg9E8FpeZDvzyOBzAM4FvRR0a7CUJBCTQkR

YMWPQmQQl0Q5LXRgyp/7BcD0RMpWRGBs+Svk75J+RKCQQEQByAukuly3Q8QK7ysQZkOCTwW2ZjpDgEkwNqrsQWMZQhQx00lnpOYhpEzS6EI4A5gl2jibBR/0FHm4kgylATwb/h7lITG1BxMbt7sh5QI/Et2HZgp7QR6fryErS9MT/EaeyEWi5ZCbMYRBGAE7loGaarYToZ9ILcO0gbyH3vMBomkGBwjGEWJnREoJnUdqZ7uJNorHlATQBOCJAdro

QCb8XYIM5yx5ql8SGIxiPkLMRekcpHweACoh72WWdMzbzOwQX55rOfrktBNJLSc8DtJc8YN4sQmXJnYsGGwGUK3a0JL7444CwDoS0073It7hy0BDBTsQ9gh3BVmrEDMDZiiOJmZ3JG8v4l/h1AdUHBJ8UcrRshyURcyRJ6Ua0hnKr8V9a5+nAflEChhUaoYTmpUZoBjQ4ofPraMSzP9AtoBmlQgKBEfFsCQYqwbRQyxlUaMlee+LE5bs21mifY4g

C6uDCTRj+C+pWa80aiQ4azKHcnmUh4SDInU2DvF4suK0dCJ5KsIutGpeiImkbkOT5C+RvkH5M1q/UpRjf754FKaSnvqNuq66DhH/n+r3R4IT/5W+GBpgA3gUAEsDsAj2C/rKAqIIkD4AA+AijOA91NkjaJw7OcHjGxXFKGu85oYvanhgED5iaC5XPzjeQtlBgFeQhgk4m1RNYK4nfaHiR6leJLiTPLuJTGrjEBJLyQBFxRknh8kkx4SaeqpRT8a2

5tBlMewEfxeUX0GgpA9oMHvBACYIEYuDuFCk30oCVhHyxMJtO68xPygZD1RRhMxArur3G3BTAf3m1H76mKagm1if7ixG54SEChD8gMACsDem6IEICdJJ+uapSRMkYgDyRikaqrgGIyT0LqhWwXrG1eZkTsEoGiqY9GCiS0KOmyRE6WY6fRg3lMBHUadoTgT8FNNsnkS8zOVh6MdWCvF7xSQM1jrAk/IjHsEgnumi06iMWIyDg79OUF1mtbhGlvJU

adMj3xsaU0FK4aUc/ExJbAV3qd2vZoDaqeCEQzGCho+qhG5p5foVQFpICaIHYpeESVIWUJIYAwfexEczp1O2hGHSmQxEcqEdRqoRsFzpGCQunAhS6QSkHmxsSz6GhZscaFxaUiJcAQULWLji3ANkDKEI+IyRbG7gnGWZDcZa7nxkOxkccYmkZzcOYaU4YAmxn82u4Mzh++9wPelaEj6dQKGJOwG+lyZMKApn1x6Ph7EFauPu6EUUmcRIC7RK4WuG

5xJQK1r0+IYSWFhhoFBGE3asFK2C44aon1F1hfmA2HJx7SKnEzh6cfTIWZ6AKqnqpmqSe53gOqaQB6pBqZsBGpgYb+SOZa5KQLhx8Wnm7/4s7jBRku8FHGE22lpKhSoUnNKvG5aLYcNqNxbtiPHdhTtkpEdxSvtRTXRPttLImy/thtoT+w4Rr4L8xQuOFzhw8dOGjxfWePGIwk8ScE9pfaViADpyyS744EtSEyotkXSHTrwBweHVwaZ3wJUhC2tw

KfE6iutPDhVgv0GcmUIDglcmEatyUPC0pgUV+k1uMtATHMhQljt48aXyY3bxpUSYd4mgdkACniWQKXTG9ug+kX7XeiGTmnqGUKYOJdBSYmb5U6n4eEiXpVQrVgtqojM3B+QJSBimcqA/tM46xYPn1Fs80yTgmuwxKdOqSpy/o4z453alSmGCNKXBT3J5hnF6bqCXuwnspiRmq59EPCbyl8JYWWqkapbAFqnRZuqfqkAQCWfdTX+lVqsQSp2UdInS

pV0VI4ghd0WCGtG1muh4jZi4UhAlw2AIkAlwwYA0DMAVfjB4KxpHuUm+QGmR3AYU+6ctkLMSZE5haEOGncDBpHHq0hzMnwMsz3iFhk4IRRq3lFHx+uzKQRC4gEY3oxpT2TBF4MSabNLZ+p3rlF5+XARmnF+RUXd7IZFahX5Qp70RhkESftADD2hWglUI/AK+nZ6ixxQZ4SpaNilzr0RraYZF+BusVjkWRg0a7BMcpRIxz0cpRCxwssZ0WOz8sk7B

yy8czbPxziskrMuyyshnLuzacTnK6zmc+7H3kvsA+SpzSc+nMHij5xnJ5yT5LnAZwac7nFpyScE+SpzmclnBZzZskbDZwwcmnKmxKca+c5yKcVbCJxmsdnP3mr5xbOvmQcgVmSx15VLPyx9s9eYOyN5o7Bxwt53HHLozsneQuzd55LMJwz5HnLpwgFSHCfk5scnG5z2cK+Y5xH5Q+VPnqcUBZfmwF1+cfkH5j7EvnQFB+ePmoF8BS5yb5m+TvlIF

Y+VfnvsaBXGx7spOGfnGsCnNgWkFnnOZzRedPDTn7+dOerpH+EjEkZKw3PLwknq04ULn481eY/m9sDLK/nDsTeR/kTsX+e3lSsv+YJw95F0EAUwFc+TfkL5lrJgXIFKheQWhslBYgW2ctBRQU4FZBXgXgFi+cQWz5oBV5wb52bIQW5s5hcAVgc2hb6yUF1bPoX75hhfQWWFjBa/626sqQFzypsuWhaW+kIUhCR637iYhPYN4CXATgXYLEURgd4E9

ibAQEE0BhgrTCAFJuYAbDgLAPmHMxqZgEG1hEuDvCyjk0RZqzh06+2a9ok46JFjg2Qy5qQGkZBAesxh0V2QyFEg/IBcCq5tmT1TPW/6YSDARoEWKLVyKUSBkJpgebrT/J0lhBGpp4eSCmIRCGf/HFRgCeknoAUKYMVg5kJmZk65odJIEM4OwA44zysOUxBomjkBAxkRKOe0JA+jEcOlbF2gQ0kSAV4MwAUAMADeDogmwNdhaxBJmMkg8vUWh7BaU

ydgmKJq6colPRG/I8XPFrxbtSxBzvuAFWQdoFAF7JmMN5DMQdHvdJce5/H5DR8djrThupweLtY7ArODWCpB9wPsZ3EQIjxb0h/zlwrtFawJ0W3xrIX7lDF3yS9m/JICB9mTFgKWHnAp6aXMVgpCxTHnA5iQElwVRyeWQg749aBmZFJDOsHghyVngyoMeKOMca42UsX37F5vgUSY/Fy6Z4pDB5dHfleKOpWTksFbCcq5Jex/lynM5PKZq4X+bwWEU

TgERVEUxFcRQkVJFKRS0BpFJXtiLhe9dFKm1GsiVLm3RnroEUh2WHgrkCUSuY4g8AklJUB8sZkFiBrAAwEYBdgntPzlPYSUZuGgBeiV/jZFD0uzgOeBRUDHfQtSOiTvAlSFeE4Zi3omTepbVFdAeZZwI0V3EzRSGkieYaRDrUltJT7lUlIEdgBgRQGW5IjFr2fE5/JbJdyFxJ0xVyXfxf2b/GouQ7osWx5SmvmmJA4qsKV4+7uDsXt0R6RHpY5ZE

ioEixlEVjZ7iWZgXntRReTUks+dSbrlmBEgN+A3gzAJsDUgiQFi4fFOKaD4al2odOEV50CnI4QhsyeUBXlN5XeWBxm4dCWw4Y0PCXNkiJdPDse1SN9DzA51sWVJyhmn5HjwRSM/T4lGMISW4BrqS+KklbuZfEe5Noq2XQp7Za9YMlLesMUtBYGayUx4yaQHk0xfZj9kF+E5cklMxfsUDmgmUKcVRLl04Xklh0TKv3yw5xZjuWYBB2XcB9I5xfYpH

63cugnfFmCYgaGxWHifZL0ZKXqVelzCTF6QVDCSwnXBsRsaUcJppVwkbRLOZaWvB7qF2ARlUZc0ktAsZfGWJlE4MmWplIqb8GOMild6Vv+3cXKn1egJXLkHmIZfgCjZfKEYAMakgJOATgJcMnjEAUYJoArAEYOxDKApjrEHplsdg3BZluRW5gVYy1kUXnAWOIZD44TZAOC/05ZTUVbZI4PUW1lVZg2XsK7uXjFtFHRYRWRpxBP0VdlaxR9YnoPyR

RXvZVFcHkpp0GT0H5+vxkkmMxY5nwGsVkKYkBe0nFeIHbFZaaU4sQTvJZ5t+KJpcmCVL0gMJLxKwU2k2GWKbu7tp9SZ2lLQq4DwCaACiOiCzAKEASCPls6d1HSVtGT5WalqFkGWWRIJXtUHVR1SdUJGjmgc7AV3mPYJgV1lBBUol30OwhZVQSEcDZczEBwjFSyFbYIElV0BhUklMfjhW/hlQVSU1VXRZQTbeoSY9mMlz2X2Usl7VZ9k5+nJfRV9V

jFQNVZO05fyVsViQDwxFp3MTi4WE08B3BGQkpUYZXQ5EVRKyMeZOEgGkksYXnVJlGapZSVXpC+VYJcldD4KV+pfYwRKgXipUyuGDs9yGl2lXcEqunBUzkpGhlS8F8pjiAFW3AQVROAhVYVRFVRVMVXFWtyoqcLnalMtc64S5vpe5WghnlUEXeVfxb5VhlUphpFaRLQDpE2Bu6TNkq688GAz3pjcP9BnFDvKmTP01HliTC+OAcVK/QtkH45OqzXOa

Gi0gniOCGC1HjR7RQlzhtYtFlJRDpe5qNT0V3x9QfXb+5EScyVtVdzMOXvG1MTlHdBcEbBmJJJNfMVDVM5QKX9J6xWAk8x50N5D98vNFWmoli8svbmKGyQHWVJypWoGtpmgcTbnl/EdFykATQJhCti+AA+UGRapTBbGRvxfvQYeotd1RMZj/KbG9a5sSxkdAUwL5C00i9qwakZh9R/yp1pzj6q44b3jaQIQJ9exBAg59TdCX1imUJnYyN9chQFkz

kP8CP1u4CnX+yeegRGZ1VZJ/VgUMdVjjluvSHMy3AeEMA1p1iOBnUdYG1u7FthJmRmGbFPsQT5Zx1mYdEm2yWcWGpZLWdSYFZpzgiie+P3r8DxxdmFjhAgDKI6HPKDmHXEQC5KqrZexEOZVltx1Wa3Gy+vYQiGK+A4UCGdZmvlcVE2c5W8C54I2i5kIQL/HhBgAz9WfW6QF9WcBSIAmGmHkNYAM4A/17WK2j/1p4oo3KNr9ao3v16jQhADk4kZXh

HctYcZlyNJWHo131hjYA27gJjQihmNLKB/Wf1hvto26Nkxr/UGND9XY1gASDRiZgNaDRA0thwyUZmYNe2ENlThAPoNm8UiTcCXrp0qHPUL1TQEvXTZMJRwhc0aUkcBORomaekQsixgMLd+2YoAxeOzEGHwiVZSDxVGU0fkMgI1oac8n3WAlndno1h8A1XdlJdXGk415dUeLUVI5d1V11X8XBn9VTdczEt1lNSYht1NdeDlcVBljCSYkMpfNVPQ9Z

F9480Y1PxmbuY9WsEnlO9l8VC1Mlf1Hb1uOQJJsAbAGEBhEHAOSJhQRPKdGjs6+LqX543Djc3CS1gA80I8zzeyyvNBpYtE4OygmykJGETCf5q1FpRrVs5EAOpGaRB2Z7VJMHpcTkfNtzd83qAvzYyBjRTeQC0uVvhUCHyJARfbX3VMySolRcklPvwcATQAdDXA34C0AmINQM4CVALoKQAKI+gOhk3FW4VDgZl7dEgTpSeVblxXA1GNmZeEz9MZCM

QlYChTLuOJfWSfA2MOybnAIzDdKCe5VeSVreOdUSB51dJTaKaAPAPyAHVseerQtVZdYmnjFQ5bEnMBo5UTVKW/dlHngpBKssU9UiQCbXt1xabDZjydNRdDACmWnHQbNDOPnkcp2eZRENq5oSIxiVLTpcWyx1xTYHO+zmmNF1Aq4JkCYQ5OudWC12OBqLYxdGQbE2Gwdqs6+uZLUhDxtibRwDJtuTVtDhIz9GCQPK7CJMDnAa8bMzUWamRK2PKbZD

iWrAMDRiXc0L9Tjgu5LTdnVXxXClq1EVD2c3rNVZFaBmmt6xua0QZozbRUwZEzQ3XKW/2X/HqWahpTUugMKVhk+q2Yn0hs1T0Cnpfew3kL5KlvNSqUnlmTmm1+QGbSzY45uwegBxKfim80QAD7WLnRWPjOpX1ESkktGK17RCaUq1ELelZQtW0VaXuoFLS0nUtHALS30tjLcy2st7LcInlAL7QtJ+w1te/7+FHlSuleVSqSEWpIklGsBRg2AJsBXg

swDACQdKcAlkL1cAAkDhwibtuHJuX0UlW2QKzF21OR6JEcUO8M9rc4VczBrpB1o1CiBXok9aK2A/AllOQhlVrTU2XtNmrfsze5dVbsyAZ/TcBnkVk7YOUdVnBF1VztPVRHk8lmadHkihlNbhKutYgdhESBU1aUKB0NWHx2CxHWEvZBtUIFqI04jafs2nt49ee2T171ToGyC+gKuDogzACYhXgZ1SvXo5peZjkb19GSLU5tn5dh3fl9xd52+d/nW9

UdOiVcIwoV7SAmSPi5SFpRk0XHTYIC0vHZ44k4ftS2hElEGL207+FVbhVVVNJEO1ydvuWEmKdvZcp1jFU7Wp0dQJ3p250VCSb9lLtk5bwEzNFNSNVNAm7VTq/QHPosACxVngziVmS1RdCAoO+FLadqyCWe381F7dRlXV5ebe0jCXij4rdK2auQlDBO3Y+2AtzCcym05rKfTlgt+SmaWQtYAdlbuoCiHh0EdRHSR1kdFHWsBUdPADR0/ByLZEqHdY

uSh0+laHQ7oeu29MS15tkyc7XKpUXPQAtALoLMCVAKECYi4AKwHeD6INYC7QlwygJUANANPpy0JVpHinJTwxkEyqPhNWNm7VmcQA9IZS4GE6qVF/kWcr2Qr3ExBM0+meJ39teFYO0yd+dcn7ydRdfZVjtTJYM0qdlFfjWh5tdZ/G9VNrVd4rt/Xfp0jVHSeNUmdk1bhFU62+o2RpmVQs5C1poSL5lzVn3FUnLdkbW07bV09evxLQQoE0AxgV4HeA

8AOiqm1rdpzddVO1t1cs5KJD1ek0SAFvVb029Oik74YKwFRWVLWbODZ4qUVzs0Q/RVPSYp/R1hNHXKUehBhUGNJ2ez1Vdh8DV1/pKfiRUC92NU11gSBGtO2ZRIeR13ztkvZd79uMvSxWzNI1cAY01mGZDmc0aKa40kRzfvaFomkwICDBRJ7UeV81RvZJUO969S72T+23dEq7dT7e0oj9x3bLWndrBed06VDOeC3XdgHbd3bRowrD3w9iPcj2o9lQ

Oj0huWPTj0IdQ/TEqAh9RjdEg99xAqlYdAPj5V+V6ACXDfg/4OZhLAmADJgrAklBMD0ARgHeAlwLAJIBYgiflPVx6GRTy2KU/+KcAM1rcPaEW8WlG7xY4krb8BzuVTcW6TwpbrPD+OBLs01QgVbuq0Dt+Ma8ldNRMdGn1dWNTRUvGQeep3EDnMbTFddDFT11MVg1e6hMMLDGwwcMApcPiK9JacHirl2KKyYVNzNaREi6M3eBjWhukJm3kZx5St3u

dSXbtXlAhAMYhQAmgCo636vEZPVIQ4YG2JxlT2MoCrgbAFGBAQNQB9h6A77qYBsAk6XB63yF5dMp94A+EPgmDXgdOmxNgtbowIoNVIEHZt+srm0+u1/aUCyD8gxwALN//bcV652RX5DUNJkKCTLZqQTAMAMc8Jc7bZ+Gsjo/RxVTpSeRfjswqEBEnRUFXGP6UEl4DISQQOY1pFYX241MLuyVfZnJewQl9BUbp2j6DA6wzsMnDCNVDynFXopkIczF

HJLWsOUOaEZu5TCSE4c9uG1ueElQPYODUck4O+eAJVt1kwVrqK62u9rukw3NSwoEA2MFAE67Lc+3W7BTDhxGK6tJvLq4zOAiwx4zLDS6kwVyuJ3Qq5GlStX+2aSqtYv3peIHUtC399/ZgCP9z/a/3v9n/d/2/9+/ZMPsw7LtMM7Csw7sP7DtjCsMA9rlW67oddtZh0O10XQW1LQklBB7RKvMqv2a5JcJrCkAcylACSUT2LR3ctyXdUVCtMBllzTw

4NQ7zQD/9MyjRDCAziUlul0nHUVu6AxYSYDlVc2VZDukmjX4DTop8lEDs7SQNQRM7Za1jNEvdp3wZvJepY1DTA/UOOtUKb70193sf4Metz3hWC4KTkT36CxEcsS4aZ2+kgkG9rneINdJzmqoNQA6g5oPaDug/oNdeRgzYP6R1jSb3tMnnUUqbAcAFUAIA94EOmSNS0JcARg15fyB61cABZjBEOyhhBwAQEEYDYjHge3H29l1ULWjDEPQP3uDTXlD

1IQ+gI6POjro370fVX+HcrZ0qwMizZi7Q6SPbiaFRSPwD0OX6reYehFeFFBBguiRXJF8YjWZDN2bgNJ+LIXV35DWfeQPkx4GQX0adNdZQMKGi7ba0A56iuKN1DApcSpNDpnnJBb6uhkzWyhVaQyox081o07rVlLue0l56pTGMMZE/uLVSuwXlF5KVFtRV77j6DjF5klGlVP3nDv7bpX/tC/bpibRWVsv0SA8I6uCIjHAMiPMAqI4QDojooFiNfD7

wRF6E8R/XInSOMuWD0+uEPZ4OGjxo1oM6DegwYNyA9AMYM7pYxgx2I4lvFe21gRI0ARQDFbVPLFjmgqWM4lS3m1wreyfSyONjv6TkPvJnI5n3gun1uJadjR3t2PkD32VQPE1NA6TVZpI48wOU1VahOPgJ3APlLVg9gjAlNNspeYpaElTboTajBzS2lrjq9RqEwkjaq+Vb1NhrvVI+vGHSaCZtZMROo+hmT4GCmpmRnF4NEgA8NYgD/U/0v9b/R/1

f9QpJ8NEN4siQ2AURcQ40dAO5NHFVhB5AnG+ZScUL7nk7DQuacNsAjg34+j5HCMIjuAEiNw9KI2iMYjv4w5NqmTk2r5pZxcUWSlxHk+XFxxUxlXE+TNcWeQi+5WQaZNxxpqdjFT7cbrJdx4I6Q19xEWj1mDxCTdj66+84Wb7xjwRTF3yQeQqdVyRkJYBX+9rvoYIWU8jOiQllYdDWMO8tEuASE4xSN6S/4NufATI6ofg1x9MkfrEPJ1dY201I1HT

ZXbNj92RjWjtdEy27NdXYyM0CjmneM0VDkeUONijzDLUM8TI1ZNZGdtfUIwGkrvI3BZ5zfkjECDM8jHKAwMky52HNK3euNr1Iw8pMRd+sifZ7jM/vf7r+T/ov4v+ktYEbT+vzdDPz+m/lIlvtJw5P1nDP7d3S90nCVzxn+wHcZUlTptY5Ui8IXmLwP+G/s/648PhTKkEtIEwGVgTCYzh3SoE4LMBcRJAAgBsAzgJJRdgm/DAC1AV4KuBxcltf4Nc

tiZism1It0EEjY2/jv9UlS3TP/TVYIlRpQF6bBFgHWEAIHgFpk3zm+FXtH4WQFlIZE1J0UT2QztPdN0yPQFiAAFQUM9j31qQNtdhQ/En9j3XYOPl9jDDdMSjApRy2LNGxRNUcDZnfmJIsFSO95SlB4vDl44L9Qg0rjKoT321J5gxACej3o76P+jAqJvxBjIY2GO2jokW6MSRHnXcXoAiQJvybAUYLMBGAcAJ2JKD+oxgYcAJcAoib89LTwBQACiK

QDBgkgHAAyYOEsGAvyT2DxDhjkzkF3axIXXozOD+sTqGbdoyo15tTsI7lYlzZcxXNGenLUBX9g9mPHLrWnvKaQFj5ObAOUjhE7blQgHwAUHGEfHmtVYVEUSbObTrI9q1cKCndyMDNOfbyMUxnVZBnV1FA512uz1A+7NTlEgNxOSjeaeUBQpYs7lAd1nrbpoAEMdDAnsIxLuYbWEo9f9NyTgMwpPIem42DOEpfwWkAAhB4xAD/B5qapXMFQLSykgt

F3WtH6V3KUv13DbMxzOJAXMzzN8zAs0LMizDQGLMCFGCwcF4LPFjIlA9rVqf1ciU8273dUV/S7USAyc8wA+jP7mnOBjN4MGOhj8IR7Y+11RT6pUIMMeqLgDOE+AR4TcAwROxD+IYYLmhS+iSHWhcNaTAUhwWA6HhIToXr1i0WAxz04DlExbMcjgimC5Gt7XUUMzSZAzyPvzxfcKNTNoo/QNezo45TVT6/E53WBI6bs3AWUe7fSh4aXQwQZWk6Jlj

miD3fYMMC1ffSDNjzi6a4NhasPsxn71ek0Zlf1xQGaHRQBixm5JSDWHaGXaQUBYuvSisvpOkynscFPGTYU+UDPjr4++Ofj345iPZztPsHEM+ocSlOuTCslHEc+nk7GE5Tx5HlMpxhU6djBZHoaFnRc7M5zN/IdC/zOCzNQMLOizSWY5MdadFIMvkNFYRlMxhPPnY0bG1cUmHTL+kxVnthVWQNk1ZFpnVkVTyvm5UBU6vuI21TA8RahNT/WS3HfLw

2d0KtTX5bPMSAKwPyAugdQPQDnYH2FGAlw3ECSBXAjeFOasD8VYAOx2W2b5C6EYGFYmhzUA90wp6jaK4m7xMrXeEhIV7a4laiZ82fH+t9yoQbVlZAeK2XzDY4fBMhDi7kPTIvTU1UHTri+XXuLTs/bOsTn8+xPfzfXUtB/zApZoZsD7rZwO/0gUICgxzk3S2C2dFEc0SlIF/KOqxzFGfHOnlOc3EGJzJcA0BHAbAB9iVAHSfYFm95QHXMNzTcy3N

tzHc13MpwPc12B9zVo0MlmDM9ZoBAQxAD2klw6jvXj8gT2A0CbCLoEBCYAMABQD/zm4VOkqRic/oNnuKEDAAlw9AC6s3yCHhdUnNjg6DPjzb5ZPN3VebZ4P6rhq8asK9UJX1OV64cu87aq4zJhVQVJUnnaHi1OBZ0HtMrQFE5jOOCFFMKtY4yuIM4aebPdFPPTaJ3zdswrgmtR00xMnTMlv9aCjaaeOUcT0zaKsBLd01KOJA4JknkQ5QjMN69M6w

H3UtgvA8quaEqcuWTkGGq2INarq3VGMZrGS9jnjDWpeY4jRWLbNHnRZCVLUADd61UYPrxw0wlYzrCTjMSA9wXpVRMpDqzl8FEAKCvgrkK8wDQrsK68UIACK4Ki4AyK6TM/dVcK+vYtE0Xi30zx/YS0Yd/C0CXQ+Qi4mPSq9c43MmIzc63Ptznc93O9z/cx9EoTg3qyigDLPeEiR4ffOoswNCwLO4OCdwNtbQxednDG2xxgvbHIxnwO87OxdWEOCZ

rOMZJ1XzZs2yMF19JYQNDrni4xMIuFrROtQZZ00KOzFIo1UPDjC6xGtx5qGYkD89nMUs3NDckGBgxyBZAZryrGzQyr6k8wA46LdOowDOnrEgx2mJzEwFeDMt2AEBC3AKazOnDDSk5es3VW40bE5Le9XDJaTBS7WRWxfG346Non03DLCbpSEJ1ibZEd8AYNsjXMvmZJk1+BLLNCysu8zay4wtbLCUw5lJTey2Q3W27k6MuZTRSILQ+ZkyxcsBZMyy

7bZbGtrlsgbYKxCtQrMK3CswbKwIivwb2y4lO7LpYcz4ZZ7PnuSxx/OGYkUCCYb5PJhgWbI1lTfDatu5zTy41k9xby91mfL8TSk2NTY8VOGT0gKzCOPV5QJ5vebvm/psFz5vC84zweMpBgNqG8pZDh+LFs3AllN2tAsyt+8X5CHxcFC7yrTZQY2UZD3a1tN/97I2yuQ6fPQ/Ejrufcjqvx78VOszF3Jdpt2tum4wOBLI1bHkgLNfqEtCVLUlqOa9

Sq+zWURYSOWQ1px68kt4mZ6+mvpLYwxc13tyEEwBUJhCbQmSJ8M0TkiJLO2ImxE7OwMDozq6pcGnD360q4XD141cMAdd4+rVEzmtRatEb1q2Rt2rlG06vUbiG60q4JPO9Ql87EiQLuc7nC6h0vLwPQolQjJLVLlmRng5oD6AawBQD4AIUiYgmr34BGD0AdQPoAUA2ArACPrNgaam6JsdtlXWCqzCIywUL2wQb/AAahR7pSZwOnkytnic4nepQaak

Ocise16k+JvqSDvfpMmzfPEVCm+2Ol1QvaOsqb/I3C5WtbE1L1l9P8+gBirlNdDaSrNxTknDaftJ2S8damQZqxDsS15BlFuKL6369sk6jkaBNc+LOxtGBhQBRgE4JJQugWIJgDlwZq+aoerXqwmu+rwEQGtBrIa2GsRrnLVGvpiEkRvzKA34PyD6Ad4EYDyLG+6YOprgW6PNhdWS0HZRda6dtoj7Y+xPtT7ZbQQY5SHcPcn4lrbdmYTGv9Dr0OY1

hM2pETJyQdnwkR2YtXnzLTTcke852ZTmPJFJdgPXzw7XtPvWXK4L2PzDs2a2tdJyNysl7gq2XvLtFexABV7I1ePambk45gHUGmyQRlSlDHsS7nJumrz7OdXfYb0pLtO7ilBbDOzYZEpouXt3Pr4qSSmvtQu9ULk4DapTn0p1OYQtndxC7P2XdnKWQvmlFC8TOAL1u7bv27ju87uu77uyYie7f4yTmUp6G5Lm21oE6bvg9Kk4rkEbgC56veri+/6u

Br7yKvvhrci7HbIE6gmZBuJGFF86kjFbX9FTyM9q9xoDB84quqZvmA+kPKJdtpkyZ76WUnrTUm0ytWzEfIDBZ7dQVLjF1980p0TtBexXWqbb8ZOsab065M2N1fi/OuY7i6wAsSAUKfk5cxT0y0Pzu+xbusNRpkE1E80ELK8qMHzaX3v9qyCz1GoLWa6pMc24WxpMKNAmdFscZhgqJmzu4mbxmSZCMgZMmhwmKMfZ0CCZMfjdWmdJm6ZHmSjgtb2k

9uSY4oAsEcaZoRxGGrHPwJEcbHbDT5qprWW0ZMhZnW6Bs9bEG31vQbsG0isjb5W2NvOZ5DfZgR7j2wxYLpjWwL6NhmxwFO4RQU+KbXHLS2UfKHduy6AO7P4Oodu7Hu6R0vHRYW8cuTByxSEsG2WWlJwU3pFXHIUQWGhSlZy2zw0CN2PutuPL4WA1kq+x/c1mrajplOTWaYjbttjh9Uwdt8Nfy8duJMp27fuIKJiIQCEAiQMoDLgMo71MZjpNC85J

6nvp4T8xWlDTi2QRwHO7EaA4DZ3FS9uQszrZyzO/RldUUD87WLzI6bOp9XPYkdIHzi+cz2zym5kdF7Uxcjtjl+R7OuFHns8Uf6bUjWUf3lw3UIztIhJO0iqjCq7Wsk7ZhFuZh0BpH/RHrrRxtWqlwXRuMSbV64zsTDEAEIW15z+QOxMsb+exycsn+VOxf5s7AJz/5Owr3kaFJBSgXGFenGoWQFbhcvl0FhZwwUIFShRWdaFJhegUAcNZx4WVnXhZ

BwEF2+XYVlnWBc2d1nxZ6YVUF9hcoWWF8+eAVPt8Z0/miFyZ+IXv5aZ1IUZnP+bSJd5S7AAUrsTZzoVGFVZyWdrnzhRuetnahXoV755Zz2fDnqhf2dRs+ZxYWOF9ZxQVWcW+f+xEFXZ5oUnnThW6wuF1Ba6wGF6554Vmct+fNFnjn7ZpXftYu0rAcFku7eM8FQG5f6JMrC3RyJnCZ5OescEhbOdcc853xyLnf+cue5nihRecOFXnCOcNnI+ThdDn

V532cEX0+URe1nz59ec6FGBYOeUXJF5+zgF7Z/eednh592dfnLZz+dqFrhWxdPnDF2AUNnQE36W8LHVlydpN22poChSQgLCszKT2PQCfkm/ChBCARgMGD4AJiL504jksz7UNwZ1u0g1gJiT/xUICs5dCJkJSGzrOqWXETjNr3mIJ1liInSYpkhTRekMZ7BpwLiyd6fbz3JHxmy4uoH6R/DstdovUX1adWm74s6b1046cClIgY9NyjK5UHODo33uH

6rmUpetYLBRZbToAHoZ6uN6j0bYPtOaGBohPdpTQE0BAQpq0POfFbBxfuxjoW1h5iX7vdtoFX/IEVclXz+7Wjf0AMMENOq2OCHu2ge4udrmXAcjBTqzutEV3x9NlIn0MjC0RV31jYO9J1uX3PS2NCGOeygfZ9fl0/OqdgV8p55HA49L0EHRB0utihIS560aiLHjCh0NfrbMytR4kyzoImeWTMGZXccywdAzik5VfVXYtW0p/dPB2V4fXH6/LUSH0

/VIfi7c/Vd1yHN3bcOKHZR1JcyXLQHJcKXSlypdqXGl990a7v3cP1Hd+hzbUQjRhzhsX9wZU7WeDXYDJiaAawEYArAm/FiA1AMmPPUrADQMQDY9MYDJjOAQpSit0dmRV/hnWoCsVVoVAtPwPZmwg95gUjiMRsC44pltZd2QjPYCihRBpFWBs96e9dmuXBzIgeHwg67nsPzq1+gcBXJQwTXi9W127M7XIqw6e3TTp03xQpGEZUcxXs+ir3PT9ghtb

+H516gAGCLaknqFuolVTvMHNO25s7Vic3p4UAswJJQmIMAOKqRjdO+wdVXaC9fvTzQK+dsSA3t77f+3i5SWuinsJaiRUNWwKzgv1XjTKfDeGGifGAoDKPIy5Bw13H0w1Y17jhJ9st60XVdhp4rc0TS1z5crXoxf5frXmt2L19jiLrafCrKSQbfezlNRzG47tNYqOh0iwbnd1YmvTqft7zVGWIGkQ8P0OA+j150ffF3R+c2cH716jdi5YXk5XfXE/

eePYzwF+UB/rN4yDc3DvBRkbRchN8Tek35N5TeYQ1N7TcNA9N4zd/jY/WjcXRhu1VM8LJu9jfQjl/XjfCLMlpIBdgBcAyBYgguHkKbUj2LgBNAm/PQCGdNgfj0puoDL2Qj+DkC7e83u4j5i0SFlKmTLAdKgEd3oPkInZZc2hEFgy3U1xtOxHxIPWibA2AKDmsr1E4SC4A+cGsDARsO/nuN3Ivc3dBX50z4sFHYV/4sRXlNfdR932YEr2Bzltz3wr

M10JetblVnVddYoEGI557Nh5W0cXFLBx7em95qvyAcAbDJoN2u/m/YNpLId6Yf/FMZ5/dm7ng5o/aPvMvIu5Xidzpc2Xaoo9oLy+jDdKgEwg+g9/7BoqUg4P80+PAVtedzUfvS/wDI9Urwu2q16n0m8yuUP1D0ad5D+03XfDrrD2tfsPldcXvWn1raX34H+t7/N6bApYOmHXA99ULWU4/FEvfQAbU32k7o0OAzGCDB0o9hn8kxGfAzhj2Hfbjk6l

YzIOBw0+0ZMWTNY8YzlEcdQM8Wlbve/rytWBeH30u0B0PjlC7oj/3gDxwDAPNQKA9+AKwBA9QPMD0i3I35KW09LDQl4YdMzxh+BNGPkPazPW4+AOy0rAT2MKDeKveJvwzgJcJJTnJCG3j2orBPaAzbxxwOTtEh5PX8DuYvkH5iLMRQUE/8d+D3aCEP+2bPLgH68V2uuUUTzQ99rC1xDoMPxAEw+2zKt2kcN3ST3jUcPm1yjszrHd8xVd3WO0utJr

te1oEKjEwS9KqUQnZTs+nGFHAkQMxkAswz3m1QnMDJ6jxfp1ALoGwB6eDQDDpB3FV4vdZtE89eu5rHg7/dBEHL1y+aAPLy1ewlaJUPdBnXwGH2zWiZCgT/PjXN3txDvj7QqeZNsYE+p3Zd6Q8xHM1zLQwvMTzXdtjy1wk9oH5pxMUpPVp7kc4v7d3red32T/w8jV1j0I8ilU48yZop0k8YplP495UjMmYfpetJLbt1yqsHz5QK/vlTO10/tP2TAj

OtPbjPG89Pghx+1MpO9wf7SHpCwBv3jeklM+fIpz9+DnPlz4QDXPtz/c/zAjz1Rxm1z6ls8dPdMwYeY3ez6Y8mHLg/9yeDiQJJT4AygDCjdvMmAohPYH2JoCVA9AFADBgKcBOD0AjQ8ze4jLz+AS0pNYNWUfbPNDKfxy9ytg8eNzmNxv+RwL3KJFNYL0+nC0qrZJug70L1sDRP1d/Q+MPzDz2WtVwvZi92vHJdreOv21+XtZPlezk+U1MQaushTs

V2I+BITEGzpC2dR/PL/ngb8xAUjbffAtMHuo65sD7t24nMoQFABQDYAQcChBxgfL1G9RnIW808A+tV6S1R36AMh+of6H+WqIfDHUyhmURIQvJ1Y7ENLfjTXaBu/ZajylLaLe2rwxZXSqi8E8kT8NVC9hOpr9XdOLMnr5fov6t03dPvpQy+82nb75k8uvn7269LriLZ69rrG+DmXeE/r36fLyfNNNPSt915qtz3DT89fRvOawF4i59bwm9c7mz8m/

bPW9wBcXjP6+gD73oz7m8y7kz+DdFz3b72+bA/b4O/Dvo7+O+Tv07zofzDmTCm87Pzb6D37PbRhBNivxAFeDOAd4JsCEA9ANgDBgiqkIA9gLoC0DxcXYBQDx3aZc89WOKZnYLtSWGtgoyn1vM/Ru8HzpVKZ2iAx8DIDdIwE4TXQTrqeVd5E8yu3ZtD/+nCfpMQxPyeY6y/OeLAq23eyfvXfJ+EHX7yNWZJJL/KOcDHWHQrlIoH1uJaf5inQeYaGr

2G9wfqjwh+SDic6hBGA+ABOAvFgXTaMz1sa5gDxria8msz7zmrgAwAlQMniYQMYIn4n7tgx3hn7Bjy9ftv2a8K+u9uG4R8e96AId/Hfp3zK/jAgNY9rpS33jnSnphJfg81fUwHV9jTuD8navOXSPVufO1a7x/nx/H4Emyb/a4tcWv8T0puDffJJJ9a3XbuUPcPdp7w9FHht8DnbAbpz3xaCF4nhnUHTmPDkv1j2rbc97CC+0e2W899GM4fpn4P3f

D1cCK6bDwkk+3uwnsNL/oAf52koOfQz058jPHKVwXyHYN3Lu6ICX0l8pfaXxl9ZfOX6uB5fBXw5VIbs1BsOcuiv+jfcLtXv6VRfrb6K/mHv89gBxrCa8S80bfYVtC/QhgscYsqFuQxpKvd6LU2HiwUB2p6aQ1+PA5iz9BeKDMhJIDCJ79ZZxlser3KzUB0Qfoa9nvMUU2Nwvu04fC6t+rZoCGtpp1a9q35p7ytYHVMWveE1pexk8Tf+L6X5pJpRy

sV/ALP4EisQEGOVwwJ88AsEtY3fuHSu3O3+7d7f7mzPVYgJiPQDMAXYHACbAPEFh86x7G2gGh3slWpP9Hsx5pNDHMx+xmRbUiJAFODRwOgR4yCKFfVpaJwI2SIxzkMSSU4eEAf8mXx/5iR1Lwx+f9okV/1xv803p7uAwUMwO3AlIhBg55n/jv8lMtjJY/kB9DKIn8woh0Af/mn9//pWktCJlsyZFcd5ljcdutuBtINv1snjsNsytsidGfPstrbGc

scxE2E/Dg2kMlsMsAsEw0LFiw1iqoFkQTqVowThVoloPF9Evsl9Uvul8YAJl82ANl9cvvl8kTgXEnMqidqtiMtpttz4cfn8c/MoZQiTjcteGnct+Gj2FyphScRGsf1GTv3scrs6dihtohZGto1n+GAB7/lsZH/tFAgAcACtGtbYdGnVxL/j8Br/p/8BtLoCOkA/95gCf8jAVY1o1t3hbGjI1dsH41zAfaFLAR/8cAjYC9AUf8HAU/8NGrngIsJ4C

L/t4Dg/jf8v/t/9U/n/8M/oACNGudVZGuydrNMk0TfDPMiPkEQp/jP85/mrtl5qWt7bshUR/O1h0TBBh8ynehtxIFg2+jQoqEPYkTKLU0WVM1wJmLToBPCHxnLnLdpkDcYqJr0UOViw9rXuT9ScBtcXZmN9dbu+9Jvmu1IUrpAO/kqB9DFHIbeMYozLD5FooDAQmXqgljmi4pPtNPAGjq9dK8lc1Pmnc0fmk8171ji0fYNgtLJNc00Wvc0MWscC3

1qcCeYHZ8M3qLss3oDcZDpr9Qbsfc3gpd9rvl791dmUYUWpcCvmtcDHmiJI7gS80zgXb8jdu/ciWtF9MgcD9CDi6AqIHMAwpF2A6gMGAKAJUAYABGArwE9hN+JsIxqrO8tLjCVnAI5hzwsjgOfN8BLgDKcfoGeI2OpSCBmE2gGvj44y3KgMtTq2p8fj2tCfvC8R2sgdSfqdMMXhadmJiN86/rgcG/rQMyaq69GfmxUawFkl5vnFdmqE0JukP9AYE

nMZZHqwgUMHWkJurU8srvB8crhR9zVpeA2AC0BsABOBJgEN07vsB5Hvs99Xvrd9q5moCloFeBd9vvtD9sfsvaqfsAtt99o3s71dgR+UI7mdt4QZy9jQaaDXAhD9wMJ6od4hcBvEi49ZgbhM6QePxkCPCxiVh0h/IN0g07H0hjFpwZy7hq1M9kJ8WzD2UyYoMCq/uqBsDmk96/pUN0duFcpQVMDcen7NQFgU9TrgSxG+mRIqcI7dhOnnkYPso9xKj

TsnrigtRfv99xftFwQ0EKhIZgzl17q7AdqEeMI0Er8Faqr8CHBLsNftcNxngocdfpXtEQXABkQWsBUQeiDMQdiDcQfiC/xhOCRwQkZQRvi1MNozMnfiK8Yvoc9PBg98nvquAXvn/1wLEI1iQSyh+bjZBccB3B13Kj8a1lThGvkj8XUjR5o/iH44gDKJ8pEwZDIJJNvnGVgxNvO53nGwgWjmE8OvvqdkGN198/pbNCQEX8DWv0CK/oWDhgTgdRgV/

NnXk38FPlWCpRvCgZgS9JN8MhQDyoG1m/FMAW1HlVf6M8o1gUc1EmOfsvQZvUFnCY8SgOpNN/oMcjQlsc9/tmRoIdbw9xDsYmNmcdNGjFs1BKBDh7kxtIIVIh7UsFArgGJCp7jzREAY0tQTigDwTjJY9fqwDDfhwDjfjwDzfnZl84v0tC4vgCI4oQCgsJhoflDZAtMsQYp7hIDUKLQDRTFw0QplmF6BmuCNwVuCMQViCcQXiCEAASDelsQ0UTpZD

JtmXFjljWEJlv8dk4mVkrlkVNbli3EyTt7V+wpVM/CtVMusqOFtDL1lWTrIDUgR28xXo6C99gfsj9o4cFKCfUJboeJrgEE9iJseJXfFoQfMHGCk9DYJipDzRf/hiVFgJUh1klWYzLgw0k9DihU7m18nkhE8UIXn9IdnQ9MISX9sIWJ9K/ojscjr2MP5gRChVkRC6Bgz9u7lMC/+ip9lmpPI0we9Jt1mvBQPguNignSCnNr3sVHniYNgdh9gtt6C8

PnqEN/rv9uMFFtjAbWR2oYfFroMVkk9M9CpIVIg3oZqI2LN1CvoR/w+ocIxNkl40GuBpCsGu5DmlowDGGN5DZgCiC0QX5DdwYFDgoXnE+lillnJuFDXMpFCZtvlkzlrlMLlvFCgTq2E6AXKNPIUtArdjbsoTjCcndi7t4TlodETjgD+AaQ0ywlZCkKEVluoUtY4Bg5DIKJidYKIOApAeL4nbMlDbluSdrTM8s37slNiADVNa+rlCMgWycjtguFXf

ugADSAohVwIsoWgMEsE7oRYLoJWBJjP3xGhK9JVQTWsDBE1DZMl2gBwBsB6ga0gWPFlUtRCx5/6o5dSStEcc/jaI0+j0DiCFNDS/hC573hkciwYdMHXjJ8xgXJ9iIRpYW/ihl80v8AKIV60qIhhM5AjU5B6luZ2TNPBFRH9NYPi5sUlldCh/Om1zKIy5+wSfYCAHKhHAKvdbhKEo7mkaxhou4BsAPxB1iFywFAK3kn2kXC9WB9dElBXDUAFXCCAD

XCbXGmcG4UKwfrqE9t7s8C2Cq8Cc3qzwILkZUVwVf5a3oERm4SXCYlG3DrAJXDapNXDa4aER64Y3DG3hjdjdjCDnfizN2pstBMIB9g2APtFKfE0BnAJhAZMDJh6AE8UgIDJhJKFGAhuukUWbkANGOosYwauVhawEDCRWrU1kAvicbPKc4CqpWU6ijWVhWiE9vohyCWyijUzXn0VOyn01Ujo10cIdElknlkdn3q3d4IuN9xQVmkkMkz9E8tFdlyhb

dcko3sqsMFglgsYpLrrZsmqHoQ46uS4luiP8I3mo87RoXMIADUBz6MoAbwC0AOAMvU7BsAC01hVczmoK8/vtxCAfjjc6rogpWEViB2EZwiUXjY9dYQ3AQKkel9AR+DdZhx0nMPVwyuN1C+kCPccSpDVUKkzQSuhmDB4e19prvVVoEbmDonAgi/YWw9H3qgipPugj66iHDG/mtDyanL0yIZyttoWZtRoFhpjgJAtBYnoYGISjgPeEP99PietDPsPN

1SgIiY3rGdnKlZ9lKgPDqhDOCXgVeMgbrIdXPhM983h59D4cfDT4ZhBz4ZfDr4bfD74Y/DH7hLUX7oD0oQQ78RLuf0v7rjdOIaGUVYRAA9PGsAgIFeAbhOR9/3D797OuARSyG9wbbpwgpvNckzBEjlG/D6pipBsZVmGWI9inihFjiXZqNCbkacD94bIBQE4DrYsiQN0Cevl7C9WlhC73nDsBQQHCsopw9NNqjtQrhWDZeqzFW/j1RNgEzdf3p4jv

oDvgPMDjgDNDU9aIRU9bQBLYNgNSoeahnDEFlqts4SPNIkbdC1/n0dwyAaE8li/wz/vNsJkeu4AQNTgeMu2R0tPMijcktZnIJDDMfNg0W4u1tcGjpCIAJvx8AJJQEAAFUmgNcj0YaFC8AVVt2YZaQQ3lLcOsHWhqXspl+4BWQnlEyimUULDDTCSc1tmLDUoZ3FJYRlCsYTLCsof3FmTl8slYYrCGpoVCGkbij8UYSjiUbA8ivl9FE5IUh2cNZRcc

GU9QCK2gw+H89V4sZAoAZq8OaBcBEgqyZ4UC2g/oEnVhaO9pghkHJ8cJTR1mqe8XLl0CGzLV1ifnE8y/nnsBgcgjC9kKCq6rX9pPuk9ywVdMzkUsULkZoBNgCZCTNv7MRHmS8qomvBock2EaIeU9rPB+1x7mg0qwDKIvkZ2CI2rt89Qft8J/vyA1gHoFo4ApELQVFwmkS0i2kbaCeET2CaMuXlAUUvcpqJ4MsQLmj80QgAFIumNdYXYJK2l6pykv

jJqQeARQkG2ogPu89vvHvF8HtWVIWMyh7gONcIXrMwOgRXd+uA6iPLjq0tkdNCdkYk9xPkN8PFl6jDkTrdCIeMCw4TgjpQRxVZRqp9zNnpQHNndc7bqpQFAtbliDHVDtvpnDLoWxDvvpEixfifZ5YHKgMWjhgGQA+sSeKEBkiPc0BUEKhiAGwBwgE+030XEQwoJ+jPoGdEf0STx/0aGggMSBjpwX9dLxnvd1fozkpdoBtJ4TC1JUQSiagESi/xmB

iP0fyAv0dBiwiLBihwcXDgMRzETwRhtgJtLkW3peC4QdtpMqEsBsqLlQvduLM0qIlUEUr5AkNIUlekGAca1nVIDSFAFyvkXZuoXT0TKKzVqvpQ8/MFvEqzJ5FmpHaBc5JoJsStn87URhDl0Y6js9iT8XUfyC10RT9bEVT8loRgjHEVgjduJPR1AZci0YbWC8dp61qynMwWcL38YlrU5dyvoYEgBLEWIfzU/kdAYxqFQ1V/rWjrNDXCUQAYAJwLRA

YdHj40qMugM8DnwiQKaD4sTWDhFESAbwCd9UsXIgA0BkBiCBMAbwNljssXo9WwhliIIHBiCAMsIkZmd9jnugB0QLgBEvsGAUIHAATEDeBVwMGAnsAuVbGAogXaEYBfgU88X4cl1/VAA1iep0hM8vMFxpkvpXnHoRKQRnUC7gcggQPnZ93pK1iJEe8nLpAi0oIJ9tMUSBEXsi8Zof2VoXLa8jMS3cTMQ4id0aHDnEZKCNoWRDqar+8A5pGjYUo+F3

gNlx3piiYSRmqDKnuNRJmJ3100QMNR/lmjx/gaDH9DAATEJhATqnAAk1ov8R5hxDwukCjnTDftxLogoe0gDigcV1iY2oUCdLkfMSmqvJemO1QRsYgFkStkEwGlNjWkH48dXlx8KcDx9QQO1wZ0dmDInhe9YXhNDevnmCGulYiBQbtjLTmgiDsQu0zMZxNtpHtcg0ZsBy1B4iyDvchjICjgxoFYstyhz8k4VigrgA9ImaGmi6nkgsjPr2Dgti+ik3

mF9bPom9icqF9unvEj03gM8gLkkjUMZcMFwRhi83nd0loFViasXViGsU1iWsYXgKAO1iJgJ1iQvhZ9rHjRim3jvDsNoxjHanUijngfDKgCsA+IPyBTAFo4w1rrwnsN+AnsF2BnzDeBtYZGtaNgotsis8piqn3ww5BUCf+D5AiSC1wfvCswgIZRVYwiP4rQpVwKkCXZumOHUw6CjhHlHSEbFin17UTfEr3t7CtsW4t5oeptFod4sQrjw9TketDCXj

zi/BvziBJhAE5mFMAgBNZs6iIG9ekCmjLLMP970RG9K0QvccPjWjozuv8QUSbEhIaxlBIWlMxbigFwYk0IhWuvo0tCXi++GXjjRDChUUW6EMUaZk6psLDOwokxNZDIDxYZ7Z0oaI1e4gKiPlkKj9tgrD8oSKjpwgR982lkDMIDMo2AADhJKCO8S4B+ZOQNgBMACYgYwJgBQqppcdwnulv6JZRlmJGCp7pndlgBBR1KMOBrcsNjcHmEgDUWBhpbCa

iFMUgQeaN9p4UHuIuflmD4DjSR1kWhDHFvTjLEbsiDMYKDx1tkdm8V4tgrscj28f6jUkjGJI4YAtNgC61bMcZ12BtdisMkixBOlho5Ai5iJcZRE2OqDw+fpvJzoV2CGEWP9PbjPV/bvQA1gKuASQBqRQccAojcgXiAsQvi3BtDixEeaoNCVoSdCTK9qaM1IcNC9MMKN49IAKARDAbxjTlIzgvCDbD6UCOjC3O8AS7myCdTiNDyHjQTacZsji/j7D

k1IzimCfsia/lujX3hzi51lGIcnDziN2vk9yXmvAvgM3BmTE8i92nZsEyExAyEZPifkWEjyrpqpscBhQQzpDjj7K5ZhQOBjhJMRioMU2AYMX+iKMXqwqMaBiaiURiSMY0SyMWCgWiQhiOYr09yul+tBnvrjhnobj0MbeNMMdC1gNn/iWgAAS6gEATKgCASPsGASICVASYCUjd/gUFYOiRBj6id+ieicVjKMYhjIQVLCT+h/dPcf6CZINkg/QFChG

YPhxSIuDxKEfZ4eaNDkyMnQjuqEhBqWnUBPaN+AgIFGAWgDeBgwJ5t+QM4ArwC0B74ViA3SgwTV0XNCsXhwEafm3jjERcYtoK3Be0ciwk/jf86oa9tczFDkkSpoJJgKLRq8ZDoBwCmBjNiESgIgw9rQnyAdrB8A6gX9BkAqCR95uAi1EYsEd8OOihwOQpPWlRDjRDdJBxjphsACCTEgC6BtnPgBEvmwwEADwBYHB9gvsEBAm8KmtmXqktz1vTsjC

VEjKTEvjcliviD6pA1EKGZAjRNWBiejhk0KlMd+4KyhFmFeFFWvChiYS9CpEPMwUKGEg5Men8UfJHFQFLSiZ5DpRA+FaSfoXZgysM3AWTMAJfMOYIn6tnofIrBRnVD9ocktaS7MImRUMJ2RpjLoZ1VnZhpgO/RsHkZcy8USEIUR0BiuFR5WarqTIWA1tQmijEhcUu9cQkhpvIBmTigJQZw/CCRZ3FzUyyjaSkCCfEsYvKdBOh1hyyWABAYGxsk5B

jiEUupUKyT5B9II2hmyHPZdIG2SOyfSTjRLSjUSQNo1EazVcUIq1wyQaRRybpQo9nsVI8EpR8yWojXEliQ0JvoZbgEuTf/hMxSyZ+Cw6PlkWSUUg2SYCgOSU5h9yXSSqqPiw2EKeTycueT6PpeSu/teTtSQhAOybeSyyN6QHyYg1yci3AETPpkbOp6SGTJ+TaSa9x6SfeSmSZmTDBNJNeaCDV3nFE0X/t/9dKHUDU7lAQUWJJk1EeAx2SYjgrFHB

R9ydTQEgMN5EcIdZpupbEBpqcpcUCP47ku+S18dACPgL0hc5FtkdjN5lQmgNN+aPnIUcJYZEcPuTKyPlJlmLxlFWv+SHcp7waPAAQhbvxSbIIZogQJK1sYhWS9FhjBiRlLiU6lll+Kd89/IF2g3MIxpKKZ8BlKT0gj4tMYHMPuTFvpMBU4QkBrYSbDYKTRonHtsATcgQpTKdbD1zIHwrKVjJFKWHwHMNoJOaLuJJIWBTUKbc590hZTDwnBRRKRjj

vKQ2oyAhg1vYCiBiUvrAZAJZDihIQB9AGvCEAF/0jQGlFTiXABAgFmBm7ChIrMcGiW0R+8pvop98EX+8O+OSpv8RhZriYEAywHcSnkYnC7OstUacGXiOwTYZD3JhArwKPtdGt8SFEJsAGgHsoU4MwAgICzJ0QAmJoSW6i3sswThvvpigUgiTOCUiT+zOW147GxBjrl5FTIF88l4r89BwDHRyuIUVZ0QBkSSTwAySXJt8KpSTp4NSToYjY4dMg4Cu

amEhW/Lj9w1M/QqPKT0ykLGEqKkIxKFPmZEcpdN+SYKThSROBRSQ+AGmJKT9ANKTVwLKT28FIQFSZG8Mcj98ejlxDF8RI1Cljo1+bihQ9KBCx15JEt4UQwYsYjbEKMGgERyR+T18WUCa2nckEUssx8yUlUcFKQFrCARFX6hGSvSRQI/gF74ppoNN3eFADWfPgoZgCx4/9gcl60KOSIKA8ovKRUJlzOgE0tAnjKpOUhRMmYI2yd0j8TltZrcvRCP+

N6lJjAWZ54OndLgG2T4UHm5WwAFhnEh9t4Ub8BycAGSSMqWRbBNrSuaB5hjBOZTrwghDsZGGC9DNAQdyddBtaYmQMYn0xPwmW4GPmloCkKmQawDdAeyaBSBjncpqPEZd3npVhdKUWQqcHUh/cJI8foIsA3aYsZuaqyZzDO7x0yGYCCkEK12NlQhgsH5SQ6Sq860qQEc5L9M5tg7SCkEFS2DCqjgoIzT/KW5MF3ldZeTEqcSkPlkG4AUgC5MU8Lcl

Pd86XxC60PnYDKbPALtAxYjaaMd3ePO4Z4HY5taZYlK0ltkMpDTQR6T/gJken8/8ICdIycplLEqSQ89DBRy3AvTF7MNMEUldJg6b3SN6acpmTPpAAQLvTjCOgRmcCRk1gFPTGsBJS/fqzQBKr7TDBAHSo+LO43EncB76ThoSesGpaQk6S26W/S0KhclDyUUg2ydclX6nppUglcpljirSs9AnSWDDARXMLMAIGSjEU9DZ4qcMSU+/vAzyci1JoPhz

5OEGgyemDPZqPNwNJMkAy4/jcA6gbu0gQMQz/8OAwvThwgCWNqIuaVno2cOfwVKJTQj6Y9DMyYRpGGW30rwpHhW6aCRT6nqQLFqmSbgMQyrlG5hBOsRIj4kbTY6tqj/oSSQEUHfTiaZmSPgPoxTxA44SkFvNfaUx0j4q/RLSHxSNGRWT00IMwHBCpSVmKwzM6XKdJ+A5s0GqvEgAUzTNGWHw2EO4SMSOWJ4GVzRiikGcDIJjEIGY19ruJ0gNaZ9t

3KXYyHUt6pk8cz1a6QMdamv9AiZGCRA1JjiDGUYInbgY1ikNPAIGUkBCItjhhOjqpgkdHTAUPEAiZGmRiSmC8cmWZRmKblwYCO44jaYmQ/oORoxoIoEjLlUy9Ls4kdqYGoqaeOjSFBCQm0PRJECFUyGUHWhhBjjhECGXS2GSq8r0v5A8uAxoCpgxSKyXEBrgPjIfVOlIYKEbSF3gx4GaSsyFmShTMyScAG1DvguNvPACcJszUzPBQsuLPAyNBAyT

gBbwQqVg8M7vAzLEjvh2NkiULrHEy+ISOBycKRZ6UpDFk5BQyf+Gm5sFO1hc7h3AIGQhobPM1wBaDxT4UfakyIpCwt6Y5CIWQ6k8yAmQCyLSFAWfalgogHJdNCsDQkCizy8RpQJYhLdu9lzT7UqnCMSMYJmeh5gUWe/UsTvjIM6nY0G4BSza2m6TPMlYo6WaSRhcThoctBRI0tKyyKaFTQOWZMAuWX78/8OZ5J7nCyzlGyzhWTVFPSamsYqVAA4q

WoA6IGzCkqSlSbXOlTcqSrgsqTlTmAHlTu5AVSkirzAucdN9LsSI969szMmMYgofzLigKADUBgwHxMdYcl1DROdZKHi1g1Gd1ck7lQhFjOMxznNlwYgbqj6EL6yignJTGcKXcJrqo0zKERpcAk0JQFMtjqCfOjPYUBE4EZys+QWi9tsZn5PUWps35qN9TMUdinERKDgTBHCDNlHDi1jciBcbVxTNB6cKiS8jNmtZT40Qyo0MMeStQfz9vkYL9MMp

e0PCR+1VSQlZpaqgAFAICMU3sKgVYNyB2AKP1+XEOz5hnsMR2Q0Ax2fgl4kYgEweHW0DIIQ9EkSPDkkW8DFwRPDpiVBduhDBdIlFOzh2UsNR2ZkBx2UhMTibyjKkecSRETUizCc5pZ8BhBsID+93vs+D64HmR3HqkFxqHgpTwgwZEclARRujVhEKq0hOEBhoB0XQoDsnWVV4P3xhDn0wZZnKFKCasik2bXi1sTSQ+gSujJqQOV7pHhDSwaKC/UR7

Nm/rwSy2fwTq+pWy+8SVJDNNnRnkfGjXfNISmqcHhGcHzTZcTqCs4Y+ilSZushzLh9KiRP5eIbwyt/gJD9mQrJOMsSVccDsZVGlllvoXXThOYYJROXHEYUJjE5ptjJYObRYWIG7wLgG2SwOeOjLKZByUrh/wVOf1pABIaJ1GfUsDTJijQprDCJAI9hobhMRPsN9hfsP9hAcMDgLsSSidlmSi2YbWQ15p2Q6PvS40tric8svcBiSCWUFWYFM3IU0s

GAdmErYNUBNMHbBmYeZCBAdjCS4sICY4tWFMSDFDnIZcsSYdctL8c3Fr8fcs5fFyjKThUjKtrLCtqq4DR7LYy4mto19smK1zKeJzFObYzwUZY1QgYyBquSJzLKPJyJOUpzlOVYJVOUZzhGEkCyrvY0CoRP50gc1NLiYgoRnHXgG8Nrk3QZ0jtIJ+z9DN+zcFLbE/2dMAAOV34gOXMwIaijgwGBUIY5IeIfaeAjDIKcBN8AaIRbDdo/EisiiScETT

qR2UBig3ihmrhyg4b6jLpoRyS2cRzjWdW8w0XWC0ifMDIMPBQTLI1S91kUDMCaiSvMb8j2OcHcWcNWjvcQP0+OSACBOavihOXWQ+4KQFiSJAwdMk6Tpjq4zhOScB0eRtlaLKRk8ICdyjRKczruIdZsmWYz2ybtzLAa4cBwIdyImaTyzuaZp8zF8AT8cgCcttijrOS9g3sHZyZiI5z5iC5zTIRjCKtuNt0sq5lyEEsEX6lzUSkgnEukOOi9GCSQDM

llyTTOZyKYeUBdXKo51HJo5tHLo59HIY5jHIITIAPZlcAQMtyURFCjljNtood5Mmto2EUWKyj1tqLDb8YVylAddEVAYKicoSyd38b8tP8RPExXr3h+8IPhsAd7932WMBFuY2TMNH4D62rwB/2ZARNucgzpGDois5OIS1Gacz2OlOjW1Dgp3HItYCWFYtAica850ahyF0fdzGqo9yH3kMC4SfhCC2StDd0SdiPuYppjbpsAZ3uRz8dqHR9Lq44DoW

3tXMYJNc6W1hQ3u8SiiQ+juhIFtRpq9wVSWL8EeSjT4ZG7SBpg9smWWwY+fvks16W5NOMnnziioAQu0JJkAQOoJ36DbTfHKOSU+Wx00+ShhbGTvzy8ULcWqAfyWwg0soYeFztIZZz0ADzzbOVMR7ObMQnOQsQ4uZjDpYR5zJed5yYamxAMYv5yZpkrzgua5D0wtDCIue6gzJhZMXhtZN3hnZM3vhlhReWFCLeYyZkuWMtSkHp95tucsATpJDYTMS

d5ARyiXeXHi0oTyjH8TttsoQaYRub7yxUZTJPBlVjw3PQA9HBWyCgYndHMEkAtRnVgKsHSinCVCA7xGEgkStbw/9vjj7pH8AaiqncCZBTQebsyT/zgXyE/DAiMOQzjGCeadhmjNTUni9yywW9yK9pZim+aW1UiVGjdDMOB2pAdCNRAoFFgrgpkcoUTO2V1F01lHtEWQP0T7KoBGABwBaiWUQFfrMMl1BEQMLgkpZhijw66CjxieKA42XMEosgBBj

aYBwADhHgBXBYKhMQBsQ6rAjxPBRBioBMDQiiMkR/BeXRAhUvDoiBwA9UG4KvBUudfBRK4MhZUBAhW/Z+IEawJWMkRz2bt0cMPiARJHAB/YNsIWEGEQdicJJyvF4LSoKgA9APwdiACSJwhd7BIhQjxohd0LUWufY2AA0L/YG4LAgOwthJOvgGrP7AFhI81hJCMKJWBsRREtrsiErrtlAHUKieNNETgU2BthDeA7qL5YwhcJIIhQcIEwI0LCiLOz5

MDXD7gZw5m4R+il1MkR54bUKqjOMK3BeV4e6J2VCiOUKbhA1ZhJDUKElEvDkiL0Au4alSjWHzAGRBBjehDhgEwOOBhSHqx1iAAAKLlgAASgrhEwjRAH2GrgPSh6FBOXBBoRBRFk7HRFT7WcFmQHyFfw08FexBJ4hQp6Ufgv/GpQogAYvDCAPw1CFH6IuFwwusALwlwAcQvCICQqJ4SQuEkKQoWohCRKFWQsZAOQryFzwtpF3gsXYRQt5cEopZF/w

sqFQIq6UCSmhFkwqgAzQsjorQvfREGI6Fcoq6FBIs6ol9k5FgwqiFPIqVwgILiIEwquFUwo/RMwrOCcwvWImgEdFywu6FPIrWF4RA2FbO22Fuwo7hJ0QOFnACOFJwphF5wstFmLWuFVkECAdwv9gRIseFbQrbhbwoSUHwrtFXwv5cPwsl+qosBFqAGBFPSmyF4IvwA3cICQgYo/RcIsFAHAERFPSnmFaIonAmIuyF2VKNWeIqNYpoqwwiYtQAJIr

5YZIseBuuOBarREP8PdHCYwNwJmUV3c+U8OguM8McYFItcFzwupFErgKFPgoZFxQqZFgQqR4bItbFSwsjF1gCtFMQr5FXzVqsZWNfsi4uSFC9HFFa4pZF2Qs4AMoogxS4oVFK4qVFl4tfswgABFawoLFUIvqFDop1FOQrEA+oszFUrk6FgQG6F3B3NFAwt3F3ItcFNooOBAcG1F0wswWtzXmF7oofsnotWFh4r9F4iSVsgYv2FYINDFArHDFbgq5

FxwJjFtwsZA9wsTFl9ieFd4rlFqYtrF4cAzFH6O+FDVT+Fr4rVF+Yo1FhYqlFxYtLFdEHLFsIr808IurF6OmRFxIoxF7cObFuIr6A+IolSnYu7FDYqq8393oxF4LvZZjzFekwM3CXGIJ6nSHJwM9ibQXwFB4WUhTk7tJd4ZQO9SCZJ8etsMvJCODscHCGxw5ksepodCnkO4i98FZEugibML+WmJL5OmOdRELgLB7qI0Be2NiJwcMLZ5mJLUugvjy

mwGFOZVNuRof0jBpXRVBA9QY5TYRJZtOgh5bHJH5DvU8IKHmbgE/P7BwWIDg37nCxcoyixTJBix78DixNQASxciHVoyWNSxKWPSxYqCyxOWOal+WPHkhWOVhFWOi4xoIXqq4E0AS8yRxtjz0WP/He4xGhQCH7TVRMFUS0DHjIi43RA590gpZSOQGYXkVWYnayQ5RJI9hGyN2Y9eMw5SCKmp0RP5WIoOWheByLZWaXUlPOPHGR6J2hfQn0MvmAOhk

AwEGU8kPC/WjSl3YOF+9pIjkN7QLhrllEAhIkYA/4v44vQHxA7oD1YIgBiwIEseEQI2WGGwtAxP0pS+XzQ6JtIkBlpAGBlVRj9QAwHBlCwxHZ0MqQxIuxGJm7INx84ImJYz13ZsuzZy08LJmVVlhlf0qeFiMo9gQMpJ4qMrBlegAhlWMq12EX3dxkIz3hNrPNU9wGvo9ACEAEYB6mbAt1hu5EjCxJGmM5ChD+xSFTMNlFUo0fEmYxUkgYp3LTMRE

WsIN2hOyFOKoJRfM6am0vwqabPL5GRzUFG6I0FLeI4JuL1WhxbPClqGU2AzrNb59mMxi+yW+2PpxlEK7kpo4fHtpihIF+F0Onxb0qj2uAV1UyuMcYvJxcF4GNogGxAOINvxpF5cKXOPSkAAOAR10QAC4BKyKQhX0LaiRMIoxUTwRhcyxciIeLBRSeLeXB+jRRSTwwgA/YJhfHLy6NQAk5aCL7mrkKYAPkK5RTHKjWOXLKgEnLngDUT3xRxLPxcRK

mhTsI6gHqLm4UaLy4UnA/pRKxKRe2K6IGBKdxUMKieIKgYANUL4jPBLZhSJKkxeoAL0LUTgJbPK8xb6KAxRsK/LD3R8QMJIcJahs8JckRjhaahCJRnL2JaagSeE6LgxbhLXBevhKJQjLQlNiL2nsIAVhHXLaJUax0xbBLGJfy4i5SeL25eqKF4dXLuJZCKGrIcFqEnOL+JUNRBJTWLv5aiKxJdXKJJa2KQJSSlZJaSLaZurjXYMHLKReoAw5eEQI

5T3Co5b515RWkAm5YnLk5eyLU5RaKIJZnLrRSERc5ceLhRUeLzGLVYsMBmLm5ZXL24TeK65bKLo5Rhc45ZQq25XKgO5QvCtRd+LqRBwA+5X+KB5fy4vBcPLhJKPKoJaBKL5XQreRXXKclIvKXRcvKn5avLAEOvLhJJvKfRVsKsJX6KJWNCLD5XfLj5RZwdhGfLvhOBLp5VfKOwPBKUNg+tdFf9K5RdlS35QtQ8hV/KQZZ8K/5VK4AFSIq8xR+L24

WAqbXJULIFTkK3BZWKERcJK6xUgqpRSgqpJW2KZJf81URZgrtcf08v2gOLO6Pg5QLkbjwLoTMJxWTKpxRTKJALgroFQQr3BZHLFxQ3LBFRQry6EnKNxSnLJ5UQlL5VnLGFfELmFaeKRReeKS5Zwq66NwrrxbXL65QIrF2EIqWlYArRFcArahRIqOANcKpFTIr4ZXKhB5aQrFFYCKx5aoraFU4rN5Vorb5UvLH5a0L9FRCBDFRoqt5aYrRyFsL8Em

qLLFUGK3FWdEpFfYqIxZ0r1FTkob5RBij5e4qTlTTLy4d4qzAO/K/Fa3Cf5RMKglawrUhaEqxFbUKixR7AIRVEqIFWEAoFXEqBJVWL4FcvKuxckqjWKkreJePKMFT2KsFWUiwRhP4sNpzKLidydzVFABVwDTZseniiZXtjgPUjPAGLA0Is/jWt3nn1cKaEQ9aQorLxBQHS7JU2hVjJnzjEu5Ka8TrLaCVDslBRNTdpdhzvoM9zTZVw9ESXi96+Vb

Ko4cAtMIv3c0iZg8dPgoSPvJuUe+e3R0TI0I2Ve2yPsbPdXpQrjgkFHtwYgHKvpTOK4ZdArz7AuLeXMzLMZaeyvBW0rqFf0KBlaLxcxUMrYJWsKUeK6rZ2UsNAhQArq5bwq24fSKjWLMNg1ZDKXxRUKwlZ3LkiIsrllb+Lz7I4qDhM6LDgm4K85ZoA55dWKllf7BNYOjKjlToqkJR6KmANZIf0bcrWdjERkiJQAzYCWqdhbBKflVAAOlXnLcxWsL

s1cir/2K8q1FU4rvxa4q/mg/L1iNkLNxX0Btxb0SAMe+i/hlqLC5WViOlQDK6ZcjLmACmq0QPoAMZSGqDhrWqCEl2qvmlTLOJUaxlAGwAlhXwQ3BYcSjxaLxmxWIAswESqn1vjxZxVSKPBRK441SOyPVcXL2lbmrmFaxL2FaXK8xUGqZ2ZDKw1eeKxlTKLGlQ+KY1a+qgNSOz91exLxFV+Ki1T+KWhXsqs1QhKM1T6qKZvmrtRc2rtFTmqK1ShKq

1WLxt5XcrCEo2q1AGDLW1dYq+gB2qf1Ymru1ehriAGGLz5ahroxZWrHlSOrMVeOrhXB+jL1UQr1iPOqzxYTwl1bTK9AKuqcMBuqt1fGq/RXBruQNMJGAEaxshSerwMeereNS0S85TeqjQPeqNKmpVclYBd8lXg4QLsOKx4eroSZWUq+CuTLLfk/yHVc+r6lS6qYNe6q5RZ6rWxbRrfVb+r/VRMLA1XpIWZaGqWReGqpRZGr7xdolHxQ6431aey4N

eErU1T3KUNZmqEeD2qMNVeqsNXXLvxbhqy1fhq3RZWrgJUjwSNXWrYiORrUtRMK21a5qKZnBr4tUxr8JSxrYtd3LCNRxqQxaOq8iFKKJ1TVq+NXOr6hQurhNRMq52EjLgZX6ADAFJrWZaRrZNYerFNVKLlNeoBVNRBjL1Rpq0QLermANprxcuUivcY78z+oGU81mK9JKKdV+QNgI6gLN8XWfEE/tjuJDIFaFOkELiZThMwDcg4SAARfScSsT1JjO

nzfgMkzoOS01NZchztZdtMJVXQ8pVYptVbrNDBgUbK+VixNDpTXzjpaFLe5Kqr+CTHjopVWzFWiPUDNDgznsRYQGXP/QWOQ9cLVeEi16i3A5KXho+2WZ90ANUrQ5YURCFc6qHXEFqQRSTxY5WFqDhq0q11cVAv1e1qStQ/A8xR5q3BRTqHNVTrIVQtRKJYyBkiIFrqJZMryFT0TKdcCNoVfMrNRYhrllckRVlQOq0NbMKvlZhrwrA1ZNFfEZKNd8

r0Na8K6YJfZkHJSLCAMURPRdlrX7E2qwZeYr95cBK21U2BJ5aA4+lTUTAgIKgbJDZI0tciqOdXNq7FQRLWNUTxPlcOq6tVxrGtWy45dc0SZ1XUqe4YJr5dUqgRNf2xutSTxetZuqP0cGqwRQNrWdiLqwiMNqudbMIhNQzq2ha4LNNRyLJABNrhJJerNNXeqn2vjr8FYTrA9esQSFXSKmlT0TWdT5r2dc5q0lcVqFdYnrmdR+ia9W6r2dUXKU9dKK

+FXzrSFY3LBdWzrhdYzqYVWLrqtdsIpdW7qgxbLrv1aLxsNTkoVdVYrjlRrr8xSHKddRcr9dZ4YKNejLjdQ8qzdZwBG9fVZQlTbrhiDJIHdT0oi5S8rXdVVrnFSwBPdffLvdUawmtXLrp1aGh+NaERg9YlrwrGHrSiBHqJNX1qY9YPqoZVrtZlVvLk9e3D6dU3rGdRi1M9TNqoUCpq15WpqA9QXq5tTkqN2TP1ClcZr8ZuPDSlRkjJxQezpxTgqb

NSXrw5cTqo1VXrQgKgA29durbGNTr2FV6qZ9enq5lX+qGJRBiqDZDKk5Z3qeFeMr+FX3ryDSTwhdcsNE9ZFrxdT3KJ9dfr4tc/q81UrrTUAvqp9eWrl9VrrXBWvqbgdWqNiJvrcNTvqD5bVr75QfrEhYzrj9XbrHVXIaYlRfqXdZVqp5QcIPdbfKnlZ2LuNT8Nn9S1qFfh/rBRd/qgxWJqetZJqADbXrgRjJrh9Qer5NWWAu9RAbD9VAawoDAahI

HAbxtQgbJtS0TkDfNrXcecRFJctq+FhSqYceaoYAJcQJwEIBCABQBdtSKcRZetYgjheJXMJ4QtKIWYsqs6pyFOlJRBbMwztHKtnlDfT0UhNdaLKKruFMXyU2XrKHuTtLftf5L/tdX8DpT6itBTp0O8T7RjWRKtLpTFKr2htSaFLSo1vluYbOk1hvUi9KfZZaqt8PYJXMI4LAiDGBciM3Y0AEeCLiByAKNeywo9f1r3VRML89bAaswMkQpWBGAJha

8JpJNNqucvqzR2CcbwiAIbWFdJJf5TEaZ1diKIjVmAwiARK99RwB7hLIVkhTAAUQOkAXhDVZnUGiA5UAAqlcHCBwgOaLKWEOrcAPQAzYOKwhQNaAu9d1qG1VTKwZdSB3DTFg9UP+xkiISBUAIAAAUgpNqADvAXhgpssklogDrnnZ57PwSJPCpN7Jo5NnJq5NXJvSFHAGZNAaHwSexo4Vectgl7xvNMrgreNgBrL1oRHr1dEGuNqABMQkvC7AJBpf

VBcog1AuooNgGu8NFAHXFn6uoV8po2Upv2l1wwsYVkhrKx8pviKRpuCNyM2YNsEq1N7etsYIGvMY8ppvAwOG71ZBqmVimuhmAhqyFwEuEN1Wt5N/JovZaAFwWIeoR4jMtLVEGPUNRuuANFiq0NQJvlNipsx4yputNTzRJ4NkntN1Bp1NfmoXoLprdNk+u/Fz+vi1y8rzNNLBUNxGoN1W+p2FmhtN11GrOiBprvAVpvEN6GrNNhPAtNjZpTNaeoV1

SPDK1gZoXZ7ADQA/WACNpxp3VJRDcN9MvbhzqATA9EpYVhxN+Ns2oBN58oTNrgoVNSpoYNCuqzQ2ytcFZWr/10eogxmZuA1LIt3lK5tdNZZuv1hZrv1NipLNJ5vzN1+qf1F6paJb+rqJbWq7NSqAbNTZrDNaZtQAlYvqFy5puNHZs6145vE1Jxq8NDpqANpGq6Fcmt+loQqlYp5vXN9Viz1wMqiNBisQNoaEeNs2pQ42CvKA2xvmogQD2Nx4poIR

xtcFJxveNsEouNfxpp1NxruNlIgeNx4ubFdICNALxsk1kpu1NHxsCV3xtDQyBsXNcWrrN5uvlNhcvBNBxChNURBhNuICd1owsRNzAGRN/bFRN6JqFAC7CxNsABxNK6sU1+JvRlhJqBlxJpgApJo4A5JqpNNJrpNdcpLgjJrPZApvYAbJu5NllqstFJr7NLJoHNwqGFNBFomFYprCNGxFItfw1lNMFtXNyZpVNdmpJ16prJ1pPB9NLIs8txAHfNnZ

osNJppzlrZpC87Zo/Nn+qhmtpomFB5pTeTpuBopZvdNpOsLF3psANvptF1PSii1UAFstZlrYAIZvQ1CVvDNoMsjN8DkN12+tjNJuqsVNhs4AiZrXNqZrF4GZu81YFrStC1AytBZqQ1RZvKt6+F6teuprV0ZrqtpGrjNtZqatokhXNhpoit7yqcVEhvgtpwv/N8VrzlPZsY1xVuDNArEPVI5uBGY5t/12QqnNfEHgc/Spf1QqC4tuAEBNvFuatK5q

TNa1uPFm5uUVxhsd1IFv3NnVqzNgQuPNsFtvNkVuq1A1umt15p+tZ5r+tdBurgDhsfNrWreVgovCty1q/NP5r2FN1pmtq1vmtB1pUtkes8NEGPeNfosgtw2uGtn5qISsBrLAXytz151rhNdFsuNNOtQNyGMc+bPEwN/62wN44twN5SvwNlSvQAOFs2oeFsnB3wmvgRFt3Ne1sOG5xtiNlNotN1Fo2EBNvotzxuONzFoFtbFpYNeeuFtFFu4tiNum

tIJtzVglshNKVJEt/MFhN4loRNQkikts7DglaJoxNClqIASloiVKlqT18moJN2ACJN46G0tvJr0t1JtpNcAHpNxlt5cQZtZNlJustvto5NW1sFNDlq8sTltlt4prctUpqfNVCq3Fd1rXNROtVN/lv51gVpStvmqjtaSthtk+uzlFRDhtcVvmt61s/V/6uTtBw26tlFoFYbpsC1AVuytQVtytV4r9NncsDF34oDt9ltDNFVqJ4EZpbVUZtqt1Zvqt

u+qRtLVp8tbVqR4HVuCtTuvxtC1suF/Vrw1iErpg+Nqy1o1s7tu6vuV8Zt7ts1oAtk+qWtqZpztcNrF4vZpmtXtvstQ5ugtstrRt7hp/RUouOtM5rOt5FoXNV1qXNy9qlY91tztj1ooNz1p3Nb1q5cH1sPNC9tHtREu1FANs41Q1pvNINrHtCPHvNqFqFQkducN5ppXtD1rv835rRVv5rvtVMFXtveqAtHhv/1WNqlNONuAlUFrhlYVsAdW9sQtJ

NuiNCtoD16FqNAmFuJVvhSSNVSNW1Lv06lE4DWAt6kwAygC7Ar7IGlBRq/JgdDkpQUHakWlBgqZQkdCWxlgIkmLtyMFVCi0PxLK1jm+cAKnUxnQLaN4qvJJnRrL53RqzZJOD6NxYOdm1fMOxtfOOxlssSYxrJXWUOoo5ISFIJjL2s6dbKbZ5imqBVvBR1BnzR1JRJ1iWkTSkmxscYHNt2Njrn2NX/SeNjFvZY2QsTOL7TEQ8pt5kBrOAlxBoFFx4

sztvEteNkrmzOCSggduIDxAUHjTln0HxAkOCNtBYrEQOGESdatuyFxBrHNJtvktxmHNtdcuyF8wsiVtEFHYErC2VYmshweQpvtPFucAyRBHVOlqlYztoMtbtqMtJlr3tNzR9tftr9tvJqlY3TpcYPSvCdvqolc5XgAV0TrrosTp6UT5vlN99tjt0ptOtapsTtPSmVFqdrlNK5qlYc1uNNmctNNvSrbNWzqQdMDopmACraVBdsvF8ztLtNLF5159g

rtRrHWdXQv9N2ooGdplu2tL7UJtPio/lLcNLhi8OutgNvmFSPByUXloWdPltGdJWooNkTpC136rYVzOuVFVzrgt/yt4NnptJ4AQpZFWyuet48pBd1zt2dqAE3NwLtT1i+vkNM4CudOzsn1VhtV1ALuntRzstNypqRdJPEBV7AF8Vn8tBV9Eq+N79rRd4lqedyaqOdcFtXltzSAlVitXhiKsisKKorFaKoSVSIqSVDYoRdt5pglxotrNwrrLForti

VnIpxFqCvxVmSpJdHADkl6ItedbTo+gzgG6dmTD8MFlr6dfTvlNzgFQAUurkVgErlFGLtLAKit6FHSp/tByoXlGLTj1S+pnA/7ClYVrojAnouMV6Ep3l3dqXt01vm1Y4OwtOxq5t5Xk8daIAYtWYFHYfjspYATrKgQTuKgzdgJ1BzopmULqhFMtumd/evidwoGIgz+pqdkvzHNGTrKgWTuIgOTqlFeTspYBTsxNxTvbhZTvhVJYrXhlTuLwaJpWF

qTurgdTv+dzTv1dPtvad7tq6d/Zp6d5rv6dyNredgdrWIeRBbt+codcEzvPFUzvLoMztmE0wyudD9t8txCoaVqzoedz4tCtpLuQdoNqhdNaphtNLuPd87rOd+dozF8Lt5dZdu4Nvesr1KLsedtdoQ1AZqndQztQAHzsZdwKpZdvzs6F/bq91gLpJ4BLs3dizs7VkLsYVUGoLlZ4thdHCrtNlzvvdNLHpdZCoSU6zoddOyt6FsrqAdP9vxd8Rlmdq

uq9dCACPd8Vp/tFLsat/9updCrFpdnioBV+wz/dPzoXhYKrcF6zvDVb7t26OHvAx8rvLhXQvKdvEpVd7LHFdsCvRViSsQVMruQ93HoFdCrqFdCKuVdMSqE94QvVdaSrQVhIq1dwkl1dg7v0thruNdSl2CAZrond1lstd1rv7lNRI2VJPEw9TroJygRtxdbrvMNL1tdF3ruM9/rqI1gbvWFwbomtDVu0NNivm1gxIgCaBoBuRmrxmDNtM1OBtNxAv

AINkbtwtCADQAMbuPFXjvjdj0Hbh/jo4lgTpXNwTozdYTvndObv5t4RHzdVesLdiTpLdPbspg5btS9lbv5A2TvlNuTqTgD9nrdclsbd1oGbd6xH49HbuqdJXqgAfbtvtYbq09LtsMtDJs9tY7oM9hnp5Nn7rHdwzpzlWbsgNvLiXdbCpXdlQDXdSzvA9YLqWdC7o9NAuvWdh7qOdZLuv1p7qm9b5ovdJzoV117qStqLsyFEAC49tzvW96HufF3Lv

fdLzrG9dltKt37o4lnzqBVzLqY9tQsA93Xqo9MptA9BHrwdCrC3d4Lqb1UHpzlMHpJ1cHtSFcLqQ9CrERdz8uRdG3ufFlntU9nVC49k+vw9pqEI9RLvS12roVYO3tBtFHu89vyuo98rFo9qHt/dH3v8VLHo/RbHtA1HHr8U6Pu4c0nt49irrk9AnoU9RhviVQkqld4nr1dknv5ddztZ9snrbdIrs59hEuU9eKoyV9Wo09pIt69S1E4ARrrHdJrv0

9vTpG9lluM9NrrM98ivtdXbq3NqPuUYLrsvldnocVOPqntTnpXNfroDdD3yuV/Oy7tnnp7tYboUltSOSNol1MJgix/uDSJgAKrEFmPAHwAiXR+xPtT+A/qiWMr4JdSHpxlOPzzBINnmscnmRqN9t3e0DRtZq0fDBq0jpe1N3OTZustL58CO+1mbKKG6jsDhCqqOR5srr5xbOzSlfTIhuVBjh4GFhQ4fjDmRhhtRljq3MjEHxwhkHThZqoVJPmMae

wtR45APhPsbjujdAEwpmCXqltEpqlFKXqCUaXqlYGXtCdtXv29UVrLF83sW9hXuLdyTtLdpXspYFbqyAVbooANbtT1YcvydDXrNtTXtKdLXtbdPEra9evvX9nXpKd/zqaddWpadqADadrtpHdg3qe9w3vV97JtedX7tndTCrGdM3v/ly7rzdq7oLdG7qOdwPtW9FerQ9azoPdepujt+PsvdP9r29IPoO9NHsvdecpO9MPrRdl3sfdQvsR9N3s5dd

3oWVIhqKtj3pKtaAB/dDHqp9rcO+9DTt+9qhrA94AYg9zCrB9ZYpYVACqwD53q49qHv71GHr19mLu4OTPtBtmPqrVhLoc9QNvlYBPuAd7uviMf9uA9pPpRtdHtIVlPu+d1PrZd4KvetnLvY9+VsB98rD5dzPrwDP6LZ9ovvk9jusU9wkm59GKuld/Prh9crpZ9pCr495/vAVgnqMNuKukl6CvU9yRE09U7oNdivt09prrV9n/s5NmvtM96yp19Q8

v4DjroN9E8ts9NvsOVRHpdF6uot9vrqpg1vrrlJirt9C9sBFjvuadT7QH9MXo8d8Xrjdo/uS9ybvK9WQDTdITozVtSrzlOXqX9oAacNCTtX9ABqsQZbs395QcKIlXurd1Xtrdc/sP9ptqKdJ/qlFLbqVdTeSqdV/o69XXroDD/vl9L/s6db/pKtH/qCD3/vG96TBGd87tmGs3tSF9QYK9YAaB9izsjtUAd4DsAbBtadu29iAa6V+zpQDK1rJ96Ae

PFmAYQ9yVth9egYfdt4sMD0Af3dhAYZ9BVpIDKwae9FAde9KgZBVAHuNFQHvv1IHpv12LogDkHv4N0HrW9C6vg9FzuwDknp4DVer4DI8qiDWLt0DwNtxdIgcCAYgeLNADoQDZHsvlRPqBNEgcUDFPqoDqgdZd7Fo5d53q5d3wexDOLsF9i8OMDPEp6ULgdRVInsldtYr59TPp49DgfZDzgfF9arpbFKns1dMvq7Fcvp8DQ7p09yvr094QECDQQa/

9lvpM9siu19droiDGIaw91npoV1+pN9bysJDdMB9dVkFSDrnpt9GQY89rO0mtlHof91NtxleuPxlEgCKVRMrHFnwISYrNqs1EAHyDsXqH9CupH9PjrH9RrAn93Sin9L3qqDmbuuDezvB9uXpidDQZt+fMCLdSTpaDaTrK9k/oq9VXpXNNXoP99XoGDilpKdwwbP9owcv9f0uv9UwZVtA7tlD+lrmDA3qZNQ3uVDywbID21t/98/qFF4zsADc3uAD

C3oTDNrmW9Rprjtfluu9MAc5dW3uJD81qQDVwZbtVzto9bVoeDSIa4Dknqu9WVs+DDIaIDo+oe98pq/dlAa+dwIYXhtAcrD8gb+9kIeZD0IZYDsIdjD7AcGVjwbO9zIu4DCPufdSPs5dKPqxDQgekDeLooNBLsntjnpI95wZJDHytkDl5pJ9ePtuDA4YfDb3qZdNId+dNPs0DDIe0D8Gs49AvoMDbIZF9HIeiVZga59Erp59fIdElEntsDZ5sFDR

gdQjIoYwjEvvFDUvo8DUoe8D8pt8DLgH8DqvpVD3JpCDGobCDWoc2VkQd1DZotiD0htN94gfXwpoat9FofSDQbrMVIbqmtuQa3hCIGodt7PN8oiKB+22gUQQgBTgmEGLViQDkA9LDWADQB0GmECAsT2EfBWeCTQsdhPisMVAEeejraWJMlCOkuFuDnnDZN0hq428EE8ZSGsEULBngQHycgrRtu5RPxbK+spUd+fvlV7BMVVC1OVVZfv3RUwNaRso

JOk0q1oaVlFbIsORHxBquxQ5XCMubxOc2Q/O3sUPP4RTvTh5PoJBAU/KPqy/Nx5/EN3ATkapo2+jbgOdCkZN/LM55+Ly5EAuCmF+LZRRAtkBTvMSYLGD1QJ6qeglKuc0oUY0lbyG4xoSHjgCJgpGHPhfpNazzsel2IkedwAYqTIslbwBsE8cEZqCCQ8xRTIclvtRG8LVL1p4AwopiEJMRW0s8lHRqdRvIL0xJsqYJKOnUF9ryL926J0dJ0osx+jq

b5xm17xbfNJwi32TsJT0OhZlmMgLdNSl1gu9lTJxYE5+zrQij0yWQr2ERysE8soWKKlkWLeQ0WOX4sWJpICWNNB1UofgtUpSx9UtzwhWKaluWKS43mjalYqGlqpWMAmng0e+dQCjAYYGIAhaXyNRkbIJTUKcg1FMC55PTI0wh2ZVE/D6Qc0obaDqhzocjCMp2BPARQ4A8jmfo+1vQJ8jygphJf2v8j+bO0dIOs5x1Q3NZPOJx2GqqqOckB4ypkF+

AbbNo5cGESlIPNQ83qThwZ0K9lyhLRy6OuM+fYNBj/fqjdBQf2NhFqbyJFojtQtqQNItpXNtxt5F4tvndktqDDcYfeNUAk+NGgZIdsqHnNRoGVtxPrOiatoEtEJs3VWtsKIolvJtbCv1tmwkNtY5tkt+YeKdylvcNeJptt6lrttmlodtOluf9/Xo9t9Yff9jYc/9jdue95MGDtovFFNUprDtLFrAtq3vHAwQv1NMdpW9hwd3d+AcrthdsdNIVrgD

Zwe2dFwfUVe3o3tjsbuDsDph9w9qLlGVvLte7p6JHcezNSep0D9dqQ1JcbKtS8rzlbdrcFY1vt9Noa89f5u8tR3sStQ9urtI9vwdfVuuFA1uI9M9tUN4RA3jWQdtDQcabA6dubN0+sHjigYHtJPB3tyRC/dB9rhlR9spYh1rPt/MGnNyzsh9vsYIA/sf+N9TsPD98r7te8YR4T1qiDr9sxt79uHt31pZD55ont1hvoD39svloDo4t4Dqht2dugdj

9tgdCNrvjt1pfjKDt/1b9tltWDv8N0Ft0D+gYltRNqQtOeuIdZNtdjDsbyD5sfwtFcd5t1sck1pFrtjnFodjVFudjbwnYT3joTd0tr61NcazNctvZdbCcutYIZsVIcbBNYceEtkcZ1tYlvhNVknjjKJqQ1YRCP9gwYttcKvcN1tt+lttvttgwEdtM1tzjHTrrD07vMtRcfV9S8aDt87srjrFurjR9o8t3cc2doLoHDkAdbjj4aTtH9tStXcdODvi

dQAUgcnD0VoIT5CYJt5ztvdISZTt48fwdk8bbjXpqrt2prytCEY3DDdt3tqwebtq8aqt7dpqtVZpvj28cQdW7tfjMkhnjxdqwT6iovNZ+okDDCdntahvntNZrtDUCcITuLvXtr5puDs4b6TX5vfjfJtWDX8bLDEdt/j6NsnNACZOt8IdwTcqEUTP3rq10CaITFMzgTlIoQT6DqQTh8ZQTDCffDjScpdmCePjd5t91D5oD18TuhtUDt7jMCfht8Ds

gTNis3tPBtQdGNq2T1CeANuNoCN9Cd+t4ibEAxNvgNKFvmTPyfIdHGL89CSJpts4NdD8/WJlYXsfG/BUi9EgF9D3NoZEvCaYtfWoETCieETVMDFtYiceNiXtRTm6pkT8aq9jdIYxTStogTpCeBN/FtUTQlojjIEqyAutu0TkluktpRETjhToLDKcaBlZiZS+FiazjViZzjQ7trD+cYcT47sYjqoY/jqwbLjbiectVcdcthKffV3ifCTXlogDLcZW

d6SenjSSaLtYSaa1XlqiTlwZiTz8eOdqye7NN7sQ9Y8dzNqSe4N9zvVTw9vXDPwY/d4qf+DYXxXjx4rXjH6OvjHSYpTKya3tg9tcFtSZzNzpuOToNoOTZvp/DF8YrN7qbEjnSYeT3SbXtLZtiThqe9Tb8c2t+ScdTYye7drFuPtE5qOtMyYvtsHpATCycptgcZ3jVScGTH4ZJ4L9sY1/Ntp9Gqc7jX9sDT+yfQThyaPDv4ZxDk+pwT+adW9kDsOd

1yaNTiVpITO8YGTeAeeTVaYwdrFpoTXKYU1o9rIdfyeQt5yrAd5NuvVHCckj8uXPBK2utZXuIt2YrwaAKEEqAEYFIAHACewzACxACiHwAUYG/ABvHwAd4BcCT2G0wm4UMj8QXS0kFNK+GJPWAZRsyqiBCsIbOE3iBXXGKVZgOyNRUJK4rX/++1J2jZD0L5Yqve1ijuz96bOOjiCJ6NU1IL9JYM0F+HO0FxVO5xfBLKOenl9mP3Ldade04GjmBugp

ZAexT0Dl5COvtuXfiqojfTvRaUb+jb0uVJhz3h5D0MR5RUa1JizJYzRSx+e2JGRsUwEJIjNIuOSAPRRtUdPxe2xaj3Qhvx7KOnCbUZgAHUe5lzmnQznGL6jpHiCwM3ha4wWDICFBOzMDKHdp19ObJHjmLc0mPxwtbSZ6bamVawtFQwYDH60B4mbI+fOu5nX2mQJf1jyUGe8lR0d8lA338lZ0eNlF0YCjxfqdepfsGC4OswzNewmNVbOX03dUSZpg

tFxCUccc9zME6yxtozqxqFqR5FyloMfylEMaiAxUuhjpUthj5UvhjlUryzSMeFAKMbSx6McaluzCxjeWJxjIIHal4qM6lklEwA+AADWXYCWA34GDAd4BpACMLWA+gTYAR+wuld6fNgVMZmxQtzBIOxllsZRqfoYfkgpIuNrAP6fWMf6d25OAXsgq7kPE/MfaNWfu8jXRpFjWHOhciGc0deHKOlYoOlj45gdaPOOwz20IDmVrIKeQUGJ6fmJgSIGf

rZzbPLxAdKRM2oOK5MNJnxmMEmxVl1++vR2yW6pIi2T0O3+hUef4uCnUElZFYapmmZQHPMEzYmbC5tMgajomapk+XJJmPENxA0maDw+H3d97RnAAs0EggbtqBoCIBzA0ADCgGQBuoI6D2ADAAOGXcy8jbRWAitOeGAYMdaDFWgOIIqFGh8jsrsDOdvgLoAOIVOe5B6HOFjpShEAnOYOIDvl9hcOw5zj5GZzYsYKA4uaZz6QBZz/RpoqMubUwBxBQ

gQOqVzXOfSAdQB8W6ueFz/Yvi8OufSAMYDTeVSANzkYAKVQXtXIpubmoOXORzpud5kcgNqyu6VNzZplViLeG5R9OZrhjOeVzhubeQqua1A2pFqgzLASdU+ggCdwBuSItmNE9jkAagedhN+AE0ModBykCdUbIzkBqeEACMA1zSbwyAgYABABo672TVO4DIi4pudVzZtzj0+0HpzdIBIAp4wSgw5krzM4BHoszHJzFeeIATQEywSHQtkNeajSMkBkw

uICWgpAEFOuABRFs7kvsQ+dq4rkERAdkF7FZoCDgygFrhUyD7zVIEHzzRV4AS+bcSl9jOUZItuwSuflzCAC1z0GKYoaliDgiYDRl9AMm0h/VOJ2AB0SxXOqz17PNA/sEMjpxMFQiDiYAiZRJzD+e5AmIGxoncu7im+bsAkkuyADQADQcABbzfyDbzhqkgg40UYAtxtxA6tnFmTWrQ2TqHBjkYErQP2YPMUerl+Z0XlyoQGCYEBYQAUBY5O9SK9wb

8T+6OIFVgJ4AN4fEHbzxmCVs6VJAiPICxQrAkP65OfHA5MlALvKNjwQgnC0ABbpNMWFYLbIhs0QFjZcTYGALEEDKU3iCkg4LhAxBCDIghYCAAA==
```
%%