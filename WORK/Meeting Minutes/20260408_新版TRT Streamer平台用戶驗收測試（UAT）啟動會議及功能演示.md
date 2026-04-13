本次會議旨在向各部門的任務負責人介紹公司為推進數位化而開發的新版TRT Streamer平台。會議介紹了新系統的功能、界面以及即將進行為期三天的用戶驗收測試（UAT）的目標與流程。與會者在功能演示後提出了多項關於系統可用性、審批流程及界面設計的具體問題與改善建議，所有反饋將被記錄以供後續優化。

## UAT目標與流程

• **UAT目的**：邀請各用戶方（User Party）測試新平台，確保其功能滿足日常操作需求，並在正式部署前找出所有潛在問題、錯誤（Bug）或可改進之處。

• **測試時間**：UAT將為期三天，涵蓋從基本用戶界面到核心功能的各個層面。

• **問題記錄**：所有參與者需將測試過程中發現的任何問題（無論大小）、不順暢之處或增強建議，記錄在由Ray準備的Excel工作表中。

• **反饋重要性**：強調這是系統上線前提出修改的唯一機會，所有問題必須在UAT期間提出，以避免未來系統凍結後無法更改。

## 新系統功能介紹 (由Ray演示)

### 儀表板與任務狀態 (Dashboard & Task Status)

• **界面概覽**：新的儀表板會以不同顏色區分任務狀態，例如**綠色**代表「Project on Track」。用戶可以清晰看到屬於自己的任務。

• **任務視圖**：用戶可以根據不同月份查看任務排程，時間間隔以一個月為單位。

• **篩選功能**：提供多種篩選器（Filter），用戶可按部門、引擎類型（Engine Type）、客戶代碼（Customer Code）、銷售訂單（Sales Order）或子專案類型（Sub-project Type）等條件篩選任務。

### 任務更新與審批流程

• **日期更新**：用戶可以為任務填寫實際完成日期。

• **延遲審批**：如果更新的完成日期超過了原定的里程碑（Milestone），系統將觸發審批流程。例如，輸入一個比預計延遲的日期，或回溯更新一個月前的日期，都需要經理批准。

• **審批人設定**：系統已為不同部門設定了預設的審批人（通常是Line Manager）。用戶在提交審批請求時可以從列表中選擇合適的審批人。

• **審批通知**：審批請求發出後，對應的Line Manager會收到通知。任務狀態需在請求被批准後才會正式更新。

### Test Plan變更與通知機制

• **自動調整**：當Test Plan變更時，系統會自動調整相關任務的完成日期。

• **變更通知**：系統會自動發送通知給受影響任務的負責人，告知他們任務排程的更新。用戶也可以選擇是否接收Email通知。

• **任務追蹤**：新機制使所有任務的變更都更易於追蹤。

### Streamer概覽頁面

• **整體視圖**：提供一個概覽頁面，展示系統中所有正在運行的Streamer，並可按銷售訂單分類。

• **進度顯示**：以進度條（淺藍色）顯示每個Streamer已經進行的天數，並標示出Induction Date和Test Date/Assembly Date。

• **詳細資訊**：點擊單個Streamer可查看其下所有任務的詳細進度，包括任務負責人、里程碑日期、預計完成日期和實際完成日期。

## 關鍵討論與用戶反饋

• **任務分配**：與會者詢問任務如何分配到具體同事。

• **父子任務關聯**：系統已根據運營經驗設定了任務間的父子關係（Parent-child Relationship）。如果關鍵路徑（Critical Path）上的任務延遲，理論上會影響後續任務。UAT期間需要驗證此邏輯是否正確。

• **延遲影響可見性**：用戶關心如何清晰看到某個引擎延遲後對後續任務的具體影響。目前系統可以通過查看日誌（Log）追蹤歷史變更，但一個更直觀的報告功能將在第三階段開發。

• **審批流程靈活性**：用戶提出審批者（Approver）是否可以直接編輯任務，而非僅僅批准或拒絕，以簡化流程。此外，也討論了上級（如老闆）是否應有權限直接修改下屬的任務。

## 已識別問題與改善建議

• **批量操作缺失**：系統缺乏批量上傳或下載功能。逐一操作任務效率低下，尤其在處理大量數據時，用戶體驗極差，可能導致用戶最終放棄更新。

