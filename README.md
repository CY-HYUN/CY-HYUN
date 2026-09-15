<div align="center">

# 👋 Hi, I'm Changyong Hyun
<!-- GitHub Profile README - Last updated 2026-09-16 -->

### 🚀 AI/ML Engineer | LLM Evaluation & Agentic Systems | MSc @ Télécom SudParis (IP Paris)

🎯 **Available from October 2026** · 🇫🇷 **Paris / Europe** · 🔬 **6 months building multi-agent LLM systems in industry** · ⚡ **PyTorch · LangGraph · MLflow**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:xhangyong.hyun@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/CY-HYUN)

</div>

---

## 🎯 About Me

**Graduating October 2026 · Open to LLM / ML Engineer roles in Paris and Europe · Work-authorised via the French post-graduation permit**

AI/ML engineer finishing an MSc in Data Science & Network Intelligence at **Télécom SudParis (Institut Polytechnique de Paris)**, currently completing a six-month industry internship at a CAD-AI startup in France.

I build LLM and multi-agent systems, and I specialise in the part most teams skip: **deciding whether the thing actually works.** On my internship the hard problem was never generation — it was that the score we graded outputs with couldn't detect several ways a result can be wrong. A part built mirrored scored about the same as the correct one. So most of my work became evaluation design: build the instrument first, then let it decide what to change.

**Core Expertise:**
- 🔬 **Evaluation design for generative systems** — rubrics against expert-built ground truth, reference labels derived from geometry rather than written by hand, pre-registered acceptance criteria
- 🤖 **LLM fine-tuning** — LoRA, DPO, PEFT (12.16M trainable parameters, +9.7% over base, zero API cost)
- 🕸️ **Agentic & multi-agent systems** — LangChain, LangGraph, orchestrator/sub-agent architectures against a live external application
- 📈 **Observability** — MLflow run tracking, Arize Phoenix tracing, reading agent behaviour span by span
- 🧪 **Controlled experiments** — one variable at a time, shuffled controls, negative results reported at the same length as positive ones

**What I'm known for:**
- 🏅 **SemEval 2026 Task 2** — CCC **0.6554** against a 0.62 target, measured on the best single model
- 🔍 **A leakage analysis that changed the answer** — found a **33.3-point** gap and reported the lower number
- 🧰 **Instruments that outlive the code** — my scorers still reproduce every number from saved files after the pipeline around them was rebuilt twice
- 🎖️ **Best Performance Award** — Hanwha Aerospace big-data internship

---

## 💼 Current Role

### 🔧 AI Engineer Intern — CAD-AI startup, France (May – Oct 2026)

**The system:** reads mechanical engineering drawings and rebuilds the part in CAD automatically — vision models for reading, a multi-agent system for code generation, executed against a live external application rather than a simulator.

**My lane:** evaluation and experiment design — the layer that decides whether a change actually helped.

- 🎯 **Designed the evaluation for the drawing-reading stage** against ten reference parts built by hand by the company's CAD expert, so no model ever graded another model's output. Built the rubric, chose the sample, and wrote a scorer that reproduces every number from saved files with **no model call**.
- 🔍 **Showed the benchmark score was blind to whole classes of error** — a mirrored part, a rotated part, and an imitated fold all scored about the same as correct ones. Built deterministic checks that could see each, and those checks became the basis for everything after.
- 🧪 **Ran controlled experiments with acceptance criteria registered before the run.** Reported two pre-registered negative results as negatives — including one where my own proposed improvement didn't survive its control.
- 🪞 **Caught my own reference labels being wrong** when three models disagreed with them. From then on every label came from geometry, not from my hands.
- 🤝 **Worked the team's review process throughout** — pull requests, trace-referenced technical reports, and adversarial verification of my own claims before sending them.

**Tech:** Python · C# · LangChain / LangGraph · MLflow · Arize Phoenix · vision-language models · pytest

> *The company's results are covered by a confidentiality agreement, so this section describes method and role rather than internal numbers. Happy to go deeper in conversation.*

---

## 🌟 Featured Projects

### 🏅 1. SemEval 2026 Task 2 — Emotion Prediction (Oct 2025 – Jan 2026)
**CCC 0.6554** — international NLP competition, against a 0.62 target

**Challenge:** Predict emotional response (valence and arousal) from temporal sequences of a user's posts, where a single post carries little signal without the user's history.

