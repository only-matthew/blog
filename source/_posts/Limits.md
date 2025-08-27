---
title: 极限运算法则 Rules of Limits 
tags: Mathematics
mathjax: true
date: 2025-08-27 09:09:40
---

# 理解等式 $x \cdot o\left(\frac{1}{x^3}\right) = o\left(\frac{1}{x^2}\right)$ 的原理

## 1. 小o符号的定义
对于函数 $f(x)$ 和 $g(x)$，当 $x \to a$（通常 $a$ 为无穷大或某定点）时，若满足：
$$
\lim_{x \to a} \frac{f(x)}{g(x)} = 0
$$
则称 $f(x)$ 是 $g(x)$ 的**高阶无穷小**，记作 $f(x) = o(g(x))$。直观上，$f(x)$ 趋向于0的速度比 $g(x)$ 更快。

## 2. 分析等式左边：$x \cdot o\left(\frac{1}{x^3}\right)$
设 $h(x) = o\left(\frac{1}{x^3}\right)$，根据小o的定义（当 $x \to \infty$ 时，因涉及 $\frac{1}{x}$ 项，通常考虑 $x \to \infty$）：
$$
\lim_{x \to \infty} \frac{h(x)}{\frac{1}{x^3}} = 0
$$
等价于：
$$
\lim_{x \to \infty} x^3 \cdot h(x) = 0
$$

## 3. 验证左边是否等于右边 $o\left(\frac{1}{x^2}\right)$
需证明 $x \cdot h(x)$ 是 $\frac{1}{x^2}$ 的高阶无穷小，即验证：
$$
\lim_{x \to \infty} \frac{x \cdot h(x)}{\frac{1}{x^2}} = 0
$$
化简左边极限：
$$
\lim_{x \to \infty} x \cdot h(x) \cdot x^2 = \lim_{x \to \infty} x^3 \cdot h(x)
$$
根据 $h(x) = o\left(\frac{1}{x^3}\right)$ 的条件，$\lim_{x \to \infty} x^3 \cdot h(x) = 0$，因此：
$$
\lim_{x \to \infty} \frac{x \cdot h(x)}{\frac{1}{x^2}} = 0
$$
这说明 $x \cdot h(x) = o\left(\frac{1}{x^2}\right)$，即 $x \cdot o\left(\frac{1}{x^3}\right) = o\left(\frac{1}{x^2}\right)$。

## 4. 本质：无穷小量的阶数运算规则
更一般地，小o符号在**乘法**下满足“阶数相加”规则：  
若 $f(x) = o(g(x))$，则对任意常数 $k$ 或缓变函数 $k(x)$，有：
$$
k(x) \cdot f(x) = o(k(x) \cdot g(x))
$$  
在此例中，$g(x) = \frac{1}{x^3}$，$k(x) = x$，因此 $k(x) \cdot g(x) = x \cdot \frac{1}{x^3} = \frac{1}{x^2}$，故：
$$
x \cdot o\left(\frac{1}{x^3}\right) = o\left(\frac{1}{x^2}\right)
$$

## 总结
该等式的原理是利用小o符号的定义，通过验证左边表达式与右边函数的比值在 $x \to \infty$ 时趋向于0，证明左边是右边的高阶无穷小。本质上反映了无穷小量在乘法运算中“阶数相加”的规律。
