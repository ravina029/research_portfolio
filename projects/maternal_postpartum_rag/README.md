# 🧠 Trustworthy Retrieval-Augmented Generation for Maternal & Postpartum Health Guidance

---

## 🔍 Abstract

Large Language Models (LLMs) exhibit strong generative capabilities but remain unreliable in high-stakes domains due to hallucinations, lack of uncertainty awareness, and limited interpretability.  

This project presents a **trustworthy Retrieval-Augmented Generation (RAG) system** designed for maternal and postpartum health guidance. The system integrates **hallucination detection, risk-aware safety evaluation, and evidence-grounded explainability** within a fully local deployment framework.

The architecture explicitly separates **generation from verification**, ensuring that outputs are not assumed correct but systematically validated. This work demonstrates how RAG systems can be redesigned for **faithfulness, safety, and transparency** in sensitive domains.

---

#### 📂 Repository Link
➡️ [View Project on GitHub](https://github.com/ravina029/Maternal_postpartum_rag)


## 1. Problem Formulation

LLMs deployed in healthcare-adjacent settings suffer from:

- Hallucinated medical claims despite retrieval grounding  
- Lack of calibrated uncertainty in high-risk scenarios  
- Opaque reasoning limiting user trust  

These issues are amplified in maternal and postpartum health, where:
- users are often non-experts  
- queries are ambiguous or anxiety-driven  
- incorrect advice can delay clinical intervention  

### Research Question

**How can a RAG system be made faithful, safety-aware, and interpretable by design in a high-stakes health domain?**

---

## 2. Research Contributions

### (1) Faithfulness-Aware Generation Pipeline
- Retrieval overlap scoring  
- NLI-based contradiction detection  
- Semantic alignment thresholds  

Generation is **post-validated**, not assumed correct.

---

### (2) Risk-Adaptive Safety Layer
- Toxicity classification  
- Medical risk pattern detection  
- Rule-based intervention  

System behavior:
- **Fail-open** → informational queries  
- **Fail-closed** → high-risk medical intent  

---

### (3) Evidence-Traceable Responses
- Sentence-level grounding  
- Explicit source attribution  
- Transparent reasoning  

---

### (4) Fully Local Deployment
- Local embeddings  
- Quantized LLMs  

Ensures **privacy-preserving and offline execution**.

---

## 3. System Architecture

```text
User Query
   ↓
Query Rewriting (Local LLM)
   ↓
Dense Retrieval (Sentence Transformers)
   ↓
Context Construction
   ↓
LLM Generation
   ↓
Hallucination Detection
   ↓
Safety & Risk Scoring
   ↓
Final Response + Evidence Attribution
```

**Key Design Principle:**  
Verification is **decoupled from generation**, enabling independent evaluation of correctness.

---

## 4. Dataset Construction

### Sources
- WHO maternal care guidelines  
- Clinical pregnancy protocols  
- Government health documents  

### Processing Pipeline
- Semantic chunking  
- Heuristic filtering  
- Domain categorization  
- Audit validation  

### Final Dataset
- **1940 high-quality chunks**  
- Categories:
  - postpartum recovery  
  - breastfeeding  
  - mental health  
  - danger signs  
  - clinical guidelines  

---

## 5. Methodology

### 5.1 Retrieval
Dense retrieval using sentence-transformer embeddings over curated medical corpus.

### 5.2 Generation
Local LLM generates responses conditioned on retrieved context.  
No external API dependency.

### 5.3 Hallucination Detection
Hallucination is defined as:
> lack of grounding or contradiction with retrieved evidence.

Methods:
1. Context overlap ratio  
2. NLI-based contradiction detection  
3. Retrieval distance threshold  

Decision logic:
- Low overlap → flag  
- High contradiction → block  

### 5.4 Safety Evaluation
Multi-factor safety model:
- Toxicity detection  
- Medical risk keyword detection  
- Rule-based escalation  

Outputs:
- Risk score  
- Safety label  
- Fallback response  

### 5.5 Explainability
- Sentence-level evidence mapping  
- Retriever logs  
- LIME / SHAP explanations  
- Transparent safety reasoning  

---

## 6. Evaluation Strategy

### Faithfulness Metrics
- Context Precision  
- Answer Grounding Score  
- NLI Contradiction Rate  

### Safety Metrics
- Toxicity Score  
- Unsafe Response Rate  
- Intervention Accuracy  

---

## 7. Results (Qualitative)

The system demonstrates:
- Reduced hallucinated content  
- Improved grounding in retrieved evidence  
- Effective blocking of unsafe responses  

Performance depends on:
- retrieval quality  
- NLI model reliability  

---

## 8. Limitations

- NLI models are error-prone  
- No human evaluation  
- Rule-based safety lacks generalization  
- Retrieval depends on corpus completeness  
- Static dataset (no temporal updates)  

---

## 9. Future Work

- Uncertainty-aware generation  
- Learning-based safety policies  
- Human-in-the-loop evaluation  
- Multilingual expansion  
- Causal analysis of hallucination  

---

## 10. Research Positioning

This work lies at the intersection of:
- Trustworthy NLP  
- Explainable AI  
- Safety-aware LLM systems  

Focus areas:
- Faithful generation  
- High-stakes AI reliability  
- Auditable NLP systems  

---

## 11. Keywords

Trustworthy NLP, Retrieval-Augmented Generation, Explainable AI, Hallucination Detection, AI Safety

#### 📂 Repository Link
➡️ [View Project on GitHub](https://github.com/ravina029/Maternal_postpartum_rag)

