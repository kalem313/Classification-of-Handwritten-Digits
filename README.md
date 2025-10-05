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
3. **Classify test images**
4. **Evaluate performance**
   
---

Visualizations include:
- Accuracy vs. basis count plot  
- Singular value decay for each class  
- Misclassified digits examples  
