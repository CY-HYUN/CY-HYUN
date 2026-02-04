<div align="center">

# 👋 Hi, I'm Changyong Hyun
<!-- GitHub Profile README - Last updated 2026-02-05 -->

### 🚀 LLM Engineer | MSc Student @ Télécom SudParis

🏆 **Top Rank SemEval 2026** (CCC 0.6833, 13% Above Baseline) | 🔥 **Production LLM Systems** | 🚀 **8 Shipped ML Projects** | ⚡ **PyTorch & Transformers Expert**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:changyong.hyun@telecom-sudparis.eu)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/CY-HYUN)

</div>

---

## 🎯 About Me

**Actively seeking 6-month LLM Engineer / ML Engineer / Data Scientist internship (starting before July 2026)**

Data Science master's student (M2) at **Télécom SudParis (Institut Polytechnique de Paris)** specializing in **LLM fine-tuning**, **deep learning**, and **production ML systems**. Experienced in **end-to-end ML pipelines** from synthetic data generation to deployment workflows, with expertise in **Model Context Protocol (MCP)** for advanced LLM integration.

**Core Expertise:**
- 🤖 **LLM Fine-tuning**: LoRA, DPO, PEFT achieving 9.7% improvement (57.5% on MMLU/HellaSwag/ARC/TruthfulQA)
- 🏆 **Competitive NLP Research**: SemEval 2026 Top rank (CCC 0.6833, 13% above target)
- 📊 **Large-scale Data Engineering**: 77,400+ data points across 172 countries
- 🚀 **Production ML Systems**: PyTorch, Hugging Face Transformers, Docker, Kubernetes

**Key Achievements:**
- 🏆 **Top rank** in SemEval 2026 International NLP Competition (CCC 0.6833, 13% above target baseline)
- 🚀 **+9.7% model improvement** through zero-cost synthetic data generation and parameter-efficient fine-tuning
- ⚡ **90% time reduction** in multi-source data engineering pipelines (5 hours → 30 minutes)
- 📊 **50,000+ video analysis** with bilingual NLP (Korean/English) for actionable business insights
- 🎖️ **Best Performance Award** at Hanwha Aerospace (Big Data Internship)

---

## 🌟 Featured Projects

### 🏆 1. SemEval 2026: Deep Learning NLP Competition (Oct 2025 - Jan 2026)
**Top Rank Performance** - CCC 0.6833 in international emotion prediction competition

**Challenge:** Predict emotional responses (Valence/Arousal) from temporal text sequences across Reddit conversations spanning multiple posts per user.

**My Solution:**
- 🔥 **Production-grade 721-line pipeline** with modular architecture (data, features, models, training, evaluation)
- 🎯 **Novel user-level embeddings**: Aggregated historical posts into 768-dim representations → **+0.226 CCC improvement** (single biggest contribution)
- 🧠 **RoBERTa ensemble**: 3 transformer models + BiLSTM for temporal dependencies
- 📊 **39 engineered features**: Sentiment scores, emotion intensities, linguistic patterns, user statistics
- ⚡ **Mixed precision training** (fp16) with multi-seed experiments (42, 123, 777) for robustness
- 📈 **Comprehensive ablation studies**: Quantified contribution of each component (user embeddings > additional features > BiLSTM)

**Results:**
- **Valence CCC: 0.7593** (strong positive emotion prediction)
- **Arousal CCC: 0.5832** (challenging dimension, +6% with specialized model)
- **Overall CCC: 0.6833** (13% above target baseline of 0.62, Top rank performance)
- **50% improvement** over naive baseline (0.45 → 0.68 CCC)

**Tech Stack:** PyTorch, Transformers (Hugging Face), BiLSTM, WandB, Mixed Precision Training, Ensemble Methods

**Deliverables:** 31-slide presentation (3.3 MB), comprehensive technical report (204 KB), interactive demo notebook

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Deep-Learning-project-SemEval-2026-Task-2)

---

