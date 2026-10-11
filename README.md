<div align="center">

# 👋 Hi, I'm Changyong Hyun
<!-- GitHub Profile README - Last updated 2026-10-10 -->

### 🚀 AI/ML Engineer | LLM Evaluation & Agentic Systems | MSc @ Télécom SudParis (IP Paris)

🇫🇷 **Paris / Europe** · 🔬 **6 months building a production multi-agent LLM system** · ⚡ **PyTorch · LangGraph · MLflow**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/changyong-hyun)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:xhangyong.hyun@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/CY-HYUN)
[![Website](https://img.shields.io/badge/Website-cy--hyun.github.io-0D1117?style=flat&logo=githubpages&logoColor=white)](https://cy-hyun.github.io)

</div>

---

## 🎯 About Me

**MSc Data Science, Télécom SudParis (2026) · Open to LLM / ML Engineer roles in Paris and Europe**

AI/ML engineer with an MSc in Data Science & Network Intelligence from **Télécom SudParis (Institut Polytechnique de Paris)**, graduated October 2026, with six months of industry experience at **MECAGENT** in Paris building and evaluating a production multi-agent LLM system for CAD automation.

I build LLM and multi-agent systems, and I specialise in the part most teams skip: **deciding whether the thing actually works.** The hard problem is rarely generation — it's that the metric you grade outputs with is usually blind to some of the ways they can be wrong. On the system I worked on, a part built mirrored scored about the same as the correct one. So most of my work became evaluation design: build the instrument first, then let it decide what to change.

**Core Expertise:**
- 🔬 **Evaluation design for generative systems** — rubrics against expert-built ground truth, machine-derived reference labels instead of hand-written ones, pre-registered acceptance criteria, shuffled controls
- 🤖 **LLM fine-tuning** — LoRA, DPO, PEFT (12.16M trainable parameters, 5.5× lower validation loss than the prompt-tuning control, zero API cost)
- 🕸️ **Agentic & multi-agent systems** — LangChain, LangGraph, orchestrator/sub-agent architectures executing against a live external application
- 📈 **Observability** — MLflow run tracking, Arize Phoenix tracing, span-level analysis of multi-hour agent sessions
- 🧪 **Controlled experiments** — one variable at a time, negative results reported at the same length as positive ones

**Key Achievements:**
- 🏅 **SemEval 2026 Task 2** — validation mean Pearson r **0.6554** on the best single model, with the metric's naming error found and corrected in my own repo
- 🔍 **A leakage analysis that changed the answer** — quantified a **33.3-point** gap and published the lower number
- 🧰 **Instruments that outlive the code** — my scorers still reproduce every number from saved artefacts after the pipeline around them was rebuilt
- ⚡ **Zero-cost fine-tuning pipeline** — synthetic data generation through DPO alignment with no API fees and no human labelling
- 🎖️ **Best Performance Award** — Hanwha Aerospace big-data internship (1st of all teams)

---

## 📈 Contribution Activity

<div align="center">

<img src="https://streak-stats.demolab.com/?user=CY-HYUN&theme=tokyonight&hide_border=true&background=0D1117&ring=58A6FF&fire=58A6FF&currStreakLabel=58A6FF" alt="GitHub Streak" />

</div>

---

## 💼 Industry Experience

### 🔧 AI Engineer Intern — MECAGENT, Paris, France (May – Oct 2026)

**MECAGENT builds an AI copilot for SolidWorks**, the most widely used mechanical CAD software. The product takes a natural-language request and generates C# macro code that executes inside the user's live SolidWorks session.

**The system I worked on:** a drawing-to-CAD pipeline — vision models read a 2D engineering drawing (orthographic views, dimensions, machining annotations), a planner turns it into a structured feature tree, and a multi-agent system generates and executes SolidWorks C# against a live CAD kernel. Not a sandbox, not a simulator: a stateful external application that fails in ways a library never does.

**My ownership:** the evaluation and experimentation layer — the part that decides whether any change was actually an improvement.

- 🎯 **Designed the evaluation for the drawing-reading stage from scratch**, for a generative component that had no measurement at all. Built the rubric, selected the sample across both source datasets and the feature classes that mattered, and anchored it on ten reference parts hand-built in SolidWorks by the company's CAD expert — so that no model ever graded another model's output. The scorer reproduces every number from saved artefacts with **zero model calls**, which is why it still runs today after the pipeline around it was rebuilt.
- 🔍 **Proved the team's headline metric was blind to entire classes of failure.** A mirrored part, a rotated part, and a sheet-metal bend imitated with extruded blocks all scored about the same as correct ones — the score aligns two solids before comparing, which erases orientation, and counts holes, which a mirror preserves. I built deterministic checks that detect each class by reading the feature types SolidWorks itself assigns, and those checks redirected the team's engineering priorities.
- 🧪 **Ran controlled A/B experiments with acceptance criteria registered before each run.** Shuffled controls killed several of my own proposed fixes. I published a pre-registered negative result at the same length as the positive ones, where my own improvement lost to the baseline and I recommended keeping the baseline.
- 🪞 **Caught my own ground-truth labels being wrong.** Three models disagreed with my hand-written answer key; checking the key against the reference geometry showed the key was wrong and the models were right. Every label after that came from a machine-derived source, and I wrote up why.
- 📊 **Instrumented long-horizon agent runs end to end** — MLflow for run tracking and model registry, Arize Phoenix for distributed tracing, reading span-by-span what an agent actually did across multi-hour sessions instead of trusting a summary of it.
- 🔧 **Built a C# helper library for the generating agent**, declared at the CAD session level, with live self-checks that each had to be demonstrated firing in both directions before I claimed they protected anything.
- 🤝 **Shipped inside a senior team's process** — pull requests, code review, trace-referenced technical reports adopted as a team template, and adversarial verification of my own claims before they left my desk.

**Tech Stack:** Python · C# · SolidWorks API · LangChain / LangGraph · MLflow · Arize Phoenix · vision-language models · AWS Bedrock · pytest

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

### 📐 2. text2cad-verifier — Does LLM-Written CAD Code Run, and Is the Part the Right Size? (Oct 2026)
**151 Text2CAD-Bench prompts, two verifiers, one repair round** — failures went from 7 to 1 (procedure prompts) and 11 to 1 (geometric prompts), against a repeat-run noise of 2 run failures and 1 size mismatch

**Challenge:** The benchmark's ground-truth geometry is not public, so there is nothing to compare a generated part against — and "the code ran" says nothing about whether the part is right.

**My Solution:**
- ▶️ **Execution verifier**: each program runs in a separate process with a 60 s limit, imports only `cadquery` and `math` (an AST allow-list checked before running), and must leave a solid that passes OpenCascade's `BRepCheck` with a positive volume
- 📏 **Size verifier with no ground truth**: the model reads each part's bounding box, in mm, separately from the two descriptions the dataset gives for every part; a part gets an expected size only when the two readings agree within 2% or 0.5 mm per axis (**120 of 151** did), and the generated solid's box is compared with it, axes sorted
- 🔁 **One repair round**: each failure goes back once with the verifier's message — the run error, or "the bounding box is X mm while the description implies Y mm"
- 🎲 **Noise floor measured first**: the same 151 prompts generated twice differ by 2 run failures and 1 size mismatch, so a change inside that band is not a result
- 🌐 **Verifiers served as an API** (FastAPI, Pydantic, OpenAPI docs, 3 tests, Dockerfile), and a [demo page](https://cy-hyun.github.io/text2cad-verifier/demo/) with every part, its program, both verdicts and a 3D view

**Results (model `claude-opus-5-5`, 151 prompts per run, 2026-10-08):**

| Run | Programs that fail to run or give no valid solid | Size mismatches (of parts with an agreed size that ran) |
|---|---|---|
| Generation, procedure prompts | 4 | 3 of 117 |
| Same prompts again (noise) | 6 | 2 of 114 |
| Generation, geometric prompts | 3 | 8 of 117 |
| After one repair round, procedure | 1 | 0 of 119 |
| After one repair round, geometric | 1 | 0 of 119 |

- **L1 (60 simple parts) almost never fails; what fails is L2 and L3** — sweeps, lofts, patterns
- **Timeouts were the machine, not the model**: 66 programs timed out while another job held the CPU; 64 ran fine when re-run alone with a 180 s limit, and the table uses the re-run results
- **What the repair numbers do not show, stated**: the size feedback quoted the expected box, so a size match after repair is measured by the same check that guided it; a run failure fixed after repair is the stronger signal
- **Cost:** 7 batches, about $5 at Batch API prices; `t2c.py report` reproduces the table from the committed results without any API call
- **Other generators, same protocol (2026-10-10):** Sonnet 5.5 failed to run 8 and 10 times on procedure prompts over two runs (Opus: 4 and 6), with size mismatches inside or below the Opus range; Haiku 4.5 failed on 83 of 151, mostly with CadQuery calls that do not exist, and one repair round fixed about a quarter

**Tech Stack:** Python, CadQuery (OpenCascade), Anthropic Message Batches API, FastAPI, pytest, GitHub Pages

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/text2cad-verifier)

---

### 🔎 3. rag-golden-eval — RAG Built Eval-First (Oct 2026)
**A frozen 140-question golden set before the pipeline** — BM25 reached GAA 0.721 (mean of three identical runs, noise band 0.014); adding a cross-encoder reranker dropped it to 0.593

**Challenge:** When the retriever changes, did the answers get better, and by more than run-to-run noise? Most RAG demos never measure this.

**My Solution:**
- 📚 **Corpus the model cannot have memorised**: 150 CC BY 4.0 arXiv papers (cs.CL / cs.LG) first submitted after the generator's knowledge cutoff, split into dev and eval slices before anything else
- 🧾 **Golden set v1** (140 questions: factoid, multi-hop, negation, list, unanswerable), each with paper id, character span and verbatim quote; a draft was kept only if the quote exists, a passages-only answer matched the gold, and unanswerables stayed unanswered against BM25 and dense top-8
- 🪜 **A retrieval ladder measured with one harness**: closed-book R0, BM25, dense, hybrid (reciprocal rank fusion), hybrid + cross-encoder rerank; same prompt, k and models
- 📏 **Metrics**: recall@k, MRR, nDCG, faithfulness, correctness, abstention accuracy, and GAA (grounded answer accuracy: an answerable question answered correctly and faithfully, or an unanswerable one declined)
- 🎲 **Noise floor first**: R1 run three times on identical input; any gap under 0.014 GAA is reported as within noise

**Results (judge `claude-opus-5-5`, rubric v1, N = 140):**

| Rung | recall@5 | GAA | vs BM25 mean |
|---|---|---|---|
| R0 closed book | - | 0.150 | -0.571 |
| R1 BM25 (3 runs) | 0.765 | 0.714 / 0.721 / 0.729 | |
| R2 dense | 0.689 | 0.679 | -0.043 |
| R3 hybrid | 0.731 | 0.721 | +0.000 (within noise) |
| R4 hybrid + rerank | 0.588 | 0.593 | -0.129 |

- **The reranker hypothesis failed on this set**, and the README says so: recall@5 fell from 0.731 to 0.588
- **Judge checked from three sides, not yet by a person**: Sonnet 5.5 and Haiku 4.5 re-judged all 560 answers and kept the same order R1 > R3 > R2 > R4; a blind second pass on a 30-item stratified sample agreed on correctness 30 of 30. A human calibration is the stated next step

**Tech Stack:** Python, bm25s, sentence-transformers, Qdrant (local mode), bge-small-en-v1.5, ms-marco MiniLM cross-encoder, Anthropic Message Batches API, pymupdf

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/rag-golden-eval)

---

### 📡 4. Paper Radar — Weekly Literature Tracker (public since Oct 2026)
**Matches new arXiv papers and Semantic Scholar citations to a ledger of open problems** on a schedule; by default no LLM runs in the weekly job

**Challenge:** Follow new research for a short list of open problems every week without reading the whole feed, and without any problem text leaving the machine.

**My Solution:**
- 📒 **A ledger of at most 10 open problems**, each with its metric, the command that produced it, and what was tried
- 🗓️ **A scheduled GitHub Actions job** matches the week's arXiv papers and Semantic Scholar citations to each problem; by default no LLM runs in the weekly job
- 🔒 **No free text leaves the machine**: the query is matched locally against the week's arXiv papers, and the only outbound requests are arXiv category-and-date windows and paper ids (for citation lookups and recommendations), enforced by a URL allow-list that refuses free text and a forbidden-terms check on every request
- ⏳ **Stale problems are skipped**: a row not re-verified for more than **14 days** is flagged and left out of the weekly fetch
- 🔌 **MCP server** on the official Python SDK with **6 tools** (list the problems, show one, this week's candidates, pending ledger updates, change one cell under the ledger's checks, start a paper card); CI calls all 6 over a real MCP connection
- 🧭 **Optional: current problems from commit history**: Claude reads the last **28 days** of a repository's commits and proposes up to **5** problems being worked on now; a problem is kept only if it cites at least **2 commits that really exist**, and its search words pass the same forbidden-terms check (off in the public demo)

**What broke along the way:**
- arXiv refused the laptop's scheduled run (HTTP 406 for that Python build), so the job moved to a GitHub Actions runner on Python 3.11
- A new seed paper brings every paper that ever cited it (**1,002** for one demo problem on a first run), so each seed now lists only its **10 newest unseen citers** per run and records the rest

**Tech Stack:** Python, GitHub Actions, MCP (official Python SDK), arXiv, Semantic Scholar

**Scope, stated honestly:** I built it to track the open problems I work on; the public repository runs on a demo ledger of public questions.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/paper-radar)

