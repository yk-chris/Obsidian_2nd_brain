help consolidate the mail content into a structured table with columns below from all mails on my mail box within current 1 month:  
of number of item | Engine_serial | subject_mail | date_TRC | date_techData | date_WS00 | dt_WS01 | filename_attached |  
  
first, to extract all mails from my mail box to include information like recepients, subject, body contents  
second, to consider below convertion criteria:  
Engine_serial: to dip whether a 5-digit number is contained on the mail subject  
subject_mail: to extract full statement on the subject of each mail  
date_TRC: capture the mail received date if the file name of the file attached have any words like 'TRC'  
date_techData : capture the mail received date if the file name of the file attached have any words like 'Tech date'  
date_WS00 : capture the mail received date if the file name of the file attached have any words like 'ws00'  
dt_WS01 : capture the mail received date if the file name of the file attached have any words like 'ws01'  
  
third, to group all data by the same Engine_serial and to list a table to check if the relative documents has received on each engine_serial like the attached image