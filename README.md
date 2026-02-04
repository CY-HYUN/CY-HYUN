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

## 💼 Work Experience

### Big Data Intern
**Hanwha Aerospace** - South Korea (6 months)

**Key Responsibilities:**
- Developed **machine learning and deep learning models** for defense analytics
- Conducted comprehensive **data preprocessing, exploratory analysis, and feature engineering** on large-scale datasets
- Built **predictive modeling solutions** for defense export analysis and agricultural price forecasting
- Performed **large-scale data integration** (77,400+ data points across 172 countries)

**Projects:**
- **Global Defense Export Model**: ML-based scoring system analyzing economic, political, and conflict indicators
- **Defense Agri-Price Forecasting**: LSTM/GRU models for market price prediction with real-time data crawling

**Achievement:** 🎖️ **Best Performance Award** for outstanding contributions to data-driven decision-making

### IT System Administrator
**S-Tec System** - South Korea (6 months)

**Key Responsibilities:**
- Managed **access control system** for enterprise security
- Performed **data analysis and reporting** to support business decision-making
- Developed **automated data processing workflows** to improve operational efficiency
- Maintained system infrastructure and ensured 99.9% uptime

**Technical Skills Applied:**
- Database management, SQL queries
- Automation scripting (Python)
- Business intelligence reporting

---

## 🛠️ Technical Skills

### 🤖 LLM & Advanced NLP
**LLM Fine-tuning & Alignment:**
- LoRA (Low-Rank Adaptation), DPO (Direct Preference Optimization), PEFT (Parameter-Efficient Fine-Tuning)
- Quantization (4-bit, 8-bit), Mixed Precision Training
- Prompt Engineering, Magpie Prompting, Synthetic Data Generation
- RAG (Retrieval-Augmented Generation), Model Context Protocol (MCP)

**Transformer Architectures:**
- RoBERTa, BERT, GPT families
- Hugging Face Transformers ecosystem
- Custom attention mechanisms, Multi-head attention

**NLP Techniques:**
- Sentiment Analysis, Text Classification, Emotion Prediction
- BiLSTM, GRU for sequential modeling
- Ensemble Methods (weighted averaging, stacking)

**Frameworks & Tools:**
- PyTorch, TensorFlow, TensorFlow Serving
- Hugging Face PEFT, Transformers
- LangChain, WandB (experiment tracking), MLflow

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗_Transformers-FFD43B?style=flat&logoColor=black)
![LangChain](https://img.shields.io/badge/🦜_LangChain-121212?style=flat&logoColor=white)

### 📊 Machine Learning & Deep Learning
**Classical ML:**
- Scikit-learn, XGBoost, Random Forest, SVM
- Ensemble Methods (bagging, boosting, stacking)
- Feature Engineering, Dimensionality Reduction

**Deep Learning:**
- LSTM, GRU, BiLSTM for time series
- Custom loss functions (CCC, MSE, dual-task optimization)
- Gradient clipping, Learning rate scheduling

**Time Series Analysis:**
- SARIMAX, LSTM/GRU ensembles
- Seasonal Decomposition, Forecasting (52-week ahead)
- Real-time data processing

**Data Science:**
- Pandas, NumPy for data manipulation
- EDA (Exploratory Data Analysis), Statistical Testing
- Feature Engineering (100+ features per project)

![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

### 💻 Programming Languages
**Expert Level:**
- Python (Advanced - Production ML pipelines, 721-line modular code)
- SQL (Advanced - Complex queries, database optimization)

**Proficient:**
- R (Statistical analysis, data visualization)
- C (System programming, performance optimization)

**Working Knowledge:**
- TypeScript, JavaScript (Full-stack web development)
- Java (Service-oriented architecture, enterprise systems)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white)

### 🗄️ Data Engineering & Big Data
**ETL & Pipelines:**
- Multi-source data integration (World Bank API, SIPRI, UCDP)
- Data warehousing (26.54 MB structured databases)
- Automated data processing workflows

**Big Data:**
- Hadoop ecosystem
- Large-scale data analysis (77,400+ data points, 172 countries)

**Databases:**
- Oracle DB (enterprise-grade database management)
- PostgreSQL, MongoDB, Redis
- Prisma ORM

![Hadoop](https://img.shields.io/badge/Hadoop-66CCFF?style=flat&logo=apachehadoop&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)

### 🚀 MLOps & DevOps
**Experiment Tracking:**
- WandB (multi-seed experiments, ablation studies)
- MLflow (model versioning, tracking)

**Containerization & Orchestration:**
- Docker (reproducible ML environments)
- Kubernetes (scalable deployments)

**CI/CD & Version Control:**
- Git, GitHub Actions
- Automated testing, deployment pipelines

**Cloud & Infrastructure:**
- AWS (cloud infrastructure)
- Linux (production environment management)

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)

### 📊 Data Visualization & BI
**Business Intelligence:**
- Tableau (interactive dashboards)
- Power BI (business reporting)

**Python Visualization:**
- Matplotlib, Seaborn (statistical plots)
- Plotly (interactive visualizations)
- Streamlit (real-time dashboards)

![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

### 🌐 Web Development & APIs
**Backend Frameworks:**
- FastAPI (REST APIs, real-time inference)
- Flask (ML model serving, web applications)
- TensorFlow Serving (production model deployment)

**Frontend:**
- Next.js 14, React (modern web applications)
- Recoil (state management), Tailwind CSS

**APIs & Integration:**
- REST APIs, GraphQL
- JWT, OAuth (authentication)

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)

---

## 🎓 Education

### MSc in Data Science & Network Intelligence
**Télécom SudParis (Institut Polytechnique de Paris)** - Paris, France (2025-2026)

**Specialization:** Large Language Models, NLP, Deep Learning, Data Engineering

**Notable Coursework:**
- Advanced Machine Learning & Deep Learning
- Large Language Model Architectures & Fine-tuning
- Natural Language Processing
- Data Engineering & Big Data (Hadoop ecosystem)
- Cloud Computing & Distributed Systems
- MLOps & Production ML Systems

**GPA:** 3.8/4.0

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
- **Fast Learner Award** - Completed LLM fine-tuning project 4× faster than timeline (7 days vs 28 days)

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

*Open to 6-month internship opportunities starting before July 2026*

</div>

<!-- Profile README - Optimized for LLM/ML/Data Science positions - Last updated: 2026-02-05 -->
