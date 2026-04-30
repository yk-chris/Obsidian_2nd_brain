---
tags: [schema, finance, workflow]
folder: 03-(FINANCE) 財務筆記
created: 2026-04-30
skills: [invest-stock-valuation, invest-fundamental-analysis]
---

# 03-(FINANCE) 財務筆記 — Schema

## 資料夾結構

```
03-(FINANCE) 財務筆記/
├── schema.md                                         ← 本文件
├── TA技術分析/
│   └── {ticker} [${綜合公允價值}].md
└── 公司業務, 護城河, 週期, 競爭格局/
    └── {ticker} [${綜合公允價值}, {護城河強度（Y）}, {週期暴露度（X）}].md
```

---

## Skill 對應表

| 資料夾 | 使用技能 | 技能路徑 |
|--------|---------|---------|
| `TA技術分析/` | `invest-stock-valuation.md` | `01-(SKILLs) 技能/skill_invest/` |
| `公司業務, 護城河, 週期, 競爭格局/` | `invest-fundamental-analysis.md` | `01-(SKILLs) 技能/skill_invest/` |

---

## Workflow A — TA技術分析

> 使用技能：[[01-(SKILLs) 技能/skill_invest/invest-stock-valuation]]

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
   - 範例：`AAPL [$210].md`

### 輸出變數

| 變數 | 說明 |
|------|------|
| `綜合公允價值` | 由估值技能計算得出的綜合目標價 |

---

## Workflow B — 公司業務, 護城河, 週期, 競爭格局

> 使用技能：[[../01-(SKILLs) 技能/skill_invest/invest-fundamental-analysis]]

### 檔名規範

| 階段 | 格式 | 範例 |
|------|------|------|
| 更新前 | `{stock ticker} [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` | `2330.TW [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` |
| 更新後 | `{ticker} [${綜合公允價值}, {護城河強度（Y）}, {週期暴露度（X）}].md` | `2330.TW [$1050, 8.5, 7.2].md` |

### 執行步驟

1. **識別 Ticker** — 從檔名解析 `{stock ticker}`
   - 範例：`2330.TW [$綜合公允價值, 護城河強度（Y）, 週期暴露度（X）].md` → ticker = `2330.TW`
2. **執行技能** — 載入 `invest-fundamental-analysis.md`，以 `{stock ticker}` 作為搜尋輸入
3. **更新內文** — 將技能輸出寫入筆記，涵蓋以下面向：
   - 商業模式與收入結構
   - 護城河分析 → `護城河強度（Y）`
   - 週期敏感度分析 → `週期暴露度（X）`
   - 競爭格局與產業地位
4. **重新命名** — 依照更新後格式重新命名檔案
   - 範例：`2330.TW [$1050, 8.5, 7.2].md`

### 輸出變數

| 變數 | 說明 | 量尺 | 用途 |
|------|------|------|------|
| `綜合公允價值` | 基本面推算的綜合目標價 | 價格 | 估值錨點 |
| `護城河強度（Y）` | 護城河評分 | 1–10 | 組合地圖 Y 軸 |
| `週期暴露度（X）` | 週期敏感度評分 | 1–10 | 組合地圖 X 軸 |

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
依更新後格式重新命名檔案
     ↓
確認檔名已反映最新數值
```

### 建議重新執行時機

- 季報發布後
- 股價出現 >15% 重大異動
- 板塊重新定價或宏觀環境轉變
- 手動複查需求

---

## 連結技能（skill_invest）

- [[01-(SKILLs) 技能/skill_invest/invest-stock-valuation]]
- [[../01-(SKILLs) 技能/skill_invest/invest-fundamental-analysis]]
- [[01-(SKILLs) 技能/skill_invest/invest-moat-margin-v2]]
- [[01-(SKILLs) 技能/skill_invest/invest-competitive-adv]]
- [[01-(SKILLs) 技能/skill_invest/invest-production-factors-v1.2.0]]
- [[01-(SKILLs) 技能/skill_invest/dive-deep-bottlenecks]]