### 🤖 2. LLM Fine-tuning: Synthetic-Instruction-Tuner (Nov 2025 - Jan 2026)
**+9.7% model improvement** - Zero-cost synthetic data generation pipeline

**Challenge:** Fine-tune Llama-3.1-8B for instruction-following without expensive API costs or human annotation.

**My Solution - 6-Stage End-to-End Pipeline:**

1. **Magpie Prompting (Stage 1):**
   - Generated 1,500 synthetic instruction-response pairs
   - Zero API costs using base model's own capabilities
   - Diverse task coverage (Q&A, summarization, reasoning, creative writing)

2. **Quality Filtering (Stage 2):**
   - 6-dimensional quality scoring: relevance, coherence, informativeness, safety, diversity, instruction-following
   - **83.9% pass rate** (1,259/1,500 samples)
   - Automated multi-filter pipeline (no human annotation)

3. **Preference Pair Generation (Stage 3):**
   - Created chosen/rejected pairs for DPO training
   - Systematic degradation strategies for negative examples

4. **LoRA Fine-tuning (Stage 4):**
   - **12.16M trainable parameters** (0.15% of total)
   - 4-bit quantization for memory efficiency
   - Rank-16 LoRA adapters on attention layers

5. **Prompt Tuning (Stage 5):**
   - Optimized instruction templates
   - Few-shot example selection

6. **DPO Alignment (Stage 6):**
   - Direct Preference Optimization for human-aligned outputs
   - Balanced chosen/rejected pair training

**Results:**
- **+9.7% improvement** over baseline Llama-3.1-8B
- **Zero cost**: No API fees, no human labeling
- **4× faster completion**: 7 days vs planned 28 days
- **Memory efficient**: 4-bit quantization enabled training on consumer GPU

**Tech Stack:** Llama-3.1-8B, Hugging Face PEFT, LoRA, DPO, 4-bit Quantization, Magpie Prompting

**Key Innovation:** Fully automated, zero-cost approach to LLM fine-tuning competitive with supervised methods

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Synthetic-Instruction-Tuner)

---

### 📊 3. QoE Prediction: Mobile Streaming Quality (Oct-Dec 2025)
**81.9% accuracy** - Machine Learning classification for Quality of Experience prediction

**Challenge:** Predict user-perceived video quality (MOS scores 1-5) from 1,543 mobile streaming sessions to optimize CDN delivery.

**My Solution:**
- 📊 **Systematic model comparison**: Evaluated 6 ML algorithms (Random Forest, SVM, XGBoost, KNN, Decision Tree, Logistic Regression)
- 🎯 **Feature engineering**: Network metrics (bitrate, packet loss, jitter), device characteristics, temporal patterns
- 🏆 **Best model**: Random Forest with 81.9% accuracy
- 📈 **Feature importance analysis**: Identified bitrate variability and packet loss as top predictors
- ⚡ **Real-time prediction**: Optimized for low-latency inference (<50ms)

**Results:**
- **81.9% classification accuracy** (Random Forest)
- **F1-score: 0.82** for critical quality levels (MOS 1-2)
- **Business impact**: Enabled proactive CDN optimization before user complaints

**Tech Stack:** Scikit-learn, Random Forest, SVM, XGBoost, Pandas, Feature Engineering

**Application:** Production-ready model for CDN quality monitoring and adaptive streaming optimization

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Poqemon-QoE-Dataset-master)

---

### 🌍 4. DEFT: Defense Export Feasibility Tracker (Sep-Dec 2024)
**77,400+ data points** - Large-scale data engineering across 172 countries

**Challenge:** Analyze defense export feasibility combining economic, political, and conflict indicators for strategic decision-making.

**My Solution:**
- 🗄️ **Multi-source ETL pipeline**:
  - World Bank API: 15 economic indicators (GDP, trade balance, inflation, etc.)
  - SIPRI: Military expenditure data
  - UCDP: Armed conflict databases
  - **26.54 MB structured data warehouse**