• **任務視圖不直觀**：目前的日曆式任務視圖（Calendar View）充滿空白，用戶難以快速識別需要關注的待辦任務。建議改為僅顯示「未完成」（Outstanding）任務的列表視圖，讓用戶能一目了然。

• **篩選功能成效不足**：用戶反映當前的篩選器未能有效過濾掉無關信息（如沒有任務的日期），作用不大。

• **審批流程僵化**：建議讓審批者擁有直接編輯的權限，以提高效率。目前的機制要求退回給原提交人修改，過程繁瑣。

• **允許輸入未來完成日期**：系統允許用戶輸入一個未來的日期作為「實際完成日期」，這在邏輯上不合理。與會者建議對此進行限制，或至少需要明確這是否為特意設計的彈性功能。

## 後續行動

• **全面測試**：所有與會者需在接下來的三天內，根據各自的日常工作流程對新系統進行全面測試。

• **記錄所有反饋**：將所有發現的問題、錯誤、體驗不佳之處及改善建議，詳細記錄到指定的Excel工作表中。

• **審批人設定**：待系統錯誤修復完成後，在正式上線前，將會根據各部門的需求確定並設定最終的審批流程及各級審批人。

• **反饋審查**：開發團隊將收集所有UAT反饋，用於系統的最終調試和優化。

---

Charity: 各位, 歡迎嚟到呢個UAT啦, 咁你哋應該唔同party會係唔同party嘅task owner啦, 咁我諗你哋喺度應該都係有experience喺你哋有deal過個TRT streamer, 所以你哋嘅大佬nominate你哋嚟試呢個asset啦。

Charity: 咁但係呢, 因為公司配合佢哋行digitalization其中一個roadmap呢, 就係將呢個asset database嘅streamer呢, 就會將佢變成一個digital嘅platform啦, 咁而家其實佢哋datalab嗰邊已經做咗大約我諗六七成嘅development啦。

Charity: 所以呢, 而家其實我哋部門已經開始做緊一啲administrative嘅一啲UAT, 咁所以呢, 今次就想invite埋你哋唔同嘅user party呢, 就幫手試一試呢個testing, 睇吓成個新嘅一個platform呢係咪有問題嘅。

Charity: 咁如果呢, 你哋等陣間Ray會話畀你哋聽其實我哋會有三日嘅UAT啦, 咁呢三日個coverage其實係有啲唔同嘅, 我哋係會由最basic嘅可能interface, user嘅interface啦, 跟住試到入去個functions你哋平時點樣答啦, 或者你哋好慣常要睇到嘅嘢有無啦。

Charity: 咁如果你哋試到有問題或者覺得kick住唔順嘅, 你哋即管出聲, 咁Ray其實佢已經prepare咗一個Excel嘅worksheet呢嚟去log低晒大家所有問題嘅, 咁如果你哋有任何問題就可以幫手fill in返嗰張Excel嘅worksheet啦, 咁等陣間Ray會再介紹畀大家。

Charity: 咁千祈唔好覺得唔好意思或者嗰啲問題好小事啫, 有又好無又好無所謂嘅, 係咪覺得enhancement又好, 真係bug佢kick住你嘅都好, 全部照mark咗先, 因為我哋唔可以而家唔mark低的話, 到到將來所有嘢freeze咗嘅時候呢, 我哋就無得再加㗎喇。

Charity: 所以呢個係我諗你哋唯一一個機會喺呢三日入面試完嘅所有嘢覺得有問題嘅就一定要擺晒上去喇, 咁就唔好等可能到個system真係deploy咗之後話喂唔係喎, 其實我入面有啲嘢其實我之前無提出到, 咁就我哋唔希望係咁樣喇。咁所以就你哋有無啲咩問題呀? 如果無我就交返畀Ray介紹返我哋新嘅嗰個system嚟緊係點樣試啦, 呢三日個agenda同埋你哋而家會點樣開始你哋嘅UAT。

Ray cw: 咁呢個新式嘅asset TRT呢, 基本上其實同舊嗰個都係差唔多嘅基礎, 例如milestone呀, project completion date同埋actual你哋完成咗task嘅date, 咁task嗰個detail你哋其實都可以喺入面睇到。

