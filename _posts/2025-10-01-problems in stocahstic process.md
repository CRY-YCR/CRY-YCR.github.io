---
title: "随机过程学习中的问题"
date: 2025-10-01
layout: single
---

本文记录一些随机过程/随机分析教材中证明中常常省略但往往又需要思考的小的问题，主要参考文献是$Protter$的$Stochastic$ $Intergation$ $and$ $Differential$ $Equations$.
##### 命题1：如果 $A$ 是一个 $predictable$ 的随机过程，$T$ 是一个停时，那么 $A_{t\wedge T}$ 同样是 $predictable$ 的.

**注:** $Protter$ 的书中,称 $\mathcal{P}$ 是 $predictable$ 的，如果 $\mathcal{P}$ 是 $\Omega\times \mathbb{R}^+$ 上使得所有 $\mathbb{L}$ 中元素关于 $\mathcal{B}(\mathbb{R})$ 可测的最小的 $\sigma$ 代数. 其中 $\mathbb{L}$ 是由所有左连续右极限的适应的随机过程所构成的集合

根据这个定义，很容易产生下面这个问题:  
<span style="color:red">是否所有可预测过程一定是左连续? 答：不一定</span>
>事实上,固定$t_0 >0$, $X_s = 1_{[0,t_0)}(s)$就是可预测但并不左连续的随机过程，由于$X$取值仅在$\{0,1\}$上，我们只需证明$\{X = 0\} \in \mathcal{P}$即可.有\\
>
>$$\begin{align*}\{X = 0\} &= \Omega \times [t_0,\infty)\\
&= \bigcap_{n=1}^{\infty} \Omega \times (t_0 - \frac{1}{n}, \infty) \in \mathcal{P}\\ \end{align*}$$
>
>而更一般的，由于逐点极限保持可测性，可以知道所有左连续过程的逐点极限(对任意$t,\omega$)仍在$\mathcal{P}$中,但它不一定左连续,比如上例 $X_{\cdot} = \lim\limits_{n\to \infty}1_{[0,t-\frac{1}{n}]}(\cdot)$ 是右连续的过程.

首先回顾一下关于右连续左极的简单过程的定义:设
\(0=T_0\le T_1\le \cdots \le T_n<\infty\) 是一列递增的停时,对应的随机变量 \(H_i\) 满足 \(|H_i|<\infty\)\; \(\text{a.s.}\) 且
\(H_i\in \mathcal{F}_{T_i}\), 令

\[H_t = H_0 1_{0} + \sum_{i=1}^n H_i1_{(T_i, T_{i+1}]}\]

这样的过程称为**简单过程**,记为$\mathcal{S}$.

通过定义向量空间$\mathcal{S}$中的收敛关系，我们可以在$\mathcal{S}$上赋予不同的拓扑结构，进而得到空间的完备性、稠密性等性质(但注意这样得到的拓扑向量空间可能并不能被度量化或赋范)

首先最简单的,可以在$\mathcal{S}$上定义关于$(t,\omega)$一致收敛. 即
$$H^n \xrightarrow{u} H \iff |H_t^n(\omega) - H_t(\omega)| \to 0\ \  uniformly\  in \ (t,\omega)$$
其中$Protter$书中关于半鞅的定义就是在这种收敛关系下得到的(page 52)

但收敛关系越强，可延拓性就越差。为了更好的延拓性，还可以定义相对弱一些的收敛关系，如$ucp$收敛(uniformly on compacts in probability). 

称$H^n \xrightarrow{ucp} H$, 如果对任意$t >0$,有
$$\sup\limits_{0 \leq s\leq t}|H_x^n - H_s|\xrightarrow{\mathbb{P}} 0 $$

进而有下面的引理成立：

**引理** 在 $ucp$ 所诱导的拓扑结构下，$\mathcal{S}$在$\mathbb{L}$中稠密.  
**证明**：参考 $(Protter) Theorem \ 10 \ in \ Chapter 2$ 

>(待解决)这里自然有一个问题，在一致收敛的拓扑结构下$\mathcal{S}$是否$\mathbb{L}$中稠密？若否，能否得到一个反例?

**关于命题1的证明<span style="color:red">(没完全解决)</span>**
**证明** 本想通过从简单过程开始做并推广，但后面发现在由$H^n_{t\wedge T} \xrightarrow{ucp} X_{t\wedge T}$且$H^n \in \mathcal{P}$推出$X_{t\wedge T} \in \mathcal{P}$的过程里遇到了问题，不确定$ucp$收敛能否想逐点收敛一样保持可测性,或许可以通过选取子列逐点收敛的方式来归纳到逐点收敛的情况，不确定.


##### 命题2  类DL的局部鞅$M_t$一定是鞅.(反之也成立)

困难的原因: 一直在想办法应用(条件)控制收敛定理来证明,但事实上,<span style="color:blue">涉及到"一致可积"的条件是，通过$L^1$收敛做往往才正确</span>. 
**证明** 设$T_n$是$M$的局部化序列，对于$s<t$,有
$$\mathbb{E}[M^{T_n}_t \mid \mathcal{F}_s] = M^{T_n}_s$$

这样根据一致可积性和几乎处处收敛，可得
$$M_t^{T_n} \xrightarrow{L^1} M_t$$ 
$$M_s^{T_n} \xrightarrow{L^1} M_s$$
 进而
 $$\mathbb{E}[M^{T_n}_t \mid \mathcal{F}_s]
 \xrightarrow{L^1}\mathbb{E}[M_t \mid \mathcal{F}_s]$$
 根据<span style="color:blue">$L^1$收敛的极限在a.s.的意义下唯一</span>证明了鞅性. Q.E.D.  
