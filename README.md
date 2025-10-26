# 🧠 NLP Newspaper Article Analysis on AI’s Impact  
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://www.python.org/) 
[![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange?logo=jupyter)](https://jupyter.org/)
[![NLP](https://img.shields.io/badge/Field-NLP-green)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> 📰 Natural Language Processing (NLP) analysis of **~200,000 newspaper articles** exploring how the media portrays the **impact of Artificial Intelligence (AI)** on jobs, industries, and society.

---

## 📘 Overview
This project applies **Natural Language Processing (NLP)** techniques to a large corpus of global newspaper articles about **Artificial Intelligence, Data Science, and Machine Learning**.  

The goal is to uncover:
- How public sentiment toward AI has evolved over time  
- Which entities and industries are most associated with AI  
- What dominant topics and narratives shape the perception of AI  

🧩 **Techniques used:**  
Tokenization · Lemmatization · Sentiment Analysis (VADER & Logistic Regression) · Topic Modeling (LDA) · Named Entity Recognition (SpaCy)

---

## 📂 Repository Structure

```bash
📦 NLP-AI-Impact-Analysis/
│
├── 📊 NLP_Final_Project_Data_Preprocessing.ipynb  # Data cleaning & feature engineering
├── 📊 NLP_Final_Project_Topic_Modeling.ipynb      # Topic modeling with LDA
├── 📊 NLP_Final_Project_Sentiment_Analysis.ipynb  # Sentiment scoring & trend analysis
├── 📊 NLP_Final_Project_NER.ipynb                 # Named entity recognition with SpaCy
├── 📄 NLP Final Project - Newspaper Article Analysis on AI Impact.pdf  # Final report
└── 📄 README.md                                   # Documentation
```

---

## 🔍 Key Findings
| **Theme**                      | **Insight**                                                                                      |
| ------------------------------ | ------------------------------------------------------------------------------------------------ |
| 📰 **Media Sentiment**         | AI coverage is overwhelmingly **positive (~90%)**, emphasizing innovation, growth, and research. |
| 💼 **Top Entities (Positive)** | ⭐ *Microsoft*, *Google*, *Apple*, *Amazon*                                                       |
| ⚠️ **Top Entities (Negative)** | *Google*, *Trump*, *Biden*, *Android* (linked to privacy & ethics concerns)                      |
| 💡 **Positive Topics**         | AI innovation, business growth, and research collaboration                                       |
| 🔒 **Negative Topics**         | Privacy risks, misinformation, political manipulation, and ethical challenges                    |
| 📈 **Temporal Trends**         | Sentiment peaked in **2022** (ChatGPT, Bard launch) with cautious decline post-2023              |

---

## 🧮 Methodology

### 🧹 Data Preprocessing
- **Goal:** Prepare the corpus (~200k articles) for downstream NLP tasks.  
- **Steps:**
  - Removed URLs, hashtags, mentions, symbols, and publication metadata.  
  - Filtered out stopwords and non-alphabetic tokens.  
  - Kept only the **5th–95th percentile** of articles by length to eliminate outliers.  
  - Tokenized and lemmatized text using **SpaCy** to standardize vocabulary.  
  - Engineered time-based features (`year`, `month`, `day_of_week`) for temporal analysis.  
- **Result:** 159,769 cleaned and feature-enriched articles ready for sentiment and topic analysis.  


### 🧭 Topic Modeling
- **Objective:** Identify dominant themes in AI-related news coverage.  
- **Approach:**
  - Used **Latent Dirichlet Allocation (LDA)** implemented with *Gensim*.  
  - Converted lemmatized tokens into bag-of-words and TF–IDF representations.  
  - Tuned the number of topics using coherence score optimization.  
- **Findings:**
  - AI-driven innovations in global markets and business growth.  
  - AI in media, communication, and public discourse.  
  - Privacy, misinformation, and ethical challenges.  
  - Technological advancements from companies like Google, Microsoft, and OpenAI.  


### 💬 Sentiment Analysis
- **Objective:** Quantify how AI is portrayed emotionally in media text.  
- **Models Tested:**
  - **Custom Logistic Regression** trained on labeled Yelp reviews (binary polarity).  
  - **VADER (Valence Aware Dictionary and sEntiment Reasoner)** for rule-based sentiment scoring.  
- **Outcome:**  
  - **VADER** selected for higher accuracy and nuanced classification of neutral sentiment.  

**Sentiment Distribution:**

| Sentiment | Count |
|------------|--------|
| 😄 Extremely Positive | 145,470 |
| 🙂 Positive | 3,318 |
| 😐 Neutral | 2,188 |
| 🙁 Negative | 988 |
| 😡 Extremely Negative | 7,805 |


### 🏷️ Named Entity Recognition (NER)
- **Objective:** Extract organizations, people, and locations frequently associated with AI discussions.  
- **Approach:**
  - Applied **SpaCy’s pre-trained `en_core_web_sm`** model for entity tagging.  
  - Linked entities to sentiment polarity to measure how they’re portrayed in AI narratives.  
- **Results:**
  - **Top Positive Entities:** *Microsoft*, *Google*, *Apple*, *Amazon*.  
  - **Top Negative Entities:** *Google*, *Trump*, *Biden*, *Android*.  
  - Notable duality — *Google* and *Microsoft* appear in both lists, reflecting mixed perceptions (innovation vs. privacy concerns).  


### 📊 Summary of Workflow
1. **Data Cleaning →** structured, tokenized corpus  
2. **Feature Engineering →** time-based variables  
3. **Topic Modeling →** LDA-based theme extraction  
4. **Sentiment Analysis →** VADER classification  
5. **Entity Recognition →** SpaCy NER + sentiment alignment  

This modular pipeline enables both **quantitative** (sentiment trend analysis) and **qualitative** (theme discovery) insights into how AI is represented across global news media.

---

## 📈 Visual Insights

### 🕓 Temporal Sentiment Trends (2020–2025)
- **2020–2022:** Steady growth in positive sentiment as AI adoption accelerated in mainstream applications.  
- **2022:** Sentiment reached its **peak**, coinciding with major AI breakthroughs such as *ChatGPT* and *Google Bard*.  
- **2023:** Noticeable **decline in positivity**, attributed to rising debates on privacy, misinformation, and ethical AI.  
- **2024–2025:** Slight rebound in optimism, but with greater nuance — reflecting public awareness of both benefits and risks.  

🧭 **Interpretation:**  
Media sentiment evolved from *enthusiastic adoption* to *cautious optimism*, suggesting a maturing understanding of AI’s societal role.


### 🧩 Entity–Sentiment Correlation
- **Positive Entities:** *Microsoft*, *Google*, *Apple*, and *Amazon* consistently appeared in favorable contexts, often tied to innovation and technological leadership.  
- **Negative Entities:** *Trump*, *Biden*, and *Android* were frequently associated with controversial narratives, politics, or data privacy concerns.  
- **Dual Polarity:** Both *Microsoft* and *Google* appeared among **positive and negative mentions**, indicating their central yet complex roles in AI discussions.  

📊 **Observation:**  
Media discourse frequently intertwines technological optimism with scrutiny of large corporations, reflecting a tension between innovation and accountability.


### 🌍 Regional Sentiment Trends
- **United States:** Generally positive, emphasizing AI-driven business growth and productivity.  
- **Europe:** Balanced tone, highlighting both innovation and regulation (GDPR, ethics).  
- **Middle East & Asia:** Strong optimism toward AI’s role in economic diversification and public services.  

💬 **Insight:**  
Global media maintains a largely **positive outlook**, though regional narratives differ based on economic maturity, policy stance, and cultural adoption of AI.



### 💡 Summary
- Sentiment toward AI remains **net positive**, with localized fluctuations.  
- Peaks in sentiment often align with major AI product launches or breakthroughs.  
- Downturns coincide with ethical debates, misinformation incidents, or regulatory events.  
- The interplay between **technological optimism** and **ethical caution** defines the modern AI narrative in media.


**Conclusion:**  
While AI is largely portrayed in a positive light, media sentiment reflects a shift toward **cautious optimism** — acknowledging both innovation and the ethical implications of rapid AI adoption.


---

## 💡 Actionable Recommendations

### 1. 🤝 Human–AI Collaboration
Encourage **collaborative integration** between humans and AI rather than replacement.  
- Reimagine job roles to leverage AI as an augmentation tool.  
- Promote **cross-functional collaboration** between technical and non-technical teams.  
- Embed **human feedback loops** in AI systems to enhance trust and usability.  


### 2. 📚 AI Upskilling & Training
Invest in large-scale **AI literacy and data education** programs.  
- Introduce **AI ethics, bias, and transparency** training in workplaces.  
- Provide hands-on exposure through **workshops, certifications, and learning labs**.  
- Empower workers to transition into **AI-augmented roles** with confidence.  


### 3. 🚀 Career Pathways & Reskilling
Develop clear **career transition frameworks** for the AI era.  
- Support employees through **mentorship programs** and flexible reskilling options.  
- Align corporate learning with **AI-driven business strategies**.  
- Create internal **AI fellowship or rotational programs** to promote adaptability.  


### 4. 🧭 AI Governance & Regulation
Establish **robust, adaptive governance** to ensure responsible AI use.  
- Create transparent AI auditing systems that track **data provenance and decision rationale**.  
- Support **public–private partnerships** to align ethical standards across sectors.  
- Strengthen public trust through **open communication and accountability** in AI deployment.  


### 5. 🔬 Continuous Learning & Innovation
Foster a **culture of experimentation** and life-long learning.  
- Launch **AI innovation labs** and internal hackathons.  
- Encourage employees to propose and test small-scale AI pilots.  
- Integrate **feedback mechanisms** to continuously evaluate societal and business impacts of AI.  


**Summary:**  
To thrive in an AI-driven world, organizations must prioritize **human-centered innovation**, **ethical frameworks**, and **continuous education**. This ensures that AI serves as a **collaborative partner** — enhancing human capability rather than displacing it.


---

## 🧭 Future Work

As this analysis provides a strong foundation for understanding how AI is portrayed in the media, several opportunities remain to **extend the scope and depth** of this research.


### 🌍 1. Multilingual & Cross-Cultural Analysis
- Expand the dataset to include **non-English news sources** (e.g., Spanish, Mandarin, Arabic) to capture global sentiment diversity.  
- Examine how cultural, political, and economic factors shape **regional differences** in AI perception.  
- Apply multilingual NLP models such as **XLM-RoBERTa** or **mBERT** for cross-language comparison.  



### 🤖 2. Transformer-Based Sentiment & Topic Models
- Replace rule-based sentiment methods (like VADER) with **deep transformer models** (BERT, RoBERTa, DistilBERT).  
- Incorporate **contextual embeddings** to detect sarcasm, tone, and complex sentiment shifts in news text.  
- Use **BERTopic** or **Top2Vec** for dynamic and contextual topic modeling.  



### 📊 3. Interactive Visualization Dashboard
- Develop a **Streamlit or Plotly Dash web app** to explore sentiment trends interactively.  
- Enable filters by **entity, region, and time period** to allow deeper insight into AI narratives.  
- Integrate **real-time updates** as new articles are scraped or added to the corpus.  



### 📈 4. Temporal Forecasting & Predictive Modeling
- Apply **ARIMA, Prophet, or LSTM models** to forecast future sentiment toward AI.  
- Identify **inflection points** that may correspond with major AI events or policy changes.  
- Explore **Granger causality** between public sentiment and stock performance of AI-driven companies.  



### 🧩 5. Ethical AI & Media Trust Analysis
- Conduct **stance detection** and **bias classification** to assess how ideological leanings affect AI coverage.  
- Analyze the framing of AI news in different media ecosystems (public vs. private, tech vs. general).  
- Study the link between **AI-related misinformation** and sentiment polarization across outlets.  


**In Summary:**  
The next phase of this project will focus on making the analysis more **interactive, multilingual, and predictive**, enabling researchers, policymakers, and the public to better understand how narratives around Artificial Intelligence evolve over time.

