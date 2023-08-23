---
layout: post
title: "笔记 (01)：布朗运动与随机过程"
date:   2023-08-23
tags: [Operations Research]
comments: false
author: AnyEpiph
---

关于随机运动过程中布朗运动的自学笔记。

（最后更新：2023年8月23日）

<!-- more -->

## Prologues

这是更新到Blog上的第一篇OR相关的笔记。

正巧最近在研究一些和布朗运动有关的随机过程，查阅了不少资料，但是关于布朗运动及其应用的认识还是云遮雾罩。今天翻看之前赵晓波老师主讲的《高级运筹学II》的教材*，发现书中第8章刚好讲到了这部分知识，只是碍于课程安排，当时《高级运筹学II》课程并没有展开讲解这一章节。接下来正好可以趁着自学的机会，做一些笔记。

\* Sheldon M. Ross (1997), *Stochastic Processes* (2nd Edition), John Wiley & Sons.

** 本文中的公式为了便于参阅原书，和原书采用的是同样的编号，因此可能有跳号的可能。

## 8.1. Introduction and Preliminaries

### 8.1.1. Definition

随机游走的醉汉是我们再熟悉不过的随机过程模型。当然，最原始的随机游走模型是一个离散的随机过程。不过，假如我们将这个过程细分到很小的时间区间 $$\Delta t$$内，并假设醉汉在这一小段时间内只能以等概率游走 $$\pm \Delta x$$的小段距离，那么在时间 $$t$$的时候，醉汉的位置为

$$
X(t)=\Delta x \left( X_1 + \dots +X_{[t/\Delta t]}\right).\tag{8.1.1}
$$

可以很容易地计算出 $$X(t)$$的期望和方差是

$$
E[X(t)]=0, \quad Var[X(t)]=\left(\Delta x\right)^2 \left[\frac{t}{\Delta t}\right].
\tag{8.1.2}
$$

如果我们想让 $$Var[X(t)]$$在 $$\Delta t \rightarrow 0$$的时候不是平凡的，很自然地我们需要让 $$\Delta x = c \sqrt{\Delta t}$$。于是我们发现，在这样的假设下，随机过程 $$X(t)$$有以下的三点性质，我们把具有这样性质的随机过程$X(t)$称为布朗运动过程（Brownian Motion Process），也叫维纳过程（Wiener Process）

1. 初始值$$X(0)=0$$
   
2. $$\left\{ X(t), t\geq 0 \right\}$$在任意时间段内都是稳定的独立增量 （stationary independent increments）
   
3. $$X(t)$$服从正态分布 $$\mathcal{N}\left(0,c^2 t\right)$$

其中，性质3利用中心极限定理是可以直观发现的。特别地，当 $$c=1$$的时候，我们得到标准布朗运动（维纳）过程。

我们还可以发现几个直观的事实（虽然严格的证明被略去了）

1. $$X(t)$$处处连续，但是几乎处处不可微分

2. 由于有独立增量性质，$$X(t)$$是一个马尔科夫过程

由于稳定独立增量的性质，并且已知 $$f_t(x)$$恰好是正态分布 $$\mathcal{N}\left(0,c^2 t\right)$$的概率密度函数，我们可以轻松地写出 $$f_{s &#124 t} (x &#124 B)$$，进而求出 $$X(s),s<t$$的条件期望

$$
\begin{aligned}
E\left[X(s) &#124 X(t)=B \right]&=Bs/t\\
Var\left[X(s) &#124 X(t)=B \right]&=s(t-s)/t.\\
Cov\left[X(s),X(t)\right] &= Cov\left[X(s),X(s)\right]=s
\end{aligned}
\tag{8.1.4}
$$

期望的表达倒是不出意外，协方差根据 $$X(s)\rightarrow X(t)$$之间的独立增量性质也是显然的。有趣的是 $$X(s)$$的方差和 $$X(t)$$是无关的！

### 8.1.2. Brownian Bridge

待续…

最后施工时间2023年8月23日21:50:06

额外吐槽一句，Notion导出的Markdown文件真的不靠谱，改了半天......
