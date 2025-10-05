# Classification-of-Handwritten-Digits
This project implements a classification algorithm for handwritten digits using Singular Value Decomposition (SVD).  

## Overview

Each digit (0–9) is represented by multiple training images.  
For every class (digit), the algorithm computes the **SVD of its image matrix** and uses the **first few singular vectors** as a basis for that class.  
Unknown test digits are classified according to **how well they can be reconstructed** from each class basis, measured by the **relative residual error** in a least squares sense.

---

## Methodology

1. **Load training and test data**
2. **Compute SVD for each digit class**
   - `A_d = U_d Σ_d V_dᵀ` for each digit `d ∈ {0,…,9}`
   - Keep the first *k* left singular vectors (`U_d[:, :k]`)

3. **Classify test images**
   - For each test image `x`, compute the least-squares projection residual  
     \( r_d = \|x - U_d (U_d^T x)\| / \|x\| \)
   - Classify `x` as the digit `d` with **minimum residual**

4. **Evaluate performance**
   - Compute classification accuracy vs. number of singular vectors (e.g., k ∈ [5, 20])
   - Optionally analyze per-digit difficulty and singular values

---

Visualizations include:
- Accuracy vs. basis count plot  
- Singular value decay for each class  
- Misclassified digits examples  
