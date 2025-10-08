---
title: LaTeX & Page Elements – Mini Cookbook
layout: primer_item
category: Estimation of Dynamic Systems   # or any category you use
youtube_id:
---

This page shows common patterns you’ll use when writing notes with LaTeX, figures, tables, code, and references.

## 1) Math basics

**Inline math** uses single dollars like $a^2 + b^2 = c^2$.  
**Display math** uses double dollars:

$$
E = mc^2.
\label{eq::ss}
$$

**Greek, hats, tildes, bold:**
$\alpha, \beta, \gamma,\; \hat{x}, \tilde{x},\; \mathbf{x},\; \boldsymbol{\Sigma}.$

### 1.1 Aligned equations (with labels & references)

Use `aligned` inside `equation` (or MathJax’s `\begin{aligned}...\end{aligned}` inside `$$ ... $$`) and add `\label{...}`. You can later refer with `\eqref{...}`.

$$
\begin{aligned}
x_{k+1} &= F_k x_k + G_k u_k + w_k, \\
y_k     &= H_k x_k + v_k. \\
\end{aligned}
$$

From \eqref{eq::ss} we derive the **Kalman gain**:
$$
K_k = P^-_k H_k^\top \left(H_k P^-_k H_k^\top + R_k\right)^{-1}. \label{eq:K}
$$

…and we’ll use \eqref{eq:K} again below.

### 1.2 Cases, piecewise, and matrices

**Piecewise**:
$$
f(x)=
\begin{cases}
0, & |x| \le \varepsilon,\\
x, & \text{otherwise}.
\end{cases}
$$

**Vectors & matrices**:
$$
\mathbf{x} =
\begin{bmatrix}
x \\ y \\ z
\end{bmatrix},
\qquad
\mathbf{R} =
\begin{bmatrix}
r_{11} & r_{12} & r_{13} \\
r_{21} & r_{22} & r_{23} \\
r_{31} & r_{32} & r_{33}
\end{bmatrix}.
$$

> **Tip:** Use `\boldsymbol{a}` for bold symbols in math, `\mathbf{A}` for bold roman (matrices).

---

## 2) Text, code, and callouts

You can use **bold**, *italics*, `code`, and blockquotes:

> **Note.** If your LaTeX contains underscores in plain text (not math), escape them like `\_`.

**Code block (with syntax highlighting):**
```python
def k_gain(P, H, R):
    # K = P H^T (H P H^T + R)^-1
    S = H @ P @ H.T + R
    return P @ H.T @ np.linalg.inv(S)
