# CLAUDE.md

## Repository Overview
This is an Obsidian second brain vault. The folder structure follows a numbered knowledge system:

| 資料夾 | 性質 | 說明 |
|--------|------|------|
| `Clippings/` | **RAW** | 網頁剪藏，未經處理的原始來源文章 |
| `02-(LEARN) 學習筆記/` | **RAW** | 學習原始筆記，輸入素材 |
| `03-(FINANCE) 財務筆記/` | **RAW** | 財務研究原始資料與研報 |
| `04-(WORK) 工作/` | **RAW** | 工作相關原始記錄 |
| `00-(IDEAVERSE) 思維系統/` | PROCESSED | 概念連結與思維框架，可讀取參考 |
| `01-(SKILLs) 技能/` | PROCESSED | 技能知識庫，可讀取參考 |
| `TaskNotes/` | PROCESSED | 任務筆記，可讀取參考 |
| `Excalidraw/` | ASSET | 視覺化圖表資產，不處理 |
| `wiki/` | **LLM OWNED** | 你完全擁有，LLM 生成的 wiki 輸出 |

## Raw Source Rules
- **RAW 資料夾內的任何檔案，絕對不可修改、刪除或重新命名**
- 只能讀取，不能寫入
- `Clippings/` 優先作為 ingest 主要來源
- `03-(FINANCE) 財務筆記/` 含高價值研究素材，ingest 時需特別標記來源與日期

---

## Wiki Structure (LLM Owned)
- `wiki/` — LLM 生成的 wiki，你完全擁有
- `wiki/sources/` — 各來源的摘要頁（每次 ingest 新建）
- `wiki/concepts/` — 跨來源的概念整合頁
- `wiki/index.md` — 每次 ingest 後更新的目錄
- `wiki/log.md` — 只可追加的行動紀錄

---

## index.md 格式

第一行固定為標題與更新時間戳，其後為 Markdown 表格：

```md
# Wiki Index
_最後更新：YYYY-MM-DD HH:MM_

| 來源檔案 | 摘要頁 | 相關概念頁 | 建立日期 | 標籤 |
|----------|--------|------------|----------|------|
| Clippings/example.md | [example](sources/example.md) | [概念A](concepts/a.md) | 2026-05-01 | #AI #投資 |
```

規則：
- 每次 ingest 追加一列，不可刪除既有列
- 標籤以 `#tag` 格式填入，多個以空格分隔
- 若無相關概念頁，填 `—`

---

## log.md 格式

嚴格 append-only。每筆記錄結構如下：

```md
## 2026-05-01 14:32 — INGEST Clippings/example.md
- **摘要頁**：wiki/sources/example.md（新建）
- **更新頁**：wiki/index.md、wiki/concepts/a.md
- **備註**：首次處理，識別 3 個關鍵概念
```

規則：
- 標題格式固定：`## YYYY-MM-DD HH:MM — [動作] [對象]`
- 動作關鍵字：`INGEST` / `UPDATE` / `CREATE` / `DELETE`
- 絕對禁止修改或刪除已有記錄
- 備註欄可省略，其餘欄位必填

---

## Ingest Workflow
當我說「ingest [檔名]」：
1. 先查詢 `wiki/index.md`，確認此來源是否已存在、既有摘要頁路徑、相關概念頁與可延續更新內容
2. 從對應的 RAW 資料夾讀取原始檔（優先順序：`Clippings/` > `03-(FINANCE) 財務筆記/` > `02-(LEARN) 學習筆記/` > `04-(WORK) 工作/`）
3. 與我討論重點，並比對 `wiki/index.md` 中既有內容，判斷是建立新頁還是更新既有 `wiki/` 頁面
4. 在 `wiki/sources/` 建立或更新對應摘要頁
5. 更新 `wiki/index.md`（若為新來源則追加表格列；若為既有來源則更新對應列資訊）及相關 `wiki/concepts/` 頁面
6. 在 `wiki/log.md` 追加符合上述格式的記錄，並註明本次為新建或更新既有內容

## Update Decision Rules
- 若 `wiki/index.md` 已存在相同來源檔案，優先更新既有 `wiki/sources/` 頁面，而不是重建新頁
- 若 `wiki/index.md` 已記錄相關概念頁，應優先更新既有概念頁，保持知識累積
- 若來源內容屬同主題但檔名不同，可建立新摘要頁，並連結到既有概念頁
- ingest 前必須把 `wiki/index.md` 視為 wiki 現況的唯一目錄依據
