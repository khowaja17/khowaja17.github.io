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
E = mc^2
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
```
## 3) Images 

For best control, use HTML `<figure>` so you can add a caption and keep the image responsive.

<figure style="text-align: center;"> 
    <img src="{{ 'assets/primer/kalmdemo_03.png' | relative_url }}" alt="Example Kalman Filter Response" style="max-width:100%;height:auto;border-radius:12px;"> 
    <figcaption><em>Figure 1.</em> Example Kalman Filter Response $K_k$</figcaption> 
</figure>

Use `<figure style="text-align: center;">` to center justify the image and the caption 

## 4) Tables with Math

You can use pure Markdown tables; MathJax renders fine inside.

| Symbol | Meaning                       | Units |
| :----: | ----------------------------- | :---: |
|  $x_k$ | State at step $k$             |   —   |
|  $P_k$ | State covariance at step $k$  |   —   |
|   $R$  | Measurement noise covariance  |   —   |
|  $K_k$ | Kalman gain from \eqref{eq:K} |   —   |

## 6) Referencing sources
GitHub Pages doesn’t run BibTeX, so the simplest is footnotes or a manual References list with inline citations.

### 6.1 Footnote citations (easy)

This approach follows standard Kalman filtering texts[^jazwinski] and a robotics-oriented treatment[^barfoot].

You can cite the same source again later[^jazwinski] without redefining it.

### 6.2 Manual references section with anchors

In text: Bar-Shalom and Li [1]
 discuss the discrete filter; Maybeck [2]
 covers extensions.

## 7) Common LaTeX snippets you’ll reuse

- Argmin / argmax: $\displaystyle \hat{x} = \arg\min_x |y - Hx|_2^2.$
- Expectation/variance: $\mathbb{E}[x],; \mathrm{Var}[x].$
- Norms: $|x|_2,; |X|_F.$
- Quaternion (scalar-first): $q = [q_w, q_x, q_y, q_z]^\top.$

## 8) TikZ Rendering 
<!-- anywhere in your .md file (no backticks) -->
<figure style="text-align: center;"> 
<script type="text/tikz">
\begin{tikzpicture}[>=stealth]
  % axes
  \draw[->,thick] (0,0) -- (3.2,0) node[right] {$x$};
  \draw[->,thick] (0,0) -- (0,2.4) node[above] {$y$};
  % vector
  \draw[very thick,red] (0,0) -- (2,1) node[midway,above] {$\mathbf{r}$};
  \fill[blue] (2,1) circle (2pt);
\end{tikzpicture}
</script>
<figcaption><em>Figure 1.</em> Example Kalman Filter Response $K_k$</figcaption> 
</figure>


## References
[^jazwinski]: A. H. Jazwinski, *Stochastic Processes and Filtering Theory*. Academic Press, 1970.  
[^barfoot]: T. D. Barfoot, *State Estimation for Robotics*. Cambridge University Press, 2017. DOI: 10.1017/9781316671528