---

### 🏅 5. SemEval 2026 Task 2 — Emotion Prediction (Oct 2025 – Jan 2026)
**Validation mean Pearson r 0.6554** — international NLP competition; the competition metric (CCC) was not measured

**Challenge:** Predict emotional response (valence and arousal) from temporal sequences of a user's posts, where any single post carries little signal without the user's history.

**My Solution:**
- 🔥 **Modular pipeline** with training, prediction, evaluation and demo stages separated into their own modules
- 🧠 **User-level embeddings**: aggregated a user's historical posts into a dense representation — the single largest contributor in the ablation
- 🔬 **RoBERTa + BiLSTM (256 hidden, 2 layers) + 4-head attention**, dual-head output for the two dimensions
- 🎯 **Arousal-specialist model**: 90% CCC-loss weighting on the harder dimension (its arousal score is not quoted: one input feature contains the target)
- 📊 **31 engineered features feed the best model**: 17 temporal (lags, rolling statistics), 4 per-user baselines, 10 text statistics
- ⚡ **Mixed-precision training** (torch.cuda.amp) with multi-seed runs (42, 123, 777, 888, 1111) for robustness
- 📈 **Differential learning rates**: 1e-5 for the encoder against 8e-5 for the custom heads
- 🧪 **Systematic ablations**: quantified each component separately — user embeddings > engineered features > BiLSTM

