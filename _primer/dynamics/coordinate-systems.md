---
title: Coordinate Systems
layout: primer_item
category: Dynamic Systems
youtube_id: kAbCdEfGh12   # replace
---
## Introduction
The study of kinematics is the matter of describing the motion of a particle without concern for it's mass or inertia. To understand motion, we must understand the position, velocity, and acceleration, that is, where and how a system is moving through space. The study of motion necessitates a frame of reference, also known as coordinate system. 

A coordinate system is defined by 

  1.) An origin (point)

  2.) An orientation (orthogonal coordinate axis components

Common coordinate systems include:
- Cartesian
- Cylindrical
- Spherical
- Inertial
- Body Fixed
- Earth Centered Inertial (ECI)
- Earth Centered Earth Fixed (ECEF)

Theoretically there are an infinite set of coordinate systems and furthermore infinite number of ways to parameterize a vector in orthogonal coordinate axis components. Furthermore, there is no incorrect choice of coordinate system just one that makes it easier to study the system.

## Notation

<figure class="tikz-figure center">
    <script type="text/tikz">
        \begin{tikzpicture}[>=stealth, line cap=round, line join=round, thick, scale=1.4]
          % --- optional light grid (comment out to remove) ---
          % \draw[step=1cm,very thin,gray!30] (-2.5,-2) grid (3.4,2.6);
          % Frame label
          \node[red] at (-1.6,2.2) {$\mathcal{N}$};
          % Origin
          \coordinate (O) at (0,0);
          % Axes
          \draw[->] (O) -- (3.0,0) node[below right=3pt] {$\hat{\mathbf n}_2$};   % x/right
          \draw[->] (O) -- (0,2.4) node[above left=3pt]  {$\hat{\mathbf n}_3$};   % up
          \draw[->] (O) -- (-2.0,-1.3) node[below left=3pt] {$\hat{\mathbf n}_1$};% down-left (gives 3-D feel)
          % Origin label
          \node at (0.25,-0.35) {$O_N$};
        \end{tikzpicture}
    </script>
    <figcaption><em>Figure 1.</em> Cartesian Coordinate System </figcaption>
</figure>
The coordinate system is defined with the following expression
$$
\mathcal{N} = \{ O , \hat{\mathbf n}_1, \hat{\mathbf n}_2, \hat{\mathbf n}_3 \}
$$
where $\hat{\mathbf x}$ denotes a unit vector (i.e $||\hat{\mathbf x} ||_2 = 1$ ).

Now we may introduce a particle $P$ where the position is defined by the vector $\mathbf{r} = \overline{OP}$ which is the vector pointing from $O$ to $P$.
<figure class="tikz-figure center">
    <script type="text/tikz">
        \begin{tikzpicture}[>=stealth, line cap=round, line join=round, thick, scale=1.4]
        % ------------------ parameters: coordinates of P ------------------
        \def\X{1.4}   % x along \hat n_1  (to the right)
        \def\Y{3.0}   % y along \hat n_2  (down-left direction)
        \def\Z{1.6}   % z along \hat n_3  (up)
        % ------------------ basis directions (2D oblique projection) -----
        \coordinate (O)  at (0,0);
        \coordinate (e2) at (1,0);        % \hat n_2  (x-axis, right)
        \coordinate (e3) at (0,1);        % \hat n_3  (z-axis, up)
        \coordinate (e1) at (-0.75,-0.48);% \hat n_1  (gives 3-D look)
        % Point and its projections
        \coordinate (Px)   at ($(O)+\X*(e1)$);
        \coordinate (Py)   at ($(O)+\Y*(e2)$);
        \coordinate (Pxy)  at ($(O)+\X*(e1)+\Y*(e2)$);
        \coordinate (P)    at ($(Pxy)+\Z*(e3)$);
        % ------------------ frame label and origin ------------------------
        \node[red] at (-1.6,2.2) {$\mathcal N$};
        \node at (0.25,-0.35) {$O_N$};
        % ------------------ axes -----------------------------------------
        \draw[->] (O) -- ($(O)+3.6*(e2)$) node[below right=3pt] {$\hat{\mathbf n}_2$};
        \draw[->] (O) -- ($(O)+2.6*(e3)$) node[above left=3pt]  {$\hat{\mathbf n}_3$};
        \draw[->] (O) -- ($(O)+2.6*(e1)$) node[below left=3pt]  {$\hat{\mathbf n}_1$};
        % ------------------ projections (dashed) --------------------------
        \draw[densely dashed] (Px) -- (Pxy) node[midway,below] {$x$};
        \draw[densely dashed] (Py) -- (Pxy) node[midway,sloped,below] {$y$};
        \draw[densely dashed] (Pxy) -- (P) node[midway,right] {$z$};
        % ------------------ position vector and point ---------------------
        \draw[very thick,blue,->] (O) -- (P) node[midway,above] {$\mathbf r$};
        \fill[blue] (P) circle (2pt) node[above right=2pt] {$P$};
        \end{tikzpicture}
    </script>
    <figcaption><em>Figure 2.</em> Cartesian Coordinate System with Particle $P$</figcaption>
</figure>
$\mathbf{r}$ is orthogonally projected into the $\mathcal{N}$-frame's coordinate axis components as 
$\mathbf{r} = x \hat{\mathbf n}_1 + y \hat{\mathbf n}_2 + z \hat{\mathbf n}_3$. In this vector equation the (\hat{\mathbf n}_1, \hat{\mathbf n}_2, \hat{\mathbf n}_3) describe direction and (x,y,z) describe magnitude. 

Note: $\mathbf{r}$ is explicitly not expressed in any reference frame and the vector equation elements $\mathbf{r}$ , $\hat{\mathbf n}_i$ are simply entities with a particular magnitude and direction in 3D space. As a result, $\mathbf{r} = x \hat{\mathbf{n}}_1 + a \hat{\mathbf{e}}_{\theta}$ is a valid vector equation. However, once we assign a reference frame to $\mathbf{r}$ like $\mathbf{r}^N$ then $\mathbf{r}^N \neq x \hat{\mathbf{n}}_1 + a \hat{\mathbf{e}}_{\theta}$. More generally $\mathbf{q} = \mathbf{r} + \mathbf{p}$, but $\mathbf{q}^N = \mathbf{r}^N + \mathbf{p}^E$ is not.   
