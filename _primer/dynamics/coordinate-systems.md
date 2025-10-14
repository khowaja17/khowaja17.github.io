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

## Cartesian Coordinate System

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
$\mathbf{r} = x \hat{\mathbf n}_1 + y \hat{\mathbf n}_2 + z \hat{\mathbf n}_3$. In this vector equation the ($\hat{\mathbf n}_1, \hat{\mathbf n}_2, \hat{\mathbf n}_3$) describe direction and ($x,y,z$) describe magnitude. 

Note: $\mathbf{r}$ is explicitly not expressed in any reference frame and the vector equation elements $\mathbf{r}$, $\hat{\mathbf n}_3$ are simply entities with a particular magnitude and direction in 3D space. 
As a result, $\mathbf{r} = x \hat{\mathbf n}_1 + a \hat{\mathbf e}_1$ is a valid vector equation. However, once we assign a reference frame to $\mathbf{r}$ like $\mathbf{r}^N$ then $\mathbf{r}^N \neq x \hat{\mathbf n}_1 + a \hat{\mathbf e}_1$. More generally $\mathbf{q} = \mathbf{r} + \mathbf{p}$, but $\mathbf{q}^N \neq \mathbf{r}^N + \mathbf{p}^E$.   

## Cylindrical Coordinate System
A cylindrical coordinate system is helpful when studying a particle with rotational motion or radial forces.
<figure class="tikz-figure center">
    <script type="text/tikz">
        \begin{tikzpicture}[>=stealth, line cap=round, line join=round, thick, scale=1.4]
          %------------------ parameters: Cartesian coordinates of P ------------------
          \def\X{1.4}   % x along \hat n_1   (down-left)
          \def\Y{3.0}   % y along \hat n_2   (right)
          \def\Z{1.6}   % z along \hat n_3   (up)
          %------------------ styles -------------------------------------------------
          \tikzset{
            axis/.style = {->},
            proj/.style = {densely dashed},
            cyl/.style  = {orange!85!black, thick, ->},
          }
          %------------------ basis directions (2D oblique projection) ---------------
          \coordinate (O)  at (0,0);
          \coordinate (e2) at (1,0);          % \hat n_2  (right)
          \coordinate (e3) at (0,1);          % \hat n_3  (up)
          \coordinate (e1) at (-0.75,-0.48);  % \hat n_1  (down-left for 3D look)
          %------------------ point and projections ----------------------------------
          \coordinate (Px)  at ($(O)+\X*(e1)$);
          \coordinate (Py)  at ($(O)+\Y*(e2)$);
          \coordinate (Pxy) at ($(O)+\X*(e1)+\Y*(e2)$);
          \coordinate (P)   at ($(Pxy)+\Z*(e3)$);
          % Cylindrical helpers: d and theta (theta measured from +\hat n_1 toward +\hat n_2)
          \pgfmathsetmacro{\thetadeg}{atan2(\Y,\X)} % degrees
          \pgfmathsetmacro{\dlen}{sqrt(\X*\X+\Y*\Y)}
          % Unit directions in the xy-plane for c_r and c_theta
          \coordinate (crdir) at ($({cos(\thetadeg)}*(e1)+{sin(\thetadeg)}*(e2)$));
          \coordinate (ctdir) at ($({-sin(\thetadeg)}*(e1)+{cos(\thetadeg)}*(e2)$));
          %------------------ frame label and origin ---------------------------------
          \node[red] at (-1.6,2.2) {$\mathcal N$};
          \node at (0.25,-0.35) {$O_N$};
          %------------------ axes ----------------------------------------------------
          \draw[axis] (O) -- ($(O)+3.6*(e2)$) node[below right=3pt] {$\hat{\mathbf n}_2$};
          \draw[axis] (O) -- ($(O)+2.6*(e3)$) node[above left=3pt]  {$\hat{\mathbf n}_3$};
          \draw[axis] (O) -- ($(O)+2.6*(e1)$) node[below left=3pt]  {$\hat{\mathbf n}_1$};
          %------------------ xy footprint & projections ------------------------------
          \draw[proj] (O) -- (Px) -- (Pxy) -- (Py) -- cycle;           % footprint rectangle
          \draw[proj] (Pxy) -- (P) node[midway,right] {$z$};           % vertical
          \draw[proj] (O) -- (Pxy) node[midway,sloped,below] {$d$};    % radial distance
          \draw[proj] (Px) -- (Pxy) node[midway,below] {$x$};          % x component
          \draw[proj] (Py) -- (Pxy) node[midway,sloped,below] {$y$};   % y component
          %------------------ cylindrical unit vectors and angle ----------------------
          % c_r and c_theta at the origin (length 1 for clarity)
          \draw[cyl] (O) -- ($(O)+1.1*(crdir)$) node[above right=1pt] {$\hat{\mathbf c}_r$};
          \draw[cyl] (O) -- ($(O)+1.1*(ctdir)$) node[below right=0pt] {$\hat{\mathbf c}_\theta$};
          \draw[cyl] (O) -- ($(O)+1.6*(e3)$)    node[left=2pt]        {$\hat{\mathbf c}_z$};
          % theta arc (from +\hat n_1 to +\hat c_r in the xy-plane)
          % small radius for readability
          \path let \p1=($(e1)$), \p2=($(e2)$) in
            coordinate (xaxis) at ($(O)+0.9*(e1)$);
          \draw[orange!85!black, very thick]
            ($(O)+0.65*(e1)$) arc[start angle=0, end angle=\thetadeg, radius=0.65cm];
          \node[orange!85!black] at ($(O)+0.95*(crdir)$) {$\theta$};
          %------------------ position vector and point -------------------------------
          \draw[very thick,blue,->] (O) -- (P) node[midway,above] {$\mathbf r$};
          \fill[blue] (P) circle (2pt) node[above right=2pt] {$P$};
        \end{tikzpicture}
    </script>
    <figcaption><em>Figure 3.</em> Cylindrical Coordinate System with Particle $P$</figcaption>