**Results — measured on the validation split:**

| Model | Mean Pearson r | Valence r | Arousal r | |
|---|---|---|---|---|
| **seed777** | **0.6554** | 0.7593 | 0.5516 | Best single model |
| arousal_specialist (seed 1111) | 0.6512 | 0.7192 | not quoted | An arousal input contains the target |
| seed42 | 0.5053 | 0.6532 | 0.3574 | Dropped from the pool |

- **Best single-model validation score 0.6554** (seed 777), a mean Pearson r on a random 15% within-user split. The training code logged it as "CCC"; I found that `validate()` computes Pearson r and corrected the name everywhere. True CCC is at most this value and was not measured.
- **Arousal was the bottleneck**: arousal r ranged 0.357–0.552 across seeds while valence reached 0.759. The arousal-specialist model logged a higher arousal r, but one of its extra features (`arousal_change`) contains the target, so I do not quote that gain.
- **Seed variance turned out to be the bigger story**: the same architecture scored **0.5053–0.6554** across random seeds. Any single-run comparison on this task is mostly measuring the seed, which is why I report the best single model and its spread rather than one number.
- **46 users, 1,266 test predictions**

**On the submitted ensemble — stated precisely:** the final submission weighted the two best models by their validation score (seed777 50.16% + arousal_specialist 49.84%). Its combined score was a **projection** — the weighted average of the two measured models plus an assumed ensemble boost — and was **never re-scored on held-out data**. So the number I quote is the measured 0.6554, not the projected ensemble figure. Being able to tell those two apart is the point.

