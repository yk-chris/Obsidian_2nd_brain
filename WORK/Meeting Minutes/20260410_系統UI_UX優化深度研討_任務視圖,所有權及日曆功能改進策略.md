本次會議深入探討了現行專案管理系統在使用者介面（UI）與使用者體驗（UX）方面所面臨的多項挑戰。討論核心聚焦於改善任務管理效率，特別是針對任務視圖、日曆功能、任務所有權分配及通知系統的不足。會議明確了當前系統視圖以「Streamer」分組的模式不符合使用者（特別是 Task Owner）直觀操作的需求，導致任務追蹤與比較困難。主要共識是，系統應轉向以「任務編號」為核心的整合視圖，將同一任務在不同引擎（Engine）下的狀態合併於單行顯示，以提升清晰度與可操作性。會議也詳細列舉了多項UI錯誤（Bugs）及系統限制，並提出了具體的優化建議與後續行動方案，旨在為下一階段的開發提供明確方向。

## 主要決策

• **採納整合式任務視圖**：決定朝著將同一任務（如 Task 10）在所有相關引擎中的進度合併到單一行顯示的方向進行設計，取代目前分散的多行顯示方式，以利於使用者進行橫向比較與追蹤。

• **原型設計優先**：同意需要創建一個原型（Demo）來模擬新的單行視圖，特別是評估如何在有限空間內有效展示包含多個子模組（Module Level）的複雜任務，以驗證設計的可行性。

• **功能優化方向確立**：確定了多個必須解決的關鍵問題，包括日曆視圖的篩選功能、任務所有權的靈活性、通知系統的精簡化，以及修復一系列影響使用者體驗的UI錯誤。

## 技術深度探討：UI/UX 問題

會議詳細剖析了系統當前面臨的多個UI/UX挑戰，主要可歸納為以下幾個方面：

### 任務列表與日曆視圖 (Task List & Calendar View)

• **篩選功能缺失**：當前視圖無法有效篩選，使用者難以查看特定時間範圍內（如未來七天）的待辦任務，也無法隱藏已完成或非當月的任務，導致資訊過載。

• **導航不便**：從任務列表點擊任務後，雖然希望能跳轉至日曆中的對應位置，但具體跳轉邏輯（如跳至任務條的起點或中間點）尚不清晰。

• **視覺混亂**：日曆中的所有任務條顏色單一，使用者無法快速區分不同負責人或不同類型的任務。此外，缺乏週與週之間的視覺分隔線（如在週日後加一條線），使得跨週任務的追蹤變得困難。

• **UI 錯誤**：使用者回報了多個影響操作流暢性的錯誤，包括滾動條（scroll bar）在不同螢幕解析度下會消失或亂跳、取消任務後頁面會自動跳回頂部、以及儲存子任務後父任務會自動摺疊起來。

### 任務所有權管理 (Task Ownership Management)

• **所有權僵化**：任務所有權（Task Owner）與範本（Template）綁定過死。一旦從範本創建了工作流程（Schema），使用者便很難在常規介面中更改任務負責人。

• **權責不清**：當一個任務被分配給多個負責人時，容易出現「你以為我會做，我以為你會做」的混亂情況，最終導致任務無人執行。

• **修改不便**：雖然管理員（Admin）頁面可以修改任務所有權，但此操作對普通使用者不便，無法應對因專案進程變化（如 Level 升級）而需要臨時更換負責人的情況。

### 任務顯示邏輯 (Task Display Logic)

• **分組邏輯不直觀**：目前系統以「Engine Streamer」為單位來組織任務列表，使用者需要逐個展開才能看到具體任務，這對於需要橫向比較同一個任務在不同 Streamer 中進度的 Task Owner 來說非常不便。

• **期望的視圖**：與會者一致認為，視圖應以「任務編號」為核心進行分組。例如，將所有關於「Task 9」的項目整合在一起顯示，無論它們屬於哪個 Streamer。

### 通知系統 (Notification System)

• **通知泛濫**：被形容為「重災區」，系統會發送大量重複或無關的通知。使用者會收到不屬於其工作流程的任務通知。

• **關鍵資訊缺失**：系統缺乏必要的通知機制，例如當一個任務被取消時，相關人員不會收到任何通知。

• **審批流程混亂**：對於需要審批（Approval）的任務，通知機制不清晰，使用者不知道該找誰審批，系統也缺少對長時間未處理審批的視覺提醒（如變色）。

## 建議方案與選項評估

• **整合式單行視圖**：核心建議是將同一任務合併到單一行顯示。對於包含多個子模組的任務，可考慮在格內顯示關鍵字，並在滑鼠懸停（hover）時顯示完整資訊，以避免介面過於擁擠。

• **日曆視覺優化**：建議為週末或週與週之間添加不同的背景色或分隔線，以增強日曆的可讀性。

• **篩選邏輯修正**：篩選器應能同時作用於任務列表和日曆，當使用者設定日期範圍後，視圖內應只顯示符合條件的任務。

• **建立原型進行驗證**：建議使用工具（如 Syncfusion）快速建立一個新視圖的原型，以直觀評估其在處理複雜任務（如多個 module task）時的顯示效果和使用者體驗。

• **提供可切換視圖**：探討是否可以提供一個切換按鈕，讓使用者能在傳統的「Streamer」視圖和新的「任務中心」視圖之間自由切換。

## 已識別的錯誤與系統限制

• **滾動條問題**：在不同螢幕尺寸下，滾動條會隨機跳動或消失。

• **操作後跳轉**：取消任務或儲存子任務後，頁面會自動滾動回頂部或摺疊已展開的項目，中斷使用者操作流程。

• **篩選器失效**：日期範圍篩選器未能有效隱藏範圍外的任務。

• **排序與搜尋問題**：任務名稱中的連字號（hyphen）影響了篩選和排序的準確性（例如，搜尋「9」無法找到名為「9-」的任務）。

• **Module Task 顯示不全**：在日曆視圖中，包含多個子模組的任務未能正確展開顯示所有子任務，只顯示為一個整合的項目。