</figure>

## Spherical Coordinate System
A spherical coordinate system is helpful when studying a particle that is moving on a surface of a conic section or sphere.
<figure class="tikz-figure center">
    <script type="text/tikz">
        \begin{tikzpicture}[>=stealth, line cap=round, line join=round, thick, scale=1.4]
          %------------------ parameters: Cartesian coordinates of P ------------------
          \def\X{1.4}   % x along \hat n_1   (down-left)
          \def\Y{3.0}   % y along \hat n_2   (right)
          \def\Z{1.6}   % z along \hat n_3   (up)
          %------------------ styles -------------------------------------------------
          \tikzset{
            axis/.style = {->},
            proj/.style = {densely dashed},
            cyl/.style  = {orange!85!black, thick, ->},
          }
          %------------------ basis directions (2D oblique projection) ---------------
          \coordinate (O)  at (0,0);
          \coordinate (e2) at (1,0);          % \hat n_2  (right)
          \coordinate (e3) at (0,1);          % \hat n_3  (up)
          \coordinate (e1) at (-0.75,-0.48);  % \hat n_1  (down-left for 3D look)
          %------------------ point and projections ----------------------------------
          \coordinate (Px)  at ($(O)+\X*(e1)$);
          \coordinate (Py)  at ($(O)+\Y*(e2)$);
          \coordinate (Pxy) at ($(O)+\X*(e1)+\Y*(e2)$);
          \coordinate (P)   at ($(Pxy)+\Z*(e3)$);
          % Cylindrical helpers: d and theta (theta measured from +\hat n_1 toward +\hat n_2)
          \pgfmathsetmacro{\thetadeg}{atan2(\Y,\X)} % degrees
          \pgfmathsetmacro{\dlen}{sqrt(\X*\X+\Y*\Y)}
          % Unit directions in the xy-plane for c_r and c_theta
          \coordinate (crdir) at ($({cos(\thetadeg)}*(e1)+{sin(\thetadeg)}*(e2)$));
          \coordinate (ctdir) at ($({-sin(\thetadeg)}*(e1)+{cos(\thetadeg)}*(e2)$));
          %------------------ frame label and origin ---------------------------------
          \node[red] at (-1.6,2.2) {$\mathcal N$};
          \node at (0.25,-0.35) {$O_N$};
          %------------------ axes ----------------------------------------------------
          \draw[axis] (O) -- ($(O)+3.6*(e2)$) node[below right=3pt] {$\hat{\mathbf n}_2$};
          \draw[axis] (O) -- ($(O)+2.6*(e3)$) node[above left=3pt]  {$\hat{\mathbf n}_3$};
          \draw[axis] (O) -- ($(O)+2.6*(e1)$) node[below left=3pt]  {$\hat{\mathbf n}_1$};
          %------------------ xy footprint & projections ------------------------------
          \draw[proj] (O) -- (Px) -- (Pxy) -- (Py) -- cycle;           % footprint rectangle
          \draw[proj] (Pxy) -- (P) node[midway,right] {$z$};           % vertical
          \draw[proj] (O) -- (Pxy) node[midway,sloped,below] {$d$};    % radial distance
          \draw[proj] (Px) -- (Pxy) node[midway,below] {$x$};          % x component
          \draw[proj] (Py) -- (Pxy) node[midway,sloped,below] {$y$};   % y component
          %------------------ cylindrical unit vectors and angle ----------------------
          % c_r and c_theta at the origin (length 1 for clarity)
          \draw[cyl] (O) -- ($(O)+1.1*(crdir)$) node[above right=1pt] {$\hat{\mathbf c}_r$};
          \draw[cyl] (O) -- ($(O)+1.1*(ctdir)$) node[below right=0pt] {$\hat{\mathbf c}_\theta$};
          \draw[cyl] (O) -- ($(O)+1.6*(e3)$)    node[left=2pt]        {$\hat{\mathbf c}_z$};
          % theta arc (from +\hat n_1 to +\hat c_r in the xy-plane)
          % small radius for readability
          \path let \p1=($(e1)$), \p2=($(e2)$) in
            coordinate (xaxis) at ($(O)+0.9*(e1)$);
          \draw[orange!85!black, very thick]
            ($(O)+0.65*(e1)$) arc[start angle=0, end angle=\thetadeg, radius=0.65cm];
          \node[orange!85!black] at ($(O)+0.95*(crdir)$) {$\theta$};
          %------------------ position vector and point -------------------------------
          \draw[very thick,blue,->] (O) -- (P) node[midway,above] {$\mathbf r$};
          \fill[blue] (P) circle (2pt) node[above right=2pt] {$P$};
        \end{tikzpicture}
    </script>
    <figcaption><em>Figure 4.</em> Spherical Coordinate System with Particle $P$</figcaption>
</figure>
