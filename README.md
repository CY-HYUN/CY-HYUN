<div align="center">

# 👋 Hi, I'm Changyong Hyun
<!-- GitHub Profile README - Last updated 2026-09-16 -->

### 🚀 AI/ML Engineer | LLM Evaluation & Agentic Systems | MSc @ Télécom SudParis (IP Paris)

🎯 **Available from October 2026** · 🇫🇷 **Paris / Europe** · 🔬 **6 months building a production multi-agent LLM system** · ⚡ **PyTorch · LangGraph · MLflow**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:xhangyong.hyun@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/CY-HYUN)

</div>

---

## 🎯 About Me

**Graduating October 2026 · Open to LLM / ML Engineer roles in Paris and Europe · Work-authorised via the French post-graduation permit**

AI/ML engineer finishing an MSc in Data Science & Network Intelligence at **Télécom SudParis (Institut Polytechnique de Paris)**, with six months of industry experience at **MECAGENT** in Lyon building and evaluating a production multi-agent LLM system for CAD automation.

I build LLM and multi-agent systems, and I specialise in the part most teams skip: **deciding whether the thing actually works.** The hard problem is rarely generation — it's that the metric you grade outputs with is usually blind to some of the ways they can be wrong. On the system I worked on, a part built mirrored scored about the same as the correct one. So most of my work became evaluation design: build the instrument first, then let it decide what to change.

**Core Expertise:**
- 🔬 **Evaluation design for generative systems** — rubrics against expert-built ground truth, machine-derived reference labels instead of hand-written ones, pre-registered acceptance criteria, shuffled controls
- 🤖 **LLM fine-tuning** — LoRA, DPO, PEFT (12.16M trainable parameters, 5.5× lower validation loss than the prompt-tuning control, zero API cost)
- 🕸️ **Agentic & multi-agent systems** — LangChain, LangGraph, orchestrator/sub-agent architectures executing against a live external application
- 📈 **Observability** — MLflow run tracking, Arize Phoenix tracing, span-level analysis of multi-hour agent sessions
- 🧪 **Controlled experiments** — one variable at a time, negative results reported at the same length as positive ones

**Key Achievements:**
- 🏅 **SemEval 2026 Task 2** — CCC **0.6554** against a 0.62 target (+5.7%), measured on the best single model
- 🔍 **A leakage analysis that changed the answer** — quantified a **33.3-point** gap and published the lower number
- 🧰 **Instruments that outlive the code** — my scorers still reproduce every number from saved artefacts after the pipeline around them was rebuilt twice
- ⚡ **Zero-cost fine-tuning pipeline** — synthetic data generation through DPO alignment with no API fees and no human labelling
- 🎖️ **Best Performance Award** — Hanwha Aerospace big-data internship (1st of all teams)

---

## 📈 Contribution Activity

<div align="center">

<img src="https://streak-stats.demolab.com/?user=CY-HYUN&theme=tokyonight&hide_border=true&background=0D1117&ring=58A6FF&fire=58A6FF&currStreakLabel=58A6FF" alt="GitHub Streak" />

</div>

---

## 💼 Industry Experience

### 🔧 AI Engineer Intern — MECAGENT, Lyon, France (May – Oct 2026)

**MECAGENT builds an AI copilot for SolidWorks**, the most widely used mechanical CAD software. The product takes a natural-language request and generates C# macro code that executes inside the user's live SolidWorks session.

**The system I worked on:** a drawing-to-CAD pipeline — vision models read a 2D engineering drawing (orthographic views, dimensions, machining annotations), a planner turns it into a structured feature tree, and a multi-agent system generates and executes SolidWorks C# against a live CAD kernel. Not a sandbox, not a simulator: a stateful external application that fails in ways a library never does.

**My ownership:** the evaluation and experimentation layer — the part that decides whether any change was actually an improvement.

