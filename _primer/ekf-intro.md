---
title: EKF Intuition for Relative Navigation
layout: primer_item
category: Estimation of Dynamic Systems
youtube_id: kAbCdEfGh12   # replace
---

**State:** $x = [p, v, q, b_g, b_a]^\top$.  
**Prediction:** $x_{k|k-1} = f(x_{k-1}, u_{k-1}) + w_{k-1}$.  
**Update:** $K_k = P_{k|k-1}H^\top(H P_{k|k-1}H^\top + R)^{-1}$.

More details…