## 關鍵討論點

• **使用者視角的重要性**：會議強調，系統設計需區分不同角色的需求，例如 Planner 可能需要鳥瞰全局，而 Task Owner 則更關心與自己相關的任務，並期望能輕鬆比較上下游任務的進度。

• **單行視圖的利弊**：單行視圖的優點是簡潔、易於比較，但挑戰在於如何在有限的空間內呈現複雜的子任務資訊。若處理不當，可能會使單元格內容過於擁擠。

• **硬編碼 vs. 靈活性**：討論中提到，系統底層的一些邏輯（如 Module Level 與 Task Owner 的關聯）可能是硬編碼（hardcode）的，這限制了系統的靈活性。未來的開發應考慮將這些邏輯提取出來，變為可配置的選項。

## 後續步驟

• **開發新視圖原型**：由開發團隊製作一個整合式單行任務視圖的原型，用於內部評估，特別是測試其在顯示多個子模組任務時的清晰度和實用性。

• **修復篩選器邏輯**：修正日期範圍（Day Range）篩選功能，確保其能正確過濾並隱藏不相關的任務。

• **解決 UI 錯誤**：將會議中提到的滾動條、頁面跳轉、任務摺疊等UI錯誤列入待辦事項並進行修復。

• **處理命名與排序問題**：向開發團隊反饋任務名稱中的連字號（hyphen）導致的排序與篩選問題，建議統一命名規範或改進後端處理邏輯。

• **提供視覺化方案**：針對日曆視圖的視覺混亂問題，要求開發團隊提供一個加入分隔線或顏色區塊的改進方案草圖。

---

Speaker 1: 打個H2O啦，因為之前個H2O比我地delay咗嘅，咁個時間需要知道個H2O嘅，mechanical嗰行要有嘅。

Speaker 2: 即係個project，即係H2O個project，你有個deviation喺入面，係咪呀？

Speaker 3: 你應該喺第一個milestone之前就要有deviation，係呀，就唔係買咗PC先覺得band D同埋再改個H2O先至要upload。

Speaker 1: 即係如果你話係delay咗嘅，比個milestone date delay咗嘅，係啦，都唔需要，唔需要你有deviation，OK。

Speaker 2: 明白。呢幾個都可能係要傾或者要界嗰條線啦，有無啲你覺得好critical，覺得佢哋唔做呢樣嘢咁樣嚟講？

Speaker 1: 好critical，個task list，個task list即係要太，不過個task list即係佢哋話可唔可以有一個譬如好似而家個system咁樣呢，有個due task list咁樣，我喺呢一日之前有啲咩task要complete嘅，比個list我，我可以feature出嚟比佢哋。

Speaker 2: 可以唔係一個range，你話咩七日內，十四個禮拜，佢而家收埋咗，因為自己佢話個calendar做唔到呢樣嘢嘅filter，而家暫時呀，咁佢要諗solution或者我哋propose過其他嘢。

Speaker 1: 係呀，因為個task list而家喺system入面係無呢樣嘢喺度，係呀，即係入面個task。

Speaker 2: 同埋我聽到個DIP嘅時候，有得唔係淨係睇DIP，定係我唔知喺個column入面一睇已經睇到呢度無個completion date，因為佢list，asset係一個table嘅嘢。

Speaker 1: 係呀，係一個table，因為佢而家無得睇到，係呀，佢睇啲outstanding係上個月嘅，佢淨係focus喺而家呢個月，我根本我唔知我outstanding嗰啲task係上個月。

Speaker 2: 佢比咗第幾個月份，呢個view淨係single month，但係個task就cross好多個禮拜或者好多個月，而家個view就係無filter嘅作用，其實係最大問題。

Speaker 1: 係呀，如果譬如佢左邊嗰個column，我click個task，佢同我即刻飛去嗰個date嗰度比我睇呢？

Speaker 2: 係呀，呢個Edmond比我建議就係個名就出現咗喺度啦，係咪都見到，一係就嗰度click就開返個task個edit個page，一係就飛埋過去見到個calendar邊個位置，係呀。

Speaker 3: 睇個位置會好啲，因為睇個task其實你感受唔到個date，其實我就想要睇到之後先撳到，因為唔係你會bypass咗睇嗰件事。

Speaker 2: 理論上最好，我覺得係撳第一格，即係撳個task個名，就飛去嗰個第一格，然後第一格入面開。

Speaker 3: 但係你飛到，喇，你如果飛，飛到邊度呀？條bar多過一個格，你飛到第一格定第二格？

Speaker 2: 中間。你要講得好清楚呀，要飛定邊一格呀。Edmond，我唔知佢會show喺邊，中間，我見到啦。

Speaker 3: 喇，嗰個screen resolution唔一樣，我唔知你見唔見到。OK，咁例如，咁例如嗰日，當中有一個task view，有一個係1號嘅，有一個係31號嘅，咁成條喺頭尾，咁你咪show唔到我見嘅地方？

Speaker 2: 佢係13號啦，13號中間。或者佢鍾意啦，佢擺到中間，show到個中間。

Speaker 3: 呢個你要講得好清楚呀，我睇到就唔好，我澄清清楚。喇，我都覺得一點都係要比佢方便佢direct到佢要做個task。

Speaker 2: 同埋我覺得有DIP，即係頭先兩件事，首先一個list咁樣我唔使睇我做完嗰啲啦，咁我比我至少睇返我自己urgent，其實係話urgent，你話可以filter到幾個禮拜，而家個view就係filter唔到睇唔到。

Speaker 1: 即係佢無得compress返想要嗰啲task剩返落嚟睇。

Speaker 2: 可以sieve到幾個禮拜，而家個view係真係sieve到睇唔到嘅。即係佢冇得compress返要嗰啲task出嚟睇，係而家個limitation係最大喺個view入面冇得咁。頭先直衝方法係得，但係嗰啲都係single single咁睇，但係有冇方法可以真係去一個pool咁樣嘅WIP task for 某個owner？喺而家個...

