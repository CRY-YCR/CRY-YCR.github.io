---
title: "单调类定理"
date: 2025-10-03
layout: single
---
这篇笔记旨在彻底弄懂(Functional)单调类定理,目标后面再补充一些用到单调类定理的例题.

测度论中单调类定理都是对集合而言的，为什么要把它放到函数空间中去，以及怎么把它放到函数空间中去？

**定义1** 对于一个集合$E$,定义$\mathcal{B}(E)$为所有从$E$到$\mathbb{R}$的映射所构成的空间. 
>$B(E)$有以下性质:
>1.它对于一致有界的递增(减)的函数列的的极限是封闭的<span style="color:gray">(一个很显然的性质，在后面会在哪里有用呢？)</span>
>2.它本身构成了一个$\mathbb{R}$上的代数<span style="color:gray">(即满足是一个向量空间、有一个封闭的双线性的乘法运算以及有乘法单位元 )</span>

**定义2** 考虑$E$上的一个$\sigma$-代数 $\mathcal{E}$, 记$\mathcal{E}_b$是$\mathbb{E}$中所有$\mathcal{E}/\mathcal{B}(\mathcal{R})$可测的函数构成的子集合.
>易知$\mathcal{E}_b$也满足上面的1. 2.性质