- 🎯 **Designed the evaluation for the drawing-reading stage from scratch**, for a generative component that had no measurement at all. Built the rubric, selected the sample across both source datasets and the feature classes that mattered, and anchored it on ten reference parts hand-built in SolidWorks by the company's CAD expert — so that no model ever graded another model's output. The scorer reproduces every number from saved artefacts with **zero model calls**, which is why it still runs today after the pipeline around it was rebuilt twice.
- 🔍 **Proved the team's headline metric was blind to entire classes of failure.** A mirrored part, a rotated part, and a sheet-metal bend imitated with extruded blocks all scored about the same as correct ones — the score aligns two solids before comparing, which erases orientation, and counts holes, which a mirror preserves. I built deterministic checks that detect each class by reading the feature types SolidWorks itself assigns, and those checks redirected the team's engineering priorities.
- 🧪 **Ran controlled A/B experiments with acceptance criteria registered before each run.** Shuffled controls killed four of my own proposed fixes. I published two pre-registered negative results at the same length as the positive ones — including one where my own improvement lost to the baseline and I recommended keeping the baseline.
- 🪞 **Caught my own ground-truth labels being wrong.** Three models disagreed with my hand-written answer key; checking the key against the reference geometry showed the key was wrong and the models were right. Every label after that came from a machine-derived source, and I wrote up why.
- 📊 **Instrumented long-horizon agent runs end to end** — MLflow for run tracking and model registry, Arize Phoenix for distributed tracing, reading span-by-span what an agent actually did across multi-hour sessions instead of trusting a summary of it.
- 🔧 **Built a C# helper library for the generating agent**, declared at the CAD session level, with live self-checks that each had to be demonstrated firing in both directions before I claimed they protected anything.
- 🤝 **Shipped inside a senior team's process** — pull requests, code review, trace-referenced technical reports adopted as a team template, and adversarial verification of my own claims before they left my desk.

**Tech Stack:** Python · C# · SolidWorks API · LangChain / LangGraph · MLflow · Arize Phoenix · vision-language models · AWS Bedrock / GCP Vertex · pytest

> *The company's internal results are covered by a confidentiality agreement, so this describes method and ownership rather than internal figures. Happy to go deeper on the engineering in conversation.*

---

## 🌟 Featured Projects

### 🤖 1. Synthetic-Instruction-Tuner — Zero-Cost LLM Fine-Tuning (Nov 2025 – Jan 2026)
**LoRA reached 5.5× lower validation loss than Prompt Tuning on identical data** — no seed dataset, no paid API, no human labelling at any stage

**Challenge:** Fine-tune an instruction-following model without API costs or human annotation — and build it so each method's contribution is separately *measured* rather than asserted as a stack.

**My Solution — a 6-stage pipeline, every stage's output committed:**

1. **Magpie Prompting** *(synthetic data generation)*:
   - Template-only prompting with Llama-3.1-8B-Instruct in 4-bit
   - Generated **1,500 instruction-response pairs** with no seed dataset — the chat template alone elicits the instructions
   - Checkpointed every 100 samples to survive Colab disconnects
2. **Quality Filtering** — six interpretable rule-based checks (length, language, repetition, format, toxicity, content quality), weighted to a single score:
   - **1,258 of 1,500 passed (83.9%)**, mean quality score 0.88; top **1,000** kept, split 900/100
   - Dominant failure was phrase repetition (**156 of 242**), not toxicity (5) — the useful finding, since it says what synthetic data actually gets wrong
3. **Preference-Pair Generation**:
   - **600 chosen/rejected pairs** via multi-temperature sampling, scored by a reward model (OpenAssistant DeBERTa-v3)
   - Every pair clears a 0.5 margin gate (mean margin 1.78, min 0.53)
4. **LoRA Fine-Tuning** — **12,156,928 trainable parameters (0.67% of base)**, r=8, alpha=16, all seven linear projections, on Llama-3.2-3B in 4-bit
5. **Prompt Tuning** *(head-to-head control, same data and hardware)* — 20 virtual tokens, **61,440 parameters: a 198× smaller adapter budget**
6. **DPO Alignment** — beta=0.1, single epoch on the 540/60 preference split, frozen SFT model as reference

**Results — measured, from committed training configs:**

| Method | Trainable params | Val loss | Peak VRAM | Wall time |
|---|---|---|---|---|
| **LoRA SFT** (r=8) | 12,156,928 (0.67%) | **0.54** | 5.3 GB | 8.2 min |
| Prompt Tuning (20 tokens) | 61,440 (0.003%) | 2.98 | 5.9 GB | 18.8 min |
| **DPO** (on top of SFT) | 12,156,928 (0.67%) | 0.55 | **4.7 GB** | **2.2 min** |