Speaker 3: 我覺得呢個如果你有，你一定搞唔掂。因為而家個action係，你容易囉，因為Excel係一個table，你容易睇到嘛。我覺得兩大concern係task...

Speaker 2: 佢想幫你入之嘛，佢想幫你入返個date之嘛，但係你唔畀佢睇到呢一件事。如果逐個位逐個位咁界呢，就好難搞，如果一排一排咁show返嗰個WIP出嚟呢...

Speaker 1: 喺個直衝可以做到，即係唔改佢個view，不過係做navigation嘅問題。個event，如果做到嘅話。唔知阿思講呢，嗰個task owner嗰度呢，可唔可以五個禮拜或者要界一界，有個好似個borderline咁樣？

Speaker 2: 即係禮拜六、禮拜日一個界？即係禮拜六同禮拜日中間呢，有一條深色嘅線。咁可能知道，即係五個禮拜。咁佢有冇心先？冇啊，我整到，呢個一定整到。唔係，你叫一吓佢郁一吓囉。

Speaker 1: 即係你可能其實你想睇個week，你又想睇埋個AP，可唔可以show埋個AP？AP唔會，AP成個月嘛，AP你嗰度根本個column唔夠。AP係day-to-day。係啊，即係我覺得個week嗰度可能係真係... 我覺得個week係有需要，因為我覺得好多entry都用個week用個week嚟計。

Speaker 2: 咁有啲咩係嗰個week係complete咗啲咩，成個week就cut咗佢。唔好叫佢去cut，佢自己link晒嗰啲嘢。係啦，係啦。如果界一界呢就做到，我覺得界到就幫到手，係啊。咁樣就會清楚少少囉，假期嗰啲都唔需要特別highlight，係需要...

Speaker 3: 係，唔係，唔好咁樣。我哋想要就係禮拜六、日你轉返少少色，一個week有一條線可以睇得到嘅indication，咁我先可以界到。其實我覺得顏色都緊要，即係你話禮拜六、日嗰兩隻色呢，咁你一望呢就知拉到第幾個禮拜。就算我冇得畀個weekly view我，monthly view其實冇問題，一直咁樣拉到睇到。

Speaker 2: Bug嗰啲呢就係scroll bar無啦啦彈上彈落，scroll bar會喺唔同screen就冇咗。同埋一cancel task會彈返去上面。就我拉得好辛苦嘅，返返轉頭。一郁咗個task，入面啲嘢就自動熄返轉頭？熄返轉頭？即係譬如task column入面拆開咗四、五個mini-module task，我入咗其中一個mini-module之後，save咗之後佢會熄返埋。

Speaker 1: 佢會彈返去上面嘛，佢熄埋先彈返去上面。哇，好有手尾。好有手尾。跟住另外呢就係，嗰個就係，個task owner嗰度呢，可唔可以跟住個task 10, task 15, task 20，可唔可以跟住個module個level嚟改個task owner？

Speaker 2: 即係task 10，即係task 10嘅就係task 10, task 15啦，如果嗰個module係level 2嘅，level 2就係M4, M5, M8，level 3就係L7, L8。我覺得呢樣嘢好難。呢樣嘢真係冇得搞。我覺得每一部entry都會面對咁嘅問題。呢個就係某程度上糾結嘛，因為我哋template係跟work scope嚟分。

Speaker 1: 係呀，喺嗰度呢，我哋之前其實面對過咁嘅問題，係因為我哋個 template 係跟 workshop 嚟分㗎嘛，所以我哋記得係喺嗰度改張 template 嘅時候改咗嗰個 task owner，嗰個 template owner。

Speaker 3: 但係因為 template 之間呢，level 1 2 3 4 分得唔係好清楚。應該咁講，template 個名其實唔夠 signal 你去其實呢個係入面啲 task 係 involve 啲乜嘢，冇得 preview 㗎。

Speaker 2: 即係喺嗰度，簡單啲講，你 load 咗先，你要記住囉，邊個 task owner。我明，即係 select 呢個 task owner，兩邊嘅 task owner 呢，就有啲問題啦，就睇返你自己邊個決定做呢個 task owner。

Speaker 1: 但唔係嗰個 screen 喎，係要喺 admin page 入面改返邊個 template。係呀，即係個 task owner 兩邊嘅，係呀，咁問題就係佢哋就兩家都睇到，咁邊個去決定做就佢哋自己去決定。

Speaker 2: 兩家都會，有啲情況就係以為我要，以為你要，最後乜都冇做。係囉，你多過一個人就唔關我事㗎啦。佢哋唔會知多過一個人，所以 show 喺佢哋畫面，而家喺 create schema 嗰個 file 嗰個畫面，我哋可以改 task owner。

Speaker 1: 要 create 咗先至可以再改嗰個。冇得改㗎啦，係 by 個 template，template 唔改得。哦，workshop 嘅每一個 module，唔係一定跟 template，佢可能執咗全部 level 1，level 1 都有人 load 過下個。

Speaker 2: 要 load 完之後先至可以改返。得㗎，我意思我想問呢，係咪呢，我當你有些 level 升咗，突然之間有些 task 入面可能真係 assign 完都要 swap 另一個 owner，咁呢個情況其實而家係完全...

Speaker 1: 而家，而家 level 2 入面有啲嘢要做，都係跟 level 2 嗰個。但如果本身 level 1 轉咗 level 2，咁本身轉 level 1 轉 level 2 係同一個 owner 嚟。1 2 3 4 都係嗰個 owner 嚟。1 2 係同一個 owner，3 4 係同一個 owner 咁樣。

Speaker 2: 轉 3 嗰啲呢？即係得唔得先？問如果要轉呢？即係我唔知佢 level 轉乜嘢，如果個 level hit 中咗嗰個 task 係揀咗個 template 後唔同咗個 owner，咁其實就塞咗喺度㗎啦。

Speaker 1: Template 起咗之後就唔可以再轉 owner。唔係，係起咗 schema 之後。冇得轉㗎嘛。可以轉到。喺邊個位置轉個 owner？喺我哋 admin 嗰個位，有得入返去。你係揀個嚟做 template 啫。

