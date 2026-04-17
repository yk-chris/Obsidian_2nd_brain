本次會議旨在演示新的項目管理系統功能，特別是「Test Plan」變動如何影響任務排程，並收集用戶的深入反饋。會議集中討論了系統的通知機制、任務可視化、數據整合以及當前工作流程中遇到的挑戰，旨在優化系統以更好地滿足用戶的實際操作需求。

## 主要討論要點

• **通知系統優化**：討論了如何改進通知功能，使其更具針對性，例如為逾期任務設置不同級別的提醒，以及在上游任務完成後自動通知下游負責人。

• **任務緊急度標識**：用戶強烈建議增加視覺提示（如顏色標記），以區分普通WIP（在製品）任務和需要立即處理的緊急任務，從而提高工作效率。

• **數據整合與搜索困難**：一個核心痛點是系統內數據孤島問題，特別是無法通過 `Module Number` 有效地反向搜索到 `Engine Number`，導致在 SAP 和其他系統中查找信息極為困難。

• **Test Plan 機制影響**：演示了 Test Plan 的改動會自動更新所有相關任務的「Project Completion Date」，並觸發通知。此核心機制將動態影響用戶的工作排程。

• **延遲原因記錄問題**：用戶發現，在系統中輸入的任務延遲原因（Delay Reason）在提交或更新後會消失，無法追蹤歷史記錄，這被視為一個需要修復的缺陷。

• **工作流程不確定性**：會議末尾揭示了更廣泛的流程問題，包括 PMO 流程、紙本與電子系統的銜接、以及對其他未完成系統模塊的依賴，這些都給用戶帶來了極大的不確定性。

## 用戶反饋與系統問題

用戶（主要為 Speaker 2）提出了多個關鍵問題和改進建議：

• **任務優先級與可視化**：

- 當前所有任務都顯示為 **WIP**，用戶難以在大量的任務列表中分辨出哪些是因上游任務完成而變得緊急的。
    
- **強烈建議**：引入顏色編碼或其他視覺標記，以高亮顯示需要「跑數」的緊急任務。
    

• **數據搜索與整合**：

- **核心問題**：在系統（及SAP S4/HANA）中，無法從 `Module Number` 輕易地追溯到 `Engine Number`。所有文檔和系統似乎缺乏連結。
    
- **用戶困境**：當只持有 `Module Number` 時，完全無法找到對應的項目信息，嚴重影響工作交接和執行。
    
- **建議**：系統需要與 AR System 或 SAP 的信息建立對應關係，幫助用戶快速定位信息。
    

• **延遲原因（Delay Reason）記錄**：

- **缺陷**：當用戶為延遲的任務輸入原因後，該記錄在後續操作中會消失。如果任務被多次延遲，舊的延遲原因會被覆蓋，無法形成完整的歷史追蹤。
    
- **期望**：系統應保存每一次延遲的記錄和原因，即使這些信息不在主界面顯示，也應在後台存檔備查。
    

• **重複項目的處理**：

- 當同一客戶的項目（如MRO）在不同時間再次出現時，系統應能通過 **Sales Order** 區分，並同時保留新舊兩個項目記錄，而非覆蓋舊記錄。

## 系統功能與核心機制

• **Test Plan 的動態排程**：

- 會議演示了當 **Planner** 修改 **Test Plan** 中的時間後，系統會自動重新計算和更新所有關聯任務的 **Project Completion Date**。
    
- 這一機制是系統的核心，意味著用戶的任務排程會因應規劃的變動而頻繁調整。
    

• **父子任務關係 (Parent-Child Relationship)**：

- 系統支持任務間的依賴關係。當一個上游（Parent）任務完成後，可以觸發通知給下游（Child）任務的負責人。
    
- 用戶對如何界定「上一家」提出疑問，因為一個任務可能有來自多個不同任務的依賴。
    

• **通知機制**：

- 每當 **Test Plan** 更新時，所有受影響任務的負責人都會收到通知。
    
- 用戶建議將通知分類或聚合，避免因頻繁更新導致信息過載。
    

## 提出的建議功能

• **高級篩選功能**：在任務視圖中增加按日期範圍（From-To）篩選的功能，讓用戶能快速查看特定時間段內（如今日或本週）需要完成的任務。

• **清晰的狀態標識**：除了現有的 WIP/Complete/Disabled 狀態外，增加一個明確的狀態，標識「上游已完成，等待我處理」的任務。

• **優化通知內容**：通知應清晰地聚合信息，而不是零散地顯示每個變動，並明確指出是哪個任務被接受或拒絕。

## 後續步驟

• **記錄並反饋問題**：會議主持人（Speaker 1）承諾會將所有討論的問題和建議記錄下來，並向開發團隊（Software House）反饋，特別是關於任務緊急度標識、數據整合和延遲原因記錄等核心問題。

• **跟進篩選功能**：主持人已向開發團隊建議增加日期範圍篩選功能，目前正在等待對方回覆。

## 開放性問題與挑戰

• **流程定義不清**：對於 **PMO (Project Management Office)** 的具體操作流程（電子化或紙本）、IMR (Inspection and Modification Record) 中是否包含所有任務，以及各部門間的銜接方式，目前仍存在大量未知數。

• **系統依賴風險**：新系統的許多功能（如CSR模組的結算）依賴於其他尚未完成或定義不清的系統模塊，導致整體項目推進受阻，用戶感到「嘥氣」。

• **用戶心態與供應商管理**：討論中提到，用戶目前只是為了完成任務而輸入數據，但系統設計未能有效保存和利用這些數據。同時也交流了與供應商（Vendor）合作的困難，指出供應商通常不會主動為客戶思考解決方案，需要非常明確的指令。