**My Solution:**
- 🧠 **User-level embeddings** — aggregated a user's historical posts into a dense representation, the single largest contributor in the ablation
- 🔬 **RoBERTa + BiLSTM** for temporal dependencies across the post sequence
- 🎯 **Dimension-specific loss weighting** — an arousal-specialist model with heavier CCC weighting on the harder dimension
- 📊 **47 engineered features** — temporal lags, rolling statistics, linguistic patterns, user statistics
- ⚡ **Mixed-precision training** with multi-seed runs (42, 123, 777, 888, 1111) for robustness
- 📈 **Systematic ablations** — quantified each component separately instead of asserting a stack

**Results:**
- **Overall CCC 0.6554** — best single model (seed 777), **+5.7% over the 0.62 target**
- **Valence CCC 0.7593** · **Arousal CCC 0.5832** (+6.0% with the specialist model)
- **The 2-model ensemble beat the 3- and 5-model ones** — more models was the wrong lever
- **Dimension-specific optimisation beat multi-task learning** — the finding I'd defend in an interview

**Tech Stack:** PyTorch · Hugging Face Transformers · BiLSTM · WandB · Mixed Precision · Ensemble Methods

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Deep-Learning-project-SemEval-2026-Task-2)

---

### 🤖 2. Synthetic-Instruction-Tuner — Zero-Cost LLM Fine-Tuning (Nov 2025 – Jan 2026)
**+9.7% over base** — no seed data, no paid API, at any stage

**Challenge:** Fine-tune an instruction-following model without API costs or human annotation — and show the result is real rather than an artefact of an easy benchmark.

**My Solution — a 6-stage pipeline:**
1. **Magpie prompting** — template-only synthetic generation, no seed dataset required
2. **Quality filtering** — a 6-dimension gate (relevance, coherence, informativeness, safety, diversity, instruction-following) at an **83.9% pass rate**
3. **Preference-pair generation** — chosen/rejected pairs via multi-temperature sampling
4. **LoRA fine-tuning** — **12.16M trainable parameters** (0.67% of the model), 4-bit quantised
5. **Prompt tuning** — evaluated as an alternative adaptation method
6. **DPO alignment** — direct preference optimisation on the generated pairs

**Results:**
- **+9.7%** over the base model on a mixed benchmark
- **Zero cost** — no API fees, no human labelling
- **Consumer-GPU trainable** — 4-bit quantisation kept it inside a single commodity GPU
- **Honest artefact note in the repo** — the committed notebook output is a demo fallback, and the repo says so rather than implying a full run

**Tech Stack:** Hugging Face PEFT · LoRA · DPO · 4-bit quantisation · Magpie prompting

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Synthetic-Instruction-Tuner)

---

### 🔍 3. QoE Prediction — the Leakage Analysis That Changed the Answer (Oct – Dec 2025)
**33.3-point gap** — where the real result is the integrity work

**Challenge:** Predict user-perceived mobile-streaming quality (MOS 1–5) from session data. The obvious model looked excellent. It wasn't.

**My Solution:**
- 🚩 **Found the leak** — the strong model leaned on features only available *after* a session ends, which a deployed system would never have at prediction time
- ✂️ **Rebuilt the experiment** restricted to objectively-available features, with class balancing
- 📊 **Reported both numbers side by side** and led with the lower one
- 🔁 **Made it reproducible** — the experiment script is committed and was re-run twice, byte-identical

**Results:**
- **81.6%** with leaky post-session features · **48.2%** objective-only (macro F1 0.442, kappa 0.261)
- **A 33.3-point leakage gap**, quantified rather than hand-waved
- The objective-only model sits *below* the majority-class baseline on raw accuracy but far above it on balanced metrics — the honest trade-off, stated as one

**Tech Stack:** scikit-learn · Gradient Boosting · Random Forest · class-balanced evaluation

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Poqemon-QoE-Dataset-master)

---

### 🌍 4. DEFT — Defense Export Market Analysis (Sep – Dec 2024)
**102,321 records across 170 countries** — multi-source ETL and scoring

**Challenge:** Combine economic, political and conflict data into a usable market-feasibility view, when the three sources disagree about what a country is even called.