- 📊 **172 countries × 30 years × 15 indicators = 77,400 data points**
- 🔍 **K-Means clustering**: Segmented countries into 4 risk categories
- 📈 **OLS regression**: Identified key predictors of export success
- 💡 **Novel cycloid weighting**: Custom algorithm for multi-dimensional scoring
- ⚡ **90% automation**: Reduced analysis time from 5 hours → 30 minutes

**Results:**
- **4 country clusters**: High-potential, stable, volatile, restricted markets
- **Key insights**: GDP growth and political stability > conflict history for export success
- **Actionable scoring**: 0-100 feasibility score per country
- **Automated reporting**: Weekly updates with new data integration

**Tech Stack:** Python, Pandas, NumPy, Multi-source APIs, K-Means, OLS Regression, Data Warehousing

**Impact:** Strategic tool for defense industry market entry decisions

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Global-Defense-Export-Analysis-Project)

---

### 📈 5. Agricultural Price Forecasting (Sep-Dec 2024)
**52-week predictions** - Time series forecasting for military food service optimization

**Challenge:** Predict agricultural commodity prices (50+ products) to optimize military food service procurement and budgeting.

**My Solution:**
- 📊 **Hybrid SARIMAX + LSTM ensemble**:
  - SARIMAX: Captures seasonality, trends, external regressors
  - LSTM: Models complex non-linear patterns
  - Ensemble: Weighted average for robust predictions
- 🔢 **100+ engineered features**:
  - Lag features (1-52 weeks)
  - Rolling statistics (mean, std, min, max)
  - Seasonal decomposition components
  - External economic indicators (inflation, exchange rates)
- 🌐 **Flask API**: RESTful endpoints for real-time predictions
- 📊 **Power BI dashboards**: Interactive visualizations for procurement planning
- 🔄 **Automated ETL**: Weekly data updates and model retraining

**Results:**
- **52-week ahead forecasting** with confidence intervals
- **MAPE < 15%** for most commodities
- **Cost savings**: Optimized procurement timing based on price predictions
- **Production deployment**: Flask API serving 1000+ requests/day

**Tech Stack:** Python, SARIMAX, LSTM, TensorFlow, Flask, Power BI, Pandas, Time Series Analysis

**Business Value:** Enabled proactive budgeting and strategic procurement for military food services

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Defense-Agri-Price-Forecasting)

---

### 🏢 6. Insurance SOA: Multi-Protocol Service Architecture (Dec 2025 - Jan 2026)
**4-protocol implementation** - Production-grade service-oriented architecture

**Challenge:** Design scalable insurance claim processing system supporting multiple communication protocols for different client types.

**My Solution:**
- 🔄 **XOR Gateway Orchestration**: Intelligent routing logic for protocol selection
- 🌐 **4 Protocol Types**:
  - REST (Jersey): JSON-based for web clients
  - SOAP (JAX-WS): XML-based for legacy enterprise systems
  - gRPC: High-performance binary for microservices
  - GraphQL: Flexible querying for modern frontends
- ☕ **Production-grade Java 11**: ~1,200 lines across 23 Java files
- 🧪 **4 Client applications**: Protocol-specific testing and validation
- 📦 **Apache Maven**: Dependency management and build automation
- 🚀 **Tomcat 9.0.113**: Production server deployment

**Results:**
- **Protocol comparison**: Benchmarked performance, latency, payload size across 4 protocols
- **Workflow automation**: Automated claim routing, validation, approval processes
- **Scalable architecture**: Modular design supporting easy protocol addition

**Tech Stack:** Java 11, Apache Maven, REST (Jersey), SOAP (JAX-WS), gRPC, GraphQL, Tomcat 9.0.113

**Architecture Pattern:** Service-oriented architecture (SOA) with gateway orchestration

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Insurance-Claim-Processing-SOA)

---

### 📺 7. YouTube Analytics: Korean Content Analysis (Jul-Sep 2024)
**50,000+ videos** - Bilingual NLP for content strategy optimization

