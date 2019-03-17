
---
layout: post
title: 信息论与墒理论
categories: Machine Learning
description: 墒
keywords: 信息墒
mermaid: true
sequence: true
flow: true
mathjax: true
---

# 信息论
## 信息量

`事件发生的不确定性`

假设$X$是一个离散型随机变量，其取值集合为$\chi$,概率分布函数$p(x)=Pr(X=x)$,$x∈χ$,则定义事件$X=x_0$的信息量为:
$$I(x) = -log(p(x_0))$$

## 信息熵
表示所有信息量的期望，即： 

$$H(X)=-\sum_{i=1}^n p(x_i)log(p(x_i))$$


## 相对熵（KL散度）
相对熵又称KL散度,如果我们对于同一个随机变量$x$有两个单独的概率分布 $P(x)$ 和 $Q(x)$，我们可以使用KL散度（Kullback-Leibler (KL) divergence）来衡量这两个分布的差异

$$D_{KL}(p||q)=-\sum_{i=1}^np(x_i)log(\frac{q(x_i)}{p(x_i)})=\sum_{i=1}^np(x_i)log(\frac{p(x_i)}{q(x_i)})$$

$n$为事件的所有可能性, $$D_{KL}$$的值越小，表示$q$分布和$p$分布越接近

#### 性质
- 非负性
$D_{KL}(p||q)>0$
当且仅当$P = Q$时$D_{KL}(P||Q)$为零

- 非对称性
$D_{KL}(p||q)\neq	 D_{KL}(q||p)$

> 非负性证明

易知$\ln(x) \leq x-1$ ，当且仅当$x=1$时取等号

$$\sum_{i=1}^n p_i \log (q_i / p_i) \leq \sum_{i=1}^n p_i (q_i / p_i - 1) = \sum_{i=1}^n (q_i - p_i) = \sum_{i=1}^n q_i - \sum_{i=1}^n p_i = 0$$
$$D_{KL}(p||q)=-\sum_{i=1}^n p_i \log (q_i / p_i) \geq 0 $$

**补充**：吉布斯不等式
若 $\sum_{i=1}^n p_i= \sum_{i=1}^n q_i=1 $，且$p_i , q_i \in (0,1]$，则有：
$$- \sum_{i=1}^n p_i \log p_i \leq - \sum_{i=1}^n p_i \log q_i$$，当且仅当等号成立$p_i = q_i \forall i$

## 交叉墒

$$
\begin{split}
D_{KL}(p||q) &=& \sum_{i=1}^np(x_i)log(p(x_i))-\sum_{i=1}^np(x_i)log(q(x_i))\\
&=& -H(p(x))+[-\sum_{i=1}^np(x_i)log(q(x_i))]
\end{split}$$
等式的前一部分恰巧就是p的熵，等式的后一部分，就是交叉熵： 

$$H(p,q)=-\sum_{i=1}^np(x_i)log(q(x_i))$$

在机器学习中，我们需要评估label和predicts之间的差距，使用KL散度刚刚好，即$D_{KL}(y||\hat{y})$，由于KL散度中的前一部分$−H(y)$保持不变，故在优化过程中，只需要关注交叉熵就可以了。所以一般在机器学习中直接用用交叉熵做loss，评估模型。