- **Adapter capacity dominated at 3B scale** — Prompt Tuning's 61K parameters could not fit the instruction distribution despite training more than twice as long. The 198× larger budget was worth it.
- **Preference alignment was nearly free** — single-epoch DPO in ~2 minutes at 4.7 GB peak, holding validation loss at SFT level
- **Fine-tuning changed style measurably on held-out probes** even with 1,000 samples: **+21% response length, +67% unique words, −36% sentence count** for DPO against base
- **Zero cost** — no API fees, no human labelling, ~200 Colab compute units end to end
- **4× faster than planned** — 7 days against a 28-day schedule

**Tech Stack:** Hugging Face PEFT, LoRA, DPO, TRL, 4-bit Quantisation, Magpie Prompting, Llama-3.1-8B / Llama-3.2-3B

**Deliverables:** 10 notebooks covering the full pipeline · 3 trained variants (LoRA / Prompt Tuning / DPO, adapters committed) · raw, filtered and preference datasets · 7 evaluation figures · a claim-by-claim data-provenance table

**What I'd point an interviewer at:** the repo's corrections log. An earlier version of it quoted MMLU/HellaSwag/ARC/TruthfulQA scores; a source audit found they were hardcoded demo values that no notebook ever produced, so they were removed and the removal documented. The numbers above are the ones that survived.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Synthetic-Instruction-Tuner)

---

### 🏅 2. SemEval 2026 Task 2 — Emotion Prediction (Oct 2025 – Jan 2026)
**CCC 0.6554** — international NLP competition, against a 0.62 target

**Challenge:** Predict emotional response (valence and arousal) from temporal sequences of a user's posts, where any single post carries little signal without the user's history.

**My Solution:**
- 🔥 **Modular pipeline** with training, prediction, evaluation and demo stages separated into their own modules
- 🧠 **User-level embeddings**: aggregated a user's historical posts into a dense representation — the single largest contributor in the ablation
- 🔬 **RoBERTa + BiLSTM (256 hidden, 2 layers) + 8-head attention**, dual-head output for the two dimensions
- 🎯 **Arousal-specialist model**: 90% CCC loss weighting on the harder dimension
- 📊 **47 engineered features**: 20 temporal (lag, rolling statistics, trend, volatility), 15 text (linguistic, punctuation, sentiment), 12 user statistics
- ⚡ **Mixed-precision training** (torch.cuda.amp) with multi-seed runs (42, 123, 777, 888, 1111) for robustness
- 📈 **Differential learning rates**: 1e-5 for the encoder against 8e-5 for the custom heads
- 🧪 **Systematic ablations**: quantified each component separately — user embeddings > engineered features > BiLSTM

**Results — measured on the validation split:**

| Model | CCC | Valence | Arousal | |
|---|---|---|---|---|
| **seed777** | **0.6554** | 0.7593 | 0.5516 | Best single model |
| arousal_specialist (seed 1111) | 0.6512 | 0.7192 | **0.5832** | Dimension-specialised |
| seed42 | 0.5053 | 0.6532 | 0.3574 | Dropped from the pool |

- **Best single-model CCC 0.6554** (seed 777), **+5.7% above the 0.62 target**
- **Arousal was the bottleneck, and specialisation paid for itself**: arousal CCC ranged 0.357–0.552 across seeds while valence reached 0.759. Weighting the loss 90% toward arousal lifted arousal CCC **0.5516 → 0.5832 (+0.0316)** while trading only **−0.0042 overall CCC**, and trained in ~24 minutes against ~2 hours for a full run. Naming what a gain costs is the part I would defend in an interview.
- **Seed variance turned out to be the bigger story**: the same architecture scored **CCC 0.5053–0.6554** across random seeds. Any single-run comparison on this task is mostly measuring the seed, which is why I report the best single model and its spread rather than one number.
- **46 users, 1,266 test predictions**

**On the submitted ensemble — stated precisely:** the final submission weighted the two best models by validation CCC (seed777 50.16% + arousal_specialist 49.84%). Its combined score was a **projection** — the CCC-weighted average of the two measured models plus an assumed ensemble boost — and was **never re-scored on held-out data**. So the number I quote is the measured 0.6554, not the projected ensemble figure. Being able to tell those two apart is the point.

**Tech Stack:** PyTorch 2.0+, Hugging Face Transformers, RoBERTa, BiLSTM, WandB, Mixed Precision Training

