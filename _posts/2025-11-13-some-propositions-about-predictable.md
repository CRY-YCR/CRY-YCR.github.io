---
title: "与$predictable$相关的小问题们"
date: 2025-11-13
layout: single
---


##### 命题

对于一个$predictable$的集合$A \in \mathcal{P}$, 定义$T = inf \{s:(s,\omega) \in A \}$, 则当$[T] \subseteq A$时, 能得到$T$是一个$predictable$的停时.

##### 证明
由$[T] \subseteq A$可知$[T] \subseteq A \cap [0,T]$. 

另一方面,对于任意$(s,\omega) \in A \cap [0,T]$,由$T$的定义可知$T(\omega) \leq s$,所以$A \cap [0,T] \subseteq [T]$

根据$A \cap [0,T] \in \mathcal{P}$可知$[T] \in \mathcal{P}$,进而$[0,T] = [0,T) \cup [T] \in \mathcal{P}$,即为$predictable$停时的的定义.