---

### Transcript

Ray: 譬如可能個task嚟緊一兩日就come喇，但係而家個status仲係WIP嘅，咁需唔需要再提一提大家呢？我覺得對各位做嘢方面會有一啲方便。咁你哋有呢啲提示其實都可以講出嚟，咁我會jot低返點樣去improve呢個notification。

Ray: 譬如遲嘅，我哋可以喺度group埋啦，group埋一啲遲嘅task喺度啦。咁就instead of send email，其實呢度都可以filter一啲遲嘅task嘅notification。

Speaker 2: 我嘅意思係喺呢度notification咩情況嘅都擺晒喺度冇問題。但係你可能遲咗已經超過咗20日都未處理嘅話，先至係email alert返你。

Ray: 咁遲20日要email，呢個你哋定啦，呢個logic係可以變嘅。咁譬如遲1日到19日呢，我可以notification都OK，冇所謂，呢個就我嘅suggestion啫，個date唔一定係嗰日嘅。因為都係嗰句啦，我19日都漏得嘅，我唔相信我自己第20日會識得去搵返出嚟去搵一搵嗰個囉。

Ray: 除咗遲，即係喺個final嘅reminder之外，仲有啲咩reminder你哋覺得需要都可以提出。

Ray: 譬如你哋有啲task可能係需要睇上家嘅，會唔會上家完成咗就send個message畀你哋下家去通知你哋？因為喺StreamMaster個structure入面，其實有個我哋有一個叫parent and child relationship。咁就例如佢呢個task 9同10係有個linkage嘅，咁module script做完呢，

Ray: 先去到呢個project compressor。咁一旦個module script個project completion date set咗，task 10呢個project completion date都會跟住郁。即係睇下各位需唔需要可能加多啲咁樣嘅notification。即係如果你屬於下家嘅task，會唔會上家做完你又收到呢？

Speaker 2: 但係其實如果上家未開始，即係如果佢未完你哋係咪可以開始得？即係你個come date綁死咗喺佢度。

Ray: 舉個例子，譬如我有個task嚟緊星期五要完喇，但係你哋而家仲未開始。

Ray: 如果嚟緊呢個 task 星期嚟緊星期五要完啦，但係你哋而家仲係 WIP 緊，你哋會唔會想要一啲提示話可能就係要預早一兩日入去 check 到底嚟緊有邊啲 task 可能今個禮拜要 come 咗佢？

Ray: 咁如果冇呢，咁 notification 我就暫時咁多啦。咁如果有其他意見就可以喺 Excel 度 mark 返，之後 mark 返落 Excel 度俾返我哋。

Ray: 另外關於呢個 task view 就再 update 返少少，咁就所有 task owner 呢，都係睇到所有 task owner 嘅 task 嘅。即係變咗係唔同嘅部門都係睇晒所有關於呢個 stream 嘅 task，咁如果你哋淨係想睇返自己呢，就要透過上面呢兩個 filter 去處理。

Ray: 去到呢度有冇啲咩問題？

Speaker 2: 冇問題我就想問下，喺呢版嘅話我就唔得可以淨係，譬如 status 有啲 items 嘅話我答咗，有啲 items 未答嘅話，係咪分得出有啲咩 items 係未答？

Ray: 我哋嚟緊會有個 status 嘅 filter 會加返落嚟，因為之前佢就即係暫時呢度 interface 就冇加呢樣嘢，咁我哋會暫定會有三種 status 嘅，即係 WIP 啦、complete 啦、同埋 disabled 嘅。

Speaker 2: 會加多一個 status 係我上一家已經 submit 咗啦，之後係追手我一定要做呢？即係你係 WIP 當中嘅話係我哋係要即刻 update，都係標位係 WIP 嘅話就係上家有 WIP 緊我有 WIP 緊，如果係佢哋 come 咗 job 嘅話我哋 suppose 要即刻 come 或者要跑去做，呢樣嘢要多啲 indicator 俾我哋囉。

Ray: 某程度上同你講嗰個 notification 係有少少係相同嘅，但係喺呢個版面嚟講會唔會 show 埋俾我睇，我呢啲我係急急哋一定要搞㗎喇。我諗到喇，譬如你上家今日星期一 come 咗嘅，咁理論上你個 task 可能係星期三先至要 come 嘅，喺呢度仲有兩個 gap，即係兩日啦，兩日時間俾你去 come。喺呢兩日你會唔會透過 system 睇返自己個 schedule 去處理返自己個 WIP task，定係你覺得即係星期一已經 come 咗，你可能要再早啲 come？

Ray: 你覺得個schedule去處理返自己嘅 WIP task，定係你覺得即係星期一已經come咗，你可能要再去做返？

Speaker 2: 係唔同嘅色令到我可以easily detect到，即係呢個一定要跑數，呢個的話就我可以繼續做嘅，actually。

Ray: 咁調返轉整理下頭先嘅問題啊。我聽落呢，你就係某個 task owner 啦，可能你角色入面 task owner，對你嘅 task owner 嚟講呢，唔單止頭先講嗰啲 active WIP 呢，就係你自己撳咗掣未啦，咁呢啲好容易啦，撳咗未撳就分咗兩類啦，做咗未做。但係頭先你嗰個 high level 難度在於你每一個 task owner 要 check 返嗰個 task owner 上一個 task 喺而家個 pool 嚟講係，無論即係而家未有啦，我 brainstorm 下成件事，個 requirement 係咪咁樣？