**Deliverables:** Joint slide deck (my part: subtask 2a) · technical report · fully reproducible pipeline (preprocessing, training, evaluation, prediction) · Codabench submission

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Deep-Learning-project-SemEval-2026-Task-2)

---

### 🔍 3. QoE Prediction — the Leakage Analysis That Changed the Answer (Oct – Dec 2025)
**33.3-point gap** — where the real result is the integrity work

**Challenge:** Predict user-perceived mobile-streaming quality (MOS 1–5) from 1,543 sessions. The obvious model looked excellent. It wasn't.

**My Solution:**
- 🚩 **Found the leak**: the strong model leaned on features only available *after* a session ends — information a deployed system would never have at prediction time
- ✂️ **Rebuilt the experiment** restricted to objectively-available features (network metrics, device characteristics, temporal patterns), with class balancing
- 📊 **Systematic model comparison**: Random Forest, SVM, XGBoost, KNN, Decision Tree, Logistic Regression
- 📈 **Reported both numbers side by side** and led with the lower one
- 🔁 **Made it reproducible**: the experiment script is committed and was re-run twice, byte-identical

**Results:**
- **81.6% with leaky post-session features** · **48.2% objective-only** (macro F1 0.442, kappa 0.261)
- **A 33.3-point leakage gap**, quantified rather than hand-waved
- The objective-only model sits *below* the majority-class baseline on raw accuracy (50.8%) but far above it on balanced metrics (F1 0.442 against 0.135) — the honest trade-off of balanced class weights, stated as one
- **Feature importance**: bitrate variability and packet loss as the top objective predictors

**Tech Stack:** scikit-learn, Random Forest, Gradient Boosting, XGBoost, SVM, Pandas, class-balanced evaluation

**Why it matters:** This is the project I bring up when someone asks how I know a metric is trustworthy. The headline number went *down* and the work got better.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Poqemon-QoE-Dataset-master)

---

### 🌍 4. DEFT — Defense Export Market Analysis (Sep – Dec 2024)
**102,321 records across 170 countries** — multi-source ETL and feasibility scoring

**Challenge:** Combine economic, political and conflict indicators into a usable market-feasibility view, when the three source databases disagree about what a country is even called.

**My Solution:**
- 🗄️ **Multi-source ETL pipeline**:
  - World Bank API: economic indicators (GDP growth, trade balance, inflation)
  - SIPRI: military expenditure and arms-transfer data
  - UCDP: armed-conflict databases
  - WGI: governance indicators (effectiveness, rule of law), 1991–2020
- 🧹 **Entity reconciliation**: mapped **210+ country-name variations** onto a single canonical set — the unglamorous step that made the join possible at all
- 📐 **Weighted three-dimensional scoring**: 9 economic variables, 6 governance indicators, and conflict casualty data (UCDP battle deaths, log-transformed and reverse-scaled)
- 📊 **K-Means clustering** for A/B/C country grading (k=3, elbow-validated)
- 📈 **OLS regression** to test whether the score explains anything — **R² = 0.366 on train, 0.461 on the held-out 20% test set**
- 🌐 **Interactive static platform**: Leaflet world map with a generated page per country, 200+ Chart.js charts, DataTables for real-time querying, ~54 MB of committed JSON

**Results:**
- **102,321 records · 170 countries** integrated into one queryable dataset (13 committed JSON files, 1991–2020)
- **Economic capacity was the only strong predictor of arms imports** — economic score **+23,170 TIV per standard deviation, p < 0.001**. Governance scored **p = 0.791: no measurable effect**, and conflict intensity was marginal (p = 0.093). That negative result mattered more than the positive one, because governance indicators were the axis the model was expected to lean on.
- **R² = 0.366 means ~63% of import variation sits outside these indicators** — alliances, political decisions, offset deals — which is the honest bound on how far indicator-only screening can go
- **South Korea's import mix**, mapped onto the US ITAR/USML 22-category taxonomy across 509 import entries (1991–2020): missiles 34.8%, aircraft 20.6%, military electronics 11.0%
- **210+ raw country-name variants reconciled** into one canonical set — the unglamorous step that made the four-source join possible at all

**Tech Stack:** Python, Pandas, NumPy, scikit-learn, statsmodels, Leaflet, Chart.js, DataTables, REST APIs (World Bank, SIPRI, UCDP, WGI)