Ray cw: 但係呢, 喺新嘅界面呢, 就會多咗你哋嘅, 即係大家user可以入去睇到嘅嘢。咁喺你哋嗰版呢, 應該見到Banner有Task Owner同埋Staffing, 咁Task Owner呢就係屬於大家唔同department, 你哋入到嚟呢, 第時就會見到呢度係streamer, 咁就見到邊個sales owner呀喺度行緊幾多日。

Ray cw: 咁呢個上面呢, 大家可以見到有幾個page, 喺左手邊呢個位, 咁你見到係streamer啦, task啦, dashboard同埋all modules。咁下面嗰兩個呢其實同大家就唔大關係嘅, 咁主要就係睇返呢個streamer, 咁banner呢, 撳入去呢, 就會create streamer啦, 根據返唔同嘅date。

Ray cw: 咁create完之後呢, 就好似之前嘅TRT咁樣, 就會入返嗰四個stage。

Ray cw: 咁呢度呢, 咁可以見到呢, 咁就係頭先個 dashboard 啦, 咁就會嗰日常嗰廿幾個 task 就會列咗出嚟。 咁, 聽日呢, 就會係唔同嘅 task 喺唔同嘅 task owner 啦, 咁 based on task owner 呢, 咁其實就會接駁返去

Ray cw: 最主要嘅一個 page 就叫做 task status 嘅 page。 咁當今日係三月八號啦, 假設啦, 咁我就可以喺呢度見到有個 task 屬於我嘅, 綠色, 咁大家可以睇返呢個 UI 唔同顏色代表唔同 status。

Ray cw: 咁綠色係 project on track, 咁即係 IT 嘅名字啦, 咁當中之後就有啲唔同顏色, 譬如 delay 呀, project on track, 咁頭先呢個係 project on track, 之後 project delay, 有啲 disable 咗, 咁喺呢度會有清晰嘅指示大家可以睇到。

Ray cw: 咁大家要做啲咩呀? 就係知道唔同 task 嚟緊幾時會起貨, 喺呢個地方, 咁你哋可以睇到個 schedule 啦, 咁嗰啲 interval 呢就係以一個月做單位嘅, 咁你基於呢度去睇唔同月份, 睇返唔同嘅 schedule。

Ray cw: 上面呢亦都提供唔同 filter, 咁可能有啲部門係需要睇多過一個嘅, 或者你需要 filter 唔同嘅 task 啦, 咁呢度亦都講咗唔同嘅 task 係屬於啲咩嘅, 譬如呢度 task score, 我可以 filter 唔同部門, 揀完之後 click 返 check 咁佢就會 filter 返返部門嘅 task。

Ray cw: 咁亦都可以揀, 譬如揀 all, 我可以 based on 唔同嘅 engine type 去 filter 啦, 我可以 search 呀, customer code 呀, sales order 呀, 咁樣你哋需要嘅資訊就會出晒嚟, 呢度亦都可以 filter 返唔同嘅 sub-project type。

Ray cw: 然後譬如三月八號, 我 engine build 需唔需要起貨嘅, 咁我喺呢度可以入返個實際嘅日期, 揀三月八號啦, 譬如, 然後... 我更新返個 status。

Ray cw: 因為唔同日子會需要唔同嘅描述, 咁好似而家三月八號, 如果入返去, 但今日係四月八號, 如果入返一個月前呢, 其實系統係會需要一啲 approval 嘅, 咁我入返一啲比較新嘅, 譬如今日四月八號。

Ray cw: 咁我 search 返今日嘅日期, 譬如十四號起貨嘅, 咁我 search, 搵完出嚟之後, 咁大家可以喺呢度去填返, 咁四月八號起貨。

Ray cw: 咁呢度收翻一啲嘅 data，咁呢度見到個 final 嘅 data，係 12 月 20 號。

Ray cw: 咁個 update 係 11 月 7 號。最基本就係咁樣，咁大家見到嘅 data 只要係今日之前，早過個 milestone 嘅。

Ray cw: 咁譬如呢個 project completion 嘅，咁個系統係會 show 咗出嚟，喺 11 月 7 號。咁有其他 case，譬如我今日入咗一個 delay 嘅，我 12 月 5 號先完成。

Ray cw: 咁呢度需要一個 approval。咁喺唔同嘅 department，我哋都 set 咗一啲嘅 user 去做呢一個 approval。咁呢度有一個 list 俾大家去揀，咁各位可以揀翻合適嘅。