**Challenge:** Analyze Korean YouTube channels to identify success factors and provide data-driven content strategy recommendations.

**My Solution:**
- 🌐 **Bilingual NLP pipeline**: Korean-English text processing
  - Korean morphological analysis (KoNLPy)
  - English sentiment analysis (VADER)
  - Cross-language topic modeling
- 📊 **8 analytical frameworks**:
  - Upload timing optimization (hour-of-day, day-of-week analysis)
  - Title keyword correlation with views
  - Subscriber ROI (views per subscriber)
  - Engagement rate modeling (likes/comments/shares)
  - Video length vs. retention analysis
  - Thumbnail effectiveness (CTR prediction)
  - Category performance benchmarking
  - Seasonal trend detection
- 📈 **200+ visualizations**: Word clouds, time series, correlation heatmaps, distribution plots
- 🎯 **Actionable insights**: Specific recommendations per channel category

**Results:**
- **23% view increase** through optimized upload timing (peak hours: 6-9 PM KST)
- **Top performing titles**: Question format + emotional keywords → +35% CTR
- **Optimal video length**: 8-12 minutes for maximum retention
- **Category insights**: Gaming (highest engagement), Education (highest subscriber loyalty)

**Tech Stack:** Python, KoNLPy, VADER, Pandas, Matplotlib, Seaborn, Word Clouds, Statistical Testing

**Deliverable:** Comprehensive 100+ page analytical report with 8 channel-specific strategy guides

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Youtube-Channel-Anaylsis-Project)

---

### 🏡 8. Korean Real Estate: Market Analysis (Jul-Sep 2024)
**Price prediction** - Regression analysis for housing market intelligence

**Challenge:** Predict housing prices and identify market trends across Korean regions for investment decision-making.

**My Solution:**
- 🏠 **Multi-feature regression**:
  - Location features (district, proximity to subway, schools)
  - Property characteristics (size, age, floor level, parking)
  - Market indicators (transaction volume, interest rates)
  - Temporal trends (seasonal patterns, year-over-year changes)
- 🗺️ **Geospatial visualization**:
  - Choropleth maps (regional price heatmaps)
  - Folium interactive maps (cluster analysis)
  - GeoPandas spatial statistics
- 📊 **Temporal trend analysis**:
  - Price trajectories (2018-2024)
  - Regional comparison (Seoul, Busan, Gyeonggi)
  - Correlation studies (price vs. infrastructure development)
- 💼 **Investment insights**: ROI predictions, growth potential scoring

**Results:**
- **R² = 0.87** for price prediction model
- **Regional patterns**: Seoul premium +40% vs. national average
- **Trend detection**: Identified emerging high-growth districts
- **Actionable recommendations**: Investment timing and location strategies

**Tech Stack:** Python, Scikit-learn, GeoPandas, Folium, Regression Analysis, Spatial Statistics

**Application:** Real estate investment advisory and market intelligence platform

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Korean-Real-Estate-Project)

---

## 🛠️ Technical Skills

### 🤖 LLM & NLP (Production Experience)
**LLM Fine-tuning** *(Synthetic-Instruction-Tuner project)*
- LoRA, DPO, PEFT - Achieved 57.5% on MMLU/HellaSwag/ARC/TruthfulQA
- 4-bit Quantization - Trained 12.16M params (0.15% of total)
- Magpie Prompting, Prompt Engineering - Generated 1,500 synthetic samples with 83.9% quality pass rate
- Synthetic Data Generation - Zero-cost automated pipeline

**Transformers** *(SemEval 2026 project - 721-line pipeline)*
- RoBERTa, BERT fine-tuning - CCC 0.6833 (Top rank)
- BiLSTM ensembles - 3-model weighted averaging
- Ensemble Learning - Multi-model orchestration for robust predictions
- Mixed Precision Training (fp16), Model Optimization - Multi-seed experiments (42, 123, 777)