**Impact:** A strategic screening tool for defense-industry market entry — and a quantified statement of where indicator-based screening stops working.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Global-Defense-Export-Analysis-Project)

---

### 🏢 5. Insurance SOA — Multi-Protocol Service Architecture (Dec 2025 – Jan 2026)
**4 protocols, one gateway** — REST · SOAP · gRPC · GraphQL

**Challenge:** Serve insurance claim processing to client types that each speak a different protocol, without maintaining four separate backends.

**My Solution:**
- 🔄 **XOR gateway orchestration**: routing logic that selects the protocol handler per request
- 🌐 **Four protocol implementations**:
  - **REST (Jersey)**: JSON for web clients
  - **SOAP (JAX-WS)**: XML for legacy enterprise systems
  - **gRPC**: Protocol Buffers, high-performance binary for microservices
  - **GraphQL**: introspection-based flexible querying for modern frontends
- ☕ **Java 11**: **1,927 lines across 17 files**
- 🧪 **Protocol-specific client applications** plus an **11-request Postman collection** for validation
- 📦 **Apache Maven** build automation, **Tomcat** deployment
- ⚖️ **Benchmarked the four** on latency and payload size rather than assuming

**Results:**
- **Protocol comparison** across performance, latency and payload size
- **Workflow automation**: claim routing, validation and approval/rejection paths
- **Modular architecture** where adding a fifth protocol touches the gateway and nothing else

**Tech Stack:** Java 11, Apache Maven, REST (Jersey), SOAP (JAX-WS), gRPC, GraphQL, Tomcat

**Architecture Pattern:** Service-oriented architecture with gateway orchestration

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Insurance-Claim-Processing-SOA)

---

### 📈 6. Agricultural Price Forecasting (Nov – Dec 2024)
**65,120 daily price rows · 17 commodities · 52-week horizon** — price forecasting for military food procurement

**Challenge:** Forecast Korean agricultural retail prices far enough ahead to change purchasing decisions, across commodities whose seasonality has almost nothing in common. 7-person team, 8 weeks.

**My Solution — two model families, trained separately and compared, not blended:**
- 📊 **Per-commodity LSTM** (Keras/TensorFlow), univariate price series:
  - **6 stacked LSTM layers** (200-100-50-50-100-200 units, tanh), dropout 0.2 and L2(0.01) on every layer, Dense(1) output
  - Adam with a per-commodity tuned learning rate (0.0005–0.0029), custom RMSE loss, EarlyStopping (patience 10, best-weights restore), seed 42
  - **One model per commodity** — 17 in total, because a single pooled model washes out the seasonality that makes each crop different
- 📉 **Seasonal ARIMA** (statsmodels `SARIMAX`, order (5,1,0), seasonal (1,1,1,52)) for the long horizon — **52-week-ahead weekly forecasts per commodity**
- 🗄️ **Data integration**: daily Garak Market retail prices merged with weather (KMA stations), GDP, fuel, and minimum-wage series; cleaning, gap handling and weekly resampling
- 🌐 **Flask dashboard** — 6 pages, all verified serving HTTP 200 — with embedded Power BI reports for stakeholders

**Results:**
- **65,120 daily retail-price rows across 17 commodities**, 2014-01-02 → 2024-12-05 (11 years)
- **17 per-commodity LSTM models**, best-epoch validation **MAE 0.022–0.094 on min-max-scaled prices** (median 0.044) — roughly **2–9% of each commodity's 11-year price range**
- **52-week-ahead forecasts** saved per commodity (napa cabbage, cabbage, carrot, cucumber, radish, garlic, onion, pepper, potato, rice, spinach, green onion)
- **Procurement timing recommendations** derived from the forecast curve rather than from last year's price

**Tech Stack:** Python, TensorFlow/Keras, statsmodels (SARIMAX), Flask, Power BI, Pandas, Time Series Analysis

**Note on scope:** an earlier version of the project README quoted test MAPE, R² and accuracy percentages whose evaluation runs were not preserved. The repository now reports only what can be re-derived from committed notebook outputs and data files — which is what the numbers above are.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Defense-Agri-Price-Forecasting-main)

---

### 📺 7. YouTube Analytics — Korean Content Strategy (Jul – Sep 2024)
**2,125 videos** — bilingual NLP across 15 channels and 3 categories

