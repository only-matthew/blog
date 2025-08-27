---
title: 泰勒公式学习笔记
date: 2025-08-26 17:30:21
tags: Mathematics
mathjax: true
---

# 泰勒公式

泰勒公式本质就是对于$x_0$处的逼近

$$
\begin{align*}
    f(x)=\sum_{k=0}^{n}\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k+ \frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}\\\\
    其中\xi介于x_0与x之间，显然f^{(0)}(x_0)=f(x_0)
\end{align*}
$$
 
$\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}$被称为拉格朗日余项

# 常见泰勒展开(最好熟记|配合之前的n阶导数记忆)

$$
\begin{align*}
    &e^x=1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+···+\frac{x^n}{n!}+o(x^n)\\\\
    &sinx=x-\frac{x^3}{3!}+\frac{x^5}{5!}+···+(-1)^n\frac{x^{2n+1}}{(2n+1)!}+o(x^{2n+1})\\\\
    &cosx=1-\frac{x^2}{2!}+\frac{x^4}{4!}+···+(-1)^n\frac{x^{2n}}{(2n)!}+o(x^{2n})\\\\
    &ln(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}-···+(-1)^n\frac{x^{n+1}}{n+1}+o(x^{n+1})\\\\
    &\frac{1}{1-x}=1+x+x^2+···+x^n+o(x^{n+1})\\\\
    &(1+x)^m=1+mx+\frac{m(m-1)}{2!}x^2+···+\frac{m(m-1)(m-2)····(m-n+1)}{n!}x^n+o(x^{n+1})
\end{align*}
$$

# 例题

求泰勒展开时，常常先求$f^{(n)}(x_0)$，再带入泰勒公式中。
泰勒展开可以很好地衡量极限过程中的“速度”，并进行比较。
但是，很多时候，确定展开的第几项也是需要数学直觉的。

## $eg_1$

求$y=2^x$的麦克劳林展开中$x^n$项的系数

不难得到$y^{(n)}=2^x(ln2)^n$,则$y^{(n)}(0)=2^0(ln2)^n=(ln2)^n$.
则$y=2^x$的麦克劳林展开中$x^n$项的系数为$\frac{y^{(n)}(0)}{n!}=\frac{(ln2)^n}{n!}$

## $eg_2$

求极限$\lim_{x \to +\infty}\left\{\frac{e}{2}x+x^2[(1+\frac{1}{x})^x-e ]\right\}$

从内层到外层慢慢地展开，先处理$(1+\frac{1}{x})^x$

$$
\begin{align*}
    (1+\frac{1}{x})^x&=e^{xln(1+\frac{1}{x})}=e^{x[1-\frac{1}{2x^2}+\frac{1}{3x^3}+o(\frac{1}{x^3})]}=e^{x-\frac{1}{2x}+\frac{1}{3x^2}+o(\frac{1}{x^2})}\\\\
    &=
\end{align*}
$$
