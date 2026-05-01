---
tags: [schema, finance, workflow]
folder: 03-(FINANCE) 財務筆記
created: 2026-04-30
updated: 2026-05-01
skills: [invest-stock-valuation, invest-fundamental-analysis, invest-moat-margin-v2, dive-deep-bottlenecks, invest-IPO, invest-cost-return]
---

# 03-(FINANCE) 財務筆記 — Schema

## 資料夾結構

```
03-(FINANCE) 財務筆記/
├── schema_finance.md                                                 ← 本文件
├── log_finance.md                                                    ← 行動事件日誌
├── TA技術分析/
│   └── {ticker} [${綜合公允價值}].md
├── 公司業務, 護城河, 週期, 競爭格局/
│   └── {ticker} [${綜合公允價值}, {護城河強度（Y）}, {週期暴露度（X）}].md
├── 企業概要/
│   └── {ticker}{company name}.md     ← 檔名格式不一，見下方解析規則
├── 產業/
│   └── {ticker}_{業務部門}.md         ← 每個業務部門獨立一個檔案
└── HK-IPO/
    └── ipo_{yyyy-mm-dd}.md               ← 以執行當日日期命名
```

---

## Skill 對應表

| 資料夾                    | 使用技能                                                    | 技能路徑                                                       |
| ---------------------- | ------------------------------------------------------- | ---------------------------------------------------------- |
| `TA技術分析/`              | `invest-stock-valuation.md`                             | `01-(SKILLs) 技能/skill_invest/evaluate_company/`            |
| `公司業務, 護城河, 週期, 競爭格局/` | `invest-fundamental-analysis.md`                        | `01-(SKILLs) 技能/skill_invest/`                             |
| `企業概要/`                | `invest-moat-margin-v2.md` + `dive-deep-bottlenecks.md` | `01-(SKILLs) 技能/skill_invest/search_company (background)/` |
| `產業/`                  | `invest-cost-return.md`                                 | `01-(SKILLs) 技能/skill_invest/search_company (know-how)/`   |
| `HK-IPO/`              | `invest-IPO.md`                                         | `01-(SKILLs) 技能/skill_invest/`                             |

---

## Workflow A — TA技術分析

> 觸發關鍵字：`TA` | `技術分析` | `valuation`
>
> 使用技能：[[01-(SKILLs) 技能/skill_invest/evaluate_company/invest-stock-valuation]]

### 檔名規範

| 階段 | 格式 | 範例 |
|------|------|------|
| 更新前 | `{stock ticker} [綜合公允價值].md` | `NVDA [綜合公允價值].md` |
| 更新後 | `{ticker} [${綜合公允價值}].md` | `NVDA [$950].md` |

### 執行步驟

1. **識別 Ticker** — 從檔名解析 `{stock ticker}`
   - 範例：`AAPL [綜合公允價值].md` → ticker = `AAPL`
2. **執行技能** — 載入 `invest-stock-valuation.md`，以 `{stock ticker}` 作為搜尋輸入
3. **更新內文** — 將技能輸出（估值分析、目標價、技術面）寫入筆記內文
4. **重新命名** — 依照更新後格式重新命名檔案
   - 範例：`GOOGL [$370].md`
5. **📋 記錄日誌** — 於 `log_finance.md` 新增一筆記錄，格式如下：
   ```
   | YYYY-MM-DD HH:MM | A | [[TA技術分析/{ticker} [${value}]\|{ticker}]] | 執行 TA 估值分析，重新命名為 {ticker} [${綜合公允價值}].md | ✅ 完成 |
   ```
   > 範例：`[[TA技術分析/NVDA [$950]\|NVDA]]`

### 輸出變數

| 變數 | 說明 |
|------|------|
| `綜合公允價值` | 由估值技能計算得出的綜合目標價 |

---

## Workflow B — 公司業務, 護城河, 週期, 競爭格局

> 觸發關鍵字：`基本面` | `護城河` | `fundamental`
>
> 使用技能：[[01-(SKILLs) 技能/skill_invest/invest-fundamental-analysis]]

### 檔名規範

| 階段  | 格式                                                | 範例                                          |
| --- | ------------------------------------------------- | ------------------------------------------- |
| 更新前 | `{stock ticker} [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` | `00700.HK [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` |
| 更新後 | `{ticker} [${綜合公允價值}, {護城河強度（Y）}, {週期暴露度（X）}].md` | `00700.HK [$556.14, 4.0, 2.0].md`           |