**Challenge:** Turn channel performance data into recommendations a creator could act on, across Korean and English text.

**My Solution:**
- 🌐 **Bilingual NLP pipeline**: Korean morphological analysis for title keyword patterns, English sentiment analysis
- 📊 **8 standalone analytical frameworks**:
  - Word cloud analysis of title keywords by category
  - Upload timing (hour-of-day, day-of-week)
  - Upload cadence and its effect on views
  - Views–likes–comments correlation (Pearson and Spearman, with significance testing)
  - Video duration against retention
  - Channel age against channel size
  - Expected-views modelling (which videos beat their own channel's baseline)
  - Subscriber efficiency (views per subscriber)
- 📈 **Sampling design**: the 5 top Korean channels in each of Fashion, Mukbang and Travel, up to 200 recent videos per channel, with Shorts and statistical outliers removed
- 🎨 **Visualisation suite**: word clouds, time series, correlation heatmaps, distribution plots

**Results:**
- **Daily uploading was optimal for only 3 of 15 channels** — the view-maximising interval is channel-specific, ranging from 1 day up to 8–14 days. There is no universal "best cadence."
- **For 10 of 15 channels, one upload interval maximised both views and likes** — cadence effects are consistent across engagement metrics
- **Channel age does not predict channel size** — older channels do not necessarily have more subscribers or total views
- **Regular uploaders average 23% more views** than irregular ones

**Tech Stack:** Python, KoNLPy, Pandas, Matplotlib, Seaborn, Word Clouds, Statistical Testing

**Note on scope:** the repository documents its own verified headline (2,125 videos / 15 channels / 3 categories) and explicitly lists the earlier unverifiable figures that were removed.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Youtube-Channel-Anaylsis-Project)

---

### 🏡 8. Korean Real Estate — Market Analysis (Jul – Sep 2024)
**Geospatial price modelling** across Korean regions

**Challenge:** Assemble a picture of the Seoul market that holds together — listings, macro indicators and city open data all come from different places, in different shapes, with Korean column names that don't match across sources.

**My Solution — collection and integration, which is where the actual work was:**
- 🕸️ **Zigbang API scrapers** across 4 endpoints — **177,794 listing IDs polled**, yielding **123,570 committed listing and transaction rows** across 8 datasets (one-room, apartment sales, commercial)
- 🧩 **Nested-JSON expansion**: transaction records arrive as JSON strings inside a column, unpacked into proper rows before anything can be joined
- 🗄️ **Multi-source integration**: listings merged with 11 years of Korean macro indicators (GDP, base rate, CPI, KRW/USD) and Seoul open data — **45 Excel datasets, 34 MB, 2013–2023**
- 🗺️ **Folium choropleth maps** and matplotlib charts by district — the interactive maps are the most polished artefact in the repo

**Results:**
- **Seoul lost residents to domestic migration in every single year from 2013 to 2023** — cumulative net **−961,881 people**, computed from the city's own migration dataset. A decade-long one-directional trend is a stronger finding than any single-year price correlation.
- **Apartment-sale listing concentration by district**: Eunpyeong-gu **403**, Gangseo-gu 388, Gangnam-gu 351
- **Macro series charted against the market period**: CPI inflation, CPI index and exchange rate across 2013–2023

**Tech Stack:** Python, Pandas, Requests, Folium, Matplotlib, openpyxl

**Scope, stated honestly:** this is a data collection, integration and visualisation project — there is no regression or forecasting model in it, and the repository says so rather than implying one. It is here because the collection and reconciliation work is real and the migration finding stands on its own.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Korean-Real-Estate-Project)

---

### 🎬 9. Movie Trip — Full-Stack Travel Platform (Dec 2025)
**Next.js 14 + TypeScript** — film locations, route planning and reviews

**Challenge:** Build a complete product, not a notebook — authentication, persistence, state management and maps, deployed as one application.

**My Solution:**
- 🔐 **JWT authentication** with protected routes
- 🗄️ **Prisma ORM over PostgreSQL** — **15 data models**
- 🗺️ **Interactive maps** covering **82 locations and 160 places**, with a 10-metre proximity threshold for location matching
- ⚛️ **Recoil state management** across **14 handlers in 9 files**
- 🏆 **Leaderboard and review system** for user contributions

**Tech Stack:** Next.js 14, TypeScript, Prisma, PostgreSQL, Recoil, JWT

