## About Me

I am a **Master of Data Science** candidate at **Monash University** (Feb 2025 – May 2027, Full-English Instruction), with an undergraduate degree in **Financial Management**.

My work focuses on **Voice AI & LLM Agent evaluation, rigorous experimental design & statistical attribution, machine learning modeling, and large-scale data engineering (PySpark)**. I enjoy turning messy real-world data and noisy model behavior into controlled ablations, actionable root-cause diagnoses, and measurable system improvements.

- **Email:** [ygen0018@gmail.com](mailto:ygen0018@gmail.com)
- **GitHub:** [github.com/ygen0018-sketch](https://github.com/ygen0018-sketch)
- **Expected Graduation:** May 2027

---

## Education

### Monash University *(2027 QS World #31)*
**Master of Data Science** *(Full-English Instruction)* · *Feb 2025 – May 2027*  
- **Core Coursework:** Machine Learning, Statistical Modelling, Data Processing for Big Data (Spark), Data Wrangling, Data Visualisation

### Shandong Youth University of Political Science
**B.Mgmt. in Financial Management** · *Sep 2018 – Jun 2022*

---

## Projects

### Voice Agent Eval: Benchmarking & Hybrid Routing
*Python, faster-whisper, DeepSeek, Gemini, Qwen-Omni, edge-tts* · **Nov 2026**  
🔗 [GitHub Repository](https://github.com/ygen0018-sketch/voice-agent-eval) · 📄 [Technical Report (REPORT.md)](https://github.com/ygen0018-sketch/voice-agent-eval/blob/main/REPORT.md)

- **Multi-Scenario Benchmark & Noise Quantification:** Built a tool-calling Chinese Voice Agent (`faster-whisper small → DeepSeek → edge-tts`) and a **596-sample benchmark** spanning 5 task types (weather, reminders, math, chat, hard edge cases) across clean TTS, human recordings, and 5 noise types at 10dB/0dB; isolated stage errors via `text_oracle` and showed 0dB background speech inflates CER by **2.7×** over equal-SNR traffic (13.6% vs. 5.1%).
- **Error Attribution & Decoding / Prompt Optimization:** Attributed **80% (44/55)** of cascade failures to ASR numeric/homophone errors using `text_oracle` and `pypinyin` (0% wrong tool/arg extraction); paired LLM prompt constraints with Whisper `initial_prompt` v2 and decoding guardrails to boost math tool accuracy from **106/158 to 125/158** (CER 13.9% → 7.7%), cut >10s outliers from 15 to 1, and rejected a city lexicon due to OOV regression.
- **Cascaded vs. End-to-End Multimodal Diagnostics:** Benchmarked Cascaded v2 (**91%**), Gemini 3.8 Flash (**98%**), and Qwen3.8-Omni-Flash (**69%**) across **164 core clips** (accuracy, mean/P90 latency); diagnosed Qwen’s reminder collapse (27%) via a **text-vs-audio 2×2 ablation with 3× reruns** (35% discordant flip rate), proving **60% of clean-audio failures persist under text input** (verbal commitment without tool execution).
- **Edge-First Confidence-Gated Hybrid Router:** Evaluated 8 Whisper confidence signals and proved via **within-scene AUC** that utterance-level `avg_logprob` / `no_speech_prob` collapse to noise detectors (0.51–0.59), while word-level `word_low_frac` retains 0.72–0.78 discrimination; under task-grouped 2-fold CV, routing **34%** of clips to Gemini lifts accuracy from **91% to 96%** (vs. 2,000-trial random 92.9%, p=0.00), keeps 66% of audio on-device, cuts Gemini spend by **~66%** (**~29%** total cost), and characterizes serial P90 latency tradeoffs (7.29s → 9.90s).

---

### Melbourne Parking & Traffic Big Data Analytics
*PySpark, DataFrame API, Spark SQL, Spark UI* · **Aug 2026 – Sep 2026**

- **Large-Scale Ingestion & Schema Enforcement:** Processed **8.6 GB (72.91M parking sensor & 10.96M traffic records)** in PySpark, enforcing explicit schemas for reliable batch parsing and type normalization.
- **Data Quality & Anomaly Attribution:** Built an audit pipeline tracking parse failures and missingness, isolating 408 exit-before-arrival anomalies traced to DST transitions and date-entry errors.
- **Multi-Source Fusion & Spark UI Tuning:** Joined 10-minute traffic feeds via Broadcast Join; eliminated redundant scans found in physical plans by pre-aggregating before windowing, cutting 3-run median runtime from **215.7s to 112.8s (1.9× speedup)** verified via `exceptAll`.

---

### ML Algorithms from Scratch & Kaggle Modeling
*Python, NumPy, scikit-learn, R* · **2025 – 2026**

- **Algorithm Implementation & Leakage Prevention:** Implemented KNN and Ridge Regression (closed-form & gradient descent) matching the scikit-learn API, paired with gapped block CV plus Bootstrap and nested CV hyperparameter tuning.
- **Feature Selection & Classification:** Built happiness regression and 5-class anxiety classifiers over ~70 survey features, applying BIC stepwise feature selection and multi-model comparison.

---

## Technical Skills

- **Voice AI & Agent Evaluation:** ASR (`faster-whisper` decoding tuning & word-level confidence scoring), LLM Function Calling & Agent failure attribution, Prompt Engineering, End-to-End multimodal audio benchmarking (Gemini / Qwen-Omni), TTS (`edge-tts`)
- **Experimentation & ML:** Python (Pandas, NumPy, scikit-learn), controlled ablations, grouped/nested cross-validation, Bootstrap CIs, AUC & permutation/random-baseline testing, feature selection, data anomaly root-cause analysis
- **Data Engineering & Tools:** PySpark (DataFrame API, Spark SQL, Spark UI execution-plan tuning), SQL, R, Git / GitHub, Docker, PostgreSQL, Jupyter
- **Languages:** Mandarin Chinese (Native); English (Full-English M.S. instruction, working proficiency)