### 執行步驟

1. **識別 Ticker** — 從檔名解析 `{stock ticker}`
2. **執行技能** — 載入 `invest-fundamental-analysis.md`，以 `{stock ticker}` 作為搜尋輸入
3. **更新內文** — 將技能輸出寫入筆記，涵蓋以下面向：
   - 商業模式與收入結構
   - 護城河分析 → `護城河強度（Y）`
   - 週期敏感度分析 → `週期暴露度（X）`
   - 競爭格局與產業地位
4. **重新命名** — 依照更新後格式重新命名檔案
   - 範例：`00700.HK [$556.14, 4.0, 2.0].md`
5. **📋 記錄日誌** — 於 `log_finance.md` 新增一筆記錄，格式如下：
   ```
   | YYYY-MM-DD HH:MM | B | [[公司業務, 護城河, 週期, 競爭格局/{ticker} [${v}, {Y}, {X}]\|{ticker}]] | 執行基本面分析，護城河強度={Y}，週期暴露度={X}，重新命名 | ✅ 完成 |
   ```
   > 範例：`[[公司業務, 護城河, 週期, 競爭格局/00700.HK [$556.14, 4.0, 2.0]\|00700.HK]]`

### 輸出變數

| 變數         | 說明          | 量尺  | 用途       |
| ---------- | ----------- | --- | -------- |
| `綜合公允價值`   | 基本面推算的綜合目標價 | 價格  | 估值錨點     |
| `護城河強度（Y）` | 護城河評分       | 1–5 | 組合地圖 Y 軸 |
| `週期暴露度（X）` | 週期敏感度評分     | 1–5 | 組合地圖 X 軸 |

---

## Workflow C — 企業概要

> 觸發關鍵字：`概要` | `企業` | `overview`
>
> 使用技能：
> - [[01-(SKILLs) 技能/skill_invest/search_company (background)/invest-moat-margin-v2]]
> - [[01-(SKILLs) 技能/skill_invest/search_company (background)/dive-deep-bottlenecks]]


### 檔名格式與 Ticker 解析規則

`企業概要/` 資料夾內檔名混用英文、中文及括號格式，統一解析規則如下：

| 檔名格式 | 範例 | 解析 Ticker |
|---------|------|---------------|
| `{ticker}.md` | `ASML.md` | `ASML` |
| `{ticker} ({company name}).md` | `Applied Materials (AMAT).md` | `AMAT` |
| `{ticker} ({company name}).md` | `GOOGL (Alphabet Inc.).md` | `GOOGL` |
| `{company name}（{ticker}）.md` | `微軟（MSFT）.md` | `MSFT` |
| `{company name}（{ticker}）.md` | `Amazon（AMZN）.md` | `AMZN` |
| `{company name} ({ticker}).md` | `特斯担 (TSLA).md` | `TSLA` |
| `{company name}（{ticker}）.md` | `Rocket Lab Corporation（RKLB）.md` | `RKLB` |
| `{company name}（{ticker}）.md` | `阿里巴巴（BABA）.md` | `BABA` |
| `{company name}（{ticker}）.md` | `Micron Technology (MU).md` | `MU` |
| `概要_{company name}.md` | `概要_群核科技.md` | 無明確 Ticker → 搜尋公司名稱外部資料 |

**Ticker 解析優先順序：**

```
1. 從檔名中第一個 () 或 （） 內讀取全大寫英文字母數字字串 → ticker
   範例：「微軟（MSFT）」 → MSFT
2. 若檔名並無括號，則將檔名去除 .md 後視為 ticker
   範例：「ASML.md」 → ASML
3. 若格式為 概要_{company name}，則以 {company name} 搜尋取得對應股票代碼
```

### 檔名規範

| 階段 | 格式 | 說明 |
|------|------|------|
| 更新前 | `{ticker}{company name}.md`（原始檔名，不更改） | 保留原檔名，更新內文 |
| 更新後 | `{ticker}{company name}.md`（同名） | 加入兩個技能輸出區塊 |

> ⚠️ **Workflow C 不重新命名檔案**，僅更新內文。

### 執行步驟

