# 🎬 Trustworthy Sentiment Classification: Classical vs Transformer Models

---

## 🔍 Abstract

Transformer-based models dominate modern NLP benchmarks, yet their deployment in real-world systems raises concerns around computational cost, interpretability, and robustness.  

This project presents a **comparative study of classical machine learning models and transformer-based architectures** for sentiment classification on the IMDB dataset. We systematically evaluate trade-offs between **accuracy, efficiency, and interpretability**, and demonstrate that well-tuned classical models can approach transformer-level performance under certain conditions.

The study highlights the importance of **model selection beyond raw accuracy**, particularly in contexts requiring explainability and resource efficiency.

---

## 1. Problem Formulation

Sentiment analysis is a foundational NLP task, often used as a benchmark for evaluating modeling approaches. While transformer-based models such as DistilBERT achieve state-of-the-art results, they introduce:

- High computational cost  
- Limited interpretability  
- Deployment complexity  

This raises a fundamental question:

> **Are transformer models always necessary, or can classical methods provide competitive performance with better interpretability and efficiency?**

---

## 2. Research Contributions

### (1) Comparative Evaluation Framework
A unified pipeline comparing:
- Logistic Regression  
- Random Forest  
- Multinomial Naive Bayes  
- DistilBERT  

All models are evaluated under consistent preprocessing and metrics.

---

### (2) Efficiency vs Performance Analysis
- Classical models achieve competitive accuracy with significantly lower computational cost  
- Transformer models provide marginal gains at higher resource expense  

---

### (3) Interpretability-Focused Design
- LIME-based explanations applied across models  
- Token-level contribution analysis for prediction transparency  

---

### (4) End-to-End Reproducible Pipeline
- Modular training, evaluation, and inference  
- Streamlit-based interactive deployment  

---

## 3. Methodology

### 3.1 Dataset

- IMDB Movie Review Dataset  
- Binary sentiment classification (positive / negative)  
- Standard train-test split  

---

### 3.2 Preprocessing

- Text cleaning and normalization  
- Tokenization  
- TF-IDF vectorization (classical models)  
- Transformer tokenization (DistilBERT)  

---

### 3.3 Models

#### Classical Models
- Logistic Regression  
- Random Forest  
- Multinomial Naive Bayes  

#### Transformer Model
- DistilBERT (fine-tuned)  

---

### 3.4 Training Strategy

- Classical models trained on TF-IDF features  
- DistilBERT fine-tuned using Hugging Face Transformers  
- Evaluation on held-out test set  

---

## 4. Results

| Model              | Accuracy | Precision | Recall  | F1      |
|--------------------|----------|-----------|---------|---------|
| LogisticRegression | 0.894    | 0.892     | 0.896   | 0.894   |
| RandomForest       | 0.848    | 0.857     | 0.834   | 0.846   |
| MultinomialNB      | 0.865    | 0.873     | 0.854   | 0.863   |
| DistilBERT         | 0.900    | 0.896     | 0.905   | 0.901   |

---

## 5. Analysis

### Key Observations

- DistilBERT achieves the highest overall performance (F1: 0.901)  
- Logistic Regression performs competitively (F1: 0.894)  
- Classical models remain strong baselines despite simplicity  
- Random Forest underperforms relative to other methods  

### Critical Insight

> The performance gap between classical and transformer models is **smaller than commonly assumed**, suggesting that model selection should consider efficiency and interpretability, not just accuracy.

---

## 6. Explainability

Interpretability is analyzed using:

- **LIME (Local Interpretable Model-Agnostic Explanations)**  
  - Provides token-level importance scores  
  - Enables comparison of reasoning across models  

Future extensions:
- SHAP for global explanations  
- Integrated Gradients for transformer interpretability  

---

## 7. System Architecture

```text
Raw Text
   ↓
Preprocessing
   ↓
Feature Extraction
   ├── TF-IDF → Classical Models
   └── Tokenization → DistilBERT
   ↓
Model Training
   ↓
Evaluation
   ↓
Prediction Interface (Streamlit)
```

---

## 8. Deployment

An interactive Streamlit application enables:

- Real-time sentiment prediction  
- Comparison across models  
- Visualization of predictions  

---

## 9. Limitations

- Single-domain dataset (IMDB only)  
- Limited interpretability methods (LIME only)  
- No bias or fairness analysis  
- No extensive hyperparameter optimization  
- No human evaluation of predictions  

---

## 10. Future Work

- Cross-domain evaluation (Yelp, Amazon)  
- Multilingual sentiment analysis  
- Bias and fairness assessment  
- Advanced interpretability methods (SHAP, IG)  
- Confidence calibration  
- Human-in-the-loop evaluation  

---

## 11. Research Positioning

This project contributes to:

- Efficient NLP modeling  
- Explainable AI  
- Practical model selection strategies  

It highlights the importance of:
- balancing accuracy with interpretability  
- evaluating real-world deployment constraints  

---

## 12. Keywords

Sentiment Analysis, Explainable AI, Classical Machine Learning, Transformers, Model Comparison, NLP

---

## ⚙️ How to Run

### Setup
```bash
git clone https://github.com/<your-username>/IMDB_text_classification.git
cd IMDB_text_classification
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Train Models
```bash
python src/train_classical.py
python src/train_hf_model.py
```

### Evaluate
```bash
python src/compare_models.py
```

### Run App
```bash
streamlit run app.py
```

---

## 👩‍💻 Author

**Ravina Behwal**  
Master’s in Mathematics | Aspiring PhD Researcher in NLP & Trustworthy AI  
