---
title: 三角函数的不定积分
date: 2025-08-29 23:47:58
tags: 
    - Mathematics
    - 不定积分
category: 
    - Mathematics
    - 不定积分
---

## 从$\int sin^2xcos^5x\,dx$看三角函数的积分

**核心： 降次**

$
\sin^2x \cos^5x = \sin^2x \cdot (1 - \sin^2x)^2 \cdot \cos x
$

令$u = \sin x$，则$du = \cos x \, dx$，即$\cos x \, dx = du$。代入后积分转化为：  
$
\int \sin^2x (1 - \sin^2x)^2 \cos x \, dx = \int u^2 (1 - u^2)^2 \, du
$

先展开$(1 - u^2)^2 = 1 - 2u^2 + u^4$，再与$u^2$相乘：  
$
u^2 (1 - 2u^2 + u^4) = u^2 - 2u^4 + u^6
$  
对多项式逐项积分：  
$
\int (u^2 - 2u^4 + u^6) \, du = \int u^2 \, du - 2 \int u^4 \, du + \int u^6 \, du
$  
根据积分公式$\int u^n \, du = \frac{u^{n+1}}{n+1} + C$，得：  
$
= \frac{u^3}{3} - 2 \cdot \frac{u^5}{5} + \frac{u^7}{7} + C
$


将$u = \sin x$代入，得到最终结果：  


$
\boxed{\frac{\sin^3x}{3} - \frac{2\sin^5x}{5} + \frac{\sin^7x}{7} + C}
$

### 积分方法总结

#### 1. 第一类换元法（凑微分法）
**核心思想**：将复合函数的微分形式转化为新变量的积分  
**关键公式**：
$$
\int f(g(x))g'(x)dx = \int f(u)du \quad (u=g(x))
$$



- **$eg_1$**：$\int 2x cos(x^2)dx$
  - 设$u=x^2$，则$du=2xdx$
  - 原式=$\int cos u du = sin u + C = sin(x^2)+C$

---

#### 2. 第二类换元法（三角代换）
**适用场景**：处理含根号的积分  
**常用代换**：
| 根号形式          | 代换方式          | 关键恒等式         |
|-------------------|-------------------|--------------------|
| $\sqrt{a^2-x^2}$ | $x=a\sin\theta$  | $1-\sin^2\theta=\cos^2\theta$ |
| $\sqrt{a^2+x^2}$ | $x=a\tan\theta$  | $1+\tan^2\theta=\sec^2\theta$ |
| $\sqrt{x^2-a^2}$ | $x=a\sec\theta$  | $\sec^2\theta-1=\tan^2\theta$ |


- **$eg_2$**：$\int \sqrt{1-x^2}dx$
  - 设$x=\sin\theta$，则$dx=\cos\theta d\theta$
  - 原式=$\int \cos^2\theta d\theta = \frac{\theta}{2}+\frac{\sin2\theta}{4}+C = \frac{\arcsin x}{2}+\frac{x\sqrt{1-x^2}}{2}+C$ 
  
- **$eg_3$**：$\int \frac{1}{\sqrt{x^2+1}}dx$
  - 设$x=\tan\theta$，则$dx=\sec^2\theta d\theta$
  - 原式=$\int \sec\theta d\theta = \ln|\sec\theta+\tan\theta|+C = \ln(x+\sqrt{x^2+1})+C$ 

---

#### 3. 三角函数积分技巧
**核心方法**：
1. **奇偶次幂拆分**：对奇数次幂的三角函数拆出一次幂作为微分项
2. **倍角公式**：利用$\sin^2x=\frac{1-\cos2x}{2}$等降次
3. **万能代换**：对混合三角函数使用$t=\tan\frac{x}{2}$


- **$eg_4$**：$\int \sin^3x dx$
  - 拆分：$\int \sin^2x \cdot \sin x dx = -\int (1-\cos^2x)d(\cos x)$
  - 结果：$-\cos x+\frac{\cos^3x}{3}+C$ 
  
- **$eg_5$**：$\int \cos^3x\cos2x dx$
  - 积化和差：$\cos3x\cos2x=\frac{1}{2}(\cos x+\cos5x)$
  - 结果：$\frac{\sin x}{2}+\frac{\sin5x}{10}+C$ 

---

### 注意事项
1. **换元一致性**：换元后需同步修改微分项（如$du=g'(x)dx$）
2. **积分域限制**：三角代换时需注意变量范围（如$x=a\sin\theta$时$\theta\in[-\pi/2,\pi/2]$）
3. **回代完整性**：最终结果需用原变量表示并保留积分常数$C$

---

### 练习题（附答案）
1. $\int x e^{x^2}dx$  
    设$u=x^2$，得$\frac{1}{2}e^{x^2}+C$
2. $\int \frac{\sqrt{x^2-9}}{x}dx$  
   设$x=3\sec\theta$，得$\sqrt{x^2-9}-3\arccos\frac{3}{x}+C$ 
3.  $\int \frac{1}{(x^2+1)^2}dx$  
   **解**：用三角代换$x=\tan\theta$，得$\frac{x}{2(x^2+1)}+\frac{1}{2}\arctan x+C$