**Tech Stack:** PyTorch 2.0+, Hugging Face Transformers, RoBERTa, BiLSTM, WandB, Mixed Precision Training

**Deliverables:** Joint slide deck (my part: subtask 2a) · technical report · fully reproducible pipeline (preprocessing, training, evaluation, prediction) · Codabench submission

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Deep-Learning-project-SemEval-2026-Task-2)

---

### 🔍 6. QoE Prediction — the Leakage Analysis That Changed the Answer (Oct – Dec 2025)
**33.3-point gap** — where the real result is the integrity work
*Télécom SudParis (IP Paris) MSc coursework · supervised project*

**Challenge:** Predict user-perceived mobile-streaming quality (MOS 1–5) from 1,543 sessions. The obvious model looked excellent. It wasn't.

**Data:** the PoQeMoN crowdsourcing dataset (LiSSi laboratory, Paris Est Créteil University) — 181 testers rating video sessions over four live French mobile networks on nine Android devices, with VLC-side metrics logged alongside each rating.

**My Solution:**
- 🚩 **Found the leak**: the strong model leaned on features only available *after* a session ends — information a deployed system would never have at prediction time
- ✂️ **Rebuilt the experiment** restricted to objectively-available features (network metrics, device characteristics, temporal patterns), with balanced class weights
- 📊 **Four classifiers, both feature sets each**: Logistic Regression, Decision Tree, Random Forest and Gradient Boosting — every model trained on both variants so the leakage gap is measured, not inferred
- 📈 **Reported both numbers side by side** and led with the lower one
- 🔁 **Made it reproducible**: the experiment script is committed and was re-run twice, byte-identical