**Why it's here:** it is the project that proves I can ship a working system end to end, not only analyse data.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Movie-Trip)

---

## 🛠️ Technical Skills

### 🔬 LLM Evaluation & Experimentation *(my differentiator)*
**Evaluation design** *(MECAGENT internship)*
- Rubric construction, sample selection, expert-built ground truth
- Machine-derived reference labels — after my hand-written key turned out to be the thing that was wrong
- Scorers that reproduce every number from saved artefacts with zero model calls

**Experiment discipline** *(MECAGENT internship, QoE project)*
- One variable at a time; acceptance criteria registered before the run
- Shuffled controls that can kill my own hypothesis
- Data-leakage detection and quantification
- Negative results published at the same length as positive ones

**Observability** *(MECAGENT internship)*
- MLflow — run tracking, model registry, experiment comparison
- Arize Phoenix — distributed tracing, span-level agent behaviour analysis
- Trace forensics across multi-hour agent sessions

![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat&logo=mlflow&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

### 🤖 LLM & NLP (Production Experience)
**LLM Fine-tuning** *(Synthetic-Instruction-Tuner)*
- LoRA, DPO, PEFT — 12.16M trainable parameters (0.67% of base)
- 4-bit quantisation for consumer-GPU training
- Magpie prompting — 1,500 synthetic samples at an 83.9% quality pass rate
- Synthetic data generation — zero-cost automated pipeline

**Transformers** *(SemEval 2026 — modular training/prediction pipeline)*
- RoBERTa fine-tuning — CCC 0.6554 against a 0.62 target
- BiLSTM ensembles, multi-head attention, dual-head output
- Mixed-precision training (fp16), multi-seed experiments for robustness

**Agentic Systems** *(MECAGENT internship)*
- LangChain, LangGraph — orchestrator/sub-agent architectures
- Model Context Protocol (MCP) tool integration
- Agents executing generated code against a live external application

**NLP** *(across projects)*
- Emotion prediction, sentiment analysis, bilingual Korean/English processing

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗_Transformers-FFD43B?style=flat&logoColor=black)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)
![WandB](https://img.shields.io/badge/WandB-FFBE00?style=flat&logo=weightsandbiases&logoColor=black)

### 📊 Machine Learning & Data Science
**ML Algorithms** *(QoE Prediction — 6-model comparison)*
- Random Forest, SVM, XGBoost, KNN, Gradient Boosting, Logistic Regression
- Ensemble methods — weighted averaging, stacking
- Class-balanced evaluation, macro F1 and kappa over raw accuracy

**Time Series** *(Agri Forecasting — 17 per-commodity models)*
- Seasonal ARIMA (statsmodels SARIMAX) for the 52-week horizon; stacked LSTM (Keras) per commodity
- Per-series tuning, EarlyStopping with best-weight restore, custom RMSE loss
- Seasonal decomposition, lag and rolling-window feature construction

**Data Engineering** *(DEFT — 102,321 records)*
- ETL pipelines, REST API integration (World Bank, SIPRI, UCDP, WGI)
- Entity reconciliation across disagreeing sources
- K-Means clustering, OLS regression across 170 countries

![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)

### 💻 Programming & Databases
**Primary Languages**
- **Python** (advanced) — 9 shipped projects, from notebook analysis to modular training pipelines
- **C#** — SolidWorks API automation, helper libraries with live self-checks
- **SQL** (advanced) — SQLD certified; PostgreSQL, and SQL against the company's CAD dataset for test-set selection
- **Java 11** — Insurance SOA, 1,927 lines across 17 files
- **TypeScript / JavaScript** — Movie Trip full-stack
- **R** — statistical analysis and visualisation

**Web Development**
- Next.js 14, React, Prisma ORM, Recoil
- Flask, FastAPI, Streamlit for model serving and dashboards

**Databases**
- PostgreSQL (Prisma ORM), SQLite, structured JSON data stores

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=next.js&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat&logo=oracle&logoColor=white)

### 🚀 MLOps & Production
**Experiment Tracking**
- MLflow — run tracking and model registry on long-horizon agent pipelines
- WandB — multi-seed experiments, ablation studies
- Git / GitHub — 9 public repositories

**Cloud & Serving**
- AWS Bedrock, GCP Vertex — frontier model access in production pipelines
- Docker, Linux — containerised environments
- Flask, FastAPI, Streamlit — API serving and interactive dashboards