Ray: 就要 check 返晒所有你個 task owner 嘅上手入面嘅 completion date 有冇。咁呢個就係你啱啱所講嘅，其實無論用顏色表達或者一個 tab 就出現一版，淨係一啲 urgent 或者淨係隻顏色都唔 care 呢樣嘢㗎喇。即係可以有少少 signal 畀你知道嘅話，咁就 OK 喇。聽落去 logical OK 嘅，但個訊息我會即係帶返畀即係 develop 嗰啲，我哋有 software house 入面做呢一樣嘢啦。咁我覺得...

Speaker 2: 因為如果係一個大版嘅 WIP 嘅話，基本上我就分唔到邊隻有次序，大版囉。淨係冇，即係你個去搵返邊隻要去追或者其他嘢我就 lost 咗個 schedule 囉。

Speaker 2: 嗯。再加上就譬如，而家唔係個個人都行 streamer 㗎嘛，基本上係好似跑馬仔咁樣，哦，邊個買邊隻就食糊咁樣，所以基本上好亂打亂仗嘅。咁會唔會其實根本跟上一家所謂嘅 completion 都唔係？佢追資源，你又追，其實你阿媽都唔知邊隻係你應該...

Ray: 但係如果係咁樣嘅話，就唔係呢個 status 可以 handle 到。因為你個 process 唔係 control 喺我哋度嘛。係。我諗緊成件事，即係 streamer 如果真係有跟到，應該得上一家嗰個關係啦，你就可以睇到下一家入面。聽落唔係太簡單，但係可以即係跟隨呢一樣嘢如果需要嘅話。

Ray: 但係你要求係我講嘅係上一家就係跟返 streamer 行緊嘅 flow 嚟講，你嘅上一個，因為佢唔係全部有啲 relationship，即係 parent-children 嗰啲就有啦。咁上一家以 number 計啊，定係點樣可以 detect 到？會唔會有啲 idea？即係點樣為之上一家？

Ray: 即係譬如我嘅話，我上一家係好多個 task 嘅，喺 model 1 嗰度。咁我哋夾晒上，可能有三四個，即係 directly 嘅上一家。用 number 而家計緊邊 streamer task 啦，咁我當你八個 task 係你嘅，咁係咪七個完成後就需要有你嗰個所謂 urgent？

Speaker 2: 如果 streamer 嘅話，如果我上一家嘅話就會除咗係 inspection 嗰邊之外的話，MR、MC 嗰邊嘅咩 critical part 嘅 inspection 呢，都會包埋入嚟。

Speaker 2: 即係你而家係其實 more than one 啦。咁可能都唔係 directly 係上一個 task 要完，可能完晒 whatever 係有啲咁樣先至可以 detect 到嗰面即係 urgent 你個 task。即係總之我想就係大版 WIP 我一定知㗎喇，但我最想知嘅係究竟邊個已經 close 咗，之後我係有啲咩 items 要追、追嚟跑數。

Ray: 係對於你嚟講係 urgent 要跑個位置啦。但係跑個位置唔係單純你下一家嗰啲，上一家好多。你話可唔可以即係十個 task...

Ray: 唔 urgent，你排個位置啦，排個位置，我驚你下家嗰啲，上家好多，你話可唔可以，即係十個 task 裡面，十個完咗之後到你嗰個第十一個，可以 check 到呢樣嘢。買到腳係一件事啦。如果上家做完係可以，但如果你可能你係喺 32，32 個 task 裡面 32 分之 31 都係唔 urgent 嘅話，我排嗰啲 task 裡面，佢個次序唔一定係咁。但如果你想可以照諗下呢個方向，唔該晒。

Speaker 2: 有無得 filter 啲日期？即係我想知我今日嘅嘢有咩要做咗先。

Ray: 我同佢 suggest 過，咁對方就話，睇下可唔可以喺呢個，即係個介面嗰度做畀我睇，咁我哋都等緊佢覆。

Speaker 2: 因為有時，雖然照道理就應該會知道係邊，有咩 engine number，有咩 engine number，但係佢成日遺漏咗。係啦，所以我嗰個目的，我今日想睇我今日有啲咩 line 要，或者今日打前有啲咩 line 仲未做嘅話。

Ray: 我嗰個建議個功能呢，就係喺嗰個 date range 裡面，即係一個 from 一個 to，咁可能你就 filter 一個 range 出嚟，就搵晒。

Speaker 2: 係啦，即係好似 Outlook 咁，佢由星期一至星期五都係度㗎嘛，你揀晒星期一至星期五啲格仔出嚟，你嚟 filter。有無得，因為而家咁樣樣，你哋心知肚明一件事呢，1000 聽呢，我想搵返個 engine number 係揼唔到出嚟嘅。

Ray: 係搵唔到㗎。

Speaker 2: 係啦，係揼唔到出嚟嘅，所有 SAP 裡面嘅世界我係揼唔到 engine number 出嚟。係呀，因為你哋入咗 module 嘛。係呀，跟住個 sales order 呢，就揼一個，就係揼 module number 㗎啫。跟住呢，我去 AR 嗰度想搵返嗰個 module number，嗰個 engine number 或者嗰份 WSI，係度度都搵唔到㗎，應該係無連結嘅成件事。所以就變咗我而家喺你個 screen 嗰度，我亦都唔知點去 search 佢出嚟。

Ray: 如果 screen 嗰度，唔知點解佢無連結。

Speaker 2: 我要用 engine 嚟 search，但係問題我而家做緊嘅係 module number。

Ray: Module set，但係你想搵返 engine 呢，module set 係 1000 聽嗰個 module set 呀嘛。Module set 呢，係 search 唔到 engine 㗎。SAP 裡面啲 module 係需要連結。