Ray cw: 如果唔合適呢，可以喺度揀翻個 user。咁當 send 咗個 approval 之後呢，預設嘅每一個部門嘅 line manager 都會喺呢度收到一個 approval request。

Ray cw: 咁需要 approval accept 咗呢個 request 之後先至可以做頭先嗰個 update。咁大家會見到個 task 隔離，都有個人頭喺度嘅，咁就代表呢個係需要 approval。

Ray cw: 咁你亦都可以利用呢個 filter 呢，去搵翻邊啲係需要 approval 嘅 task。咁呢個係其中一個 case 啦，入咗一個 delay 之後需要 approval，咁可以 cancel 嘅，如果你入錯咗。

Ray cw: 咁亦都有返，咁亦都有返個 approval 嗰個 line manager 嗰邊。我先入翻去呢個 approval 嗰個位。

Ray cw: 咁呢度首先 approve 咗之後見到個 task delay 咗，咁變咗最新嘅 data 係遲咗嘅。呢度有晒啲紀錄喺度。咁個 task 嘅 status 都會係 update 咗 delay。

Ray cw: 咁仲有其他 case 係需要 approval，譬如我而家將個 project completion 係 18 號。

Ray cw: 咁所以都要approval啦，譬如而家原本個project completion day係18號。

Ray cw: 咁我而家我改咗個project completion day，係29號。

Ray cw: 咁原本29號到18號中間嗰啲task，係未有approval嘅。

Ray cw: 咁當如果你再改多一次個project completion day，譬如你唔係29號，係早咗，早咗幾時，咁就需要approval啦。

Ray cw: 咁有啲幾時係需要部門嘅line manager去做approval，基本上個schema就係咁樣運作，不過我哋仲有幾點需要同你哋傾下。

Speaker 3: 想問下呢個task係點樣分派出去？即係你哋有幾多個task？

Speaker 4: 係啊，我哋有幾個同事需要做，之後需要...係，特定有兩個condition。

Speaker 3: 係啦，係啦，係delay。無錯，無錯。咁跟住到個check或者個confirm，我哋而家有無approval或者係點樣去做呢？

Ray cw: 暫時係要同你哋部門討論究竟係assign邊個同事去做approval。

Charity: 咁呢個呢，我想遲啲我哋真係launch嘅時候，我哋就會畀返啲information你哋，去話畀你哋聽可能delegate邊一位同事，可能係做開呢樣嘢或者熟識呢個流程係啲咩嘢。

Charity: 咁到時我哋就會喺個system度set返個機制個workflow就係邊一個部門，佢哋嘅下一層嘅approval line係邊個，未必係head of嘅人去做approval。

Charity: 但可能有些function佢哋想自己handle返嘅，咁佢哋我哋就會擺返入去。咁呢個會等到所有bug fixing嘅動作完成晒之後，我哋最尾launch之前就會做嘅嘢。

Ray cw: OK，咁介紹多小小啦。咁傳統上呢，大家都會聽過個test plan成日轉架啦。

Ray cw: 喺而家嘅新系統入面，個test plan一轉呢，就會所有task嘅completion day都會郁。咁當郁嘅時候，我哋而家有個機制。

Ray cw: 咁就可能set大家嘅task可能係跟個project completion day，咁就可能係而家嚟緊可能假設係10日啦，咁係8號可能10日到28號打後嘅日子嘅task。

Ray cw: 突然間因為個test plan更改，變到由而家8號到18號呢個range入面，假設啊，假設係10日。系統就會有個notification send出嚟畀所有負責呢個task嘅task owner。

Ray cw: 咁佢哋就會知有啲咩update咗，邊啲task加咗入去。咁都係需要各位去睇返個schedule，去知道有啲呢啲嘢update咗。

Ray cw: 咁變咗而家所有task都係比較容易trace，知道發生緊咩事。

Ray cw: 好似之前嗰個schedule，其實都有啲啲update咗。咁變咗而家所有task都係比較容易trace，知道發生緊咩事。

Speaker 3: 係email通知定係點？定係要每日入去呢個位睇？

Ray cw: Email其實係你自己可以揀嘅，係。

Speaker 3: 因為你之前係咪本身整咗條條phase，或者係整咗一個Gantt chart，係跟返個test plan或者係milestone嘅嘢？

Ray cw: 嗰個milestone係第一下load出嚟啦，係咪第一下load出嚟？Test plan改咗又要depend on。

