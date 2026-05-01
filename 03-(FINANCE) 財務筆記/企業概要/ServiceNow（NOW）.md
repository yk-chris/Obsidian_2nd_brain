---
ticker: NOW
company: ServiceNow
exchange: NYSE
sector: Enterprise Software / AI Platform
tags: [finance, 企業概要, NOW, SaaS, ITSM, AI-platform]
created: 2026-05-01
updated: 2026-05-01
---

# ServiceNow（NOW）

> **Workflow C** — 企業概要分析（`invest-moat-margin-v2` + `dive-deep-bottlenecks`）
>
> 資料截止日期：Q1 2026（截至 2026-03-31）；最新市值資料約 2026-05 初。

---

## Part A — 護城河 & 毛利率分析

> 來源技能：`invest-moat-margin-v2.md`

### 1. 業務單元深度拆解 (The Profit Engines)

> **雙軸閱讀指引：**
> - 「毛利率 GM%」→ 衡量技術含金量與定價能力（縱軸：賺錢效率）
> - 「毛利貢獻佔比」→ 衡量對公司整體盈利的體量貢獻（橫軸：賺錢體量）
> - 理想業務：**高毛利率 × 高貢獻佔比**；警示業務：**低毛利率 × 高貢獻佔比**

| 業務單元<br>(按毛利率↓排序) | 經營<br>開始年份 | 主要競爭對手 | 5年營收<br>CAGR | 最新<br>毛利率<br>(GM%) | 毛利貢獻<br>佔比<br>(% of Total GP) | 5年毛利率<br>趨勢<br>(↑/↓/→) | 淨利率/<br>貢獻利潤率 | 核心技術護城河<br>(Tech Moat) |
| :--- | :---: | :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **訂閱服務 (Subscription)** | 2004 | Salesforce, BMC Helix, Atlassian, Microsoft | ~24% | **85%** (non-GAAP) | **~97%** | ↑ | ~32% (non-GAAP Q1 2026) | 深度嵌入企業工作流、高轉換成本、Agentic AI 原生平台壁壘、CMDB 資料鎖定 |
| **專業服務 (Professional Services)** | 2004 | Accenture, Deloitte, IBM | ~12% | **~8.5%** (non-GAAP) | **~3%** | → | 負值 (GAAP) | 實施能力，定位為訂閱採納加速器而非利潤中心 |
| **合計 / 公司整體** | — | — | ~24% | **~79% (GAAP) / 83% (non-GAAP)** | **100%** | ↑ | ~12.4% (GAAP, Q1 2026) | — |

> **Q1 2026 最新數據：** 訂閱收入 $3.671B（+22% YoY，+19% cc），總收入 $3.770B（+22% YoY），cRPO $12.64B（+21% cc），Non-GAAP 營業利潤率 32%，FCM 44%。FY2026 訂閱收入全年指引上調至 $15.735B–$15.775B（~21% cc 增長）。630 個客戶 ACV>$5M（+22% YoY），16 筆新增 $5M+ 交易（+80% YoY）。
>
> **注意：** 中東（伊朗戰爭相關）交易延遲造成 Q1 2026 訂閱收入增速約 75bps 逆風，管理層已在全年指引中保守考量。

#### 毛利結構視覺化（文字版瀑布圖）

```
公司整體毛利（non-GAAP）= 100%
├── 訂閱服務：████████████████████████ ~97%（毛利率 ~85%）
└── 專業服務：█ ~3%（毛利率 ~8.5%，主要支援訂閱採納）
```

#### 五年毛利率趨勢對比表

| 財年 | 訂閱 GM%（GAAP） | 整體 GM%（GAAP） | 整體 GM%（non-GAAP） |
| :---: | :---: | :---: | :---: |
| FY2020 | ~79% | ~76% | ~80% |
| FY2021 | ~80% | ~76.8% | ~81% |
| FY2022 | ~81% | ~78.6% | ~83% |
| FY2023 | ~82% | ~78.8% | ~83.5% |
| FY2024 | ~82% | ~79.2% | ~82.5% |
| FY2025 | ~83% | ~76.6% (TTM) | ~83.5% |
| Q1 2026 | ~83%+ | ~79%+ (est.) | **~85% (Q1 指引)** |
| **趨勢** | **↑** | **→** | **↑** |

> FY2026 訂閱毛利率預計因第三方雲端使用量及收購攤銷略有承壓，管理層指引 non-GAAP 訂閱 GM 約 84-85%。

---

### 2. 護城河與技術壁壘分析

**最高毛利率業務：訂閱服務（Subscription）— 非GAAP GM ~85%**

#### 2a. 毛利結構解碼

