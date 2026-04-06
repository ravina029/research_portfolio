# Master's Thesis: Stability and Accuracy of Permutation-Invariant Embedding Schemes

hhhh
## 📌 Overview

This thesis investigates the **theoretical foundations of permutation-invariant representations**, a critical component in modern machine learning architectures dealing with unordered data such as sets, point clouds, and graphs.

The work focuses on two key properties:

- **Injectivity (Separation):** Ensuring distinct inputs map to distinct representations  
- **Stability (Bi-Lipschitz continuity):** Ensuring robustness to small input perturbations  

The goal is to design embedding schemes that are both **expressive and stable**, while minimizing computational complexity.

---

## 🎯 Problem Statement

Many real-world machine learning tasks involve **unordered data** (e.g., sets, point clouds, graphs). Standard neural architectures fail to respect permutation invariance.

Key challenges:

- Designing **permutation-invariant embeddings**
- Ensuring **injectivity (no information loss)**
- Achieving **stability under perturbations**
- Reducing **embedding dimension (computational cost)**

---

## 📚 Research Context

This work builds on foundational architectures such as:

- DeepSets (Zaheer et al., 2017)
- Permutation-invariant embeddings (Balan et al.)
- Low-dimensional invariant embeddings (Dym & Gortler)

### Key gap addressed:
- Existing methods either:
  - Lack **stability guarantees**, or  
  - Require **very high embedding dimensions**  

---

## 💡 Core Contributions

### 1. ❌ Limitation of Algebraic Embeddings
- Proved that **power-sum based embeddings are NOT Bi-Lipschitz**
- Extended result:
  - Any embedding based on **smooth or piecewise smooth summation functions fails stability**

👉 Implication:  
Common architectures like DeepSets (sum aggregation) have **fundamental stability limitations**

---

### 2. 📉 General Negative Result
- Proved that:
  > Any permutation-invariant function that is differentiable at certain structured points is NOT Bi-Lipschitz

👉 This is a **broad impossibility result**, not just a specific case

---

### 3. ✅ Sorting-Based Embeddings (Positive Result)
- Analyzed embeddings of the form:
  \[
  \beta_A(X) = \downarrow (AX)
  \]

- Showed:
  - These embeddings are **Bi-Lipschitz**
  - Stability depends on **singular values of matrix A**

---

### 4. 🚀 Improved Theoretical Bound (Key Contribution)

Improved required embedding dimension for injectivity:

| Work | Required Dimension |
|------|------------------|
| Balan et al. | \(1 + (d-1)n!\) |
| Dym & Gortler | \(2nd + 1\) |
| **This Work** | **\(D > n(d - 1)\)** |

👉 This is a **significant reduction**, making models more practical

---

### 5. 📊 Improved Lipschitz Bounds

Derived tighter bounds:

- Upper bound:  
  \[
  M = \sigma_1(A)
  \]

- Lower bound:  
  \[
  \sigma_{d,k}(A) \le m \le \sigma_d(A)
  \]

👉 Direct connection between **linear algebra properties** and **model stability**

---

## 🧪 Experimental Analysis

Two experiments were conducted:

### 1. Stability Analysis
- Empirical estimation of Lipschitz constants
- Key finding:
  - Stability improves with **embedding dimension (D)**
  - Surprisingly stable even when theory suggests otherwise

---

### 2. Classification Task
- Synthetic permutation-invariant binary classification
- Architecture:
  - Sorting-based embedding + fully connected network

### Results:
- Accuracy:
  - >99% for small D
  - 100% for D > 20
- Stability–accuracy tradeoff observed

---

## 🔍 Key Insights

- ❌ Sum-based aggregation (DeepSets-style) → **inherently unstable**
- ✅ Sorting-based embeddings → **robust and theoretically grounded**
- ⚠️ Theory vs practice gap:
  - Empirical results outperform theoretical guarantees
- 📈 Embedding dimension plays the most critical role

---

## 🔮 Future Directions

- Further reduce embedding dimension below theoretical bounds
- Analyze discrepancy between:
  - **Theoretical guarantees vs empirical performance**
- Extend framework to:
  - Graph neural networks
  - Real-world datasets
- Explore applications in:
  - **Trustworthy AI**
  - **Robust representation learning**

---

## 🔗 Research Output

- A key theorem from this thesis was included in:
  - *Neural Injective Functions for Multisets, Measures and Graphs via a Finite Witness Theorem*
  - arXiv: https://doi.org/10.48550/arXiv.2306.06529

---

## 🛠️ Artifacts

- 📄 Full Thesis: [https://github.com/ravina029/Research_portfolio/blob/main/Research/M.Sc_thesis.pdf]
- 💻 Code: [https://github.com/ravina029/Research_portfolio/tree/main/Research/Experiments_and%20_observations/Experimetal_code]
- 📊 Experimental Results: [https://github.com/ravina029/Research_portfolio/blob/main/Research/Experiments_and%20_observations/Observations]

---

## 🧠 Research Relevance

This work directly connects to modern research areas:

- Trustworthy AI
- Robust Machine Learning
- Set / Graph Representation Learning
- Geometric Deep Learning

---

## ⚡ Personal Takeaway

This thesis shaped my current research direction toward:

> Designing **stable, interpretable, and efficient representation learning methods** for real-world AI systems.

---