Speaker 3: 個milestone都會跟住個test plan，即係個test plan如果鬆咗，你都會拉長個milestone。

Ray cw: 會拉長，咁就根據機制，某啲task會拉長，某啲task唔會。

Charity: 應該咁講啦，其實舊嗰個streamer我哋未有四百幾個task，咁其實我哋之前睇email嗰個講法係operation嘅層面，就係有啲task會延遲，其實係會影響下一家嘅工作。但係有啲呢係一啲我哋所謂嘅critical path啦，就係如果佢真係遲咗嘅，係啦，Irene嗰邊啲嘢遲咗返嚟，咁到最後係引擎嗰邊試唔到車，或者inspection做唔到嘅，根本都落唔到下一步去做in-house rework。

Charity: 咁呢一啲呢我哋就睇得緊啲啦，有唔同嘅機制就去set咗佢哋邊一個task同另外一個task係有parent-child嘅relationship嘅。咁嗰啲relationship其實我哋一set就喺入面。咁所以到時你哋試嘅時候呢，都可以試下就話「喂，點解Irene嗰個未返，但係後面嗰啲嘢全部都唔郁呢？」，咁呢啲就係debug嗰部分。咁所以或者係我哋畀佢哋個setting做得唔好，或者係我哋setting做setting嘅時候，或者做個linkage去define child同parent嘅時候，可能我哋諗漏咗都唔出奇。

Charity: 但係我哋based on我哋平時operation上面嘅experience啦，我哋就已經set咗一啲relationship喺入面。咁所以理論上你哋試完之後就可以「喂，冇理由引擎嗰度未做完inspection之後佢係delayed咗嘅話，後面裝拆嗰啲冇理由冇影響㗎嘛，in-house rework冇理由冇影響下一家嗰個milestone㗎嘛」。咁如果你真係見到有呢啲問題嘅話，就要mark返喺個Excel嗰度。

Speaker 3: 因為我係主要想知佢個引擎完咗，收返之後，嗰度係邊一個task係真係反映到個引擎delay咗十幾日之後嘅嘢。

Charity: 我哋其實有嘅，之後我哋會有類似，因為咁樣其實我哋成個streamer就分咗幾個phase。咁第一個phase主要係講緊個function入面點樣去做啦。咁其實去到第二、第三個phase呢，我哋係會有一啲reporting啦，同埋會有一啲interface呢就畀大家show返completed咗嘅streamer有啲咩engine number。咁其實你入到去呢，理論上你都係會見到有actual啦，milestone啦，同埋個project completion date嘅。

Charity: 咁如果你見到入到去呢，你click入去，其實理論上你可以睇返啲delay reason。咁但係你話真係想要一個靚仔啲嘅report或者show邊個引擎遲咩task呢，咁呢個會係第三個phase，which我都答唔到你幾時做得完，即係如果你想要一個靚仔咁樣嘅樣。咁但係你話唔係嘅，你知邊個引擎，你純粹想嗰個引擎自己喺complete嗰度去搵返嗰個引擎睇返以前啲record呢，咁其實呢個係會有嘅。

Speaker 3: 因為我以為係譬如話之前講緊milestone係個reference point啦，咁如果你個而家個milestone都郁咗，咁咪變咗睇唔到。

Charity: 唔係，應該咁講啦，我哋有log，log返原本嗰度出嚟，係啦，會睇到milestone之前係咩，而家係咩，同埋其實有兩個column㗎嘛，一個係project completion，一個係本身load落去嗰個㗎嘛。咁你本身load落去嗰個同你project嗰個milestone唔同，咁其實就係郁過囉。咁而郁過嘅log record呢，其實入面都會有嘅。所以你到時可以睇返入面睇下明唔明白。

Charity: 咁呢度都可以睇返，咁而家肉眼睇個 log 呢，咁其實肉眼睇個 log record 呢，其實入面都會有嘅。所以你哋都可以喺呢度睇下咩事。個 log 而家都有。log 有㗎喇。Ray 可以等陣話畀大家聽 log 喺邊。

Ray cw: 咁介紹完 part A 啦，我而家介紹返 streamer 啦。咁其實可以畀大家一個 overview 咁睇返所有 streamer，而家喺系統嘅 streamer。