Speaker 2: 問題係我要知個 engine number 呀嘛，我都係講呢句啦。我求其掹咗張紙，我求其掹咗一大疊嘢嘅話，我都唔知資料。呢個而家喺 S4 HANA 我都會搵呢樣嘢。1000 聽嗰啲 module number 係有少少亂。

Ray: 即係由 engine type 嘅時候無 specify 得好好。

Speaker 2: 或者最簡單，如果你哋做嗰個 PM order 有個影印紙嘅話，PM order 個 front page 裡面呢，照計有一行叫做 engine 嘅 information 嘅，但係而家現時呢，就入晒嗰個 module 嗰個 serial number 落去。咁變咗，但係我喺 AR 嗰度睇嘅時候呢，我要用呢一個 engine 嘅 number 先至 search 到佢出嚟㗎嘛。咁 engine number 我點 search？我喺所有 document 裡面你搵唔到連結。

Ray: Sales order打，你一次聽得每一個module都會有唔同嘅sales order嘅。係。咁...

Speaker 2: 你意思係咪我AR上面打晒，本身佢engine serial number入咗，其實應該係ESN嘛，佢就變咗NSN。

Ray: 咁我sales order打，咁我搵返，譬如我sales order搵返呢啲嘢，咁搵到之後，佢唔同module有唔同sales order number，ESN上面係呀，NSN上面係呀。

Speaker 2: 係呀，我有唔同module，我有唔同module，我有唔同module，咁我點樣可以搵返呢啲嘢出嚟？呢啲大佬手寫嘅通話，就係知點樣入點樣搵啦，但如果我係三手，我手上真係得一個module number，我打電話去，三手，今日個overhaul到咗喇，你幫我攞返去come。

Speaker 2: 我揸住嗰個module number我點搵返佢出嚟？係，變咗要我諗要對應返你哋呢一個AR system入面嘅資訊，睇吓點樣可以幫我哋sort返出嚟。或者SAP入面，我覺得係module number嘅話，我點樣可以喺呢度對應返返去SAP嗰度。

Speaker 2: 我無所謂，我提出我嘅問題啫。可以，可以。我覺得你mark返落個Excel度，我哋會搵返啲細節。另外就係譬如Circus，個MRO，咁今次就係呢啲喇，咁過咗一年或者係幾個月之後再有喇，咁我CRT嗰個database嘅話，最終係有兩個，舊嘅、新嘅，定話係加咗新嘅會冚咗舊嗰個呢？因為而家我CRT嗰個做法係會冚咗舊嗰個嘅嘛。

Ray: 佢會同時存在嘅。咁會用sales order嚟分。OK，咁如果是的話，譬如Circus 1273版嘅話，佢嗰個sales order轉咗，即係佢係一定會有新嘅sales order。係，咁呢度之後我哋計劃係，佢會create多一個page叫complete。即係所有come咗嘅streamer都會喺一個獨立嘅page嗰度畀你睇返。無問題。即係用sales order嚟分。係。

Ray: 或者你去返呢個就主要係WIP，WIP嗰啲就喺度search返個engine number就OK。無其他問題？無喇，咁今日會示範long planning，改個test planning，對返task有啲咩影響。

Ray: 原本係 1 月 23 日嘅 process stage 01 係 20 號會做。

Ray: 咁而家呢變咗 4 月 28 號嘅 process stage 01 係 20 號做。

Ray: 咁其他變咗嘅係呢啲 schedule 啦，同大家解釋返，BMS partial 佢哋嘅 project completion 係喺 10 月份。

Ray: 咁呢個 NGP 係遲咗一日啦，去到 4 月 27，原本係 4 月 26 嘅。咁全部呢啲 BMS 嘅 partial 都係遲咗一日。

Ray: 咁你哋再望望，可能係遲咗 30 日。

Ray: 呢個係 Test Plan 嘅過程入面係點樣運作。咁你再睇返，即係佢嘅，譬如佢嘅 30 號，

Ray: 咁呢個係 22 號，咁呢啲係 Test Plan 入面嘅過程。咁呢個係 Test Plan 改嘢嘅時候，Trigger 到個 Test List 嘅變更。

Ray: 咁喺 Notification 嗰度，佢都會齊返相應嘅 Test Order，邊個 Task 係由邊個 Condition 嚟改咗，係因為咩事，因為個 Test Plan 改咗 Update 咗。

Ray: 咁成個 Test Plan 嘅核心運作大概係咁樣。咁對返個 Task 嗰度會出現呢個，喺 Notification 嗰度可以睇返，知道有啲咩改動。

Ray: 係咪仲有啲咩問題？

Ray: 大家係咪明呢個道理，而家成個機制？因為呢個會影響呢，其實最主要影響個 Project Completion Date。成樣嘢會因為 Planning，即係個 Planner 去決定，其實不停郁緊，可能大家本身諗住幾時要做嗰件事呢，會不停郁。

Ray: 除咗你自己主動可以改啦，另外其實最大部分時間係可能按佢個所謂嘅 Time Slot 呢，就有冇 Lock 去做嗰件事嚟重新排位。一排位其實會影響好大部分嘅 Task。

Ray: 就係而家一個機制去，即係一個由個 Test Plan 入面影響返所有 View 啊，所有信，如果再遠啲嘅話，成個 Time Slot 嘅串流都會郁動。咁到時你會見到呢，即係當有咩見到可能今日要做，但係突然間，哦，又遲咗幾日呢，其實就係因為呢個機制。