Speaker 2: 我入去睇返喺 schema 入面有個 task，入去改嗰個 task owner，係個別，唔係 template，唔關 template 事。哦，得嘅。佢而家得兩條 line 囉，一個 10 個 20。係囉，跟 module level 嚟分。而家唔得就一定要跟 module level。

Speaker 1: 你哋想點樣呀？係呀，因為其實點講呢，因為其實機會其實係要開完之後，就咁撳撳撳，撳一撳嗰兩個 task owner。因為唔係每一個 engine 都會有咁嘅情況出現。

Speaker 2: 所以而家其實做得倒嘅係... 我覺得呢，如果畀我，如果唔係個 system 真係好聽話嘅話，其實呢啲 level 嘅意義等同於某個 owner，我覺得係有啲危險嘅。你話唔知 module 幾嘅 level 就已經係等於嗰個 owner，呢個 setting...

Speaker 1: 當初係 share 嗰個，嗰時係話放喺下個 phase，我記得係。跟住下個 phase 嘛，所以。嗰時佢話喺 admin 嗰度加返啲嘢。係呀，畀你 control 囉，即係呢個。

Speaker 2: 其實係呀，如果你控制囉，即係一個控制，即係如果你根本唔知幾時去，根本唔會有，SAP已經，不過已經可能唔會。

Speaker 1: 但係呢個係方便你哋。唔係方便呀，你係唔會開錯嘅，你係唔會入唔到。因為你set死咗有。咁全部你set死晒咁就無機會俾你開錯，我明。

Speaker 2: 但係唔係呀，而家即係我最眼見係，佢task owner個度好多推嘢，係會死。即係你話呢個開錯，開錯有得改返我話，最多話，啊，真係開錯。你話真係critical。

Speaker 3: 同埋如果佢要做到俾你可以任set，即係module幾level後，就要有owner default係啲乜。呢個logic抽出嚟俾你去改。如果唔係，阿媽底hidden咗hardcode咗，咁還好。但係到時侯唔係咁做，咁點做？

Speaker 2: 即係好彩而家都係得個兩個task set。係呀，我覺得，因為佢啲streamer好似開龍打冷咁，即係如果你自己咁推嘢好，睇下有無，睇下有無得打，打返轉頭。係呀，我覺得係，都係人嘅問題。

Speaker 1: 即係如果話開錯或者真係in case真係有其他要改嘅時候，唔記得咗改。假設係admin，個下真係個level升咗，唔記得咗呢個有關係，咁仲需可以自己做到，仲可以改到囉。

Speaker 2: 阿峰，其實我唔係，我覺得而家notification係多咗，係因為太多重複嘅嘢。係呀，係呀。唔係呀，有啲係佢哋，譬如CD有啲，佢哋都唔知CD發生緊乜嘢，佢寫埋其他task關佢哋，唔係佢哋flow嘅事。

Speaker 1: Modification個度又係一個重災區，即係包埋approval個度。我最驚嘅係佢排期，notification其實都係乜嘢，即係approval呢個其實係一個好大嘅，好大嘅範圍。其實點解我哋要整approval？

Speaker 2: 即係，係有啲嘢嘛，要有approval。呢個後加嘅最後先至加。係，係，係。但係頭先我發email單嘢嘅意思就係話，哦，佢如果20日後都未approve，係咪提下佢呀？咁呢啲頭先講。

Speaker 1: 即係outstanding嘅嘢，有無其他HR嘅notification？即係因為呢啲係唔by action係咪永遠擺喺度係可以。即係佢又唔知邊個approve。但係我覺得，佢係咪有一個template notification，有一個template approval？

Speaker 2: Approval嗰個template其實佢應該，我諗，有啲嘢pending咗好耐佢會變咗顏色呀，或者點。起碼有啲嘢囉。或者其實大家有意識入去，見到有個嘢有數字，就入去check下囉。

Speaker 1: 同埋係唔齊，即係，呢個approval個度，我覺得notification個度簡單啲呢，其實好多嘢唔齊。頭先話咩話？俾人cancel咗唔知啦。係呀，唔知。之後notify，點樣為之notify，其實有無講過notify啲咩內容？

Speaker 2: 呢個好細嘛。即係有幾多嘢要notify？Notify無講到好細。咁notify邊一個？即係頭先係咪130個都係關於，即係by owner？我當初嗰個notify機制係話owner，係by role嘛，即係by task owner，就所有task owner都會收到。

Speaker 1: 而家係拆咗做by planner by task owner。即係我，即係而家係咪後面到時上到去佢先知道，task owner大家係分開部門嘅。係咪？所以佢係無。

Speaker 2: 所以呢，係咪後尾度唔想攞去，佢先知度，佢係分開報？

Speaker 1: 所以佢係冇得開。好似頭先同Akif講，其實Task View嗰度，佢而家應該係Show晒，總之你係屬於Task Owner，你就睇晒所有人嘅Task。

Speaker 2: 係，而家係睇到六七個人。係咪我哋想要嘅嘢？唔係，佢Edit到、睇到係咪問題？睇到晒所有人嘅Task。冇問題，佢要睇上家㗎嘛，有時我覺得睇到係需要，因為可能係每個人都想睇吓呢度有啲咩爭。

Speaker 1: 佢未必係嗰個Task Owner，佢睇其他人，佢決定佢嗰個改自己嗰個係自己嗰個先改到。係呀，睇可以睇晒。例如Logistic嘅時候都要睇之前嗰個做完未㗎嘛，咁未必係佢自己嚟㗎嘛。

Speaker 2: 但而家個Calendar View就係好難睇，我全部同一隻色，我唔知邊個係邊個。除非我哋用上面個Filter，先Filter到。但好似Logistic嗰啲，佢話要睇上下家關係，我覺得你揀囉，你只揀兩個，但兩個都係畀兩嚿綠色，我都唔知邊個打邊個。