**Results:**
- **81.6% with leaky post-session features** · **48.2% objective-only** (macro F1 0.442, kappa 0.261)
- **A 33.3-point leakage gap**, quantified rather than hand-waved
- The objective-only model sits *below* the majority-class baseline on raw accuracy (50.8%) but far above it on balanced metrics (F1 0.442 against 0.135). Balanced weights move the errors rather than raising the ceiling: **Bad-session recall reaches 84.2%** where a majority-class predictor detects nothing at all.
- **The gap replicates across all four model families** (+29.1 to +34.6 points), so it is a property of the feature set rather than of one lucky model
- **The classifier barely mattered** — test accuracy spanned only 45.0–48.2% across all four. The objective feature set, not the model family, was the binding constraint.

**Tech Stack:** scikit-learn (Logistic Regression, Decision Tree, Random Forest, Gradient Boosting), Pandas, class-balanced evaluation, stratified splitting

**Why it matters:** This is the project I bring up when someone asks how I know a metric is trustworthy. The headline number went *down* and the work got better.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Poqemon-QoE-Dataset-master)

---

### 🌍 7. DEFT — Defense Export Market Analysis (Sep – Dec 2024)
**102,188 records, 170 countries scored** — multi-source ETL and feasibility scoring

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
- **102,188 records** integrated into one queryable dataset (13 committed JSON files, 1991–2020); **170 countries** scored after standardisation
- **Economic capacity was the only strong predictor of arms imports** — economic score **+23,170 TIV per standard deviation, p < 0.001**. Governance scored **p = 0.791: no measurable effect**, and conflict intensity was marginal (p = 0.093). That negative result mattered more than the positive one, because governance indicators were the axis the model was expected to lean on.
- **R² = 0.366 means ~63% of import variation sits outside these indicators** — alliances, political decisions, offset deals — which is the honest bound on how far indicator-only screening can go
- **South Korea's import mix**, mapped onto the US ITAR/USML 22-category taxonomy across 509 import entries (1991–2020): missiles 34.8%, aircraft 20.6%, military electronics 11.0%
- **210+ raw country-name variants reconciled** into one canonical set — the unglamorous step that made the four-source join possible at all

