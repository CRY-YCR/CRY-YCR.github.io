---
title: "Affine Process探究"
date: 2025-12-28
layout: single
---


例1 参数为$\lambda(t)$的非时齐$Poisson$过程$N_t$是 $Affine \ process$.

证明: 对于$0 \leq s \lt t$,$\forall u \in \mathbb{R}$,
$$
\begin{align*}
\mathbb{E}[e^{u N_t}|\mathcal{F}_s ]&= \mathbb{E}[e^{u (N_t-N_s)}] \mathbb{E}[e^{u N_s}| \mathcal{F}_s ]\\
&=\frac{\mathbb{E}[e^{uN_t}]}{\mathbb{E}[{e^{u N_s}}]} e^{u N_s}\\
&=exp\lbrace{e^u(\lambda(t)-\lambda(s)) - (\lambda(t)-\lambda(s)) }\rbrace exp\lbrace{u N_s} \rbrace
\end{align*}
$$
取$\phi_s(t,u) =e^u(\lambda(t)-\lambda(s)) - (\lambda(t)-\lambda(s)) $, $\psi_s(t,u) = u$可知$N_t$是一个非齐次的$Affine\ process$