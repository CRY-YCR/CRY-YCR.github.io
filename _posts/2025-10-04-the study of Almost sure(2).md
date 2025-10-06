---
title: "基于Almost sure的学习笔记(2) (拟鞅相关的知识)"
date: 2025-10-04
layout: single
---

#### 1. [Quasimartingale](https://almostsuremath.com/2012/04/12/quasimartingales/)

**注1** 单独的上鞅或者下鞅无法构成一个向量空间(因为对负的数乘不封闭),但拟鞅全体构成了一个向量空间. 
**注2** 对于一个$FV$过程$X_t$来着，若$X_t$的变差的期望在任意$[0,t]$上有限, 即$\mathbb{E}[|X|_t]<\infty$, 那么$X$是一个拟鞅，反之不成立.


**Rao's Theorem (Protter p119)**
A quasimartingale $X$ has a unique decomposition $X = M+A$, where $M$ is a local martingale and $A$ is a predictable process with **path of locally integrable variation**. 

**证明** 证明重点是$A$ 是locally integrable variation的,即存在一列停时列$\tau_n$使得 $A^{\tau_n}$是integrable variation的. 根据拟鞅的分解定理，$X = Y-Z$, 其中$Y,Z$均为非负上鞅,那么根据Doob Meyer分解，
$$Y = M^{(1)} + A^{(1)}$$ $$Z = M^{(2)} + A^{(2)}$$
其中$M^{(1)}, M^{(2)}$均为局部鞅, $A^{(1)},A^{(2)}$为可预测的适应的增过程,且满足$\mathbb{E}[A_{\infty}] < \infty$ (最后的不等式是因为上鞅$Z$是非负，利用Theorem 16, chapter 3, Protter)那么令$A = A^{(1)} - A^{(2)}$是一个可预测的适应的有限变差过程. 且 $$\mathbb{E}[{\int_0^\infty} d|Z_s|] = \mathbb{E}[A^{(1)}_\infty + A^{(2)}_\infty] < \infty $$
因此可以得到**A实际上是integrable variation的,比原条件更强! 证毕**