Ray: 即係如果唔係本身係你大佬自己動手改咗啲時間，咁 Project Completion Date 就係影響你幾時可能 Delay 嘅問題。呢個機制就係做緊呢樣嘢。明白嗎？大家？

Speaker 2: 我想問呢，你個 Test Plan 呢，排次序係 A 到 Z 定係點樣？邊個 Test Plan 嘅行？

Ray: 你問邊個？Test Plan 嗰行？最頂嗰個？

Speaker 2: 係，最頂嗰個。因為你頭先嗰個 Test Plan，你應該由細到大嘅日子啦，或者大到細啦，但係你個 Test Plan 撳咗之後呢，佢係 A 到 Z，佢跟啲英文字母同數字。

Ray: 邊個 Column？Test Plan 嗰行？Sort？呢行？最頂嗰個？最頂嗰個？撳咗？佢係 A 到 Z 咁排，由細到大。唔係由舊到新。明白，明白。你哋兩個幫手睇吓係咪一樣。

Ray: 佢而家個 Column 係跟返個次序 A 到 Z。所以佢嗰度，對啲 Task 嚟講，佢哋最主要影響就係佢哋本身諗住幾時做嗰件事呢，會因為呢個機制。

Ray: 我再等一等，佢哋最主要嘅影響就係佢哋本身諗住幾時做嘅一啲，會因為呢一個 plan upload 上去呢，就會影響到所有嘅 task。

Ray: 如果未原之前，原咗其實佢哋就按返嚟原咗嘅時間去 capture 返。

Speaker 2: 咁呢個 notification 會唔會有個 acceptance change 嘅嘢，即係通知返佢哋個 task 係會點樣去郁返？

Ray: 會呀，呢個會通知返。

Ray: 因為呢度佢又有 back to show 畀佢睇啦，咁我頭先嗰個，邊個 task 係由原本個 test cell 嗰個 task 嗰度嚟。

Ray: 所以如果你係個 task owner，管理得多比較多 task 嘅話，呢度會收到好多 notification。同埋每次 upload 一次，pending 每次 upload 一次，就會彈一次個 list 出嚟。

Ray: 所以變咗頭先就提到話個 notification 嗰度，會幫大家分返開囉，即係我哋會有呢個 suggestion。

Ray: 呢個 notification 係會 show 返畀一啲 task owner 睇，即係話佢哋一啲 task 係會受影響。

Ray: 咁我哋喺其他 DFS 嗰啲 task，佢都會話畀個 task owner 聽，即係所有你見到藍色 icon 嗰啲 DFS 嘅，佢都會因為 test plan 嘅改動，而喺呢度會有返通知。

Ray: 我哋可以試埋個 parent chart 嗰度，show 埋畀你睇。

Ray: 而家 task 388 啦，task 388。

Ray: 我 show 埋個 parent chart 畀你睇，388 嗰度，task 388。

Speaker 2: 係啊，會多咗好多，我，我自己覺得不切實際。其實Line Manager嘅approval，如果你個task帶有好多個cell嘅status，係啊，你唔可以將啲task拆散，你唔會拆散，更加煩。我，我細有佢有，我需要知道成個timeline嘅interact係咪真係需要佢。

Ray: 需要嘅，因為變咗亦都唔想，我亦都唔想，我亦都唔會建議喺個program入面有咁多task owner嘅出現，因為係啊，咁就好好睇，好似好容易管理，管理返自己嗰part，但係總體亦都好難實時去check。

Speaker 2: 仲有，有啲地方佢可能真係得一個supervisor，嗰個supervisor放假，咁點呢？係啊，即係我，我唔可以代表其他部門講，但我諗喺我哋個department嚟講嘅話，that could be that complex嗰個情況。係囉，變咗嗰個Line Manager嗰個approval，變咗真係多咗好多，因為我每個人都要搞，我覺得我未必真係做到實時去ensure嗰啲嘢。

Ray: 我想理解，有晒上個禮拜五聽咗你哋講清楚嗰個流程，需要嗰個流程嘅entry，即係譬如話我聽咗你哋講清楚嗰個流程。好多個operation，即係就算Line Manager介意approve都好，但係我作為一個去打approve畀佢嗰個，我都覺得，係囉，我想問你，KPI嗰啲嘢，你哋報得點樣？心入面？

Speaker 2: 冇，唔好，唔係，真係唔得，即係基礎嘅技巧嗰度嗰啲都睇咗叫做過關。但係呢，而家咪就係好似我嗰日同Steve佢哋講過話，我好需要視乎返你哋個system開order啦，你會畀一個乜嘢嘅資訊我，令到我可以入到去search到呢部engine，search到呢個module出嚟繼續做我嘅嘢呢？呢個係我kick嘅地方。

Speaker 2: 你都喺度諗緊，而家佢成日都sell我哋就係用revision number呀，用嗰個唔知乜嘢頭四個英文字母嗰個number。如果你冇，冇嗰啲數據入SAP就大鑊。係呀，呢個我冇呀。佢話係，佢就話係要抄返之前，應該係上一round嘅人係唔知邊個equipment定係唔知邊個location定係revision嗰啲嘢嚟㗎嘛。好重工呀。講呀，講囉。係囉，係囉，睇下有啲咩大家。

Ray: 係囉，睇下有啲咩大家。係呀，上個禮拜四講到好落力下，我哋基於你哋邊度邊度，基於你哋又原咗邊度邊度。係呀，所以而家都要好配合，所以就話，變咗我哋都唔好樂觀得滯。係呀，個PM嗰度點呀而家？PM？係呀，乜都冇。係呀，呢個咪就係我哋嗰日五個部門一齊開session，大家都有咁嘅疑慮。