- **收入端：** 純訂閱制（ACV 模式），依工作流模組（ITSM、HRSD、CSM、SecOps、ITOM、App Engine 等）按席位或工作流數量收費。Now Assist（Gen AI）已作為額外 ACV 附加費商業化，大型企業年均 ACV 超過 $1M，630 個客戶 ACV>$5M（Q1 2026，+22% YoY）。
- **成本端：** 主要 COGS 為資料中心/雲端託管成本（AWS、Azure 等，RaptorDB 自建替換中）、客服支援人力及 SBC。軟件邊際交付成本接近零，規模效應顯著。
- **量化：** 「每增加 $1 訂閱收入，邊際成本增加約 $0.15-$0.17」（non-GAAP GM ~83-85%）。

#### 2b. 不可複製性

| 壁壘類型 | 具體說明 |
| :--- | :--- |
| **客戶轉換成本** | 企業平均建立 **10+ 跨系統整合**（HR、IT、安全、財務），遷移週期 2-4 年，遷移成本達原授權費 3-5 倍。高整合客戶流失率低 40% |
| **Agentic AI 鎖定（2026 新增）** | Autonomous Workforce 已上線，Level-1 Service Desk AI 自主解決 >90% IT 請求（ServiceNow 內部數據），歷史工作流訓練資料形成 AI 飛輪，競爭對手難以複製 |
| **CMDB 資料鎖定** | 客戶歷史工作流資料、配置管理資料庫（CMDB）長期積累，AI 訓練資產高度客製化，任何遷移意味資料和模型損失 |
| **平台生態（App Engine）** | App Engine + Store 上的自定義應用形成輕度網絡效應，企業在 Now Platform 上二次開發應用越多，遷移成本越高 |
| **安全合規壁壘** | CVE-2025-12420（BodySnatcher）漏洞已揭示 Agentic AI 安全風險；ServiceNow 在 Q2 2026 修補並強化 Deterministic Workflow Orchestration，反而強化了「平台信任」品牌護城河 |

#### 2c. 定價權 (Pricing Power)

- **98%+ 客戶續約率**（接近 99%，Q4 2025），遠高於 Salesforce (~90%)，為定價能力的最強佐證。
- 過去五年透過「upsell & cross-sell」（新增模組、升級席位、Now Assist AI 附加費）實現有效提價，NRR 估計維持 **125%+**（業界估算，未獨立披露）。
- Q1 2026：16 筆 $5M+ 新增 ACV 交易（+80% YoY），顯示大型企業對平台擴張意願強勁。
- FY2026 訂閱收入指引上調，即使中東地緣政治逆風，管理層維持 ~21% cc 增長指引，體現定價韌性。

---

### 3. 轉型與未來 (The "Next" Engine)

#### 3a. 低毛利 × 高R&D 業務識別

| 新興業務 | 當前毛利率 | 毛利貢獻佔比 | R&D投入佔收入比 | 轉型方向 |
| :--- | :---: | :---: | :---: | :--- |
| **Now Assist / Autonomous Workforce（Agentic AI）** | 嵌入訂閱層，未獨立披露 | 包含於訂閱 ~97% | ~23% (整體 R&D/Rev) | 傳統 ITSM 工單 → AI 自主代理，目標代理解決率 90%+ |
| **App Engine（低代碼平台）** | 嵌入訂閱層 | 快速增長，未披露 | 同上 | 工作流搭建 → 企業自建 AI 應用（Platform of Platforms）|
| **RaptorDB（自建資料庫）** | 基礎設施層（成本節省） | N/A | 同上 | 第三方 DB → 自建高性能資料庫，降低 COGS，提升 GM |
| **Moveworks（收購，2026）** | 整合初期，虧損 | 增量，未披露 | 高（AI 研究密集型） | 對話式 AI + 企業搜尋 → 統一 Now Platform 前端入口 |

#### 3b. 轉型條件評估

- **商業模式轉型路徑：** 從「ITSM 工單系統」→「Agentic AI 企業控制塔（AI Control Tower）」。ServiceNow 已於 2026 年 2 月推出 Autonomous Workforce，Level-1 Service Desk AI 在其自身企業內部自主解決 >90% IT 請求、99% 更快解決速度，為商業化提供概念驗證。
- **關鍵技術里程碑：** (1) Autonomous Workforce 代理解決率行業客戶達 70%+，(2) Moveworks 整合完成並進入 Now Platform 統一前端，(3) RaptorDB 替換完成（預計 2026-2027），(4) App Engine MAU 突破 100 萬。
- **毛利率目標：** RaptorDB 降低基礎設施 COGS 後，non-GAAP GM 有望從 ~84% 提升至 **86-87%**（2027-2028 穩態）。

