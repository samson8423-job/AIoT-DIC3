# AI Fitness Coach 🏃‍♂️

> **A Domain AI Agent for Personalized Running & Healthy Living**  
> 結合 AI × 運動 × 健康數據，打造你的專屬慢跑教練。

## Project Overview

AI Fitness Coach 是一個以「對話為唯一入口」的 Domain AI Agent 慢跑教練網站，目標是降低傳統健身 App 的手動紀錄負擔，並將慢跑規劃、天氣、路線、運動紀錄、食物辨識與營養建議整合到單一使用流程中。

### Core Positioning

- **AI Agent**：FitnessCoachAgent + ScopeGuard + Tool Loop
- **Domain Knowledge**：慢跑配速、運動安全、氣象、路線、營養與過敏原
- **Data Analytics**：路線距離、運動時間／配速、飲食與運動紀錄、Token 用量
- **Real-World Application**：以自然對話取代繁瑣表單，提供個人化慢跑與飲食建議

## Abstract

全球約 18 億成年人身體活動不足，死亡風險高出 20–30%（[WHO](https://www.who.int/news-room/fact-sheets/detail/physical-activity)）；台灣規律運動人口亦僅 35.6%（公視新聞）。**然而**，約 70% 使用者在百日內棄用健身 App，主因為手動登錄負擔與缺乏環境感知，且語音延遲與雲端成本限制進一步阻礙個人化指導之普及（JMIR）。為此，我們提出 AI Fitness Coach——以對話為唯一入口之慢跑教練網站，整合語音 Agent、數位人像口型、氣象路線、食物視覺辨識與 MCP 營養建議，其構想獲對話代理提升運動量之統合分析實證支持（PubMed）。系統採 Vanilla JS ＋ FastAPI 架構，部署於 Vercel ＋ Supabase，以單一 FitnessCoachAgent 搭配 ScopeGuard 意圖過濾與 Token 用量預算控制成本。評估採人工評分與自動化指標雙軌驗證端到端流程。預期成果：系統可在免費雲端環境完成主要使用者流程並有效控制模型用量，為 AIoT 領域提供可公開展示、可重現之整合架構。

> **Note:** 提案階段對尚未完成的實驗採用 **Expected Outcomes** 表述，不將預期結果宣稱為已完成的實驗結果。

## System Architecture

```text
User / Browser
     │
     ▼
Voice / Text / Digital Human UI
     │
     ▼
VAD / STT / Input Validation
     │
     ▼
ScopeGuard ──► Token Budget
     │
     ▼
FitnessCoachAgent
     │
     ├──► CWA Weather API
     ├──► Leaflet / Geoapify Route
     ├──► Supabase Database
     ├──► Food Vision
     └──► MCP Nutrition
     │
     ▼
Backend Validation
     │
     ├──► Text / Cards
     ├──► Azure TTS
     └──► Digital Human Lip-sync
```

## Main Functions

### 🗣️ Conversation-first Coaching
使用者可以直接以文字或語音詢問，例如：「今天想跑 30 分鐘。」系統可取得天氣與路線資訊，產生慢跑計畫草案，再由使用者確認。

### 🌦️ Weather & Route Awareness
整合中央氣象署天氣資訊與地圖／路線資料，使慢跑建議能納入當下環境條件。

### 🏃 Running Planning & Records
支援慢跑計畫、開始／暫停／結束流程與距離補登，並計算運動時間與配速。

```text
Pace = duration(s) / distance(km)
```

### 🍱 Food Recognition & Nutrition
整合食物視覺辨識、份量／熱量估算與 MCP 營養建議，搭配個人飲食紀錄與偏好／過敏原資訊。

### 🧑‍💻 AI Agent + ScopeGuard

```text
User Input
    ↓
ScopeGuard
    ↓
Intent / Quota Check
    ↓
TaskSpec
    ↓
FitnessCoachAgent
    ↓
Tool Call
    ↓
Backend Validation
    ↓
Text / Card / TTS / Digital Human
```

ScopeGuard 在非 LLM 層進行意圖與用量控制，降低不必要的模型呼叫與成本失控風險。

## A2Z SOP Mapping

| Letter | SOP | AI Fitness Coach 對應 |
|---|---|---|
| A | Attention Getter | 全民健康與個人化慢跑需求 |
| B | But | 表單負擔、環境感知不足、雲端限制 |
| C | Cure | 對話式 AI Fitness Coach |
| D | Development | CyborAgent / CyborAssistant、Vanilla JS + FastAPI |
| E | Experiments | 端到端流程驗證 |
| F | Findings | 預期完成主要流程並控制 Token |
| G | General | 數位健身市場現況 |
| H | However | 技術與應用瓶頸 |
| I | In literature | 傳統 App → Voice → LLM Agent → Digital Human |
| J | Judgement | 不同方法的優缺點分析 |
| K | Keypoint | 對話入口、多模組整合、免費部署、ScopeGuard |
| L | List organization | 論文／提案結構 |
| M | Methods | 既有方法分類 |
| N | New proposed | LLM Tool Loop + MCP + STT/TTS + Digital Human |
| O | Organize | 文獻比較與歸納 |
| PA | Aim | 公開連線 AI 慢跑教練 |
| PB | Based on | CyborAgent / CyborAssistant |
| PC | Cure / Cause | FitnessCoachAgent + ScopeGuard |
| PD | Design | Vanilla JS + FastAPI + Supabase |
| PE | Paper Element | 六大交付模組 |
| PF | Formulation | 配速、Token Budget、State / Idempotency |
| PG | Graph | Flowchart / Sequence / State Diagram |
| PH | How | ScopeGuard → TaskSpec → Agent → Tool → Output |
| PI | Implementation | REST / WebSocket / Tool Gateway |
| PJ | Jump to an example | 「今天想跑 30 分鐘」完整情境 |
| PK | Key points contribution | 對話整合、成本控制、可重現部署 |
| PL | Later how to do simulation | GPS / 感測器後續擴充 |
| PM | Math proof / Logic | 配速、暫停、時區、交易鎖定 |
| Q | Quality & Quantity | P95 延遲與停止播放指標 |
| R | Related method to compare | 表單 App、LLM Chatbot、語音助理等 |
| S | Simulation Setup | 展示帳號、路線、免費 API 額度 |
| T | Tuning parameters | Tool / Call / Timeout / Token 限制 |
| U | Useful results | 路線、計時器、食物卡片、營養菜單 |
| V | Verify | 21 項驗收情境 |
| W | What proposed | 對話式 Domain AI Agent |
| X | eXcel | 慢跑規劃、免費雲端、ScopeGuard、數位人 |
| Y | Yields | GitHub、README、DESIGN、Demo、Proposal |
| Z | Zen | GPS、感測器、成本與長期記憶展望 |

## Deep Research

### Five Core Thinking Patterns
1. 配速與心肺區間
2. 能量補充時機
3. 氣候與安全風險
4. 個體適應性與傷痛預防
5. 行為習慣養成與動機維持

### Three Major Professional Debates
1. 配速控制 vs. 心率區間導向
2. 語音／視訊數位人臨場感 vs. API 延遲與成本
3. 手動補登／簡單對話 vs. 持續高精度 GPS 追蹤

### Ten Deep Questions
涵蓋 Why、What-if、Trade-off、Failure Case、Evidence、Comparison、Impact、Scalability、Ethics、Future 等推理面向。

## Evaluation Plan

採 **人工評分 + 自動化指標** 雙軌驗證端到端流程。

涵蓋：
- 對話建議
- 天氣與路線查詢
- 手動運動紀錄
- 食物熱量辨識
- MCP 營養菜單
- 數位人像口型同步
- 無關請求拒絕
- 中斷／插話
- 資料隔離
- 雲端重現

| Metric | Target |
|---|---:|
| 一般頁面 P95 | < 2 s |
| 文字 → 首段回覆 P95 | < 8 s |
| 語音 → 可聽回覆 P95 | < 12 s |
| 停止播放 | < 300 ms |

> 上述數值為提案中的體驗目標，不代表目前已完成的實測結果。

## Repository Contents

```text
AIoT-DIC3/
├── README.md
├── docs/
│   ├── AI-Fitness-Coach-提案分析.pdf
│   └── AI-Fitness-Coach-資訊圖表.png
├── DESIGN.md
├── proposal.md
└── ...
```

## Future Work

- 手機瀏覽器持續 GPS 追蹤
- 步數與動作姿態感測
- 更低成本的數位人口型生成
- 長期記憶
- 更完整的運動／營養個人化
- 更大規模的實驗與使用者研究

## Project Deliverables

- GitHub Repository
- `README.md`
- `DESIGN.md`
- 公開連線網址
- Demo Video
- Proposal / Presentation

## References

- [World Health Organization — Physical Activity](https://www.who.int/news-room/fact-sheets/detail/physical-activity)

> 台灣運動人口、健身 App 留存、語音延遲／雲端成本及對話代理提升運動量等數據，正式論文／提案版本應依實際採用之公視、JMIR 與 PubMed 文獻補上完整 bibliographic citation。