Speaker 1: 唔係，嗰啲Task係分咗畀邊個人，左手邊嗰個Column，係Task幾、邊個Owner。係，但嗰個係Task幾，唔係Owner。如果你記得就係啦。Calendar View好煩，就係可能佢好煩，一兩個星期，一個睇唔到一個，跟住一個消失咗咁樣。

Speaker 2: 即係個Date，可能呢個係18號，呢個係20號，咁我睇唔到嗰個邊。你冇得揀個Range。係呀，冇得揀。暫時都冇得揀。暫時都係唔係呢度，係個Task List。TO-DO List。你原本個Setting應該係，所以話睇Streamer都睇到Location，係開個Streamer爆開嗰個Task，即係Click嗰個Task爆下層嗰個Task。

Speaker 1: 一個Task有幾多個Streamer。而家嘅情況係睇Streamer，撳Streamer睇Task。係呀。但我覺得Task反轉佢好似好啲，佢哋會咁樣做。真係我想知到底例如我淨係做Task 9嘅，即係而家個View咁大版㗎嘛，我當我淨係睇Task 9，我就要，我有十隻Streamer，爆開爆開，之後睇返我嗰個。

Speaker 2: 我諗個Task Owner其實要爆開晒。但如果個Planner呢，就係咁樣。我覺得大個View係個Task Owner囉，所以應該爆開晒嚟睇。我知。爆開係由邊度開始爆？即係Akif意思係我畀咗一個Task落去，我Task 10嘅，點樣排？

Speaker 1: 我畀個第二個例子你呀，其實而家本身Task Log就係Group by個MST Task，雖然佢唔一定係同一個Task，理論上係某一個Task啦。頭先個角度就係Group by某一個Task嘅角度去Show晒所有嘢出嚟，無論Under任何一個Streamer。

Speaker 2: 所以佢係Group by Task，唔係每一個Engine Streamer，跟住可能係每一個Engine Streamer嚟去，嚟去抽出嚟睇。我原本係想睇晒成個Engine。咁有Streamer睇，咁你唔會理佢個... 其實係睇咗個Task先。如果淨係睇嗰個，係睇嗰個Owner自己。

Speaker 1: 其實而家每一版都有呢個Task。以三版Task Management個角度嚟睇呢，係睇咗個Task先，所有嘅，擺埋所有嘅Engine，所有嘅Task，譬如話所有嘅Task 10，應該List晒出嚟，擺埋一齊嚟睇。其實我一直都覺得係咁樣㗎嘛。係呀。而家係下面呢一隻呀嘛，即係各自嘅Task，你要爆開佢先比較到啲嘢。但喺Task Owner角度其實係咁樣㗎嘛。係呀，Group埋一齊呀嘛。

Speaker 2: 即係而家用緊嗰個，只係上面呢一隻順眼啲囉。我成個Filter係咁Filter出嚟，即係你我Filter個Task，你諗吓，你揀。

Speaker 1: 而家你用緊嘅嗰個 filter 係上面嗰隻純眼啲囉。我成個 filter 係咁 filter 出嚟㗎嘛，即係你，我 view 個 task，你諗下，你 show 啲咩畀我呀？你而家爆晒啲嘢畀我，你又冇收埋晒任何嘢喎。

Speaker 2: 即係呢度會爆喎，即係如果有十個 task 喺度爆喎。佢冇爆添，係爆一個，然後下面嗰啲全部，咁如果我嗰日有十個 task，佢會唔會爆開晒？同埋佢唔係爆開喎，如果有十個 task 喺同一個 task 嗰度，佢應該 task 9 show 咗出嚟，然後 task 10 show 咗出嚟。

Speaker 1: 係呀，佢係兩行咁 show 㗎嘛。佢而家個 filter 係咁樣，佢係冇爆。即係如果佢係同一個 task 呢，你即係 group 埋咗佢，但你 group 埋咗 MS Project 係有一樣嘢，你其實 group 埋咗 MS Project 係有 trigger，有 function 可以畀你個爆，即係佢會做，但而家我哋呢度冇。

Speaker 2: 所以 anyway，係，咁樣先啱，因為咁樣呢，如果佢係 multi，我所謂嘅 filter 係 multiple assignee 呀、或者 owner 呀，如果佢想 filter 某多過一個嘅 owner，owner 自己，就唔係，一係佢就同我做到兩行，一係就好似而家咁樣，即係一行過，上面唔亂。

Speaker 1: 即係起碼咁樣嘅時候，咁我就可以四隻 engine 排喺度，咁我都睇到，邊隻 engine 同邊隻 engine 係反派。但係點解佢當初設計同 task 會 show 兩行做，我哋叫佢定係點樣？我哋冇講過。當初都係 design，呢度係冇，呢度係佢自己做咗出嚟。

Speaker 2: 佢做咗個 calendar view 呀嘛。我諗呢度要改返呢度囉，呢度真係要改返呢度。係呀，睇下得唔得，呢度真係一行。如果係四個 calendar view 唔要，唔係唔要 calendar view，係 calendar view 嚟㗎，呢度係 calendar view 嚟㗎。呢度係佢 show 嘅方式，row 嘅方式，show 嘅 row 嘅方式唔好咁樣。

Speaker 1: 即係佢 expand，呢個係 expand 嘅樣，而家係 show 緊，即係其實應該係，即係其實應該係，expand 完之後，係要 expand 㗎嘛。但係依家佢嗰個 calendar 就延長咗佢個 bar，即係咁嘅 view 就已經解決咗 user 譬如搵到自己嘅 task 啦。

Speaker 2: 如果佢，譬如，上面嗰隻三月，下面嗰隻四月嘅，咁其實佢都睇唔到。係呀，睇唔到㗎。咁但係理論上呢個時候佢就唔使關心四月嗰啲住。我同佢哋大家，阿 Nick 講返，當初要兩行兩行睇得清楚啲。係呀，即係好似啱啱咁樣，一堆嘢喺下面 material，跟住下面四個 task，噉就死得啦，真係。