**Tech Stack:** Python, Pandas, NumPy, scikit-learn, statsmodels, Leaflet, Chart.js, DataTables, REST APIs (World Bank, SIPRI, UCDP, WGI)

**Impact:** A strategic screening tool for defense-industry market entry — and a quantified statement of where indicator-based screening stops working.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Global-Defense-Export-Analysis-Project)

---

### 📈 8. Agricultural Price Forecasting (Nov – Dec 2024)
**65,120 daily price rows · 17 commodities · 52-week horizon** — price forecasting for military food procurement

**Challenge:** Forecast Korean agricultural retail prices far enough ahead to change purchasing decisions, across commodities whose seasonality has almost nothing in common. 7-person team, 8 weeks.

**My Solution — two model families, trained separately and compared, not blended:**
- 📊 **Per-commodity LSTM** (Keras/TensorFlow), univariate price series:
  - **6 stacked LSTM layers** (200-100-50-50-100-200 units, tanh), dropout 0.2 and L2(0.01) on every layer, Dense(1) output
  - Adam with a per-commodity tuned learning rate (0.0005–0.0029), custom RMSE loss, EarlyStopping (patience 10, best-weights restore), seed 42
  - **One model per commodity** — 16 in total (a 17th notebook block is labelled cabbage but loads the potato series, so it is not counted), because a single pooled model washes out the seasonality that makes each crop different
- 📉 **Seasonal ARIMA** (statsmodels `SARIMAX`, order (5,1,0), seasonal (1,1,1,52)) for the long horizon — **52-week-ahead weekly forecasts per commodity**
- 🗄️ **Data integration**: daily Garak Market retail prices merged with weather (KMA stations), GDP, fuel, and minimum-wage series; cleaning, gap handling and weekly resampling
- 🌐 **Flask dashboard** — 6 pages, all verified serving HTTP 200 — with embedded Power BI reports for stakeholders

**Results:**
- **65,120 daily retail-price rows across 17 commodities**, 2014-01-02 → 2024-12-05 (11 years)
- **16 per-commodity LSTM models**, best-epoch validation **MAE 0.022–0.094 on min-max-scaled prices** (median 0.044) — roughly **2–9% of each commodity's 11-year price range**
- **52-week-ahead forecasts** saved per commodity (napa cabbage, cabbage, carrot, cucumber, radish, garlic, onion, pepper, potato, rice, spinach, green onion)
- **Procurement timing recommendations** derived from the forecast curve rather than from last year's price

**Tech Stack:** Python, TensorFlow/Keras, statsmodels (SARIMAX), Flask, Power BI, Pandas, Time Series Analysis

**Note on scope:** an earlier version of the project README quoted test MAPE, R² and accuracy percentages whose evaluation runs were not preserved. The repository now reports only what can be re-derived from committed notebook outputs and data files — which is what the numbers above are.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Defense-Agri-Price-Forecasting-main)

---

### 📺 9. YouTube Analytics — Korean Content Strategy (Jul – Sep 2024)
**2,125 videos** — statistical analysis across 15 channels and 3 categories

**Challenge:** Turn channel performance data into recommendations a creator could act on.

