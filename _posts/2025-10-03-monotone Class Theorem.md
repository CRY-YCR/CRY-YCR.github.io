---
title: "单调类定理"
date: 2025-10-03
layout: single
---
这篇笔记旨在彻底弄懂单调类定理,目标后面再补充一些用到单调类定理的例题.

单调类定理和$\pi-\lambda$定理的应用场景不同，前者作用于函数族上，从"比较简单"的函数族所具有“某种性质”推知在由这个函数族所生成的$\sigma$代数下可测的所有函数均具有该性质；后者作用在集族上，用于有类似性质的"比较简单"的小集族推知它所生成的$\sigma-$代数中的任意元素都具有该性质. 

**定义1** 对于一个集合$E$,定义$\mathcal{B}(E)$为所有从$E$到$\mathbb{R}$的映射所构成的空间. 
**定义2**称一列$\mathcal{B}(E)$中的函数列 $ f_1,\dots f_n $是有界的，如果存在$K\gt 0$,使得对任意$n$, $|f_n| \leq K.$
>$B(E)$有以下性质:
>1.它对于有界的递增(减)的函数列的的极限是封闭的<span style="color:gray">(一个很显然的性质，在证明中会在哪里有用呢？)</span>. 
>2.它本身构成了一个$\mathbb{R}$上的代数<span style="color:gray">(即满足是一个向量空间、有一个封闭的双线性的乘法运算以及有乘法单位元 )</span>. 

**定义2** 考虑$E$上的一个$\sigma$-代数 $\mathcal{E}$, 记$\mathcal{E}_b$是$\mathbb{E}$中所有$\mathcal{E}/\mathcal{B}(\mathcal{R})$可测的函数构成的子集合.
>易知$\mathcal{E}_b$也满足上面的1. 2.性质

对于$\mathcal{E}$上的一个子向量空间$\mathcal{H}$,记$$\mathcal{H}_+ = \{f \in \mathcal{H} : f \geq 0\}$$

**定理1(单调类定理)** 
设$\mathcal{K} \subseteq \mathcal{B}(E) $对乘法封闭,$\mathcal{H}$为$\mathcal{B}(E)$的子向量空间且满足
* $\mathcal{K} \subseteq \mathcal{H}$.
* $1 \in \mathcal{H}$.
* $\mathcal{H}_+$ 对有界的递增函数列的极限封闭.
则有${\sigma(\mathcal K)_b\subseteq\mathcal H}$

**证明**


**例1** 证明$\mathbb{R}^+$上有限$Borel$测度唯一被它的$Laplace$变换所决定.

对于$\mathbb{R}^+$上任意两有限的$Borel$测度$\nu,\mu$, 设两者$Laplace$变换相等, 根据$\pi- \lambda$定理,只需证明$\nu([c,\infty)) = \mu ([c,\infty ))$即可(该结论可推广到$\sigma-$有限测度).

记

$$\mathcal{H} = \lbrace f \in \mathcal{B}(\mathbb{R}^+): \nu(f) = \mu(f) \rbrace$$

$$\mathcal{K} = \lbrace f_a := e^{-ax} : a \geq 0\rbrace$$

其中$\nu(f) = \int f(x) \nu(dx)$. 
这样可逐一验证$\mathcal{H}$满足定理1的三个条件,其中测度有限保证了第三个条件成立.  

因此有$\sigma(\mathcal{K})$从

$$\lbrack c,\infty) \in f_a^{-1} ((0,e^{-ac}])$$

即可得到.

**例2**

若满足**定理1**条件的"性质"$\mathcal{H}$额外具有封闭的乘法结构,则有

$$\sigma (\mathcal{H})_b = \mathcal{H} $$

因此有 $\sigma(\mathcal{K})_b \subseteq \mathcal{H}$，故只需证 $\mathbf{1}_{[c,\infty)}$ 关于 $\sigma(\mathcal{K})_b$ 可测即可。