**My Solution:**
- 🗄️ **Multi-source ETL** — World Bank API, SIPRI military expenditure, UCDP conflict data, WGI governance indicators
- 🧹 **Country-name reconciliation** — mapped 210+ naming variations onto a single canonical set, the step that made the join possible at all
- 📐 **Weighted three-dimensional scoring** across economic, political and conflict axes
- 📊 **K-Means clustering** for A/B/C country classification and **OLS regression** (R² = 0.366) to identify the strongest predictor
- 🗺️ **Interactive platform** — Oracle DB, Leaflet map, Chart.js

**Results:**
- **102,321 records · 170 countries** integrated into one queryable warehouse
- **Analysis time cut from 5 hours to 30 minutes**
- Economic score emerged as the strongest predictor in the regression

**Tech Stack:** Python · Pandas · NumPy · scikit-learn · Oracle DB · Leaflet · Chart.js

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Global-Defense-Export-Analysis-Project)

---

### 📈 5. Agricultural Price Forecasting (Sep – Dec 2024)
**52-week horizon** — SARIMAX + LSTM for procurement planning

**Challenge:** Forecast commodity prices far enough ahead to change purchasing decisions, across commodities with very different seasonality.

**My Solution:**
- 📊 **Hybrid approach** — SARIMAX for seasonality and external regressors, LSTM for non-linear patterns
- 🔢 **100+ engineered features** — lags, rolling statistics, seasonal decomposition, economic indicators
- 🌐 **Flask application** with dashboards for procurement planning
- 🔄 **Automated ETL** with scheduled data refresh

**Tech Stack:** Python · SARIMAX · LSTM · TensorFlow · Flask · Streamlit · Power BI

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Defense-Agri-Price-Forecasting-main)

---

### 🏢 6. Insurance SOA — Multi-Protocol Service Architecture (Dec 2025 – Jan 2026)
**4 protocols, one gateway** — REST · SOAP · gRPC · GraphQL

**Challenge:** Serve insurance claim processing to clients that each speak a different protocol, without four separate backends.

**My Solution:**
- 🔄 **XOR gateway orchestration** routing each request to the right protocol handler
- 🌐 **Four implementations** — REST (Jersey), SOAP (JAX-WS), gRPC (Protocol Buffers), GraphQL (introspection)
- ☕ **Java 11**, ~1,927 lines across 17 files, Maven build, Tomcat deployment
- 🧪 **Protocol-specific client applications** plus an 11-request Postman collection for validation
- ⚖️ **Benchmarked the four** on latency and payload size rather than assuming

**Tech Stack:** Java 11 · Maven · Jersey · JAX-WS · gRPC · GraphQL · Tomcat

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Insurance-Claim-Processing-SOA)

---

### 📺 7. YouTube Analytics — Korean Content Strategy (Jul – Sep 2024)
**2,125 videos** — bilingual NLP across 15 channels and 3 categories

**Challenge:** Turn channel performance data into recommendations a creator could act on, across Korean and English text.

**My Solution:**
- 🌐 **Bilingual NLP** — Korean morphological analysis plus English sentiment
- 📊 **Eight analytical frameworks** — upload timing, title keywords, subscriber ROI, engagement modelling, length vs retention, category benchmarking, seasonal trends
- 📈 **Statistical testing** rather than eyeballed correlations
- 🎨 **Visualisation suite** — word clouds, time series, correlation heatmaps

**Tech Stack:** Python · KoNLPy · Pandas · Matplotlib · Seaborn · statistical testing

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Youtube-Channel-Anaylsis-Project)

---

### 🏡 8. Korean Real Estate — Market Analysis (Jul – Sep 2024)
**Geospatial price modelling** across Korean regions

**Challenge:** Explain regional price differences with something better than "location matters".

**My Solution:**
- 🏠 **Multi-feature regression** — location, property characteristics, market indicators, temporal trends
- 🗺️ **Geospatial analysis** — choropleth maps, Folium interactive clustering, GeoPandas spatial statistics
- 📊 **Temporal trend analysis** across regions and years

**Tech Stack:** Python · scikit-learn · GeoPandas · Folium · regression analysis

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Korean-Real-Estate-Project)

---

### 🎬 9. Movie Trip — Full-Stack Travel Platform (Dec 2025)
**Next.js 14 + TypeScript** — film locations, routes and reviews

