---
tags: [schema, finance, workflow]
folder: 03-(FINANCE) 財務筆記
created: 2026-04-30
updated: 2026-04-30
skills: [invest-stock-valuation, invest-fundamental-analysis, invest-moat-margin-v2, invest-cost-return]
---

# 03-(FINANCE) 財務筆記 — Schema

## 資料夾結構

```
03-(FINANCE) 財務筆記/
├── schema_finance.md                                                 ← 本文件
├── TA技術分析/
│   └── {ticker} [${\u7d9c合公允價值}].md
├── 公司業務, 護城河, 週期, 競爭格局/
│   └── {ticker} [${\u7d9c合公允價值}, {\u8b77城河強度（Y）}, {\u9031期暴露度（X）}].md
└── 企業概要/
    └── {ticker}{company name}.md     ← 檔名格式不一，見下方解析規則
```

---

## Skill 對應表

| 資料夾 | 使用技能 | 技能路徑 |
|--------|---------|---------|
| `TA技術分析/` | `invest-stock-valuation.md` | `01-(SKILLs) 技能/skill_invest/evaluate_company/` |
| `公司業務, 護城河, 週期, 競爭格局/` | `invest-fundamental-analysis.md` | `01-(SKILLs) 技能/skill_invest/` |
| `企業概要/` | `invest-moat-margin-v2.md` + `invest-cost-return.md` | `01-(SKILLs) 技能/` |

---

## Workflow A — TA技術分析

> 使用技能：[[01-(SKILLs) 技能/skill_invest/evaluate_company/invest-stock-valuation]]

### 檔名規範

| 階段 | 格式 | 範例 |
|------|------|------|
| 更新前 | `{stock ticker} [綜合公允價值].md` | `NVDA [綜合公允價值].md` |
| 更新後 | `{ticker} [${\u7d9c合公允價值}].md` | `NVDA [$950].md` |

### 執行步驟

1. **識別 Ticker** — 從檔名解析 `{stock ticker}`
   - 範例：`AAPL [綜合公允價值].md` → ticker = `AAPL`
2. **執行技能** — 載入 `invest-stock-valuation.md`，以 `{stock ticker}` 作為搜尋輸入
3. **更新内文** — 將技能輸出（估值分析、目標價、技術面）寫入筆記內文
4. **重新命名** — 依照更新後格式重新命名檔案
   - 範例：`GOOGL [$370].md`

### 輸出變數

| 變數 | 說明 |
|------|------|
| `綜合公允價值` | 由估值技能計算得出的綜合目標價 |

---

## Workflow B — 公司業務, 護城河, 週期, 競爭格局

> 使用技能：[[01-(SKILLs) 技能/skill_invest/invest-fundamental-analysis]]

### 檔名規範

| 階段  | 格式                                                | 範例                                          |
| --- | ------------------------------------------------- | ------------------------------------------- |
| 更新前 | `{stock ticker} [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` | `00700.HK [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` |
| 更新後 | `{ticker} [${\u7d9c合公允價值}, {\u8b77城河強度（Y）}, {\u9031期暴露度（X）}].md` | `00700.HK [$556.14, 4.0, 2.0].md`           |

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

### 輸出變數

| 變數 | 說明 | 量尺 | 用途 |
|------|------|------|------|
| `綜合公允價值` | 基本面推算的綜合目標價 | 價格 | 估值錨點 |
| `護城河強度（Y）` | 護城河評分 | 1–10 | 組合地圖 Y 軸 |
| `週期暴露度（X）` | 週期敏感度評分 | 1–10 | 組合地圖 X 軸 |

---

## Workflow C — 企業概要

> 使用技能：
> - [[01-(SKILLs) 技能/invest-moat-margin-v2]]
> - [[01-(SKILLs) 技能/invest-cost-return]]

### 檔名格式與 Ticker 解析規則

`企業概要/` 資料夾內檔名混用英文、中文及括號格式，統一解析規則如下：

| 檔名格式 | 範例 | 解析 Ticker |
|---------|------|---------------|
| `{ticker}.md` | `ASML.md` | `ASML` |
| `{ticker} ({company name}).md` | `Applied Materials (AMAT).md` | `AMAT` |
| `{ticker} ({company name}).md` | `GOOGL (Alphabet Inc.).md` | `GOOGL` |
| `{company name}（{ticker}）.md` | `微軟（MSFT）.md` | `MSFT` |
| `{company name}（{ticker}）.md` | `Amazon（AMZN）.md` | `AMZN` |
| `{company name} ({ticker}).md` | `特斯拉 (TSLA).md` | `TSLA` |
| `{company name}（{ticker}）.md` | `Rocket Lab Corporation（RKLB）.md` | `RKLB` |
| `{company name}（{ticker}）.md` | `阿里巴巴（BABA）.md` | `BABA` |
| `{company name}（{ticker}）.md` | `Micron Technology (MU).md` | `MU` |
| `概要_{company name}.md` | `概要_群核科技.md` | 無明穒 Ticker → 搜尋公司名稱外部資料 |

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
   - 載入 `invest-cost-return.md`，以 `{stock ticker}` 作為輸入
3. **合並內文** — 將兩個技能輸出寫入同一檔案，依序排列：
   ```
   # {ticker} {company name}

   ## Part A — 護城河 & 毛利率分析          ← invest-moat-margin-v2 輸出
   ...

   ---

   ## Part B — 成本結構 & 投資回報分析    ← invest-cost-return 輸出
   ...
   ```
4. **更新 YAML Frontmatter** — 在檔案頂部更新 `updated` 日期欄位
5. **保存檔案** — 覆寫原檔，檔名不變

### 輸出內容誤明

| 區塊 | 來源技能 | 內容概要 |
|------|---------|--------|
| **Part A** | `invest-moat-margin-v2` | 護城河類型評分、毛利率分析、定價權評估、NRR/Churn 等 |
| **Part B** | `invest-cost-return` | 成本結構拆解、ROIC/ROE、資本配置效率、開支平衡點分析 |

---

## 通用更新流程

```
開啟目標檔案
     ↓
從檔名解析 {stock ticker}
     ↓
執行對應技能（以 ticker 為搜尋輸入）
     ↓
將技能輸出寫入筆記內文
     ↓
依更新後格式重新命名檔案（Workflow A & B）
或 覆寫原檔內文（Workflow C）
     ↓
確認檔名 / 內容已反映最新數值
```

### 建議重新執行時機

- 季報發布後
- 股價出現 >15% 重大異動
- 板塊重新定價或宏觀環境轉變
- 手動複查需求

---

## 連結技能（skill_invest）

- [[01-(SKILLs) 技能/skill_invest/evaluate_company/invest-stock-valuation]]
- [[01-(SKILLs) 技能/skill_invest/invest-fundamental-analysis]]
- [[01-(SKILLs) 技能/invest-moat-margin-v2]]
- [[01-(SKILLs) 技能/invest-cost-return]]
- [[01-(SKILLs) 技能/skill_invest/invest-competitive-adv]]
- [[01-(SKILLs) 技能/skill_invest/invest-production-factors-v1.2.0]]
- [[01-(SKILLs) 技能/skill_invest/dive-deep-bottlenecks]]
