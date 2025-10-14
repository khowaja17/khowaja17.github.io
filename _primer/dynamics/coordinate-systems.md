---
title: Coordinate Systems
layout: primer_item
category: Dynamic Systems
youtube_id: kAbCdEfGh12   # replace
---

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

Notation:

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
\mathcal{N} = \{ O_N , \hat{\mathbf n}_1, \hat{\mathbf n}_2, \hat{\mathbf n}_3 \}
$$
where $\hat{\mathbf x}$ denotes a unit vector (i.e $||\hat{\mathbf x} ||_2 = 1$ ).