#### 3c. 催化劑時間窗口

| 催化劑事件 | 預期時間 | 對毛利結構的潛在影響 | 概率評估 |
| :--- | :---: | :--- | :---: |
| Now Assist / Autonomous Workforce 大規模企業採用 | 2026-2027 | 訂閱 ARPU 提升 15-25%，ACV 擴張加速 | 高 |
| RaptorDB 替換第三方資料庫完成 | 2026-2027 | COGS 下降，GAAP/non-GAAP GM 擴張 1-3ppt | 中 |
| Moveworks 整合完成，推動 AI 搜尋市場滲透 | 2026-2027 | 新增中端市場入口，但短期增加整合複雜性 | 中 |
| 中東地緣政治持續惡化，大型交易延遲擴散 | 2026 下半年 | 訂閱增速從 21% 降至 17-18%，估值壓縮 | 中 |
| 企業用 AI 縮減席位數量（SaaS 反向衝擊） | 2026-2028 | Workflow Density 策略可緩衝，但不可完全免疫 | 低-中 |

---

### 4. 投資結論：毛利結構健康度評分

| 評估維度 | 評分 (1-5) | 關鍵依據 |
| :--- | :---: | :--- |
| 整體毛利率水平（絕對值） | 5/5 | GAAP ~79%、non-GAAP ~83-85%，遠高於企業軟件均值 ~70% |
| 毛利率趨勢（五年方向） | 4/5 | non-GAAP 持續擴張；GAAP 受 SBC 及收購攤銷短期承壓 |
| 最高毛利業務的護城河深度 | 5/5 | 98%+ 續約率、10+ 整合綁定、CMDB 鎖定、Agentic AI 飛輪，護城河極深 |
| 毛利結構集中度風險 | 3/5 | 訂閱業務佔毛利 ~97%，高集中度穩健但缺乏多元緩衝 |
| 新興業務轉型可信度 | 4/5 | Autonomous Workforce 已上線且內部驗證；Moveworks 收購加速 AI 入口布局；R&D ~23% 收入，執行力有記錄支撐 |
| **綜合評分** | **4.2/5** | 高護城河 Agentic AI 平台，轉型催化劑更清晰；核心風險為估值偏高（股價自 2025 初下跌 ~60%）及地緣政治交易延遲 |

---

## Part B — 瓶頸深挖分析

> 來源技能：`dive-deep-bottlenecks.md`

---
研究主題：ServiceNow（NOW）— 企業關鍵瓶頸識別與深挖

時間窗口：過去 144 小時（2026-04-25 至 2026-05-01）+ 中期結構性瓶頸（12-24 個月）

分析深度：深度分析

報告語言：繁體中文

生成日期：2026-05-01

---

## 近期重大動態

### 資本市場

- **Q1 2026 業績超預期但股價下跌：** 訂閱收入 $3.671B（+22% YoY），超出指引高端；但中東（伊朗戰爭相關）交易延遲造成 ~75bps 逆風，股票盤後下跌，反映市場對地緣政治尾部風險的高度敏感。（來源：CNBC, 2026-04-22）
- **FY2026 訂閱收入指引上調至 $15.735B–$15.775B**（~21% cc）；Non-GAAP 營業利潤率全年指引 ~32%。（來源：ServiceNow Q1 2026 業績報告）
- **股價自 2025 年初下跌 ~60%**，本益比大幅壓縮；現價 ~$85，市場重新評估高成長 SaaS 估值溢價合理性。（來源：Yahoo Finance, 2026-04-22）
- **Moveworks 收購完成（2026 年）**，ServiceNow 整合對話式 AI + 企業搜尋，向 Microsoft Copilot 正面宣戰。

### 技術與產品

- **Autonomous Workforce 上線（2026-02-27）：** Level-1 Service Desk AI 自主解決 ServiceNow 自身 >90% IT 請求，99% 更快解決速度；企業治理框架（Deterministic Workflow Orchestration）成為差異化賣點。（來源：Futurum Group, 2026-02-26）
- **CVE-2025-12420（BodySnatcher）：** AppOmni 發現 Now Assist Virtual Agent API 嚴重漏洞，可繞過 MFA/SSO 控制；ServiceNow 已修補，但事件暴露 Agentic AI 安全系統性風險。（來源：AppOmni, 2026-04-09）
- **RaptorDB 推進中：** 自建資料庫替換 AWS/Azure 第三方 DB，預計 2026-2027 完成，目標降低訂閱業務 COGS 1-3ppt。

### 監管與政策