Speaker 1: 你個意思係，即係，做返所有嘢，成行要合返埋，冇咗啦。係呀，佢有個 filter 喺度㗎。佢有個 filter 係 sort 晒。冇 filter，冇 filter 嘅效果，即係。冇 filter，冇 filter 就係一行，會 show 晒。佢而家就 show 晒佢啲 task 喺度，show 一格。係咪唔會，我哋一定係 show milestone date 㗎嘛，即係 show 某個特定嘅日。

Speaker 2: 係，即係 show 某個特定嘅日。當初，唔係，當初本身定出嚟 milestone date 我哋係 show milestone date。Milestone date 理論上呢，理論上基本上你一，一生出嚟嘅話，一開出嚟嘅話，個 milestone date 就喺嗰度。

Speaker 1: 我喺度等緊個milestone date出嚟。Last Monday，理論上，理論上基本上你一生出嚟嗰個話，一開出嚟嗰個話，個milestone date同嗰個PCD係一樣。即係理論上，你呢度應該係見到milestone同個completion date，如果佢哋係，係咪咁樣？係呀，佢係應該有。

Speaker 2: 佢真係唔見咗，係咪swap咗？係呀，係呀。試下搵一搵一隻有，搵一個data，佢會show兩個格。你係咪打個四落去？打個四落去，所以先咁樣show嘅。係咪？係呀，打咗四落去。我記得係咁樣。你試下將其中一格，譬如將個31個projected completion date改咗佢。改18。

Speaker 1: 佢揼咗位。佢show一隻喎，唔係show兩格喎。即係唔係show兩隻，唔係show兩格仔。一格仔。一格仔。一格仔咁樣嘅，四方格嗰啲嘢。無呀，全部係咁轉格仔。原本呢，有actual completion date就show返actual completion date，再唔係就轉唔知邊隻。總之就有milestone到finish date到一格。

Speaker 2: 係呀，有好多個方案走出嚟。係呀。而家係單格仔方案。單格仔只係會轉某個date去show返出嚟。咁如果是單格仔，咁佢係全部合併埋一行，呢個自己落個顏色，咁就算囉。好耐，但係我覺得要filter囉。即係呢個filter，呢個，我filter咗嗰度，呢兩行唔要。呢兩行唔要。係喇，我filter咗唔要嘅行，梗係唔show啦。

Speaker 1: 佢而家話，佢要一個day range，而家開心同埋嘅filter，day range一定要成個calendar。咁我梗係X同Y夾埋一齊先有結果嚟㗎嘛，佢而家得個Y咁樣出結果嚟。如果得個Y邊有結果？佢就係咁囉。無收埋任何嘢，講緊淨係收埋咗嗰一個格式格仔。收埋咗個task。其他唔關事嘅。佢個task都無收埋，個task仲喺度。

Speaker 2: 我filter咗三隻，但係呢個task係真係有，但係過咗呢個月份嘛。但係佢唔會想睇嗰啲，佢係排嗰啲。係咪真係有？我度下。係咪有㗎？呢一個task係咪真係有？佢唔可以一隻畀你囉。下面呢兩隻。但係嗰隻，expand咗之後搵唔到佢部分。28、31、32。你撳咗個sort，個completion date喎。

Speaker 1: 佢有，你咪filter咗個，係咪出咗版嗰個induction date？係呀，得返三秒搵佢。但係有expand，佢個day range無filter。佢本身係無set到，要你自己去撳expand。包晒所有。但係你會去到好遠搵佢出嚟囉。但係唔一定係而家個月份。係喇，所以佢應該要成個月份，先filter嘛。佢day range無filter，先至有filter嘛。

Speaker 2: 做一陣先，我諗。我疑問緊點解要search engine係咪擺第四、第五格呢？我之前唔想講，但係我覺得有啲奇怪。擺喺中間。即係task擺喺頭。無所謂，呢個好細，總之我哋人係咁決定。milestone先啦，之後有engine type會大過ESN嘛，佢個單，之後先至出temperature。即係嗰三樣嘢嘅優先次序。我唔想講，但係應該係。

Speaker 1: 你唔會大過個 ASN 嘛，佢個 Data 咁樣，之後咪會出咗個 Table 囉。即係嗰三樣嘢要 show 晒出嚟。但係應該呢，應該三同三擺埋一齊先，應該係三喺度，三喺度，跟住下面，即係咁樣，就唔使有三喺度，就唔使分開。

Speaker 2: 呢個係因為，你想像下，頂層係有嘢嘅，佢而家係頂層無嘅無咗，但唔會排次序呀。即係你頭先講嗰個係要排。但係做咗個包圍嚟睇，但係我要一疊一疊咁包，之前嗰樣嘢，即係 collapse 咗囉。但係都好長喎，即係逐隻包完之後，你疊埋一齊之後，佢就會收埋。

Speaker 1: 點收埋呀？好有手尾呀，一隻做完就收埋。唔知呀，呢度係咪無名呀？即係浪費。唔係，我覺得係如果你講緊呢個係真係長嘅話，我諗你 reset at the very beginning 係最簡單。佢係有問題，佢可以而家呢舊嘢係，因為係幾個方案之後佢就亂咗。

Speaker 2: 我諗我哋之前嗰個方案係 show 咗包、箱同埋個 pallet 之間嘅 actual 咁樣。所以佢就係要將每個 task 分開嚟 show。咁但係我哋如果最後分開一個個 box 嘅話，我哋可以將所有嘅 tasking 分晒出嚟。唔係，但係你而家呢個，你呢個 show 咗呢一個，呢格其實係一格。

Speaker 1: 嗰個 description 係一號搞掂咗。即係將啲嘢放落去。唔係，呢行好咗，直接去個格式，呢行三、四擺入去，就變返一行，跟住唔同日，之後唔同格仔，即係同一個 task 就喺唔同嘅日子度。嗰格仔有返個名，嗰日有兩行，兩行任務係咪疊埋咗？即係同一個日子 output 咁樣嘛。