**Testing**
- pytest — fixture tests, strict xfail for documented gaps
- Self-checks demonstrated firing in both directions before being claimed as protection

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat&logo=amazonaws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

### 📊 Visualisation & BI
**Business Intelligence** *(Hanwha Aerospace)*
- Power BI — defense analytics dashboards
- Tableau — interactive business reports

**Python Visualisation** *(all projects)*
- Matplotlib, Seaborn — statistical plots
- Folium, Leaflet — choropleth and interactive geospatial maps
- Chart.js, Leaflet — web-facing interactive charts

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)

---

## 🎓 Education

### MSc, Data Science & Network Intelligence
**Télécom SudParis — Institut Polytechnique de Paris**, France · 2025–2026

**Specialisation:** Large language models, NLP, deep learning, data engineering

**Relevant coursework:** Deep Learning & Neural Networks · Natural Language Processing · Big Data Analytics · Statistical Modeling & Time Series · Database Systems

### Bachelor's Degrees

**Tech University of Korea** — Siheung, South Korea
- B.Eng, Computer Engineering

**Changwon National University** — Changwon, South Korea
- B.Eng, Robot Control & Instrumentation Engineering

---

## 🏆 Achievements & Certifications

### 🥇 Awards
- **Best Performance Award** — Hanwha Aerospace big-data internship, team project on global defense trends, **1st of all teams**
- **SemEval 2026 Task 2** — CCC 0.6554, above the 0.62 target

### 📜 Certifications
- **SQLD** — SQL Developer, Korea Data Agency
- **SMAT** — Service Management Aptitude Test

### 📈 Technical Highlights
- **Seed variance quantified** — the same SemEval architecture scored CCC 0.5053–0.6554 across seeds, which bounds what any single run proves
- **5.5× lower validation loss than the control** — LoRA against prompt tuning on identical data, at zero API cost
- **33.3-point leakage gap quantified** — and the lower number published
- **210+ country-name variants reconciled** — DEFT, the step that made a four-source join possible
- **83.9% quality pass rate** — synthetic data filtering pipeline

---

## 💼 What I Bring

### ✅ I measure before I claim
Every number in this profile names what it was measured on. When my own improvement lost to the baseline, I reported that and recommended the baseline. When my hand-written reference labels turned out to be wrong and three models were right, I rebuilt the labels from geometry and wrote up why.

### ✅ I build the instrument first
On the internship system, the drawing-reading stage had no measurement at all, so I built one: a rubric anchored on ten reference parts a CAD expert built by hand, a scorer that reproduces every number from saved artefacts with zero model calls, and shuffled controls that killed four of my own proposed fixes before a reviewer had to.

### ✅ I ship inside a team's process
Pull requests, code review, trace-referenced technical reports, and adversarial verification of my own claims before they leave my desk — six months of it in a senior team at a funded startup.

### ✅ I work across the stack
Nine shipped projects spanning LLM fine-tuning, NLP research, multi-agent systems, time series, data engineering and full-stack web — in Python, C#, Java and TypeScript.

### ✅ I communicate in two languages and three registers
Korean (native), English (professional) — and the register that matters most: explaining a technical result to someone who has to make a decision with it.

---

## 📫 Let's Connect

**Graduating October 2026. Open to LLM Engineer / ML Engineer / AI Engineer roles in Paris and Europe** — work-authorised through the French post-graduation permit, open to hybrid or remote.

### 🎯 What I'm Looking For

- LLM evaluation, instrumentation and benchmarking
- Agentic and multi-agent system engineering
- Fine-tuning and alignment (LoRA, DPO, PEFT)
- Applied NLP — ideally where the output is verifiably right or wrong

### 📧 Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:xhangyong.hyun@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN)

---

<div align="center">

![Profile Views](https://komarev.com/ghpvc/?username=CY-HYUN&color=58A6FF&style=flat-square&label=Profile+Views)
![GitHub Followers](https://img.shields.io/github/followers/CY-HYUN?style=flat-square&color=58A6FF&labelColor=0D1117)

**⚡ "Build the measurement first."**

*Available from October 2026 · Paris / Europe · Remote-friendly*

</div>

<!-- Profile README — optimised for LLM / ML engineer roles — last updated 2026-09-16 -->
