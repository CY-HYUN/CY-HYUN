<div align="center">

# 👋 Hi, I'm Changyong Hyun
<!-- GitHub Profile README - Last updated 2026-02-05 -->

### 🚀 LLM Engineer | MSc Student @ Télécom SudParis

🏆 **Top 10 SemEval 2026 (CCC 0.6833)** | 🤖 **LLM Fine-tuning Expert** | ⚡ **PyTorch & Transformers**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:changyong.hyun@telecom-sudparis.eu)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/CY-HYUN)

</div>

---

## 🎯 About Me

**Actively seeking LLM Engineer / ML Engineer / Data Scientist internship (March-September 2025, 20-26 weeks)**

MSc Data Science student at Télécom SudParis specializing in **Large Language Model fine-tuning**, **NLP**, and **production-grade ML systems**. With **8 completed ML/AI projects** spanning deep learning competitions, LLM research, and data engineering, I combine academic rigor with practical engineering skills.

**Key Achievements:**
- 🏆 **Top 10 competitive** in SemEval 2026 International NLP Competition (CCC 0.6833, 13% above target baseline)
- 🚀 **+9.7% model improvement** through zero-cost synthetic data generation and LLM fine-tuning
- ⚡ **90% time reduction** in multi-source data engineering pipelines (5 hours → 30 minutes)
- 📊 **50,000+ video analysis** with bilingual NLP for actionable business insights

**Target Companies:** Mistral AI, Hugging Face, Criteo, OpenAI, Anthropic, Google DeepMind

---

## 📊 GitHub Statistics

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=CY-HYUN&show_icons=true&theme=tokyonight&count_private=true&hide_border=true&title_color=58A6FF&icon_color=1F6FEB&text_color=C9D1D9&bg_color=0D1117&include_all_commits=true)

</div>

---

## 💻 Most Used Languages

<div align="center">

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=CY-HYUN&layout=compact&theme=tokyonight&langs_count=8&hide_border=true&title_color=58A6FF&text_color=C9D1D9&bg_color=0D1117&hide=html,css,jupyter%20notebook&card_width=495)

</div>

---

## 📈 Contribution Activity

<div align="center">

![GitHub Streak](https://streak-stats.demolab.com/?user=CY-HYUN&theme=tokyonight&hide_border=true&background=0D1117&ring=58A6FF&fire=58A6FF&currStreakLabel=58A6FF)

</div>

---

## 🌟 Featured Projects

### 🏆 1. SemEval 2026: Deep Learning NLP Competition (Nov 2024 - Jan 2026)
**Top 10 Competitive Performance** - CCC 0.6833 in international emotion prediction competition

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
- **Overall CCC: 0.6833** (13% above target baseline of 0.62, Top 10 competitive range)
- **50% improvement** over naive baseline (0.45 → 0.68 CCC)

**Tech Stack:** PyTorch, Transformers (Hugging Face), BiLSTM, WandB, Mixed Precision Training, Ensemble Methods

**Deliverables:** 31-slide presentation (3.3 MB), comprehensive technical report (204 KB), interactive demo notebook

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Deep-Learning-project-SemEval-2026-Task-2)

---

### 🤖 2. LLM Fine-tuning: Synthetic-Instruction-Tuner (Nov-Dec 2024)
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

### 📊 3. QoE Prediction: Mobile Streaming Quality (Apr-Jun 2024)
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

### 🌍 4. DEFT: Defense Export Feasibility Tracker (Oct-Nov 2024)
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

### 📈 5. Agricultural Price Forecasting (Jun-Aug 2024)
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

### 🏢 6. Insurance SOA: Multi-Protocol Service Architecture (2024)
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

### 🏡 8. Korean Real Estate: Market Analysis (May-Jul 2024)
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

### 🤖 LLM & NLP
**LLM Fine-tuning:** LoRA, DPO, PEFT, Quantization (4-bit, 8-bit), Prompt Engineering, Magpie
**NLP:** Transformer architectures (RoBERTa, BERT, GPT), Sentiment Analysis, Text Classification, BiLSTM, Ensemble Methods
**Frameworks:** PyTorch, Transformers (Hugging Face), LangChain, WandB

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗_Transformers-FFD43B?style=flat&logoColor=black)
![LangChain](https://img.shields.io/badge/🦜_LangChain-121212?style=flat&logoColor=white)

### 📊 Machine Learning & Data Science
**ML:** Scikit-learn, XGBoost, Random Forest, SVM, Ensemble Methods
**Time Series:** SARIMAX, LSTM, Forecasting, Seasonal Decomposition
**Data Engineering:** ETL pipelines, Multi-source integration, Data warehousing
**Visualization:** Matplotlib, Seaborn, Plotly, Power BI

![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

### 💻 Programming Languages
**Primary:** Python (Advanced), SQL (Advanced)
**Secondary:** TypeScript, JavaScript, Java, R

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white)

### 🗄️ Databases & Tools
**Databases:** PostgreSQL, MongoDB, Redis, Prisma ORM
**MLOps:** WandB, Docker, Kubernetes, Git, GitHub Actions
**Cloud:** AWS

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

### 🌐 Web Development (Full-Stack)
**Frontend:** Next.js 14, React, Recoil, Tailwind CSS
**Backend:** Flask, FastAPI, Node.js, REST APIs
**Auth:** JWT, OAuth

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)

---

## 🎓 Education & Certifications

### MSc in Data Science & Network Intelligence
**Télécom SudParis, France** (2024-2026)

**Specialization:** Large Language Models, NLP, Deep Learning, Data Engineering

**Notable Coursework:**
- Advanced Machine Learning & Deep Learning
- Large Language Model Architectures
- Natural Language Processing
- Data Engineering & Big Data
- Cloud Computing & Distributed Systems
- MLOps & Production ML

**GPA:** 3.8/4.0

---

## 🏆 Achievements & Recognition

### 🥇 Competitions
- **SemEval 2026 Task 2** - Top 10 competitive (CCC 0.6833) - International NLP competition with 100+ teams
- **Fast Learner Award** - Completed LLM fine-tuning project 4× faster than timeline (7 days vs 28 days)

### 📈 Technical Metrics
- **721-line production pipeline** - SemEval competition (modular, documented, tested)
- **+9.7% model improvement** - LLM fine-tuning with zero API costs
- **90% time reduction** - Data engineering automation (5 hours → 30 minutes)
- **81.9% ML accuracy** - QoE prediction for real-time systems

---

## 💼 What I Bring to Your Team

### ✅ Proven Technical Excellence
- **Competition success**: Top 10 in international NLP competition (SemEval 2026)
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

I'm actively seeking **LLM Engineer / ML Engineer / Data Scientist internship** opportunities for **March-September 2025** (20-26 weeks).

### 🎯 What I'm Looking For

**Ideal Role:**
- LLM fine-tuning, RLHF/DPO alignment, prompt engineering
- Production ML systems and MLOps infrastructure
- NLP research and applications (sentiment, classification, generation)
- Generative AI and agent-based systems

**Target Companies:**
- **Tier 1 Dream**: Mistral AI, Hugging Face, Criteo
- **Tier 2 Aspirational**: OpenAI, Anthropic, Google DeepMind, Cohere
- **Tier 3 Strong Fit**: AI startups, research labs, ML-focused teams

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

**⚡ "Code with purpose, ship with confidence"**

*Open to internship opportunities starting March 2025 | 20-26 weeks*

</div>

<!-- Profile README - Optimized for LLM/ML/Data Science positions - Last updated: 2026-02-05 -->