**My Solution:**
- ☁️ **Title-keyword word clouds** per channel and category (Korean title words only)
- 📊 **8 standalone analytical frameworks**:
  - Word cloud analysis of title keywords by category
  - Upload timing (hour-of-day, day-of-week)
  - Upload cadence and its effect on views
  - Views–likes–comments correlation (scatterplots from the real run; the Pearson script computes coefficients when a dataset is supplied)
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

**Tech Stack:** Python, Pandas, Matplotlib, Seaborn, Word Clouds, descriptive statistics

**Note on scope:** the repository documents its own verified headline (2,125 videos / 15 channels / 3 categories) and explicitly lists the earlier unverifiable figures that were removed.

[![GitHub](https://img.shields.io/badge/View_Project-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CY-HYUN/Youtube-Channel-Analysis-Project)

---

### 🏡 10. Korean Real Estate — Market Analysis (Jul – Sep 2024)
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

### 🎬 11. Movie Trip — Full-Stack Travel Platform (Dec 2025)
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

### 🏢 12. Insurance SOA — Multi-Protocol Service Architecture (Dec 2025 – Jan 2026)
**4 protocols, one gateway** — REST · SOAP · gRPC · GraphQL
*Télécom SudParis (IP Paris) MSc coursework · service-oriented architecture module*

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

### 🧰 More public tools (Oct 2026)

| Project | What it does | Tests |
|---|---|---|
| [**claim-gate**](https://github.com/CY-HYUN/claim-gate) | A Claude Code Stop hook that blocks a reply claiming "done", a count, an absence or "all/every" without the evidence behind it | 17 tests |
| [**job-posting-checker**](https://github.com/CY-HYUN/job-posting-checker) | Reads a job posting and answers, with the sentence behind each answer, whether French is required, whether the role is open to someone in France, the contract, the salary against a floor and the years asked; plus a careers-API fetcher | 445 labelled cases |
| [**korean-ai-tell**](https://github.com/CY-HYUN/korean-ai-tell) | Flags "AI tells" in Korean (and English) text with a rule id and a fix hint; CLI, library, pre-commit hook and a Claude Code skill. On PyPI: `pip install korean-ai-tell` | 13 tests |
| [**kmmlu-lighteval**](https://github.com/CY-HYUN/kmmlu-lighteval) | Adds the Korean benchmark KMMLU to Hugging Face lighteval and checks it question by question against lm-evaluation-harness: on 5 of 45 subjects with one small model on CPU, 700 of 700 same prompt, tokens and prediction. Proposed upstream as [lighteval#1424](https://github.com/huggingface/lighteval/issues/1424), then opened as [pull request #1425](https://github.com/huggingface/lighteval/pull/1425) (open) | parity table + 3 tests |

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
- 4-bit quantisation; Colab T4 (free tier) for generation, A100 for training
- Magpie prompting — 1,500 synthetic samples at an 83.9% quality pass rate
- Synthetic data generation — zero-cost automated pipeline

**Transformers** *(SemEval 2026 — modular training/prediction pipeline)*
- RoBERTa fine-tuning — validation mean Pearson r 0.6554 (SemEval 2026 Task 2)
- BiLSTM ensembles, multi-head attention, dual-head output
- Mixed-precision training (fp16), multi-seed experiments for robustness

**Agentic Systems** *(MECAGENT internship)*
- LangChain, LangGraph — orchestrator/sub-agent architectures
- Model Context Protocol (MCP) tool integration
- Agents executing generated code against a live external application

**NLP** *(across projects)*
- Emotion prediction with lexicon sentiment features (SemEval)

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗_Transformers-FFD43B?style=flat&logoColor=black)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)
![WandB](https://img.shields.io/badge/WandB-FFBE00?style=flat&logo=weightsandbiases&logoColor=black)

### 📊 Machine Learning & Data Science
**ML Algorithms** *(QoE Prediction — 4 classifiers, both feature sets each)*
- Logistic Regression, Decision Tree, Random Forest, Gradient Boosting — every model trained on both variants so the leakage gap was measured, not inferred
- Class-balanced evaluation: macro F1 and Cohen's kappa over raw accuracy, stratified splitting
- Also used elsewhere: SVM, XGBoost, K-Means clustering (DEFT country grading)

**Time Series** *(Agri Forecasting — 16 per-commodity models)*
- Seasonal ARIMA (statsmodels SARIMAX) for the 52-week horizon; stacked LSTM (Keras) per commodity
- Per-series tuning, EarlyStopping with best-weight restore, custom RMSE loss
- Seasonal decomposition, lag and rolling-window feature construction

**Data Engineering** *(DEFT — 102,188 records)*
- ETL pipelines, REST API integration (World Bank, SIPRI, UCDP, WGI)
- Entity reconciliation across disagreeing sources
- K-Means grading of the 170 scored countries, OLS regression on the training split

![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)

### 💻 Programming & Databases
**Primary Languages**
- **Python** (advanced) — most of the projects above, from notebook analysis to modular training pipelines
- **C#** — SolidWorks API automation, helper libraries with live self-checks
- **SQL** (advanced) — SQLD certified; PostgreSQL
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
- Git / GitHub — every featured project above is a public repository

**Cloud & Serving**
- AWS Bedrock — frontier model access in production pipelines
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

### Undergraduate

**Tech University of Korea** — Siheung, South Korea
- B.Eng, Computer Engineering

**Changwon National University** — Changwon, South Korea
- Robot Control & Measurement Engineering (studies only, transferred to Tech University of Korea)

---

## 🏆 Achievements & Certifications

### 🥇 Awards
- **Best Performance Award** — Hanwha Aerospace big-data internship, team project on global defense trends, **1st of all teams**
- **SemEval 2026 Task 2** — validation mean Pearson r 0.6554, and the metric's naming error found and corrected

### 📜 Certifications
- **SQLD** — SQL Developer, Korea Data Agency
- **SMAT** — Service Management Aptitude Test

### 📈 Technical Highlights
- **Seed variance quantified** — the same SemEval architecture scored 0.5053–0.6554 (mean Pearson r) across seeds, which bounds what any single run proves
- **5.5× lower validation loss than the control** — LoRA against prompt tuning on identical data, at zero API cost
- **33.3-point leakage gap quantified** — and the lower number published
- **210+ country-name variants reconciled** — DEFT, the step that made a four-source join possible
- **83.9% quality pass rate** — synthetic data filtering pipeline

---

## 💼 What I Bring

### ✅ I measure before I claim
Every number in this profile names what it was measured on. When my own improvement lost to the baseline, I reported that and recommended the baseline. When my hand-written reference labels turned out to be wrong and three models were right, I rebuilt the labels from geometry and wrote up why.

### ✅ I build the instrument first
On the internship system, the drawing-reading stage had no measurement at all, so I built one: a rubric anchored on ten reference parts a CAD expert built by hand, a scorer that reproduces every number from saved artefacts with zero model calls, and shuffled controls that killed my own proposed fixes before a reviewer had to.

### ✅ I ship inside a team's process
Pull requests, code review, trace-referenced technical reports, and adversarial verification of my own claims before they leave my desk — six months of it in a senior team at a funded startup.

### ✅ I work across the stack
Shipped projects spanning LLM fine-tuning, NLP research, multi-agent systems, time series, data engineering and full-stack web — in Python, C#, Java and TypeScript.

### ✅ I communicate in two languages and three registers
Korean (native), English (professional) — and the register that matters most: explaining a technical result to someone who has to make a decision with it.

---

## 📫 Let's Connect

**MSc Data Science, Télécom SudParis (2026). Open to LLM Engineer / ML Engineer / AI Engineer roles in Paris and Europe** — open to hybrid or remote.

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

*Paris / Europe · Remote-friendly*

</div>

<!-- Profile README — optimised for LLM / ML engineer roles — last updated 2026-10-10 -->