Ray cw: 咁佢其實可以用返 sales order 嚟分嘅喺呢度。咁呢度 overall 你可以見到個 streamer total 有幾多人，而家行緊。譬如呢度 60 幾、70 幾、50 幾咁。咁唔同嘅 icon 就 indicate 返係 engine 啊、module 啊、module set 啊呢啲咁樣嘅 streamer。

Ray cw: 咁你見到個淺藍色呢就係佢而家行咗第幾日啦。咁呢度有 show 返個 number 係第幾日。咁見到有兩個 date 喺頭尾，第一個 date 就係，sorry，induction date，第一個 date 就係 induction date 啦，後面嗰個呢就係 test date 嚟嘅。

Ray cw: 咁如果係屬於 module 嘅呢，咁就，嗰個 date 呢就唔係屬於 test date，就係佢嘅 assembly date。咁呢度你見到係前面有一啲 engine 嘅 information，engine type 啊、邊個客啊、同埋佢嘅 work level 啦。

Ray cw: 咁上面你見到亦都有一啲 filter 啦，可以畀大家去揀返啲資料。咁揀返 engine type 啦、唔同嘅 information 啦。咁究竟呢個 streamer 係 WIP 緊啊，定係完咗啊，定係 disabled 咗。咁 disabled 嗰啲就係一啲唔行嘅機啦。我哋 default 呢都會 show WIP 嘅。

Ray cw: 咁呢度亦都分咗唔同嘅 streamer type，有 DIB 啊、post-delivery DIB 啦，同埋唔同嘅客底啦，同埋屬於 engine 啊 module 啊呢啲 filter。咁呢啲 bar 呢其實可以 click 入去嘅。click 入去之後呢，你就可以見到晒入面所有 task 嘅進度。

Ray cw: 咁睇到唔同嘅 task owner、唔同嘅 task name 啦，同埋佢哋嘅 milestone date、project completion date 同埋 actual finish date。咁去到最底呢，就可以睇返呢部 engine 入面有嘅 module，module serial number、work level 同埋佢嘅 status。

Ray cw: 呢度亦都有幾個 icon 嘅，咁可以將呢個 list 收埋個 induction date、test date、同埋 milestone 同埋 test date 嘅一個 project completion date 嘅 show 同埋 hide。

Speaker 3: 所以佢最主要係想睇返部機，即係呢部機，所以佢最主要係想睇返部機，即係因為佢有時，佢有時會 show 唔到。

Speaker 3: 咁其實你哋而家呢個個版呢，其實你哋係咪已經 apply 咗落去㗎喇？

Charity: 大家睇完之後，如果有咩問題，其實而家有好多問題係未解決，可以問。如果明咗之後，發現仲有唔啱洗或者做唔到你哋想做嘅，一律寫低。等大家都有個練習，知道邊度有問題。無論係你發現係覺得唔好用，其實都可以寫。用唔到你哋想做嘅情況下，可以問咗先再寫都得。

Charity: 應該發現好多問題係做唔到你哋想當日，或者唔方便你自己做。全部寫低，等大家俾多啲意見。唔明大家可以直接問嘅。

Speaker 3: 佢而家個掣其實都幾尷尬，即係一隻一隻撳呢 OK 嘅，即係叫行到啦。但係頭先你話 bulk 嘅 upload 又好，download 又好，如果你俾個小朋友喺度撳呢啲嘢，佢會崩潰。

Speaker 3: 其實呢度就算唔係小朋友，如果你入咗嗰個狀態，你又想睇到一啲嘢，我哋啲 data 係好粉碎嘅。本身你入咗個 summary，幾日之後個 summary，或者幾日之後個 summary，你係想人哋 update 得好啲，你梗係方便啲啦。如果我每一隻每一隻幫你撳先 update 到，我相信 at the end 係冇人會撳嘅。

Speaker 3: 因為真係太唔方便。寫低佢，我哋需要大家嘅意見。唔緊要，我當呢個唔係 bug 先，我哋寫低。呢個其實我都覺得係 bug。你頭先講，我唔肯定，我本身想問下 PC，小雞應該你有入咗線嘅。係囉。同埋假設啦，假設我老細真係覺得有嘢唔啱，咁其實佢都可以 update 㗎嘛。

