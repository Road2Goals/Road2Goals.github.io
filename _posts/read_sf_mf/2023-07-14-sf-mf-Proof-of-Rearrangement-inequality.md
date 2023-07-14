---
title: "「SF-MF」证明排序不等式"
subtitle: "Math Foundations - Proof of Rearrangement inequality"
layout: post
author: "Matrix"
header-img: "img/sf_mf/pori.jpg"
header-mask: 0.3
tags:
  - MF (数学基础)
  - SF (软件基础)

---



> 本文使用数学归纳法和Abel变换这两种方法证明排序不等式



## 概述



**排序不等式**是数学上的一条不等式, 它是说: 

如果 $ x_{1}\leq x_{2}\leq \cdots \leq x_{n} $ 和 $ y_{1}\leq y_{2}\leq \cdots \leq y_{n} $ 是两组实数, 而 $ x_{\sigma (1)},\ldots ,x_{\sigma (n)} $是 $ x_{1},\ldots ,x_{n} $ 的一个任意排列, 排序不等式指出 $ x_{1}y_{1}+\cdots +x_{n}y_{n}\geq x_{\sigma (1)}y_{1}+\cdots +x_{\sigma (n)}y_{n}\geq x_{n}y_{1}+\cdots +x_{1}y_{n} $.

以文字可以说成是顺序和大于等于乱序和, 乱序和大于等于逆序和. 与很多不等式不同, 排序不等式不需限定 $ x_{i},\,y_{i} $ 的正负.



## 证明



以下提供两种证明方法



### 数学归纳法



设 $\left(a_1, a_2, \cdots, a_n\right),\left(b_1, b_2, \cdots, b_n\right)$ 是两个增加的实数列. 假定 $\left(i_1, i_2, \cdots, i_n\right)$ 是 $(1,2, \cdots, n)$ 的任意一个排列, 则
$$
a_1 b_1+a_2 b_2+\cdots+a_n b_n \geqslant a_1 b_{i_1}+a_2 b_{i_2}+\cdots+a_n b_{i_n}
$$
而且乱序和的数量为 $$  n! $$



**易证** 当 $$ n = 2 $$ 时, $$  \sum_{k=1}^n a_k b_k\geq \sum_{k=1}^n a_k b_{i_k} $$ 成立, 即 $$ a_{1}b_{1}+a_{2}b_{2}\geq a_{1}b_{2}+a_{2}b_{1}  $$ .

**假设** 在项数为 $$ n $$ 且 $$ n > 2 $$ 时, $$  \sum_{k=1}^n a_k b_k\geq \sum_{k=1}^n a_k b_{i_k} $$依然成立.

不妨设顺序和为 $$S_1 = \sum_{k=1}^n a_k b_k$$ , 乱序和为 $$ S_r = \sum_{k=1}^n a_k b_{i_k} $$ , 则有 $$ S_1\geq S_r $$ 成立, 其中 $$ S_r $$ 可以为任意一个乱序和.

**证明** 当项数为 $$  n+1 $$ 时, 设顺序和为 $$S_2 = \sum_{k=1}^{n+1} a_k b_k$$ , 乱序和为 $$ S_3 = \sum_{k=1}^{n+1} a_k b_{i_k} $$ , 则对于任意一个 $$ S_3 = \sum_{k=1}^{n+1} a_k b_{i_k} $$ 来说, 都能够在上述的 $$ n! $$ 个 $$ S_r = \sum_{k=1}^n a_k b_{i_k} $$ 中, 找到一个 $$ S_r $$ , 使得 $$  S_3 = S_r - {a_u}{b_v} + {a_u}{b_{n+1}} + {a_{n+1}{b_v}} $$, 其中 $$ n + 1 \geq u, v \geq 1 $$ .

又因为 $$  (a_{n+1}-a_u)(b_{n+1}-b_v) \geq 0$$

所以有
$$
S_1 +  (a_{n+1}-a_u)(b_{n+1}-b_v) \geq S_r \\
S_1 + {a_{n+1}}{b_{n+1}} + {a_u}{b_v} - {a_u}{b_{n+1}} - {a_{n+1}{b_v}} \geq S_r \\
S_1 + {a_{n+1}}{b_{n+1}} \geq S_r - {a_u}{b_v} + {a_u}{b_{n+1}} + {a_{n+1}{b_v}} \\
S_2 \geq S_3
$$


根据数学归纳法, 则上述作出假设得证.



而对于乱序和大于逆序和, 只需要将 $b_1 \leqslant b_2 \leqslant \cdots \leqslant b_n$ 乘以  $$ -1$$ , 即 $$  -b_1 \geq -b_2 \geq \cdots \geq -b_n $$ 

然后有顺序和大于等于乱序和
$$
-a_1 b_n-a_2 b_{n-1}-\cdots-a_n b_1 \geqslant -a_1 b_{i_1}-a_2 b_{i_2}-\cdots-a_n b_{i_n}
$$
根据数学归纳法证明上述式子, 最后乘以 $$ -1 $$ , 则乱序和大于逆序和可证.





### Abel变换



设 $\left(a_1, a_2, \cdots, a_n\right),\left(b_1, b_2, \cdots, b_n\right)$ 是两个增加的实数列. 假定 $\left(i_1, i_2, \cdots, i_n\right)$ 是 $(1,2, \cdots, n)$ 的任意一个排列, 则
$$
a_1 b_1+a_2 b_2+\cdots+a_n b_n \geqslant a_1 b_{i_1}+a_2 b_{i_2}+\cdots+a_n b_{i_n}
$$
如果序列 $\left(a_1, a_2, \cdots, a_n\right)$ 是增加的, 而序列 $\left(b_1, b_2, \cdots, b_n\right)$ 是减少的, 则上面的不等式改变方向.

**证明** 注意到 $a_1 \leqslant a_2 \leqslant \cdots \leqslant a_n$ 和 $b_1 \leqslant b_2 \leqslant \cdots \leqslant b_n$, 所以根据 **Abel 公式**
$$
\begin{aligned}
\sum_{k=1}^n a_k b_k-\sum_{k=1}^n a_k b_{i_k}= & \sum_{k=1}^n a_k\left(b_k-b_{i_k}\right)=\left(a_1-a_2\right)\left(b_1-b_{i_1}\right)+ \\
& \left(a_2-a_3\right)\left(b_1+b_2-b_{i_1}-b_{i_2}\right)+\cdots+ \\
& \left(a_{n-1}-a_n\right)\left(\sum_{k=1}^{n-1} b_k-\sum_{k=1}^{n-1} b_{i_k}\right)+a_n\left(\sum_{k=1}^n b_k-\sum_{k=1}^n b_{i_i}\right) \geqslant 0
\end{aligned}
$$
因为对所有 $k=1,2, \cdots, n$, 我们有
$$
\sum_{j=1}^k b_j \leqslant \sum_{j=1}^k b_{i j}
$$
当序列 $\left(a_1, a_2, \cdots, a_n\right)$ 是增加而 $\left(b_1, b_2, \cdots, b_n\right)$ 减少的情况的证明是类似的.