1. **識別 Ticker** — 依照上方解析規則從檔名取得 `{stock ticker}`
   - 範例：`微軟（MSFT）.md` → ticker = `MSFT`
   - 範例：`GOOGL (Alphabet Inc.).md` → ticker = `GOOGL`
2. **同步執行兩個技能** — 同時對同一 ticker 執行：
   - 載入 `invest-moat-margin-v2.md`，以 `{stock ticker}` 作為輸入
   - 載入 `dive-deep-bottlenecks.md`，以 `{stock ticker}` 作為輸入
3. **合並內文** — 將兩個技能輸出寫入同一檔案，依序排列：
   ```
   # {ticker} {company name}

   ## Part A — 護城河 & 毛利率分析          ← invest-moat-margin-v2 輸出
   ...

   ---

   ## Part B — 瓶頸深挖分析                  ← dive-deep-bottlenecks 輸出
   ...
   ```
4. **更新 YAML Frontmatter** — 在檔案頂部更新 `updated` 日期欄位
5. **保存檔案** — 覆寫原檔，檔名不變
6. **📋 記錄日誌** — 於 `log_finance.md` 新增一筆記錄，格式如下：
   ```
   | YYYY-MM-DD HH:MM | C | [[企業概要/{filename without .md}\|{ticker}]] | 執行企業概要分析（moat-margin-v2 + dive-deep-bottlenecks），更新內文 | ✅ 完成 |
   ```
   > 範例：`[[企業概要/Rocket Lab Corporation（RKLB）\|RKLB]]`

### 輸出內容說明

| 區塊 | 來源技能 | 內容概要 |
|------|---------|--------|
| **Part A** | `invest-moat-margin-v2` | 護城河類型評分、毛利率分析、定價權評估、NRR/Churn 等 |
| **Part B** | `dive-deep-bottlenecks` | 企業關鍵瓶頸識別、成長限制因素、結構性風險深挖分析 |

---

## Workflow D — HK-IPO

> 觸發關鍵字：`HK-IPO` | `IPO`
>
> 使用技能：[[01-(SKILLs) 技能/skill_invest/invest-IPO]]

### 檔名規範

| 規則        | 格式                  | 範例                     |
| --------- | ------------------- | ---------------------- |
| 以執行當日日期命名 | `ipo_yyyy-mm-dd.md` | `ipo_2026-05-01.md`    |
| 當日檔案已存在   | 直接更新同名檔案（不新建）       | 覆寫 `ipo_2026-05-01.md` |

### 執行步驟

1. **取得當日日期** — 以 `yyyy-mm-dd` 格式作為目標檔名
2. **檢查檔案是否存在** — 確認 `03-(FINANCE) 財務筆記/HK-IPO/ipo_yyyy-mm-dd.md` 是否已存在
   - **存在** → 直接更新該檔案內文
   - **不存在** → 依模板新建該檔案
3. **執行技能** — 載入 `invest-IPO.md`，依技能結構填寫 IPO 分析內容
4. **寫入筆記** — 將分析輸出寫入 `03-(FINANCE) 財務筆記/HK-IPO/ipo_yyyy-mm-dd.md`
5. **更新 YAML Frontmatter** — 更新 `updated` 日期欄位
6. **📋 記錄日誌** — 於 `log_finance.md` 新增一筆記錄，格式如下：
   ```
   | YYYY-MM-DD HH:MM | D | [[HK-IPO/ipo_{yyyy-mm-dd}\|{yyyy-mm-dd}]] | 執行 HK-IPO 分析，新建/更新當日 IPO 筆記 | ✅ 完成 |
   ```
   > 範例：`[[HK-IPO/ipo_2026-05-01\|2026-05-01]]`

### 輸出路徑

```
03-(FINANCE) 財務筆記/
└── HK-IPO/
    └── ipo_{yyyy-mm-dd}.md    ← 例：ipo_2026-05-01.md
```

### 觸發範例

> 輸入：`HK-IPO` 或 `IPO`
> → 自動定位今日日期 → 檢查/新建 `HK-IPO/ipo_{yyyy-mm-dd}.md` → 執行 `invest-IPO.md` 技能

---

## Workflow E — 產業（業務部門拆分）