**NLP** *(8 projects)*
- Emotion Prediction, Sentiment Analysis - SemEval 2026
- Bilingual Text Processing (Korean/English) - YouTube Analytics (50,000+ videos)

**Tools**
- PyTorch, Hugging Face Transformers, WandB (experiment tracking)

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗_Transformers-FFD43B?style=flat&logoColor=black)
![WandB](https://img.shields.io/badge/WandB-FFBE00?style=flat&logo=weightsandbiases&logoColor=black)

### 📊 Machine Learning & Data Science
**ML Algorithms** *(QoE Prediction - 81.9% accuracy)*
- Random Forest, SVM, XGBoost, KNN - 6-model comparison
- Ensemble Methods - Weighted averaging, stacking

**Time Series** *(Agri Forecasting - 52-week predictions)*
- SARIMAX, LSTM, GRU - Hybrid ensemble approach
- Seasonal Decomposition - Real-time data processing with Streamlit

**Data Engineering** *(DEFT project - 77,400+ data points)*
- ETL Pipelines, REST API - World Bank API, SIPRI, UCDP integration
- Feature Engineering - 39-100+ features per project
- K-Means Clustering, OLS Regression - 172 countries analysis

**Core Tools**
- Python: Pandas, NumPy, Scikit-learn
- TensorFlow (LSTM/GRU models)
- Statistical Testing, EDA, Data Visualization

![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)

### 💻 Programming & Databases
**Primary Languages**
- **Python** (Advanced) - 8 production projects, 721-line modular pipeline
- **SQL** (Advanced) - SQLD Certified, Oracle DB, PostgreSQL
- **R** - Statistical analysis, data visualization
- **C** - System programming, performance optimization

**Web Development** *(Movie Trip project)*
- React.js, Next.js 14 - Full-stack web application
- TypeScript, JavaScript - Modern frontend development

**Databases** *(Hanwha Aerospace internship)*
- Oracle DB - Enterprise data management
- PostgreSQL - Movie Trip full-stack app
- Hadoop - Big data processing

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat&logo=oracle&logoColor=white)
![Hadoop](https://img.shields.io/badge/Hadoop-66CCFF?style=flat&logo=apachehadoop&logoColor=black)

### 🚀 MLOps & Production
**Experiment Tracking** *(SemEval 2026)*
- WandB - Multi-seed experiments, ablation studies
- Version Control - Git, GitHub (8 public repositories)

**Deployment** *(Agri Forecasting)*
- Docker, Kubernetes - Containerized ML environments and orchestration
- Flask, FastAPI - API serving for price predictions
- Streamlit - Real-time interactive dashboards
- AWS, Linux - Cloud infrastructure and system administration

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat&logo=amazonaws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

### 📊 Visualization & BI Tools
**Business Intelligence** *(Hanwha Aerospace internship)*
- Power BI - Defense analytics dashboards
- Tableau - Interactive business reports

**Python Visualization** *(All projects)*
- Matplotlib, Seaborn - Statistical plots (200+ visualizations)
- Plotly - Interactive charts

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)

---

## 🎓 Education

### MSc in Data Science & Network Intelligence
**Télécom SudParis (Institut Polytechnique de Paris)** - Paris, France (2025-2026)

**Specialization:** Large Language Models, NLP, Deep Learning, Data Engineering

### Bachelor's Degrees

**Tech University of Korea** - Siheung, South Korea (2023-2025)
- Bachelor's degree in Computer Engineering

**National Center for Lifelong Learning** - Seoul, South Korea (2022-2023)
- Bachelor's degree in Business Administration

**Changwon National University** - Changwon, South Korea (2021-2023)
- Bachelor's degree in Robot Control Measurement Engineering

---

## 🏆 Achievements & Certifications

### 🥇 Competitions & Awards
- **SemEval 2026 Task 2** - Top rank (CCC 0.6833) - International NLP competition with 100+ teams
- **Best Performance Award** - Hanwha Aerospace (Big Data Internship)