Speaker 2: 咁到底係EPMO啊，定係paperwork，即係hard copy嘅PMO啊，定係點呢？咁到時點樣現返個PMO出嚟？佢有掟返畀Jeffery喎，佢話大機率睇，睇唔得，唔得嘅。

Speaker 2: 咁到底係電腦入面做好晒所有嘢，跟住先print出嚟簽名嘅hard copy啊，定係真係好似以前咁，print咗hard copy，跟住喺上面打晒啲嘢落張PMO度？

Speaker 2: 係呢？跟住啲嘢點樣print？係，呢個咪跟住就話，等下William傾囉，等下TS下，佢點樣搞。因為我個IMR，因為而家佢哋都仲未決定到到底TS嗰度仲係行呢個Red Dot嘅document，定係佢哋真係好有信心將所有嘢individual task咁樣可以擺到入個IMR入面。

Speaker 2: 如果佢哋係逐個item擺入IMR入面呢，咁就唔使行Red Dot。或者係得返好少部分行Red Dot。所以呢樣嘢要大家最好有個肯定嘅，IMR入面有啲咩master code，有啲咩sub master code，係咪真係可以cover晒所有嘢。

Speaker 2: 係啊，係啊，咪卡住晒囉。所以而家我只能夠我自己嗰部分先囉，即係最簡單我嗰部分，especially settlement嗰部分。我理得你點樣畀錢，最緊要我點樣收貨，點樣出個牌，點樣出個，點樣出呢一個repair。咁呢度呢我暫時都仲可以做有E-system。

Speaker 2: 但係個點樣啲嘢嚟到畀我，問號問號問號問號，咁多問號，跟住又問返我哋而家個E-system啊，諗住cover埋。但係佢新核心嗰個都未搞掂，你諗咁多周邊嘅嘢，其實係嘥氣囉。最簡單，即係CSR，我嗰度都係啦，因為而家現有嗰個CSR係可以喺SAP度攞錢。

Speaker 2: 呢一段要Jeffery佢哋要求要我哋行E-system，行個新CSR個模組之後呢，我變成我同佢哋夾咗，畀佢哋未build嗰個linkage，現有嗰個CSR嗰個，即係點樣攞錢。係囉，唔係搞咗好耐。係，係，係，係，係。

Speaker 2: 係，我作為production嗰邊呢，我係好舒服嘅，因為我嗰邊係行緊CSR個模組，係完全可以行到。但係呢，個part number同埋個description呢，嗰度呢，我哋而家嗰個CSR係仲有啲嘢未搞掂。跟住阿Paul話，係喎，三個repair，三個repair，嗰個part number唔同。

Speaker 2: 我哋而家畀人，我哋而家畀人。係啊，要，要

Ray: 可以繼續，哎呀，要畀多少錢畀人哋。係啊，係啊，係係啊，係啊，係啊

Speaker 2: 係啊，係啊，係啊

Speaker 2: 你真係 project 嚟改到嘅，即係阿 Jane 就做到嘅。咁你 project 係咪一定，如果遲咗係咪一定要入返個 delay reason？應該好似係，我見佢彈出嚟。但係如果 project delay 就唔使，但係如果阿婆嗰度，但係 project delay 就唔使。咁但係如果我 project delay 咗，影響到嗰個，嗰個 completion date 嘛，會推嘛。係囉，即係變成我如果我 completion date 都係遲咗嘅話，都係要阿婆。我試過其他地方撳嘛，我撳到嘅，咁推咗兩日，好似你頭先咁樣講。係囉，咁推咗兩日，我入咗個 delay，呢一個 delay 就唔使阿婆。咁就係 delay 囉。係係係。但係頭先如果你話真係，真係去到嗰日我再，再，因為你郁呢度或者郁呢度，如果係 delay 其實都要郁返次，就要阿婆。但係你就咁改今日就唔使。咁譬如如果本身你個 finish date 係 14 號嘛，咁但係我 delay 咗兩日，咁到時我入 16 號，其實佢都係當我，就唔使再打囉。就唔使再做阿婆啦。因為我 project 個日子已經係推咗啦。知唔知啊？

Ray: 但係你呢個係，係早咗喎。即係早咗，早咗去又無嘢嘅。早咗，因為 5 月嘛。本身，亦都係 future 咗囉。但係，亦都係早過 5 月你本身個 finish date 同埋個 project date 嘅。我頭先入 16 號嘛，無問題囉。佢都無遲無早。但我入 15 號嘅話，其實都無問題嘅。但係呢，原本呢度入咗個 delay reason 係無咗嘅。哦，因為你無 delay 到嘛，你本身，佢本身 finish date 5 月 14 號嘛，而家你 4 月嘛。改過，改過，畀呢度。即係你 assume 應該佢改咗，入咗 delay reason，其實應該 keep track 咗呢樣嘢喺度，filing 咗嘅。咁如果我無論我個日子早定遲，咁可能啲 notification，唔係，頭先入咗，我揀咗，咁係有 show 喺度嘅，個 delay reason。但係 ACCT 嘅時候無咗。連呢個 projection change 都無咗。呢個，projection change 有啊。個 delay reason 同埋 projection change，但係個 reason 無咗。哦，即係佢應該會 keep 喺呢個位嘅。咁如果，假設啊，假設啊，因為我無試，我試唔到。假設如果我第一次我推咗兩日，有個 delay reason 1。咁但係可能我而家要再推多一個禮拜啦，係第二樣嘢嘅。咁我要再改，咁嘅時候，第一個個 reason 就無咗囉。我 suppose 應該啲 reason 儲，呢度唔 show，其實呢度應該 show。應該係 back end。

