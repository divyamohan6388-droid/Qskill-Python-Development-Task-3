# 🔢 MatrixMaster: Interactive NumPy Operations Console

> **QSkill Python Development Internship — Slab 1, Task 3**

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.26%2B-013243?logo=numpy&logoColor=white)](https://numpy.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Internship](https://img.shields.io/badge/QSkill-Python%20Internship-purple)](https://qskill.in/)

---

## 📌 Project Overview

**MatrixMaster** is a fully interactive, command-line matrix operations console built entirely with **Python** and **NumPy**. It allows users to input matrices row-by-row via keyboard, choose from a numbered menu of **9 matrix operations**, and receive richly formatted results with **full step-by-step mathematical working** shown for every computation — including verification steps to confirm correctness.

---

## ✨ Features

- 🖥️ **Interactive CLI Menu** — Numbered keyboard-driven interface (choices 0–9)
- 📥 **Flexible Matrix Input** — Enter any matrix row-by-row, space-separated
- ✅ **9 Full Operations** — Addition, Subtraction, Multiplication, Transpose, Determinant, Inverse, Eigenvalues, Rank, Trace
- 📐 **Step-by-Step Working** — Full mathematical working shown for every operation
- 🔁 **Verification Steps** — Automatic checks: `A × A⁻¹ = I`, `A·v = λ·v`
- 🛡️ **Input Validation** — Shape checks, singularity detection, type error handling
- 📘 **Auto Demo** — All 9 operations demonstrated on sample matrices (Step 7)
- 🌀 **Eigenvalue Visualization** — Eigenvector quiver plot in 2D space

---

## 🗂️ Project Structure

```
MatrixMaster/
│
├── MatrixMaster_NumPy_Operations.ipynb   # Main Jupyter Notebook
└── README.md                             # This file
```

---

## ⚙️ Operations Supported

| # | Operation | Notation | Requirement | Step-by-Step Method |
|---|-----------|----------|-------------|---------------------|
| 1 | ➕ Addition | `A + B` | Same shape | `C[i,j] = A[i,j] + B[i,j]` per cell |
| 2 | ➖ Subtraction | `A − B` | Same shape | `C[i,j] = A[i,j] − B[i,j]` per cell |
| 3 | ✖️ Multiplication | `A × B` | A-cols = B-rows | Dot product expansion per cell |
| 4 | 🔄 Transpose | `Aᵀ` | Any matrix | Each index swap: `Aᵀ[i,j] = A[j,i]` |
| 5 | 📐 Determinant | `det(A)` | Square only | 2×2 formula / 3×3 cofactor / n×n LU |
| 6 | 🔃 Inverse | `A⁻¹` | Square + non-singular | det check → Gauss-Jordan → `A × A⁻¹ = I` verify |
| 7 | 🌀 Eigenvalues | `λ, v` | Square only | Characteristic eq. → `A·v = λ·v` verification |
| 8 | 📊 Rank | `rank(A)` | Any matrix | SVD singular values counted |
| 9 | ➰ Trace | `tr(A)` | Square only | Diagonal sum + eigenvalue sum verification |

---
```
═══════════════════════════════════════════════════════
  Welcome to 🔢 MatrixMaster!
  QSkill Python Internship | Slab 1 — Task 3
═══════════════════════════════════════════════════════

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  🔢  MatrixMaster — Main Menu
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  [1]  ➕  Addition            (A + B)
  [2]  ➖  Subtraction         (A − B)
  [3]  ✖️   Multiplication      (A × B)
  [4]  🔄  Transpose           (Aᵀ)
  [5]  📐  Determinant         (det(A))
  [6]  🔃  Inverse             (A⁻¹)
  [7]  🌀  Eigenvalues         (λ, v)
  [8]  📊  Rank                (rank(A))
  [9]  ➰  Trace               (tr(A))
  [0]  🚪  Exit
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  👉 Enter your choice (0–9):
```

---

## 📥 How to Input a Matrix

Enter matrices **row by row**, with values **space-separated**. Type `done` after the last row.

```
  📥 Enter Matrix A row by row (space-separated values).
     Type  "done"  after the last row.
     Example row → 1 2 3
  ---------------------------------------------
    Row 1: 3 1
    Row 2: 2 4
    Row 3: done

  Matrix A  [2×2]
  ┌──────────────┐
  │ C1    C2    │
  ├──────────────┤
  │  3     1    │
  │  2     4    │
  └──────────────┘
```

### Quick Input Reference

| Matrix Size | Example Input |
|-------------|--------------|
| 2×2 | `Row 1: 1 2` → `Row 2: 3 4` → `done` |
| 3×3 | `Row 1: 1 2 3` → `Row 2: 4 5 6` → `Row 3: 7 8 9` → `done` |
| 2×3 | `Row 1: 1 2 3` → `Row 2: 4 5 6` → `done` |
| 1×4 | `Row 1: 5 10 15 20` → `done` |

---

## 🔍 Step-by-Step Working Examples

### ➕ Addition (2×2 matrices)
```
  🔍 Step-by-Step Working:
     C[1,1] = A[1,1] + B[1,1] = 3 + 1 = 4
     C[1,2] = A[1,2] + B[1,2] = 1 + 2 = 3
     C[2,1] = A[2,1] + B[2,1] = 2 + 3 = 5
     C[2,2] = A[2,2] + B[2,2] = 4 + 1 = 5
```

### 📐 Determinant (2×2 matrix)
```
  🔍 Step-by-Step Working:
     det(A) = (a×d) − (b×c)
            = (3×4) − (1×2)
            = 12 − 2
            = 10
  ✅ Matrix is NON-SINGULAR (invertible).
```

### 🔃 Inverse (2×2 matrix)
```
  🔍 Step-by-Step Working:
     Step 1 → Calculate det(A) = 10
     Step 2 → det(A) ≠ 0, so inverse exists.
     Step 3 → A⁻¹ = (1/10) × [[4, -1], [-2, 3]]
     Step 4 → Verify: A × A⁻¹ ≈ Identity matrix
              Check passed: True ✅
```

### 🌀 Eigenvalues
```
  Eigenvalue  λ1 = 2.0
  Eigenvector v1 = [ -0.7071  0.7071 ]
  Verify A·v1 ≈ λ1·v1: ✅ PASS

  Eigenvalue  λ2 = 5.0
  Eigenvector v2 = [ -0.4472  -0.8944 ]
  Verify A·v2 ≈ λ2·v2: ✅ PASS
```

---

## 🛡️ Input Validation & Error Handling

MatrixMaster validates every input before computation:

| Validation | Error Message |
|------------|---------------|
| Non-numeric input | `❌ Invalid input — use numbers only (e.g. 1 2 3).` |
| Row length mismatch | `❌ Row length mismatch — expected N values, got M.` |
| Empty input | `⚠️  Empty input — enter numbers or type "done".` |
| Shape mismatch (add/sub) | `❌ Shape mismatch: A(m×n) ≠ B(p×q). Cannot add.` |
| Incompatible shapes (mul) | `❌ Shape error: Need A-cols(n) == B-rows(p).` |
| Non-square for det/inv/trace | `❌ Not square: (m×n). Operation requires n×n matrix.` |
| Singular matrix (inverse) | `❌ det(A) ≈ 0 → Matrix is SINGULAR. Inverse does not exist.` |

---

## 📐 Mathematical Background

### Key Formulas Used

**Determinant (2×2):**
```
det(A) = a·d − b·c
```

**Inverse (2×2):**
```
A⁻¹ = (1/det(A)) × [[d, -b], [-c, a]]
```

**Matrix Multiplication:**
```
C[i,j] = Σ(k) A[i,k] × B[k,j]
```

**Eigenvalue Equation:**
```
A·v = λ·v  ⟹  det(A − λI) = 0
```

**Trace:**
```
tr(A) = Σ(i) A[i,i] = sum of diagonal elements = sum of eigenvalues
```

**Rank (via SVD):**
```
rank(A) = number of non-zero singular values of A
```

---

## 🧑‍💻 Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| Python | 3.10+ | Core programming language |
| NumPy | 1.26+ | All matrix operations (`numpy.linalg`) |
| Matplotlib | 3.8+ | Eigenvalue/eigenvector visualization |
| Jupyter Notebook | 7.x | Interactive development environment |

### NumPy Functions Used

| Operation | NumPy Function |
|-----------|---------------|
| Addition | `np.add(A, B)` |
| Subtraction | `np.subtract(A, B)` |
| Multiplication | `np.matmul(A, B)` |
| Transpose | `A.T` |
| Determinant | `np.linalg.det(A)` |
| Inverse | `np.linalg.inv(A)` |
| Eigenvalues | `np.linalg.eig(A)` |
| Rank | `np.linalg.matrix_rank(A)` |
| Trace | `np.trace(A)` |
| SVD (for rank) | `np.linalg.svd(A)` |

---

## 💡 Key Highlights

- **Zero dependencies beyond NumPy** — pure NumPy linalg for all math operations.
- **Works for any size** — from 2×2 to n×n matrices (memory permitting).
- **Educational focus** — every step of the working is printed, not just the result.
- **Verification built-in** — `A × A⁻¹ = I` and `A·v = λ·v` checks run automatically.
- **Graceful error handling** — invalid inputs never crash the console; clear messages guide the user.

---

## 🎓 Internship Details

| Field | Details |
|-------|---------|
| Organization | QSkill |
| Domain | Python Development |
| Slab | Slab 1 (Beginners) |
| Task | Task 3 of 3 |
| Duration | 1st April 2026 – 1st May 2026 |
| Deadline | 1st May 2026 |

---

## 🙌 Acknowledgements

- Built using **NumPy's `linalg` module** for all linear algebra computations
- Built as part of the **QSkill Python Development Internship — Slab 1**

---

*Made with ❤️ using Python & NumPy*
