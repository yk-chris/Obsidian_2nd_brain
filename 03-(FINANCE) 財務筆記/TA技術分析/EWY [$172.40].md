我先講明一點：**[EWY — iShares MSCI South Korea ETF](https://www.ishares.com/us/products/239681/ishares-msci-south-korea-capped-etf)** 係一隻**韓國股票 ETF**，唔係單一營運公司，所以嚴格意義上的公司層面 **DCF / EV/EBITDA / PS / SOTP** 並不直接適用。今次我會採用**穿透式（look-through）估值**：用 EWY 持倉加權後的 **P/E、P/B** 反推出每股穿透盈利與每股淨值，再用可比 ETF 倍數做相對估值，並以 **NAV 平價**作交易錨定。EWY 最新可得核心資料包括：P/E 16.99x、P/B 1.94x、持股 81 隻；前兩大持倉為 Samsung Electronics 22.35%、SK hynix 18.78%，資訊科技佔比 44.91%，顯示其本質上是高度集中於韓國半導體與大型權值股的投資工具。[EWY Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewy-ishares-msci-south-korea-etf-fund-fact-sheet-en-us.pdf)

可比標的方面，我選用同屬大型、流動性高、以國家/區域股票敞口為主的 **[EWT](https://www.ishares.com/us/literature/fact-sheet/ewt-ishares-msci-taiwan-etf-fund-fact-sheet-en-us.pdf)**、**[EWJ](https://www.ishares.com/us/literature/fact-sheet/ewj-ishares-msci-japan-etf-fund-fact-sheet-en-us.pdf)**、**[EEM](https://www.ishares.com/us/literature/fact-sheet/eem-ishares-msci-emerging-markets-etf-fund-fact-sheet-en-us.pdf)** 作 peer set；其 P/E 分別為 21.37x、18.82x、16.40x，P/B 分別為 2.71x、1.91x、2.27x，因此我採用**同業中位數**作為保守估值基準：**P/E 18.82x、P/B 2.27x**。[EWT Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewt-ishares-msci-taiwan-etf-fund-fact-sheet-en-us.pdf) [EWJ Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewj-ishares-msci-japan-etf-fund-fact-sheet-en-us.pdf) [EEM Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/eem-ishares-msci-emerging-markets-etf-fund-fact-sheet-en-us.pdf)

現價方面，我採用 **2026-04-24 最新可得收盤價 US$154.57**；官方頁面同時顯示 EWY 當日 **NAV 約 US$153.38**，即市價相對 NAV 約有 **0.78% 溢價**，代表交易價格與基金資產淨值大致貼近，冇明顯情緒性偏離。[EWY Product Page](https://www.ishares.com/us/products/239681/ishares-msci-south-korea-capped-etf) [Google Finance](https://www.google.com/finance/beta/quote/EWY:NYSEARCA)

### 加權綜合結論

- **標的：** [EWY — iShares MSCI South Korea ETF](https://www.ishares.com/us/products/239681/ishares-msci-south-korea-capped-etf)
- **綜合公允價值：** **US$172.40**
- **現價：** **US$154.57**
- **總體偏離幅度：** **+11.5%（低估）**
- **安全邊際評級：** **一般**
- **核心觀點：** EWY 目前相對可比亞洲/新興市場 ETF 仍有一定估值折讓，尤其 PB 折讓較明顯；但由於其高度集中於 Samsung 與 SK hynix，實際表現很大程度取決於記憶體景氣循環、韓元匯率、全球科技資本開支與中國需求。因此我會將其判斷為**輕度低估**，但**未達 ≥15% 的強安全邊際買點**。 [EWY Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewy-ishares-msci-south-korea-etf-fund-fact-sheet-en-us.pdf)

### 估值模型矩陣

|估值模型|方法類型|關鍵假設|公允價值|偏離幅度|加權比重|
|---|---|---|---|---|---|
|DCF 現金流折現|不適用|ETF 無基金層自由現金流；不對基金本身產生營運 FCF|—|—|0%|
|PE 相對估值|同業倍數|EWY P/E=16.99x；穿透 EPS = 154.57 ÷ 16.99 = **US$9.10**；Peer 中位 PE = **18.82x**（EWT/EWJ/EEM）|**US$171.22**|**+10.8%**|**45%**|
|EV/EBITDA|不適用|ETF 無基金層 EBITDA；基金資產為股票組合，非單一營運公司|—|—|0%|
|PS 收入倍數|不適用|ETF 無基金層 Revenue；收入倍數對基金主體失真|—|—|0%|
|PB 淨資產法|資產基礎|EWY P/B=1.94x；穿透 BVPS = 154.57 ÷ 1.94 = **US$79.68**；Peer 中位 PB = **2.27x**|**US$180.86**|**+17.0%**|**40%**|
|NAV 平價法|ETF 特有|官方 NAV = **US$153.38**；市價較 NAV 溢價約 **0.78%**|**US$153.38**|**-0.8%**|**15%**|
|DDM 股息折現|排除|EWY 為年度分派、配息受成分股分紅與匯率影響大，穩定股利模型不可靠|—|—|0%|
|SOTP 分部加總|不適用|ETF 並非多事業營運集團|—|—|0%|

上述加權為 **45% + 40% + 15% = 100%**。計算式為：  
**綜合公允價值 = 171.22 × 45% + 180.86 × 40% + 153.38 × 15% = US$172.40**；  
**總體偏離幅度 = (172.40 - 154.57) ÷ 154.57 = +11.5%**。  
模型離散度方面，適用模型的變異係數約 **6.8%**，**未超過 30% 警戒線**，即 PE / PB / NAV 三種估值訊號方向整體一致，冇出現嚴重分歧。 [EWY Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewy-ishares-msci-south-korea-etf-fund-fact-sheet-en-us.pdf) [EWT Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewt-ishares-msci-taiwan-etf-fund-fact-sheet-en-us.pdf) [EWJ Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewj-ishares-msci-japan-etf-fund-fact-sheet-en-us.pdf) [EEM Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/eem-ishares-msci-emerging-markets-etf-fund-fact-sheet-en-us.pdf)

### 摘要總表

|日期|Ticker|標的名稱|現價|綜合公允價值|總體偏離幅度(%)|低估/高估|安全邊際評級|DCF 現金流折現|PE 相對估值|EV/EBITDA|PS 收入倍數|PB 淨資產法|核心觀點|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2026-04-26|EWY|iShares MSCI South Korea ETF|US$154.57|**US$172.40**|**+11.5%**|低估|一般|不適用|**US$171.22**|不適用|不適用|**US$180.86**|EWY 仍較可比亞洲/新興市場 ETF 有估值折讓，但其回報高度綁定韓國半導體周期與匯率波動；屬輕度低估，未到強安全邊際。|

### 我嘅最終判斷

如果你問我一句：**EWY 依家係咪平？**  
我會答：**係，屬於「輕度低估」，但未到「明顯便宜」**。以我今次較保守、ETF 結構相符的估值框架，EWY 大概有 **11.5%** 上行空間，安全邊際只算**一般**，未達我會明確定義為「高勝率買點」的 **15%+** 水平。若你看好韓國記憶體周期延續、Samsung 與 SK hynix 盈利修復、以及韓股折價收斂，EWY 有配置理由；但若你想追求更大 margin of safety，較理想的進場區間會比現價再低一些。 [EWY Fact Sheet](https://www.ishares.com/us/literature/fact-sheet/ewy-ishares-msci-south-korea-etf-fund-fact-sheet-en-us.pdf)

如果你想，我下一步可以直接幫你做 **EWY 的三情景估值（牛市 / 基準 / 熊市）**，或者同 **[EWT](https://www.ishares.com/us/products/239686/ishares-msci-taiwan-etf)**、**[EWJ](https://www.ishares.com/us/products/239665/ishares-msci-japan-etf)**、**[EEM](https://www.ishares.com/us/products/239637/ishares-msci-emerging-markets-etf)** 做一個 **橫向估值比較表**。