Speaker 2: 係呀，第一個 reason 係冇咗嘅。我 suppose 呢個 reason 係儲喺度，唔 show，其實呢度應該 show。應該係 back end 有嘢錯咗，但係而家係冇咗，即係佢唔 show 啦。係囉。咁即係都係，如果我再入呢就會下一個 log 住咗又有一個 delay reason。唔知佢後面有冇儲。

Speaker 2: 唔停。如果簽得好 record 嘅話就 final。其實好似頭先 Russell 所講，好似而家咁，其實我哋都係 fulfill 個 task，我 fulfill 個要求，個工作要求。係呀，你叫我入返我就入返啦，遲到。但係如果你哋預第日要再攞嚟做 further 啲嘅嘢呢，咁其實而家個 structure 簽得唔係咁好。

Speaker 2: 唔係好 fully 睇得返。即係我哋都係為咗，哎呀你叫我入返個 task 我就入返畀你囉，而家呢個狀態。但係我覺得，你幫我諗下囉。你嘅角度係入咗就入，但係應該要入到嘅嘢好似入唔到。Keep 唔返轉頭啲 data 仲有冇返齊整。係呀，因為佢 step 咗落去。因為即便而家個 system 其實佢會 overwrite 嚟㗎嘛。

Speaker 2: 佢你入咗落去，我記得呢佢喺 database 度，佢有個位，佢有啲嘢係會 overwrite 咗之前。佢得一行畀你放儲嘢。但係因為我哋冇人，嗰日返去特別改嘢，因為我見單出嚟個 Excel 係有。佢冇一兩次，好似頭先你講如果係第一次 record，改完之後佢冇儲第一次、第二次出嚟，佢只係儲返。

Speaker 2: 因為而家佢畀你寫嗰個位，講返好似，我好少改嘅。講返好似其實你繼續喺度改日子，嗰個 remark 都仲係嗰度。但係佢冇，佢唔係好似而家呢個咁係揀，跟住佢幫你 run 完之後，佢應該食咗呢個 data。但係佢而家食咗唔見咗啦。咁舊嗰個而家用緊嗰個 database 就好似佢繼續 keep 住嗰行嘢。

Ray: 佢就係應該要 keep，當你唔改之前佢都應該 keep 㗎。係呀。咁就唔知佢。呢個。佢就咁轉唔到 projection 嗰條線。我睇，譬如你呢個三月過咗啦，嗰個 projection 唔應該係咁樣。我都睇咗佢係 user 嚟。譬如我而家想，我改啦，我而家想 projection 改啦。呢度又得，projection 有 delay reason。

Ray: 但係我我想 submit 呢，譬如我 submit 今日啦。今日需要 approval 啦。咦，咁又得喎，奇怪。你喺呢度撳得，喺出面 task 嗰版撳。一樣。冇嘢。唔係喎，35 號係我撳咗頭先。係呀，佢撳咗。呢個。咁本身佢就係 27 號。

Ray: 咁我哋呢排呢，就係喺度搞緊一個，即係喺香港嗰邊，我哋做緊一啲，即係一啲，我唔可以話係，即係一啲 customer 啦，因為而家我哋係做緊一啲，即係一啲，即係幾個人，即係喺度做緊一啲 testing 嘅。

Ray: 咁我哋就係想睇下大家，即係喺個體驗上面，其實你想睇返啲咩，即係喺個 customer 啦，因為而家我哋係做緊一啲，即係一啲，即係幾個人，即係喺度做緊一啲 testing 嘅。

Speaker 2: 其實係思維嘅問題啦，大家。嘩，思維呀。即係譬如你要行，冇理由唔行㗎嘛。睇下點樣行，點樣行得舒服啲。思維呀。思維呀。思維呀，唔係變色呀，好簡單嘅啫。

Speaker 2: 唔係呀，你而家已經變咗幾廿隻色，你變多一隻色唔係咁簡單。啲色好亂呀，老細。我睇嗰個 chart 嗰啲點點點點斜，嗰個斜斜斜斜同埋，你全部都綠色嘅，得嗰度，嗰度紅咗。係呀嘛。嗰版呢應該差唔多，近到 deadline 你先變黃色呀，或者過期先變紅色。

Ray: 唔係佢個 task 咁到 deadline 呀。人哋嗰啲係人哋上一個 task 完咗未呀。完咗跟住佢個 task 就會變色。係有啲咁嘅嘢。即係佢對佢哋來講一完咗可能有一啲人有一啲部門係要即刻做嘢㗎嘛，佢想提埋佢，我 urgency 嘅問題。係囉。咁但我有好多問題，呢個 urgency，因為唔係 detect 佢自己嗰個。而家通常啲嘢係你做完之後我 action，佢就完喇。佢提你係提你啲色，係提你有冇連埋一齊。

Speaker 2: 不過我自己我覺得 so far 我自己我冇諗過自己呀，講真，我試，我就見到好多細節位。係囉。即係，你個程序係點樣。係囉。Feel 唔 feel 唔到。我想講，好多好簡單嘅嘢唔係咁 complicated。一望就知。即係好似我兩日後要交出去。即係，啲客可能問我哋啦，一嚟，成渣字，有理冇理隊晒落去。邊一個案幾時。我諗都係唔問呀，跟住係個客出咗事之後問你對唔對。係呀，但其實佢肯幫你諗，冇理由諗唔到。佢其實唔做，唔知係咪覺得咁樣，計多啲 hour 方便啲。唔知係咪計多啲時間。係囉，我整完咗之後你叫我整過。

