# AI Fitness Coach — Proposal Analysis

## 1. Core Positioning

The project is positioned as a **Domain AI Agent**, rather than a single-model application or simple chatbot.

- **AI Agent:** FitnessCoachAgent with a typed tool loop, ScopeGuard intent filtering, and usage-budget control.
- **Domain Knowledge:** running planning, CWA weather information, pace/effective-time calculation, nutrition data via MCP, and allergy/preference matching.
- **Data Analytics:** Leaflet/Geoapify route distance and GeoJSON, food visual quantity estimation, exercise/food history, and model/token usage tracking.
- **Real-World Application:** reduces the manual form-filling and environmental-awareness burden found in conventional fitness apps.

## 2. Abstract / Introduction Structure

### Abstract A–F

- **A — Attention Getter:** personalized exercise guidance and natural conversation.
- **B — But:** manual forms, lack of environmental awareness, digital-human integration, voice latency, multi-module complexity, and free-cloud limitations.
- **C — Cure:** AI Fitness Coach as a conversation-first running coach integrating voice Agent, digital-human lip sync, weather/routes, food vision, and nutrition.
- **D — Development:** CyborAgent + CyborAssistant integration, Vanilla JS + FastAPI, Vercel + Supabase, FitnessCoachAgent + ScopeGuard.
- **E — Experiments:** end-to-end validation of conversation, weather/routes, exercise records, food recognition, MCP menus, and lip synchronization.
- **F — Findings:** proposal-stage expected outcomes only; the system is expected to complete major flows on free-priority cloud infrastructure while controlling model usage.

### Introduction G–L

- **G — General:** digital fitness market and AI/wearable adoption.
- **H — However:** cognitive burden of forms, difficult real-time integration of weather/routes/food, and free-cloud latency/deployment constraints.
- **I — In literature:** traditional fitness records → voice assistants → pose detection → LLM Agent tool calling → real-time voice/lip-sync digital humans.
- **J — Judgement:** compares limitations and advantages of form-based interaction, voice assistants, and digital humans.
- **K — Keypoint:** conversation entry, multimodal integration, public cloud deployment, ScopeGuard and usage budgeting.
- **L — List organization:** organizes the paper into related work, proposed method, simulation/validation, and conclusion.

## 3. Related Work & Deep Research

### AI / Domain balance

**AI side**
- LLM Agent
- Gemini
- Groq Whisper STT
- Azure Speech TTS
- Vision-based food recognition
- MCP

**Domain side**
- Running pace calculation
- Exercise heart-rate/time management
- Weather and environmental safety
- Nutrition and meal planning

### Deep Research

**Five core thinking patterns**
1. Pace and cardiovascular zones
2. Energy replenishment timing
3. Climate and environmental safety
4. Individual adaptation and injury prevention
5. Habit formation and motivation

**Three major debates**
1. Pace control vs. heart-rate-zone guidance
2. Voice/video digital-human presence vs. API latency and cost
3. Manual backfill/simple conversation vs. continuous high-precision GPS

**Ten deep-question dimensions**
Why, What-if, Trade-off, Failure Case, Evidence, Comparison, Impact, Scalability, Ethics, Future.

## 4. Proposed Scheme

### Eight major modules

1. **User/Application Scenario** — mobile/desktop browser conversation and exercise/food pages.
2. **Query/Input Processing** — VAD/STT, frontend transmission, text sanitization.
3. **Planner & Reasoning Agent** — ScopeGuard + FitnessCoachAgent tool loop.
4. **Data Acquisition/Retrieval** — CWA API, Leaflet/Geoapify, Supabase.
5. **Analytics Engine** — exercise duration/pace, food quantity/calorie estimation, Token Budget.
6. **Domain Knowledge Integration** — nutrition MCP server, running safety rules, emergency stop mechanism.
7. **Decision/Recommendation** — draft_run_plan, recommend_meal_plan.
8. **Output & Interaction** — web cards, Azure TTS, AI digital-human lip sync.

### Core flow