Speaker 2: 係呀，疊咗。因為你而家 filter 咗嘛，所以其實如果你撳兩隻嘅話，佢應該係一格係三，跟住第二格係四，咁樣去寫返出嚟咁樣。咁你咪一行可以做晒 ASN、Task 3、Task 4。Module level 嗰啲點樣？Module level 全部插晒入去，六、七個。Module level 先至會爆出嚟，佢爆係為咗 module level 呀，係咪咁講呢應該？

Speaker 1: 有無一隻係 module level？揀個 module level task 睇下。Module strip 呀，係呀。Inspection 呀，得唔得呀？我爆。你搵個 module strip 我睇下，有無？九。咦？全部都係 0。咁你撳下佢。全部都係 0 喎。唔係，你去睇下 26066 有無 module task 呀？去嗰個大圖度，嗰個 schema 嗰度。

Speaker 2: 咦，有喎。前兩日嗰個 engine。下半截 31231。有呀，九有喎。咦？但係我嗰度得一個都有個 4 喺度。係咪有頂層同埋下層？邊行呀？睇返 3 月 12 有無呢啲嘢。無呀，10 咪喺嗰兩日發生晒囉。喺呢兩日。係呀無呀。呢個我可以話係錯啦，咁但係好明顯無 show 過啦。

Speaker 1: 即係話其實佢爆開其實應該要為咗，即係我可以 task，佢嗰六個 module 六個 task，你應該有六個。

Speaker 2: 為咗，即係我可以task，如果六個module六個task，你應該有六個格仔喺度㗎嘛。係呀，冇可能係縮埋一格。

Speaker 1: 即係佢個爆開，佢呢舊係可以根據tree map爆開，但爆開係爆module。但係如果咁細格你寫到啲咩字入去？狗，真係狗。唔係，佢可以長啲嘅，佢個map唔一定係正方形，佢長啲會更加容易睇到，因為好多空隙位。

Speaker 2: 但會多咗格仔，因為你變晒喺同一行，即係呢個入面呢，佢嘅所有task係擺喺同一行，咁睇落去可能係多咗嘢，但係。咁不如試下用Syncfusion，即刻整一個demo出嚟試一試個tool。

Speaker 1: 睇下點樣將一放落去，一放落去個格度有咩效果，即係如果我哋咁樣討論落去，有啲抽象。係有啲抽象。唔一定要用Syncfusion嘅。Syncfusion做例子，如果我全部喺同一行，我唔爆啦，但我將所有module task都show晒喺同一格度，會唔會太樣衰呢？

Speaker 2: 有機會會啦。咁之後或者唔係呢，咁個字放喺邊度會唔會太樣衰呢？如果太樣衰就。你字多點都係難睇㗎啦。即係你話成行，module 1, 2, 3, 4, 5, 6 咁樣好長。係呀，show到睇唔到。同埋佢個tree map係咁樣。

Speaker 1: 好似呢個咁，個search就喺呢度，但係task view就喺呢個位，所以。sorry，你頭先講邊個位？嗰啲位全部都係component嚟，係呀。係呀，如果你擺晒呢堆嘢入去。係呀，如果你擺同一個顏色，佢有機會黐埋一齊，分唔到邊個打邊個。

Speaker 2: 一係你就加個框。其實我諗緊可以畫個demo。係呀，佢都係咁諗。你明唔明？唔係，而家唔知點搞，唔知搞啲咩出嚟。佢而家custom make嘛，佢又要用Syncfusion，又要用舊嗰套，又要用新嗰套，幾多嘢要諗。

Speaker 1: 你可以唔show字全名嘅，show最重要嗰幾個，之後hover嘅時候先睇到嗰啲嘢。個名其實唔係咁重要嘅。係，對住個mouse一劃過去就睇到。如果SAP有個customer code俾人lock咗，知唔知搵邊個解決？

Speaker 2: Customer code俾人lock咗，應該搵邊個？SAP呀？SAP可以俾人lock。我見過lock住個control number。係呀，可以有咩處理方法？搵返嗰個人囉。佢唔喺度呢？問下佢咩事先。係呀，engine入面成日發生，搵返嗰個人就開到。

Speaker 1: 佢俾個control number，搵返個control number就開到。可能係佢哋。係咪佢哋個contract，係咪佢哋個contract啲日期唔啱？我諗係contract嗰類，因為個customer code俾人lock咗。咁點解呀？你話俾我聽。係呀，搞掂呢個先。

Speaker 2: 所以變咗如果要擺晒啲字喺一格入面，太長會睇唔到。你既然task ID係unique，你show個number。理論上係，show個字，show 9XX... 咁樣。好唔點，好有問題。如果想美觀少少嘅話，咁其實。

Speaker 1: 其實個總數個字，我show 9 XXX 點點點咁樣。好唔點啊，又點。唔係，如果我想美觀少少嘅話，其實show 個number 係。其實你show 唔show 嗰個9 喺個of course 唔係好緊要，因為其實你已經揀咗。

Speaker 2: 如果你係multi-task 呢，就。Multi-task 係指啲咩呢？可能係。通常。唔係，如果multi-task 係三五九，三五九你唔知嘛。咁你就要show 啲嘢。例如我係EO 我一次過睇幾個task 嘅，咁啲三五九都係。咁multi-task 呢，可能要睇嘅呢，就係9、10 同埋15 喇。咁multi-task 就要睇9、10、15。

Speaker 1: 我唔知佢有呢堆task 喎。咁如果你唔知佢點樣標碼，但係個尺度。但係會有好多碼。好似10、15、31 咁樣。10、15、31 係咩？即係你頭先。10、15、31 頭先係我哋無揀過task 嘛。無。佢無show 到出嚟。10、15、31 係無嘅。佢只係揀咗top 嗰個嘛。

Speaker 2: 唔係，即係如果你揀inspection 之後再揀9 呢，頭先。唔係，你task number 唔好揀嘢。Task 嗰度留空。唔係，睇9 同埋O4 嗰版。Inspection 9 同埋O4。9 嗰度無9 喎。咦？頭先係module change 無9，module repair 先有。唔係module repair，係module repair。Module repair 係bench。10 嗰度。喺上面。喺下面嗰度。Bench 加module repair 呢。咦？9 喺邊個？無set 到，無set 到。9 係邊個？Module repair，module repair 係9。