> 觸發關鍵字：`產業` | `業務部門` | `cost-return`
>
> 使用技能：[[01-(SKILLs) 技能/skill_invest/search_company (know-how)/invest-cost-return]]

### 核心邏輯

執行 `invest-cost-return` 後，從分析結果中識別 `{ticker}` 的所有 `{業務部門}`，並為**每個業務部門**獨立建立一個筆記檔案，實現業務部門層級的細粒度產業分析。

### 檔名規範

| 規則             | 格式                        | 範例                          |
| -------------- | ------------------------- | --------------------------- |
| 每個業務部門獨立一個檔案   | `{ticker}_{業務部門}.md`      | `NVDA_資料中心.md`              |
| 同一 ticker 多部門  | 每個部門分別建立獨立檔案              | `NVDA_資料中心.md`、`NVDA_遊戲.md` |
| 已存在時           | 直接更新同名檔案（不新建）             | 覆寫 `NVDA_資料中心.md`           |

### 執行步驟

1. **識別 Ticker** — 從用戶輸入或上下文中取得 `{ticker}`
2. **執行技能** — 載入 `invest-cost-return.md`，以 `{ticker}` 作為搜尋輸入，進行完整的成本結構與投資回報分析
3. **識別業務部門清單** — 從 `invest-cost-return` 輸出結果中提取所有 `{業務部門}`
   - 範例（NVDA）：`資料中心`、`遊戲`、`專業視覺化`、`汽車`、`OEM & 其他`
   - 範例（AAPL）：`iPhone`、`Mac`、`iPad`、`穿戴裝置`、`服務`
4. **分拆建立檔案** — 針對每個 `{業務部門}` 獨立建立或更新筆記：
   - 路徑：`03-(FINANCE) 財務筆記/產業/{ticker}_{業務部門}.md`
   - 每個檔案包含該部門專屬的成本結構、投資回報、成長驅動分析
5. **每個檔案的內容結構**：
   ```markdown
   ---
   ticker: {ticker}
   業務部門: {業務部門}
   tags: [產業, {ticker}, {業務部門}]
   created: {date}
   updated: {date}
   skill: invest-cost-return
   ---

   # {ticker} — {業務部門}

   ## 業務部門概覽
   > 描述此部門的主要業務範疇、產品/服務、目標市場

   ## 收入與成本結構
   - **收入貢獻（Revenue %）**：
   - **毛利率**：
   - **主要成本驅動因素**：

   ## 投資回報分析（invest-cost-return）
   - **投入資本（Invested Capital）**：
   - **ROIC / 部門資本回報率**：
   - **FCF 貢獻**：

   ## 成長驅動因素
   ## 競爭格局與定價權
   ## 風險因素
   ## 估值參考與可比公司
   ```
6. **更新 YAML Frontmatter** — 每個分拆檔案均更新 `updated` 日期欄位
7. **📋 記錄日誌** — 於 `log_finance.md` 為**每個業務部門檔案**各新增一筆記錄，格式如下：
   ```
   | YYYY-MM-DD HH:MM | E | [[產業/{ticker}_{業務部門}\|{ticker}_{業務部門}]] | 執行產業分析（invest-cost-return），拆分業務部門：{業務部門} | ✅ 完成 |
   ```
   > 範例：`[[產業/NVDA_資料中心\|NVDA_資料中心]]`

### 輸出路徑

```
03-(FINANCE) 財務筆記/
└── 產業/
    ├── {ticker}_{業務部門1}.md    ← 例：NVDA_資料中心.md
    ├── {ticker}_{業務部門2}.md    ← 例：NVDA_遊戲.md
    ├── {ticker}_{業務部門3}.md    ← 例：NVDA_專業視覺化.md
    └── ...（依實際業務部門數量）
```

### 觸發範例

> 輸入：`產業 NVDA` 或 `NVDA 業務部門分析`
> → 執行 `invest-cost-return.md` → 識別業務部門清單
> → 分別建立 `產業/NVDA_資料中心.md`、`產業/NVDA_遊戲.md`、`產業/NVDA_專業視覺化.md` ...
> → 於 `log_finance.md` 記錄每個部門的建立事件

---

## 通用更新流程

