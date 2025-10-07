---
title: "t基于Almost sure的学习笔记(2) (拟鞅相关的知识)"
date: 2025-10-04
layout: single
---

#### 1. [Quasimartingale](https://almostsuremath.com/2012/04/12/quasimartingales/)

**注1** 单独的上鞅或者下鞅无法构成一个向量空间(因为对负的数乘不封闭),但拟鞅全体构成了一个向量空间. <br>
**注2** 对于一个$FV$过程$X_t$来着，若$X_t$的变差的期望在任意$[0,t]$上有限, 即$\mathbb{E}[|X|_t] \lt \infty$, 那么$X$是一个拟鞅，反之不成立.  

**Rao's Theorem (Protter p119)**
A quasimartingale $X$ has a unique decomposition $X = M+A$, where $M$ is a local martingale and $A$ is a predictable process with **path of locally integrable variation**, $A_0 = 0$. 

**证明** 证明重点是$A$ 是locally integrable variation的,即存在一列停时列$\tau_n$使得 $A^{\tau_n}$是integrable variation的. 根据拟鞅的分解定理，$X = Y-Z$, 其中$Y,Z$均为非负上鞅,那么根据Doob Meyer分解,  

$$Y = M^{(1)} + A^{(1)}. $$ 

$$Z = M^{(2)} + A^{(2)}. $$

其中$M^{(1)}, M^{(2)}$均为局部鞅, $A^{(1)},A^{(2)}$为可预测的增过程,且满足$\mathbb{E}[A_{\infty}] \lt \infty$ (最后的不等式是因为上鞅$Z$是非负，利用Theorem 16, chapter 3, Protter)那么令$A = A^{(1)} - A^{(2)}$是一个可预测的有限变差过程. 且 

$$\mathbb{E}[{\int_0^\infty} d|Z_s|] = \mathbb{E}[A^{(1)}_\infty + A^{(2)}_\infty] \lt \infty $$

因此可以得到**A实际上是integrable variation的,比原条件更强! 证毕**

**locally integrable variation过程的分解定理:**<br>
设$A$是一个locally integrable variation的有限变差过程, 那么存在一个唯一的分解:  

$$A = M + \tilde{A}$$ 

其中$M$是一个局部鞅, A是一个可预测的有限变差过程. 
**注**<span style="color:blue"> 此问题出自$Protter$书中$Compensator$这一节，并未给出严格证明. 因为A局部化之后才是quasimartingle, 而我对从局部化之后如何回到整体的证明方法仍不熟悉，故严格写一遍该定理的证明.  </span>

**证明** 由于$A$是locally integrable variation的, 存在一列停时列$\{\tau_n\} \uparrow \infty$使得$A^{\tau_n}$是integrable variation的, 由 **注2** 知$A^{\tau_n}$是一个拟鞅, 故由$Rao's \ Theorem$知存在分解 $A^{\tau_n} = M^{(n)} + \tilde{A}^{(n)}$. 其中$M^{(n)}$为局部鞅, $\tilde{A}^{(n)}$是一个integrable variation的有限变差过程, $\tilde{A}_0^{(n)} = 0$. 
对于任意$n \lt m$, 有:
$$A^{\tau_n} = (M^{(m)})^{\tau_n} +(\tilde{A}^{(m)})^{\tau_n}$$. 
其中$(M^{(m)})^{\tau_n}$为局部鞅,另由[predictable性对stopped process是可遗传的](https://almostsuremath.com/2009/11/15/stopping-times-and-the-debut-theorem/)知$(\tilde{A}^{(m)})^{\tau_n}$可预测,再根据$Protter$书中$Chapter 3$定理15, "既是局部鞅又是可预测的有限变差的过程必为常数"可知:  

$$ M^{(n)} = M^{(m)} \quad on\  \{ t\leq \tau_n\}.$$

$$ \tilde{A}^{(n)} =\tilde{A}^{(m)} \quad on\  \{ t\leq \tau_n\}.  $$ 

那么如下**定义整体的$M, \tilde{A}$**：

$$M_t := M_t^{(n)}  \quad on \ \{ t\leq \tau_n\}.  $$

$$\tilde{A}_t  := \tilde{A}_t^{(n)} \quad on \ \{ t\leq \tau_n\}.$$  

或更严格的, 取$E_n =\lbrace {(\omega, t)}: \tau_{n-1} \lt t \leq \tau_n(\omega) \rbrace$, 则$M,\tilde{A}$可写成:  

$$M:=\sum_{n\geq 1} M^{(n)} \cdot 1_{E_n}. $$

$$\tilde{A}:= \sum_{n \geq 1} \tilde{A}^{(n)}\cdot 1_{E_n}.  $$

根据上面的论述可知如此定义的$M,A$均良定义. 

对于$M$来说, 给定任意的$n$, $M^{\tau_n}$是一个局部鞅. 记$\mathcal{M}$为全体右连续左极限的鞅过程的空间,由于[$\mathcal{M}$是stable的空间](https://almostsuremath.com/2009/12/23/localization/),得$Loc(Loc(\mathcal{M})) = Loc(\mathcal{M})$, 因此$M \in Loc(Loc(\mathcal{M}))$一定是一个局部鞅. 

对于$\tilde{A}$来说, 一方面对于$a.s. \ \omega$和$T\gt0$, 存在$N\gt 0$, 使得$T \lt \tau_{N}(\omega)$, 故有:

$$|\tilde{A}|_t(\omega) \leq |\tilde{A}^{(n)}_t (\omega)| \lt \infty. $$

因此$\tilde{A}$是一个有限变差过程.

另一方面, 根据[可测空间的等价定义](https://almostsuremath.com/2016/11/22/predictable-processes/)可知 $E_n  = (\tau_{n-1}, \tau_n]\in \mathcal{P}$, 再根据$\mathcal{P}$对内部乘法和可数和是封闭的(测度论中的经典命题, 在此不再赘述), 可知这样定义的$\tilde{A}$是可预测的.  

该分解的唯一性同样由$Protter$书中$Chapter 3$定理$15$得到. $Q.E.D. $