User input → ScopeGuard intent/quota check → TaskSpec → FitnessCoachAgent → Tool call → backend validation → text/card/TTS/lip-sync output.

### Pace formulation

Pace = duration(s) / distance(km)

## 5. A2Z SOP Mapping

| Letter | SOP | Project implementation |
|---|---|---|
| A | Attention Getter | Health motivation and personalized running need |
| B | But | Form burden, weak environmental awareness, cloud limits |
| C | Cure | Conversation-first AI Fitness Coach |
| D | Development | CyborAgent/CyborAssistant + Vanilla JS/FastAPI |
| E | Experiments | End-to-end flow validation |
| F | Findings | Expected outcomes without fabricated results |
| G | General | Digital fitness market context |
| H | However | Technical/application bottlenecks |
| I | In literature | App → voice → pose → LLM Agent → digital human |
| J | Judgement | Method comparison and trade-offs |
| K | Keypoint | Conversation, integration, cloud deployment, ScopeGuard |
| L | List organization | Paper structure |
| M | Methods | Literature/method classification |
| N | New proposed | Tool loop + MCP + STT/TTS + digital human |
| O | Organize | Literature comparison |
| PA | Aim | Publicly accessible AI running coach |
| PB | Based on | CyborAgent/CyborAssistant |
| PC | Cure/Cause | FitnessCoachAgent + ScopeGuard |
| PD | Design | Vanilla JS + FastAPI + Supabase |
| PE | Paper Element | Six major delivery modules |
| PF | Formulation | Pace, Token Budget, state/idempotency |
| PG | Graph | Flowchart, sequence, state diagram |
| PH | How | ScopeGuard → TaskSpec → Agent → Tool → Output |
| PI | Implementation | REST, WebSocket, Tool Gateway |
| PJ | Jump to an example | “I want to run for 30 minutes” scenario |
| PK | Key points contribution | Integration, cost control, reproducibility |
| PL | Later how to do simulation | GPS/sensor expansion |
| PM | Math proof / Logic | Pace, pause, timezone, transaction logic |
| Q | Quality & Quantity | P95 experience targets |
| R | Related method to compare | Form App, LLM chatbot, voice assistant, local GPU |
| S | Simulation Setup | Demo account, route seed, free API quotas |
| T | Tuning parameters | Tool/call/timeout/inference/token limits |
| U | Useful results | Route cards, timer, food cards, MCP meal plans |
| V | Verify | 21 acceptance scenarios |
| W | What proposed | Conversation-based Domain AI Agent |
| X | eXcel | Running planning, free cloud, ScopeGuard, digital human |
| Y | Yields | GitHub, README, DESIGN, URL, Demo, Proposal |
| Z | Zen | GPS, sensors, cost optimization, long-term memory |

## 6. Evaluation

The proposal specifies **manual scoring + automated metrics** for end-to-end validation.

Validation areas include:
- conversation recommendations
- weather/route lookup
- manual exercise records
- food calorie recognition
- MCP nutrition menus
- digital-human lip synchronization
- irrelevant-request rejection
- interruption/interjection
- data isolation
- cloud reproducibility

### Experience targets

| Metric | Target |
|---|---:|
| General page P95 | < 2 s |
| Text → first response P95 | < 8 s |
| Voice → audible response P95 | < 12 s |
| Stop playback | < 300 ms |

These are proposal-stage experience targets, not claims of completed measurements.

## 7. Engineering / Handover Notes

The analysis identifies several items to complete before final submission:

1. Add line-numbered pseudocode for the FitnessCoachAgent loop.
2. Fully document Deep Research Q1–Q3.
3. Add the required Article Summary Table: Ref. | Year | Problem Limitation | AI Method | Domain Knowledge | Dataset | Findings.
4. Add numbered labels (①②③…) to the system architecture and map each label to the corresponding description.
5. Preserve expected-outcome wording for experiments that have not yet been performed.

## 8. Expected Deliverables

- GitHub repository
- README.md
- DESIGN.md
- Public URL
- Demo video
- Proposal / presentation