- **中東地緣政治（伊朗戰爭）：** Q1 2026 造成多筆大型政府/金融客戶交易延遲，管理層已在全年指引中保守考量地區風險。
- **AI 監管趨勢：** 歐盟 AI Act 合規要求對 Agentic AI 部署形成額外認證負擔，尤其影響 GDPR 嚴格地區的自主決策工作流商業化速度。

---

## 主要障礙與瓶頸

### 技術層面

| 瓶頸 | 描述 | 難度 |
|------|------|------|
| **Agentic AI 準確率與幻覺風險** | Autonomous Workforce 在長鏈工作流（跨 10+ 系統）中的決策準確率仍不穩定，幻覺錯誤在 IT 以外的財務/法務等高風險場景中可能造成合規事故 | ⭐⭐⭐⭐⭐ |
| **平台整合複雜度（Moveworks 收購）** | 將 Moveworks 對話式 AI 架構與 Now Platform 工作流引擎深度整合，需統一資料模型、權限邏輯及 API 介面；短期可能造成平台穩定性風險 | ⭐⭐⭐⭐ |
| **RaptorDB 遷移執行風險** | 大規模替換生產環境中的第三方資料庫（處理全球 8,600+ ITSM 客戶資料），遷移中的資料一致性及服務連續性是核心技術挑戰 | ⭐⭐⭐⭐ |
| **AI 安全（CVE-2025-12420 類事件）** | Agentic AI 在獲得跨系統執行權限後，安全攻擊面大幅擴大；每次新 AI 功能發布均可能引入新攻擊向量，需持續的安全審計投入 | ⭐⭐⭐⭐ |

### 非技術層面

- **估值高企與市場情緒逆轉：** 股價自 2025 年初下跌 ~60%，市場對高成長 SaaS 估值溢價的容忍度顯著降低，任何增速放緩（即使僅 1-2ppt）均可能觸發大幅多重壓縮
- **企業 IT 預算緊縮：** 宏觀不確定性（關稅、利率）促使 CIO 延後大型平台升級決策，尤其對 $5M+ ACV 大單的成交週期有延長壓力
- **AI 工具替代 SaaS 席位的威脅：** 企業用 AI 自動化工作可能縮減需要授權的人工操作員數量，對傳統 per-seat 訂閱模式形成結構性壓力（ServiceNow 的 Workflow Density 策略可部分對沖，但不能完全免疫）
- **地緣政治暴露（中東、中國）：** 中東戰爭已造成 Q1 2026 顯性逆風；若擴大至其他高風險地區，可能進一步侵蝕增速
- **競爭格局複雜化：** Microsoft（Copilot + Azure）、Salesforce（Agentforce）、Workday 均正在構建跨部門 AI 工作流，直接侵入 ServiceNow 的非 IT 擴張領域（HR、財務、供應鏈）

### 情境條件（Gherkin）

```gherkin
Scenario: Agentic AI 商業化受阻
  GIVEN ServiceNow 已推出 Autonomous Workforce 並在內部驗證 >90% 解決率
  WHEN  企業客戶（CIO）因安全合規顧慮（如 CVE 類事件）或監管要求，延遲或拒絕部署自主代理
  THEN  Now Assist ACV 附加費落地速度低於預期，FY2026 訂閱增速從 ~21% 降至 ~17%
  AND   市場重新定價 ServiceNow 從「Agentic AI 平台」退回「進階 ITSM 工具」，估值倍數承壓
  BUT   核心 ITSM 訂閱業務（98%+ 續約率）提供底部保護，不至於出現收入負增長

Scenario: Moveworks 整合延遲
  GIVEN ServiceNow 已完成 Moveworks 收購，計劃整合對話式 AI 入口
  WHEN  技術整合複雜度超出預期，統一平台延遲 2-4 個季度上市
  THEN  短期 R&D 費用上升壓縮 non-GAAP 利潤率，市場對管理層執行力的信心下降
  AND   Microsoft Copilot 利用窗口期深化企業綁定，競爭格局對 ServiceNow 更不利
  BUT   ServiceNow 現有工作流資產（CMDB + 10+ 整合）提供防守壁壘，不易被快速替代
```

---

## 可行解決方案

1. **Deterministic Workflow Orchestration 作為 Agentic AI 安全護城河（Commercial）：** ServiceNow 在 Autonomous Workforce 架構中嵌入確定性工作流編排與策略強制層，在 AI 代理執行每個跨系統動作前進行規則校驗，直接回應 CIO 最大顧慮（78% 仍擔憂安全合規，來源：Futurum 1H 2025 調研）。已商業化，是 vs. Microsoft/Salesforce 的差異化賣點。