Speaker 3: 即係如果你 set 咗嗰個 hierarchy 嘅話，我只可以定係得我嗰個 level 嘅人可以改。咁相反如果老細見到佢係咪真係改唔到啦？一定要叫返嗰個人入返去，做返個 approval。我唔肯定啦，但係老細見到唔啱，我直接幫你改返佢，咁我搞掂啦，唔使搞你搞我。

Charity: 因為其實我哋又唔係特別多層，我哋想佢簡單啲。我哋好簡單啫。寫低佢。唔係，我覺得係好多意見，其實個個都一致嘅。但係而家要真係寫低多啲，唔好介意寫。就算頭先嗰啲，落低你話 approval 機制會係 simplify 到，直接係 approver 可以做埋個 edit 嘅動作。

Charity: 我覺得有啲可以研究。Approver 我覺得成個機制要跟返自己個 department 要求，即係佢覺得佢需要嘅，咁就需要好多個機制。係有啲有啲係個 pathway 我哋可以改。其實對好多好多 department 其實可能都係涉及一兩個，佢有冇做囉。

Speaker 3: 但係而家有啲難度係，好似頭先問我，可唔可以一次過睇晒？頭先咪話一次過睇晒先，唔好話一次過入晒。一次過睇晒我而家剩低啲咩 task 要睇。而家個 task view 係睇唔到。佢分佈喺唔同時間，而唔係分佈佢有幾多種數。呢個 chart 都好特別。呢個 view 都唔係好啱。

Speaker 3: 你搵返出嚟，佢唔應該淨係 show 好似一個月曆咁樣嘅嘢，佢應該 show outstanding，我有啲咩嘢。唔需要 show 冇命中嘅日子嘅嘢。如果唔係搵到我哋眼花。你應該 show 我哋 attention 嘅嘢出嚟，咁就最好。我都好想。好奇怪，我以為咩都冇，原來係白晒。

Charity: 寫低呢個要寫低。就算佢嘅意見就話，我 show 個 list 我就可以 show 晒出嚟。你嘅意見我覺得就係個 calendar 上面，如果我唔需要嘅嘢點解你要 show 出嚟。

Speaker 3: 我收咗個 list，我哋可以 show 晒出嚟。你依家呢就係個 calendar 上面，如果我唔需要嘅嘢點解你要 show 出嚟？睇唔到要有啲乜嘢囉。個 filter 係……係囉，個 filter 冇好大作用囉可能。佢唔 filter 個日子囉，係。

Speaker 3: 係啊，有啲怪。如果揀晒呢，佢就會……咁樣。係啊，我都覺得好怪。係啊，我都想改。嗰啲 delay 呢點解可以寫落 Google？你過到喎。係啊，佢有得揀。係啊，我哋之前……你 save 咗喎。

Speaker 3: 你 save 咗喎。但係我之前 delay 咗嗰份嘢嘛。我 delay 咗嗰份嘢，跟住佢問……佢問嗰樣嘢就係點解 CCC project date 可以畀人改。即係本身我話今日要 delay，尋日係已經 delay 咗個 project date。如果你夾硬郁佢，你改返聽日，嗰個係唔可以。Delay 有 reason 囉。

Speaker 3: 哦，因為你冇郁過。冇郁過啲……reason for delay 我有嘢入咗。但係照計係可以郁嘅，即係……哦，OK，咁都好啲。但我頭先呢……頭先你郁呢個呢，照計係……係有得郁嘅。但係郁近啲呀好似。我唔知呀。

Speaker 3: 你再……點解由 future date 改返去同一個月？Future date 畀我入，即係 completion date 我入咗 5 月 7 號，我嗰度有入。Future date 畀我入，即係 completion date。係呀。哦，你可能預知聽日完成。紮低佢，紮低佢。紮低佢。但係呢個唔得喇。

Charity: 但係要諗清楚喎，如果你唔想……係唔想定係特登？有啲位呢，你用 tolerate 件事係畀你咁樣做，係有啲人……但係呢個反而有 future date。但係話 back date 反而……Back date 我都冇入。因為你做完喇嘛，咁你做完你咪點返尋日囉。但係你唔會知道下個禮拜一已經做完。同埋我哋關係係咁……我都知佢 flexible 嘅，但我會 confirm 囉。

Speaker 3: 你有冇分 session？

Speaker 3: 係囉，我諗住畀人……畀人入返。即係話畀佢聽，冇理由做唔到呢樣嘢。即係 CCC 嗰個……即係畀人……