```
開啟目標檔案
     ↓
從檔名解析 {stock ticker} 或取得當日日期（Workflow D）或識別 ticker（Workflow E）
     ↓
執行對應技能（以 ticker、日期或產業名稱為輸入）
     ↓
將技能輸出寫入筆記內文
     ↓
依更新後格式重新命名檔案（Workflow A & B）
或 覆寫原檔內文（Workflow C）
或 新建/更新當日 HK-IPO 筆記（Workflow D）
或 依業務部門拆分建立多個產業筆記（Workflow E）
     ↓
📋 於 log_finance.md 新增行動事件記錄
     ↓
確認檔名 / 內容已反映最新數值
```

### 建議重新執行時機

- 季報發布後
- 股價出現 >15% 重大異動
- 板塊重新定價或宏觀環境轉變
- 手動複查需求
- 新 HK-IPO 招股或上市當日（Workflow D）
- 產業結構、業務部門拆分或競爭格局重大變化（Workflow E）

---

## 行動事件日誌

> 每次執行 Workflow 後，請將事件同步記錄至 [[log_finance]] 以保持執行軌跡。

| 欄位 | 說明 |
|------|------|
| **日期時間 (HKT)** | 格式：`YYYY-MM-DD HH:MM` |
| **Workflow** | `A` / `B` / `C` / `D` / `E` |
| **Ticker / 目標** | 以 `[[path/filename\|display]]` wikilink 連結至對應筆記，顯示文字為簡潔的 ticker 或日期 |
| **執行動作說明** | 簡述執行了什麼技能及產出 |
| **結果 / 備註** | `✅ 完成` / `⚠️ 部分完成` / `❌ 失敗` + 原因 |

### Ticker / 目標 欄 wikilink 格式對照表

| Workflow | wikilink 格式 | 範例 |
|----------|------------|------|
| A | `[[TA技術分析/{ticker} [${value}]\|{ticker}]]` | `[[TA技術分析/NVDA [$950]\|NVDA]]` |
| B | `[[公司業務, 護城河, 週期, 競爭格局/{ticker} [${v}, {Y}, {X}]\|{ticker}]]` | `[[公司業務, 護城河, 週期, 競爭格局/00700.HK [$556.14, 4.0, 2.0]\|00700.HK]]` |
| C | `[[企業概要/{filename without .md}\|{ticker}]]` | `[[企業概要/Rocket Lab Corporation（RKLB）\|RKLB]]` |
| D | `[[HK-IPO/ipo_{yyyy-mm-dd}\|{yyyy-mm-dd}]]` | `[[HK-IPO/ipo_2026-05-01\|2026-05-01]]` |
| E | `[[產業/{ticker}_{業務部門}\|{ticker}_{業務部門}]]` | `[[產業/NVDA_資料中心\|NVDA_資料中心]]` |

> 📂 完整日誌檔案：[[03-(FINANCE) 財務筆記/log_finance]]

---

## ⚠️ log_finance.md 不可變更規則

> 🔒 **此規則適用於所有 Workflow（A / B / C / D / E）及任何手動操作，無例外。**

- **嚴禁刪除** `log_finance.md` 中任何已存在的記錄行，包括歷史紀錄、初始化條目及任何 Workflow 所寫入的事件
- **只可新增**（Append-only）：每次執行 Workflow 後，僅於表格末尾追加新的一行記錄，絕不修改或移除既有行
- 若發現 `log_finance.md` 內容遭刪減，應視為**操作錯誤**，須立即還原被刪除的記錄
- 此檔案是整個財務筆記系統的**不可竄改執行軌跡（Immutable Audit Trail）**，其完整性高於一切

---

## 連結技能（skill_invest）

- [[01-(SKILLs) 技能/skill_invest/evaluate_company/invest-stock-valuation]]
- [[01-(SKILLs) 技能/skill_invest/invest-fundamental-analysis]]
- [[01-(SKILLs) 技能/skill_invest/search_company (background)/invest-moat-margin-v2]]
- [[01-(SKILLs) 技能/skill_invest/dive-deep-bottlenecks]]
- [[01-(SKILLs) 技能/skill_invest/search_company (know-how)/invest-cost-return]]
- [[01-(SKILLs) 技能/skill_invest/invest-competitive-adv]]
- [[01-(SKILLs) 技能/skill_invest/invest-production-factors-v1.2.0]]
- [[01-(SKILLs) 技能/skill_invest/invest-IPO]]