2. **Workflow Density 策略對沖 Per-seat 風險（Commercial）：** 轉型定價邏輯從「席位數」→「工作流數量 & AI 代理調用次數」，確保即使企業縮減人力，平台使用量（和 ACV）仍能增長。FY2025 已有部分大客戶開始按 Outcome-based 定價。

3. **RaptorDB 自建資料庫降低 COGS（Pilot → 2026-2027 Commercial）：** 減少對 AWS/Azure 第三方 DB 依賴，目標節省 COGS 1-3ppt，推動 non-GAAP GM 從 ~84% 升至 ~86-87%（2027-2028），強化盈利能力作為估值支撐。

4. **Moveworks 整合推進企業 AI 搜尋市場（Pilot）：** 將 Moveworks 的 LLM-based 企業搜尋能力整合至 Now Platform，形成「Ask ServiceNow」統一入口，直接競爭 Microsoft 365 Copilot，覆蓋更廣泛的企業知識管理場景。

---

## 主要影響力公司（競爭格局）

### ServiceNow（NOW）— 防守方

**定位：** AI Control Tower for Business Reinvention — 企業跨部門工作流自動化平台，向 Agentic AI 轉型

| 維度 | 數據（Q1 2026）|
|------|------|
| 核心產品 / 服務 | Now Platform（ITSM、HRSD、CSM、SecOps）、Now Assist、Autonomous Workforce、App Engine |
| 收入來源 | 訂閱 ~97%（$3.671B Q1 2026）、專業服務 ~3% |
| 主要成本項 | R&D ~23% 收入、S&M ~30%（est. FY2026）、雲端基礎設施（RaptorDB 替換中）|
| 估值 / 市值 | 股價 ~$85（2026-05 初），市值 ~$440B；股價自 2025 初下跌 ~60% |
| 核心競爭優勢 | 98%+ 續約率、10+ 跨系統整合鎖定、CMDB 資料飛輪、Agentic AI 已商業化 |
| 主要風險 | 估值偏高、地緣政治（中東）逆風、Moveworks 整合複雜性、AI 安全事件 |

### Microsoft（競爭對手 #1）

**定位：** Copilot + Azure AI + Teams — 從生產力工具切入企業 AI 工作流

| 維度 | 數據 |
|------|------|
| 核心產品 / 服務 | Microsoft 365 Copilot、Azure AI Foundry、Power Automate、Dynamics 365 |
| 競爭威脅 | 已深度嵌入企業 Office 生態，Copilot 可在 Teams/Outlook/SharePoint 內直接觸發工作流，威脅 ServiceNow 的 HRSD 和 CSM 市場 |
| 差異化劣勢 | CMDB & IT 運營管理深度不及 ServiceNow；工作流治理（governance layer）較弱 |

### Salesforce（競爭對手 #2）

**定位：** Agentforce — 從 CRM 切入跨部門 AI 代理

| 維度 | 數據 |
|------|------|
| 核心產品 / 服務 | Agentforce（Agentic AI）、Service Cloud、Sales Cloud、MuleSoft |
| 競爭威脅 | Agentforce 定位與 ServiceNow Autonomous Workforce 高度重疊；MuleSoft 的整合能力威脅 ServiceNow 的多系統整合護城河 |
| 差異化劣勢 | IT 基礎設施管理（ITSM/ITOM）深度不及 ServiceNow；CMDB 缺席 |

### BMC Helix / Atlassian Jira SM（ITSM 傳統競爭對手）

**定位：** 傳統 ITSM 工具，ServiceNow 在此市場市佔 44.4%（~6倍領先）

| 維度 | 數據 |
|------|------|
| 競爭威脅 | 中低端市場（SMB / 政府機構）的價格競爭；Atlassian 在開發者場景有生態優勢 |
| 差異化劣勢 | 企業級 AI 能力、Agentic AI 商業化均遠落後 ServiceNow |

---

## Constraints 聲明

- 本報告資料截至 **2026-05-01**，以 Q1 2026 業績（2026-04-22 公告）及近期動態為基礎，後續財務數據請以 Q2 2026 業績（預計 2026-07 發布）更新
- 財務數據中未標注「GAAP」者均為 non-GAAP（調整後）口徑，排除 SBC、攤銷等項目
- NRR（淨收入留存率）~125% 為業界分析師估算，ServiceNow 未官方披露此指標
- Moveworks 收購財務影響（整合成本、收入貢獻）尚未有完整公開數據，相關分析為推算
- CVE-2025-12420 修補狀態及後續安全審計進展請持續追蹤 AppOmni 及 ServiceNow 安全公告
