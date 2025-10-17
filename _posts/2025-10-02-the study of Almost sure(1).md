---
title: "基于Almost sure的学习笔记(1)"
date: 2025-10-03
layout: single
---

正因为上一篇笔记中对$predictable$这一概念理解不深，因此这篇笔记计划学习$Almost sure$博客中的相关部分.  

[这篇survey](https://projecteuclid.org/journals/probability-surveys/volume-3/issue-none/An-essay-on-the-general-theory-of-stochastic-processes/10.1214/154957806000000104.pdf)前三章系统总结了有关$ptrdictable$的所有知识！可以当词典来用.

计划每篇笔记中精读最有针对性的不超过三篇博客,并针对性的写下批注.  
本文计划学习的路线为:
[$Sigma\ Algebras\  at\ a\ Stopping\ Time$](https://almostsuremath.com/2009/11/23/sigma-algebras-at-a-stopping-time/). 
[$Predictable\  Stopping\  Time$](https://almostsuremath.com/2009/11/30/predictable-stopping-times/)
和
[$Predictable\  Processes $](https://almostsuremath.com/2016/11/22/predictable-processes/)
目标每两天更一篇

##### $Sigma\ Algebras\  at\ a\ Stopping\ Time$


**命题** 设$X$ 是一个$predictable$的随机过程,$\tau$是一个停时, 则$X_\tau \in \mathcal{F}_{\tau-}$.

$$\mathcal{F}_{\tau- } := \sigma (\mathcal{F}_0, \lbrace A \cap \lbrace t \lt \tau \rbrace ; t \gt 0, A \in \mathcal{F_t} \} )$$

****

Mark住： [这里面定理3的证明](https://almostsuremath.com/2009/11/15/stopping-times-and-the-debut-theorem/) (能够直接解决上篇博客中的命题1)





##### [$Predictable\  Stopping\  Time$](https://almostsuremath.com/2009/11/30/predictable-stopping-times/)

> 读之前的思考问题:
>
>1. $Predictable\ Process$和 $Predictable\ Stopping\  times$有什么关系,前者的定义是所有关于由$\mathbb{L}$所生成的 $\sigma-$代数可测的随机过程, 跟后者有什么联系
>2.“一个RCLL过程$X$是拟左连续的 $\iff$ 它所有跳发生的时间都是$totally\  inaccessible$”是否成立.