Full-stack application for discovering Korean filming locations: JWT authentication, Prisma ORM, Recoil state management, interactive maps and a leaderboard. 82 locations and 160 places modelled across 15 data models.

**Tech Stack:** Next.js 14 · TypeScript · Prisma · PostgreSQL · Recoil

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Movie-Trip)

---

## 🛠️ Technical Skills

### 🔬 LLM Evaluation & Experimentation *(my differentiator)*
- **Evaluation design** — rubric construction, sample selection, expert-built ground truth, scorers that run with no model call
- **Experiment discipline** — one variable at a time, pre-registered acceptance criteria, shuffled controls, negative results published
- **Adversarial verification** — refuting my own claims before they ship
- **Observability** — MLflow (run tracking, model registry), Arize Phoenix (tracing), span-level trace analysis

![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat&logo=mlflow&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

### 🤖 LLM & NLP
- **Fine-tuning** — LoRA, DPO, PEFT, 4-bit quantisation, synthetic data generation (Magpie)
- **Transformers** — RoBERTa/BERT fine-tuning, BiLSTM ensembles, mixed-precision training
- **Agentic systems** — LangChain, LangGraph, orchestrator/sub-agent architectures, MCP
- **Applied NLP** — emotion prediction, sentiment analysis, bilingual Korean/English processing

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗_Transformers-FFD43B?style=flat&logoColor=black)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)
![WandB](https://img.shields.io/badge/WandB-FFBE00?style=flat&logo=weightsandbiases&logoColor=black)

### 📊 Machine Learning & Data Science
- **Algorithms** — Random Forest, SVM, XGBoost, Gradient Boosting, K-Means, OLS regression
- **Time series** — SARIMAX, LSTM, GRU, seasonal decomposition
- **Data engineering** — multi-source ETL, REST API integration, feature engineering, entity reconciliation
- **Evaluation** — class-balanced metrics, leakage detection, ablation studies

![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)

### 💻 Programming & Infrastructure
- **Python** (advanced) · **SQL** (SQLD certified) · **C#** · **Java** · **TypeScript** · **R**
- **Databases** — PostgreSQL, Oracle DB, Prisma ORM
- **Web** — Next.js, React, Flask, FastAPI, Streamlit
- **Tooling** — Git, pytest, Docker, Linux, AWS Bedrock / GCP Vertex

![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

---

## 🎓 Education

### MSc, Data Science & Network Intelligence
**Télécom SudParis — Institut Polytechnique de Paris**, France · 2025–2026
*Large language models · NLP · deep learning · data engineering*

### Bachelor's Degrees
- **Tech University of Korea** — B.Eng Computer Engineering
- **Changwon National University** — B.Eng Robot Control & Instrumentation Engineering

---

## 🏆 Achievements & Certifications

- 🥇 **Best Performance Award** — Hanwha Aerospace big-data internship (team project on global defense trends, 1st of all teams)
- 🏅 **SemEval 2026 Task 2** — CCC 0.6554, above the 0.62 target
- 📜 **SQLD** — SQL Developer certification, Korea Data Agency
- 📜 **SMAT** — Service Management Aptitude Test

---

## 💼 What I Bring

### ✅ I measure before I claim
Every number in this profile names what it was measured on. When my own improvement lost to the baseline, I reported that. When my hand-written reference labels turned out to be wrong and three models were right, I rebuilt the labels from geometry and wrote it down.

### ✅ I build the instrument first
Evaluation design is the skill I'd bring on day one: rubrics against ground truth that can't share the model's blind spots, scorers that reproduce their numbers with no model call, and controls that can kill my own hypothesis.

### ✅ I ship inside a team's process
Pull requests, code review, trace-referenced technical reports, and adversarial verification before anything leaves my desk.

### ✅ I work across the stack
Nine shipped projects spanning LLM fine-tuning, NLP research, multi-agent systems, time series, data engineering, and full-stack web — in Python, C#, Java and TypeScript.

---

## 📫 Let's Connect

**Graduating October 2026. Open to LLM Engineer / ML Engineer / AI Engineer roles in Paris and Europe** — work-authorised through the French post-graduation permit, and open to hybrid or remote.

**What I'm looking for:** LLM evaluation and instrumentation · agentic and multi-agent systems · fine-tuning and alignment · applied NLP — ideally somewhere the output is verifiably right or wrong.

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
