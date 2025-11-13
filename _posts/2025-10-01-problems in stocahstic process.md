---
title: "随机过程学习中的问题"
date: 2025-10-01
layout: single
---

本文记录一些随机过程/随机分析教材中证明中常常省略但往往又需要思考的小的问题，主要参考文献是$Protter$的$Stochastic$ $Intergation$ $and$ $Differential$ $Equations$.
##### 命题1：如果 $A$ 是一个 $predictable$ 的随机过程，$T$ 是一个停时，那么 $A_{t\wedge T}$ 同样是 $predictable$ 的.

**注:** $Protter$ 的书中,称 $\mathcal{P}$ 是 $predictable$ 的，如果 $\mathcal{P}$ 是 $\Omega\times \mathbb{R}^+$ 上使得所有 $\mathbb{L}$ 中元素关于 $\mathcal{B}(\mathbb{R})$ 可测的最小的 $\sigma$ 代数. 其中 $\mathbb{L}$ 是由所有左连续右极限的适应的随机过程所构成的集合. (因此验证$\mathcal{P}$中元素所具有的性质是很可能会用到单调类定理, 归类到$\mathbb{L}$中元素是否具有该性质)

根据这个定义，很容易产生下面这个问题:  
<span style="color:red">是否所有可预测过程一定是左连续? 答：不一定</span>
>事实上,固定$t_0 >0$, $X_s = 1_{[0,t_0)}(s)$就是可预测但并不左连续的随机过程，由于$X$取值仅在$\{0,1\}$上，我们只需证明$\{X = 0\} \in \mathcal{P}$即可.有\\
>
>$$\begin{align*}\{X = 0\} &= \Omega \times [t_0,\infty)\\
&= \bigcap_{n=1}^{\infty} \Omega \times (t_0 - \frac{1}{n}, \infty) \in \mathcal{P}\\ \end{align*}$$
>
>而更一般的，由于逐点极限保持可测性，可以知道所有左连续过程的逐点极限(对任意$t,\omega$)仍在$\mathcal{P}$中,但它不一定左连续,比如上例 $X_{\cdot} = \lim\limits_{n\to \infty}1_{[0,t-\frac{1}{n}]}(\cdot)$ 是右连续的过程.


最初曾尝试从简单函数逼近的思路,但没成功,卡在了可测性在ucp收敛的极限下不确定是否保持这一步上.
**证明1** 记

$$\mathcal{H}  = \lbrace X \in \mathcal{P} :for \ all \ stopping \ time \  \tau , X^\tau \in \mathcal{P} \rbrace $$

由因为对于任意$X \in \mathbb{L}$和停时$\tau$, $X^\tau \in \mathbb{L}.$ 因此 $\mathbb{L} \subseteq \mathcal{H}.$

又因为$\mathcal{H}$ 满足单调类定理的条件，见单调类定理笔记中定理1,其中第三条可由<span style="color:blue">逐点收敛保持可测性(这一点在验证单调类的条件中常常用到)</span>保证，根据单调类定理得到

$$\mathcal{P} = \sigma(\mathbb{L})_b \subseteq \mathcal{H}$$

$Q.E.D.$

##### 命题2  类DL的局部鞅$M_t$一定是鞅.(反之也成立)

感到困难的原因: 我一直在想办法应用(条件)控制收敛定理来证明,但事实上,<span style="color:blue">涉及到"一致可积"的条件时，通过$L^1$收敛做往往才正确</span>. 
**证明** 设$T_n$是$M$的局部化序列，对于$s<t$,有

$$\mathbb{E}[M^{T_n}_t \mid \mathcal{F}_s] = M^{T_n}_s$$

这样根据一致可积性和几乎处处收敛，可得:

$$M_t^{T_n} \xrightarrow{L^1} M_t$$ 

$$M_s^{T_n} \xrightarrow{L^1} M_s$$. 

 进而

 $$\mathbb{E}[M^{T_n}_t \mid \mathcal{F}_s]
 \xrightarrow{L^1}\mathbb{E}[M_t \mid \mathcal{F}_s]$$

 根据<span style="color:blue">$L^1$收敛的极限在a.s.的意义下唯一</span>证明了鞅性. $ Q.E.D.$  

**命题3** 若存在一列停时列$\{\tau_n\}\uparrow \infty$,使得$M^{\tau_n}$是局部鞅，那么$M$也是局部鞅.  

**证明** 这实际上是定理:对[若一个空间$P$是stable的,有$Loc(Loc(P)) = Loc(P)$](https://almostsuremath.com/2009/12/23/localization/)的特例,取P为所有鞅构成的空间即可. $Q.E.D.$

**注** 此命题在在验证某些局部化的性质在整体中依旧保留往往有用.

**命题4** 设$\tau$是一个$random \ time$, 即它是一个$\mathcal{F}/\mathcal{B}(\mathbb{R^+})$的随机变量, 那么$\lbrace (\omega,t): \tau(\omega) \le t \rbrace \in \mathcal{F}\times \mathcal{B}(\mathbb{R})$. 

**证** 更一般的,验证$\tau-t$关于$\mathcal{F}\times \mathcal{B}(\mathbb{R})/ \mathbb{R}$可测即可.易知

$$(t,\omega) \to (t, \tau(\omega)) \to \tau(\omega) - t$$

每个映射均可测. $Q.E.D.$

**推论** 若$X$是一个$jointly\  measurable$的随机过程, $\tau$是一个$random\ time$, 那么$X^\tau$同样是$jointly\ measurable$的随机过程. 

因为

$$X^\tau_t = 1_{\lbrace \tau \leq t\rbrace} X_t + 1_{\lbrace \tau \gt t\rbrace} X_\tau$$
在第二项中, 由$X\ jointly\  measurable$ 知$X_\tau$ 一定$\mathcal{F}/\mathcal{B}(\mathbb{R})$可测的随机变量，可视为$jointly\  measurable$的过程.