### 📜 Professional Certifications
- **SQLD** - SQL Developer Certification (Korea Data Agency)
- **SMAT** - Service Management Aptitude Test

### 📈 Technical Metrics
- **721-line production pipeline** - SemEval competition (modular, documented, tested)
- **+9.7% model improvement** - LLM fine-tuning with zero API costs (57.5% on MMLU/HellaSwag/ARC/TruthfulQA)
- **90% time reduction** - Data engineering automation (5 hours → 30 minutes)
- **81.9% ML accuracy** - QoE prediction for real-time systems
- **83.9% quality pass rate** - Synthetic data generation pipeline

---

## 💼 What I Bring to Your Team

### ✅ Proven Technical Excellence
- **Competition success**: Top rank in international NLP competition (SemEval 2026)
- **Production-quality code**: 721-line modular pipeline with documentation and testing
- **Research depth**: Published-quality technical reports and ablation studies

### ✅ Fast Execution & Adaptability
- **4× faster delivery**: Completed LLM project in 7 days (planned: 28 days)
- **Self-directed learning**: Mastered DPO, LoRA, PEFT independently
- **Diverse tech stack**: 8 projects across NLP, ML, data engineering, full-stack

### ✅ End-to-End Ownership
- **Research → Deployment**: Complete project lifecycle experience
- **MLOps mindset**: WandB tracking, Docker, reproducible experiments
- **Business impact**: Always translate technical work to measurable outcomes

### ✅ Communication & Collaboration
- **Bilingual**: English (professional) + Korean (native)
- **Technical writing**: Comprehensive documentation, presentations, reports
- **Open source**: Active GitHub contributor with clean, documented code

---

## 📫 Let's Connect!

I'm actively seeking **LLM Engineer / ML Engineer / Data Scientist internship** opportunities for **6-month internship starting before July 2026**.

### 🎯 What I'm Looking For

**LLM Engineer:**
- LLM fine-tuning (LoRA, DPO, RLHF), model alignment, prompt engineering
- Generative AI systems, retrieval-augmented generation (RAG)
- Production-scale inference optimization and deployment

**ML Engineer:**
- End-to-end ML pipeline development (data → training → deployment)
- MLOps infrastructure (experiment tracking, model versioning, CI/CD)
- Real-time prediction systems and API serving

**Data Scientist:**
- Large-scale data engineering and ETL pipeline design
- Predictive modeling and statistical analysis
- Business intelligence and data-driven decision making
- Time series forecasting and anomaly detection

**Research Interests:**
- NLP applications (sentiment analysis, emotion prediction, text classification)
- Deep learning architectures (Transformers, LSTM, ensemble methods)
- Synthetic data generation and self-supervised learning

### 📧 Contact Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:changyong.hyun@telecom-sudparis.eu)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN)

**Response Time:** Within 24 hours (usually < 6 hours)

---

<div align="center">

### 📊 Profile Stats

![Profile Views](https://komarev.com/ghpvc/?username=CY-HYUN&color=58A6FF&style=flat-square&label=Profile+Views)
![GitHub Followers](https://img.shields.io/github/followers/CY-HYUN?style=flat-square&color=58A6FF&labelColor=0D1117)
![GitHub Stars](https://img.shields.io/github/stars/CY-HYUN?style=flat-square&color=58A6FF&labelColor=0D1117)

---

### 💡 Let's Build Something Impactful Together

**"From research to production, I turn ML ideas into scalable systems that solve real problems."**

I bring **proven track record** (Top rank SemEval 2026), **fast execution** (4× faster delivery), and **end-to-end ownership** (research → deployment). Ready to contribute from day one with production-quality code and data-driven mindset.

📩 **Open to 6-month internship opportunities starting before July 2026** | Response within 24 hours

</div>

<!-- Profile README - Optimized for LLM/ML/Data Science positions - Last updated: 2026-02-05 -->