Ray: 唔係即刻可以改到。係囉。我整完之後你叫我整。係咪當你amendment又整囉。但係我心諗呢個係咁，係囉。啱咗幾千個鐘你仲啱。

Speaker 2: 係咁就真係。唔係唔係唔係。我覺得係某個地區嘅人。係囉。低難度，低難度。嗰個地方有一條河。最難嘅難度係印度。

Speaker 2: 係咁就。香港有幾間公司。你問都唔問就做。即刻就。仲有好多bug。你話做。你做。仲差過啱啱出嚟做嘢嘅developer。

Speaker 2: 痴線㗎。我有曾經用過。一個搵錢賺錢嘅心態諗佢係啱。真係我有諗過。所以我覺佢係絕對啱。咁但係你話畀我聽我嘥啲乜嘢幫你整。問題係我一直都有一個諗法係vendor係唔會幫你諗。

Speaker 2: 呢個係前提。因為佢唔會。你要佢幫你諗係extra effort。就收你錢。用嗰部分收你錢。等如我收你錢。但係呢度冇人咁諗。冇人明白個責任係搵人developer嗰個。

Speaker 2: 所以SAP咪有一個問題囉。但係SAP有諗。佢哋vendor諗得好細。收咁多錢。佢個scale大好多。大好多。但係佢都係。你係大老闆，你係最大老闆。佢係二老闆，我係三老闆。佢係嗰個。你收大份，你收第二份，我收第四份。慢慢收。逐個層次收。

Speaker 2: 係。但我成日覺得聽係責任。我成日都話聽係有責任。即係聽咗嗰度你錯過一次兩次。講唔清楚。但係冇乜好多user嘅角度可以將件事完整咁講畀你知。咁你問我兩句我先答到。你唔問你都做到。天才。唉。做出來唔係。

Ray: 你做到嘅係。原來係另一個台。呢個係。都幾。好。我唔知佢閃下閃下又得，閃下閃下又唔得。即係我最尾覺得冇問題。你梗係覺得冇問題，因為你做乜都得。我試過呀大佬，我試過好多次。但係如果你企喺佢嘅立場諗，你企返佢立場諗，你覺得佢啱。

Speaker 2: 你企喺佢個立場諗，你唔知佢做乜。企喺你個立場諗，你咪受苦囉。要受苦就要跟住受苦。所以我成日都話。你唔好畀佢accumulate啲嘢畀你。你要將件事。譬如你睇唔明。你要。如果我企喺佢立場，我真係唔知。我企喺度。佢畀啲乜嘢我。我睇唔明。我係畀錢嗰個，就要你解釋。解釋完之後仲要畀啲垃圾我。

Speaker 2: 企喺我立場我一定督佢。梗係整啦。有冇搞錯。而家係畀全世界。大佬全部都睇到。大佬邊個睇呀。畀咗個project。

Ray: 咁真係喎，有無個重點囉，真係。你畀全世界睇，你擺咗全部都睇到。大佬，邊個會睇呀？畀咗個 project 你，你諗掂佢啦哥。

Speaker 2: 你執邊個？我係個保險度入。但我企喺佢立場去諗，所以呢，佢哋一定會唔在乎，因為佢哋一定會唔在乎。

Ray: 你同佢解釋，慢慢解釋佢聽。你唔執啲嘢，畀佢諗，下，邊個？邊個？好多問題，我問你十個問題，八個一百個。你解釋原理上嘅嘢，唔係真係解釋點樣一步一步去，係講佢知，佢哋嘅角度，PCD 係有機會畀人改嘅。

Ray: 喺個情況下，聽下，佢未必真係覺得幾時改或者點樣。你要去邊個位知道，你 parent children 都係呀，你講 parent children，佢都唔知咩係 parent children。佢都無呢個 concept。你要解釋一大輪，佢先會知道你未來攞成嘅字眼。

Ray: 你解釋下基本上面嘅嘢啦，好少人會改，一兩，改個 date 一兩日啫。基本上係 double check 囉肯定。五個單唔同你講呀，就咁揼咗落去。

Speaker 2: 邊個？Jackie 同埋阿 Alex。坐嗰邊嗰個，差唔多。

Ray: 五個直程唔係呢樣嘢。係呀，係呀。係呀，好耐啦。唔係，即係話禮拜五返嚟，禮拜六已經返咗嚟啦。我諗禮拜六返咗嚟，一齊食餐飯。

Speaker 2: 我當然諗緊而家，遲啲都畫定畀佢。Notification，即係同佢講話，幾行唔好畀佢呢，分散得太散。你將啲嘢集返埋一齊，下次你 check 都易啦。你話佢高過嗰堆渣嗰啲，遲啲都睇完又睇，睇完又錯。睇到好亂，我自己覺得係，好多字眼。

Speaker 2: 最緊要有一個，我係咩名，我畀人 accept 咗，你同我打個名出嚟。我唔知咩，你即係出咗我個 accept 嗰個 task 先得㗎嘛。或者你 hold 咗。跟住呢，有兩種，一 accept，一 reject。你畀佢揀 accept 同 reject，佢只係睇到 reject 啫。

Ray: 係呀，我頭先都係咁講。要個 status final，唔係喺而家 show 出嚟呢，無得揀。係 show 一行，畀佢 filter。而家其實我覺得嗰個 table 只要有 filter，嗰啲 column 呢，插埋晒一齊。我自己諗啫，task ID，首先要有先啦，因為 more than one，如果同一個客。兩邊呢，