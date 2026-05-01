
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
- **RAW 資料夾內的任何檔案，絕對不可修改內容、刪除或重新命名**
- 只能讀取，不能寫入
- **唯一例外**：完成 ingest 後，對原始 Markdown 檔加上 `#wiki` tag（規則見下方 Tagging Rules）
- `Clippings/` 優先作為 ingest 主要來源
- `03-(FINANCE) 財務筆記/` 含高價值研究素材，ingest 時需特別標記來源與日期

## Folder Schema Rules
- 每當進入一個主資料夾或其子資料夾處理文件前，先檢查該層是否存在 `schema_xxx.md` 類型文件
- `schema_xxx.md` 指檔名符合 `schema_*.md` 的 Markdown 文件
- 若存在一個或多個 `schema_*.md`，必須先讀取並遵守其中規範，再處理該資料夾內文件
- schema 規範優先於一般預設流程；若 schema 與通用規則衝突，以 schema 為準，但不得違反「RAW 只能讀取不可修改」原則（`#wiki` tagging 例外除外）
- 若同一層存在多個 schema，優先採用最貼近當前任務的 schema；若仍有衝突，先向使用者確認
- 進行 ingest 時，需把 schema 檢查視為每次進入資料夾的必要步驟，而不是可選步驟

## Tagging Rules
完成 ingest 後對原始 Markdown 來源檔加上 `#wiki` tag，遵守以下規則：

- **文件已有 frontmatter（`---` 區塊）**：在 `tags:` 欄追加 `wiki`
  ```yaml
  ---
  tags: [existing-tag, wiki]
  ---
  ```
- **文件無 frontmatter**：在文件最後一行追加，不得插入文中
  ```md
  （原有內容不動）

  #wiki
  ```
- **禁止**：修改檔案任何其他內容、標題、正文
- **禄測**：若檔案已含 `#wiki` tag，跳過此步驟，不得重複加入

---

## Wiki Structure (LLM Owned)
- `wiki/` — LLM 生成的 wiki，你完全擁有
- `wiki/sources/` — 各來源的摘要頁（每次 ingest 新建）
- `wiki/concepts/` — 跨來源的概念整合頁
- `wiki/synthesis/` — 跨來源合成分析頁（由 Query workflow 生成）
- `wiki/lint-reports/` — Lint 健康報告頁
- `wiki/index_wiki.md` — 每次 ingest 後更新的目錄
- `wiki/log_wiki.md` — 只可追加的行動紀錄

---

## index_wiki.md 格式

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

## log_wiki.md 格式

嚴格 append-only。每筆記錄結構如下：

```md
## 2026-05-01 14:32 — INGEST Clippings/example.md
- **摘要頁**：wiki/sources/example.md（新建）
- **更新頁**：wiki/index_wiki.md、wiki/concepts/a.md
- **備註**：首次處理，識別 3 個關鍵概念
```

規則：
- 標題格式固定：`## YYYY-MM-DD HH:MM — [動作] [對象]`
- 動作關鍵字：`INGEST` / `UPDATE` / `CREATE` / `DELETE` / `SYNTHESIS` / `LINT`
- 絕對禁止修改或刪除已有記錄
- 備註欄可省略，其餘欄位必填

---

## Ingest Workflow
當我說「ingest [檔名]」：
1. 先查詢 `wiki/index_wiki.md`，確認此來源是否已存在、既有摘要頁路徑、相關概念頁與可延續更新內容
2. 從對應的 RAW 資料夾讀取原始檔前，先檢查即將進入的主資料夾或子資料夾是否存在 `schema_*.md`，若存在必須先讀取並遵守
3. 從對應的 RAW 資料夾讀取原始檔（優先順序：`Clippings/` > `03-(FINANCE) 財務筆記/` > `02-(LEARN) 學習筆記/` > `04-(WORK) 工作/`）
4. 檢查原始檔是否已含 `#wiki` tag，若已存在則變更 workflow 為 update 模式
5. 與我討論重點，並比對 `wiki/index_wiki.md` 中既有內容，判斷是建立新頁還是更新既有 `wiki/` 頁面
6. 在 `wiki/sources/` 建立或更新對應摘要頁
7. 更新 `wiki/index_wiki.md`（若為新來源則追加表格列；若為既有來源則更新對應列資訊）及相關 `wiki/concepts/` 頁面
8. 依照 Tagging Rules 對原始檔加上 `#wiki` tag
9. 在 `wiki/log_wiki.md` 追加符合上述格式的記錄，並註明本次為新建或更新既有內容