Speaker 1: 喺下面，下面。O4。咦？有O4。O4。啱喇，啱喇。頭先我揀唔啱個task number，所以唔知。真係。但係頭先我哋都無知個task number。即係佢只係show 個最top 嗰個畀你。譬如359。譬如而家有出喇。如果你唔揀task number，PO PO。好，無10 task。係咪個個都係咁樣？係啊，個個都係最top 嗰個。哎呀。係咪個hyphen 睇唔到？睇唔到。哎呀，我唔夠。睇唔到個9 出嚟。又有喇。9 喇。哎呀，好蠢啊。

Speaker 2: 係咪個hyphen 遮住咗，所以佢唔當。佢唔當係。即係揀咗9。即係揀到最尾嗰版。其實OK 嘅。用hyphen 呢，喺個task 嗰度。有排次序。即係而家佢真係。即係無排嘅話呢，有啲難。你叫Fergus 改返個9 空格。唔好用9 hyphen 囉。我之前mark 低咗。但係正常如果你揀9，佢應該會出task number。即係module。遮咗隔離嗰個。遮咗隔離嗰啲。淨係揀task。好難講，揀9 唔代表。因為每樣嘢都無link 埋。無關係。獨立嘅。獨立。

Speaker 1: 係。所以變咗，即係而家基本上變咗。佢改咗嗰度。即係hyphen 之前加個space。唔係，你要講個作用，唔好講個名。因為你assume 個名改返，佢就會排返靚。我諗直接講你想排嗰個位置有問題。你就，佢有咩方法。就唔好咁多意見都OK。總之，心目中最簡單其實對家係改返個file name。但係要佢由頭排返。Always show easily。佢都唔想咁多嘢。但係排嗰個位需要提。兩樣嘢嚟嘅。兩個問題。呢度hyphen 前後加返個space。個次序都要跟。但我哋waste 咗個bug 係佢。Module level 嗰啲喺個task name 嘅底。Task number 喺個底。呢個係個問題。佢哋自己諗點解決。

Speaker 2: 但係我哋，我哋 Workspace 嗰邊唔係佢 Module Level 嗰啲喺個 Task Name 嘅底度，Task Number 喺個底度呀，呢個係個問題，佢哋自己諗點解決。唔好指清楚對，如果唔係佢話係我哋決定，就話係我哋決定。

Speaker 1: 咁我唔知你點諗啦，我畀返個意見你。我諗緊呢度，你講呀你講。

Speaker 2: 即係呢度，即係好似咁樣做返先。咁已經係兩樣嘢嚟㗎喇，第一樣嘢，唔一樣嘅。因為呢，點解，點解頭先話之後嗰個融合呢？因為如果我想咁樣，但我又例如我左係九號嘅，我想睇埋八號發生咩事，咁樣就會難睇啲。

Speaker 1: 咩八號？八號咩？八號？八號有自己條線，跟住有 Expand，跟住你加返落去返港。即係你針對單一嘅 Task 去睇。

Speaker 2: 所以帶融合咗就可以咁樣嚟睇囉。因為例如好似頭先話齋我想知道上家係一貨，或者係會唔會遲貨呀，我同時揀咗上一格嘅 Task，佢就應該，如果喺同一行，我就睇晒兩格，咁我就即刻知佢係咪遲咗，所以我遲咗。咁就唔使隻眼郁嚟郁去咁樣嘛，係咪先？

Speaker 1: 所以你個重點係喺同一行。係啦。如果同一行睇晒呢，即係如果你咁講呢，如果佢係有 Module，即係同一行睇晒，如果佢嗰啲 Task 係有 Module，要佢，我諗要佢試一試放落去，如果一格嘅話 Show 咁多行出嚟發生咩事，會唔會有幾多層？

Speaker 2: 因為理論上呀吓，就算，就算兩層都好，其實佢，即係要有好大位睇，例如我真係嗰個 Module 睇晒 Module 咁多個 Task，睇埋啲 Module Task，喺 Task Owner 嘅角度唔應該好多會發生嘅。佢最主要，例如我係 Owner，我咪淨係睇 Owner，咁應該係得一格仔啫。除非我又會無端端關心其他，其他 Module 發生緊咩事嘛。諗下諗下啦吓。之後最多我咪睇埋前後嘅八同十發生緊咩事囉。

Speaker 1: 係啦，或者再前後。即係如果 Module Level 淨係關心自己個 Module 㗎之嘛。要佢喺個 Development 砌幅 Cap 圖嚟睇下。或者你呢度可以咁樣呢，可以咁樣，睇下佢哋可以 Switch 呢？得唔得？點樣 Switch？即係如果個人有幾層，即係如果你擺晒上去，Engine 嗰行，即係嗰個 Task Owner 嗰行，喺度做嗰個，係。但你要話畀人知邊個係主角。

Speaker 2: 係呀，即係你要寫返清楚。係呀，你塞咗個 Task 喺度，你由返咁遠，你 Show 晒出嚟啦，好似個，係呀，即係你個重點係佢嗰行，你想擺上去嘅。其實係咪應該有個掣可以一次過睇晒？應該要有。你睇個四，或者一，睇單一個嗰啲。OK，你跟住去返呢個位置，你開返三秒嚟睇，爆開返大佢。咁咪等於嗰個樣囉。上去其實都已經睇到。不過你要跳，爆開咗就唔使人哋逐個逐個開咁解呀嘛。

Speaker 1: 你而家擺返上去，你而家直情每一個都隔咗一行，你而家咁樣變咗無意義㗎喇，個 Gap。你可以擺埋，擺返上去就得，其實佢喺同一行就得。係呀，因為嗰度直情係用嚟 Show 個 Engine Number 嗰啲嘢。Group By Completion。其實我諗嗰時我哋有嘅。