## Update Decision Rules
- 若 `wiki/index_wiki.md` 已存在相同來源檔案，優先更新既有 `wiki/sources/` 頁面，而不是重建新頁
- 若 `wiki/index_wiki.md` 已記錄相關概念頁，應優先更新既有概念頁，保持知識累積
- 若來源內容屬同主題但檔名不同，可建立新摘要頁，並連結到既有概念頁
- ingest 前必須把 `wiki/index_wiki.md` 視為 wiki 現況的唯一目錄依據
- 處理任何資料夾內容前，必須先完成該資料夾層級的 schema 檢查
- 原始檔有 `#wiki` tag 主動識別為 update 模式，對已 ingest 檔案不重複加 tag

---

## Query Workflow
當我提出一個問題（例如：關聯到研究、書本、個人目標等），LLM 應：

1. **索引查詢**：先讀取 `wiki/index_wiki.md`，根據問題找出相關頁面（sources、concepts、synthesis）。
2. **內容閱讀與整理**：讀取相關頁面，並：
   - 摘要內容、整理論點。
   - 明確標示引用來源（例如 `[[source-2026-04-01-論文名稱.md]]`）。
3. **回覆格式**：以 Markdown 格式回覆，根據問題類型選擇：
   - 一般問題：段落、清單、表格。
   - 比較問題：加入比較表。
   - 演講或簡報需求：用 Marp syntax 生成 Markdown slides。
4. **持久化判斷**：若這個分析是「有價值的新洞察」（例如：比較表、圖表解析、跨來源的合成），應：
   - 在 `wiki/synthesis/` 下建立新頁面（命名規則：`synthesis-[主題]-YYYY-MM-DD.md`，例如 `synthesis-公司比較-2026-05-01.md`）。
   - 在 `wiki/index_wiki.md` 添加對應條目（標籤欄標記 `#synthesis`）。
   - 在 `wiki/log_wiki.md` 追加一條 `[SYNTHESIS]` 記錄，格式如下：
     ```md
     ## 2026-05-01 14:32 — SYNTHESIS wiki/synthesis/synthesis-公司比較-2026-05-01.md
     - **來源頁面**：wiki/sources/A.md、wiki/concepts/B.md
     - **問題**：使用者詢問 X 與 Y 之比較
     - **備註**：生成比較表，識別 3 個關鍵差異
     ```

持久化觸發條件（符合任一即應建立 synthesis 頁）：
- 回覆包含跨頁面的合成比較表
- 回覆整合了 3 個或以上不同來源
- 回覆中產生了原始頁面中不存在的新洞察或框架
- 使用者明確要求「儲存」或「記錄」這份分析

---

## Lint Workflow
當我說「請對 wiki 做一次 lint 檢查」，LLM 應執行健康掃瞄並輸出報告，**不自動修改任何內容**，除非我明確授權。

### 檢查項目

1. **矛盾檢查**：不同頁面之間，同一主張或數字是否衝突（例如同一公司 revenue 有兩個版本且未說明差異）。
2. **過時內容**：某頁面太久未更新，但同主題已有新來源，標示為「可能過時」。
3. **孤立頁面（Orphan）**：沒有被任何其他頁面透過 `[[wikilinks]]` 引用的頁面。
4. **缺失頁面**：文本中提到某個概念或實體，但沒有對應的 `wiki/` 頁面，建議創建。
5. **缺失 Cross-references**：明顯應互相關聯的頁面之間缺少 `[[wikilinks]]`。
6. **資料缺口**：某頁面提到關鍵數據或外部知識但沒有來源，建議透過 `search_web` 工具補充。
7. **日誌與索引一致性**：
   - 檢查 `wiki/log_wiki.md` 是否完整記錄所有操作。
   - 檢查 `wiki/index_wiki.md` 是否包含所有 `wiki/` 下的頁面。

### 輸出格式

- 建立報告頁面：`wiki/lint-reports/YYYY-MM-DD-lint-report.md`，格式如下：
  ```md
  # Lint Report — YYYY-MM-DD

  ## 矛盾
  - （列出衝突項目，若無則填「無」）

  ## 過時內容
  - （列出可能過時的頁面與原因）

  ## 孤立頁面
  - （列出無任何引用的頁面）

  ## 缺失頁面
  - （列出建議新建的概念頁）

  ## 缺失 Cross-references
  - （列出建議補充 wikilinks 的頁面對）

  ## 資料缺口
  - （列出建議搜尋補充的項目）

  ## 日誌與索引一致性
  - log_wiki.md：（是否完整）
  - index_wiki.md：（缺漏頁面列表，若無則填「無」）

  ## 總結
  - 健康評分（0–100）
  - 建議優先處理項目
  ```
- 在 `wiki/log_wiki.md` 追加一條 `[LINT]` 記錄，格式如下：
  ```md
  ## 2026-05-01 14:32 — LINT wiki/lint-reports/2026-05-01-lint-report.md
  - **掃瞄頁數**：XX 頁
  - **問題數量**：矛盾 X｜過時 X｜孤立 X｜缺失頁面 X｜缺失引用 X｜資料缺口 X
  - **備註**：（可省略）
  ```
