---
time : "2025-11-02"
---

# Chapter2 - Cauchy's Theorem and Its Applications

/// quote | Quote

<span style = "font-family: 'Times New Roman';">
The solution of a large number of problems can be reduced, in the last analysis, to the evaluation of definite integrals; thus mathematicians have been muchoccupied with this task... However, among many results obtained, a number were initially discovered bythe aid of a type of induction based on the passagefrom real to imaginary. Often passage of this kind led directly to remarkable results. Nevertheless this part of the theory, as has been observed by Laplace, is subject to various diﬃculties... After having reﬂected on this subject and brought together various results mentioned above, I hope to establish the passage from the real to the imaginary based on a direct and rigorous analysis; my researches have thus led me to the method which is the object of this memoir...
</span>

-- $A.L.Cauchy\, , 1827$
///

## Context

对应 `复变函数简明教程` Ch3 的内容.
主要有 `Goursat定理`, `Cauchy定理` , `Liouville定理`, `Morera定理`, `Cauchy不等式`.

- Stein : `Schwarz Reflect Principle`, `Runge's approximation theorem`
- 复变函数简明教程: `Schwarz引理` 及 非欧几何介绍

同时, 在复变函数简明教程这本书中关于 Cauchy定理 的证明有误, 详细可看 Stein 的 Complex Analysis 的 **Appendix B: Simple Connectivity and Jordan Curve Theorem**. 

*如果有时间我可能会在第二章目录下面梳理并翻译.*

## Exercise

### Exercise 1

/// Question | Exercise 1  $\quad$ ( From Stein Ch2 ET1 )

Prove that

\[\int_0^\infty \sin(x^2)dx = \int_0^\infty \cos(x^2) dx = \frac{\sqrt {2\pi}}{4}.\]

These are the **Fresnel integrals.** Here, $\int_0^\infty$ is interpreted as $\lim_{R \to \infty} \int_0^R .$
[Hint : Integrate the function $e^{-x^2}$ over the path in Figure 14. Recall that $\int_0^\infty e^{-x^2} dx = \sqrt \pi.$]

![Figure 14. The contour in Exercise 1](../img/Ch2/Figure1.svg)
/// figure-caption | 14
The contour in Exercise 1
///

///

!!! proof
    取 $e^{-z^2}$ 为被积函数, 围道$C$如上图. 由柯西定理, 知

    \[ \int_C e^{-z^2}dz = 0.    
    \]

    我们考虑圆弧

    \[\Gamma_R = \{z = Re^{i\theta} : 0 \le \theta \le \frac{\pi}{4}\}, \]

    放缩有, 

    \begin{align}
    \left| \int_{\Gamma_R}e^{-z^2} dz \right| &= \left| \int_0^{\frac{\pi}{4}} e^{R^2(\cos 2\theta + \mathrm{i} \sin 2\theta)} \mathrm{i}Re^{\mathrm{i}\theta} d\theta \right|\\ 
    &\le R\int_0^\frac{\pi}{4} e^{-R^2\cos 2\theta} d\theta.
    \end{align}

    下面我们来估计阶. 对于 $\forall \varepsilon, 0 < \varepsilon < 1$, $\exists \delta > 0$ 使得在 $[\frac{\pi}{4}-\delta, \frac{\pi}{4}]$ 上有

    \[-2(\theta - \frac{\pi}{4}) \ge \cos 2\theta \ge -2(\theta - \frac \pi 4) \times \varepsilon, \]

    这是由 $\cos 2\theta$ 在 $\frac{\pi}{4}$ 处的 Taylor 公式得来的. 于是有

    \[\int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2[-2(\theta - \frac \pi 4)]} d\theta \le
    \int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2\cos 2\theta} d\theta \le
    \int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2[-2(\theta - \frac \pi 4)\varepsilon]} d\theta,  \]

    计算得, 

    \[\frac{1-e^{-2\delta R^2}} {2R} \le \int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2\cos 2\theta} d\theta \le \frac{1-e^{-2\varepsilon\delta R^2}} {2\varepsilon R}, \]

    全部乘以 $2R$ 再令 $R \to \infty$ 得

    \[ 1 \le \lim_{R \to \infty} 2R \times R\int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2\cos 2\theta} d\theta \le \frac 1 \varepsilon. \]

    由于 $0 < \varepsilon < 1$ 的任意性, 令 $\varepsilon \to 1$, 即得

    \[R\int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2\cos 2\theta} d\theta \sim \frac 1 {2R} \to 0, \: R \to \infty.\]

    显然又有

    \[R\int_{\frac \pi 4 - \delta} ^ \frac \pi 4 Re^{-R^2\cos 2\theta} d\theta = O(Re^{-\varepsilon R^2}), \: \varepsilon > 0.\]

    于是

    \[\lim_{R \to \infty} \int_{\Gamma_R}e^{-z^2}dz = 0.\]

    回到最初的围道积分, 在 $\theta = \frac \pi 4$ 射线上带入 $z = xe^{i\frac{\pi}{4}}$ 有

    \[\int_0^\infty (\frac {\sqrt2} 2 \cos x^2 + \frac {\sqrt2} 2 \sin x^2) + i (\frac {\sqrt2} 2 \cos x^2 - \frac {\sqrt2} 2 \sin x^2) dx = \frac {\sqrt\pi} 2\]

    比较实部和虚部即有 

    \[\int_0^\infty \sin(x^2)dx = \int_0^\infty \cos(x^2) dx = \frac{\sqrt {2\pi}}{4}.\]

<!-- /// details | "另一个我的证明"
    type : proof

利用积分

\[ \int_0^\infty e^{-x^2} dx = \frac{\sqrt \pi}{2}.\]

从而考虑

\[\int_0^\infty \cos x^2 - \mathrm{i} \int_0^\infty \sin x^2 dx = \int_0^\infty e^{-ix^2} dx = \frac 1\xi \int_0 ^\infty e^{-(\xi x)^2} d(\xi x) = \bar \xi \frac {\sqrt \pi} 2 \]

然后比较实部和虚部即可.

/// -->


/// remark | Remark
我们有一般的 Fresnel 积分公式

\[\int_0^\infty \sin x^k dx = \frac 1k \Gamma(\frac 1k) \sin (\frac \pi {2k}), \]

\[\int_0^\infty \cos x^k dx = \frac 1k \Gamma(\frac 1k) \cos (\frac \pi {2k}). \]

其中 $k > 1$.
///

---

### Exercise 2

/// Question | Exercise 2  $\quad$ ( From Stein Ch2 ET2 )

Show that $\int_{0}^\infty \frac{\sin x}{x} dx = \frac{\pi}{2}.$

[Hint: THe integral equals $\frac{1}{2i}\int_{-\infty}^{+\infty}\frac{e^{ix}-1}{x}dx.$ Use the indented semicircle.]
///

/// Proof | Proof

利用欧拉公式, 我们首先有

\[\int_0^\infty \frac {\sin x} x dx = \int_0^\infty \frac {e^{ix} - e^{-ix}} {2ix} dx = \frac{1}{2i}\int_{-\infty}^{+\infty} \frac {e^{ix}} x dx.\]

考虑函数 $\frac{e^{iz}}{z}$, 围道 $\Gamma = \Gamma_R \cup \Gamma_\varepsilon \cup [\pm\varepsilon, \pm R]$, 其中大小圆弧分别为

\[\Gamma_R = \{Re^{i\theta} : 0 \le \theta \le \pi\}, \quad \Gamma_\varepsilon = \{\varepsilon e^{i\theta} : 0 \le \theta \le \pi\}.\]

在大圆弧十, 由控制收敛定理

\begin{align}
\lim_{R \to \infty} \left| \int_{\Gamma_R} \frac{e^{iz}}{z} dz \right| &= \lim_{R \to \infty} \left|\int_0^\pi \frac {e^{iR(\cos \theta + i \sin \theta)}}{Re^{i\theta}} Re^{i\theta} d\theta\right|\\ 
&\le \lim_{R \to \infty} \int_0^\infty e^{-R\sin \theta} d\theta\\
&= 0. 
\end{align}

另一方面, 在小圆弧上, 由控制收敛定理有

\[\lim_{\varepsilon \to 0} \int_{\Gamma_\varepsilon} \frac {e^iz} z dz = \pi i.\]

于是有

\[ \int_{-\infty}^{+\infty} \frac{e^{ix}}{x}dx = \lim_{R \to \infty, \varepsilon \to 0} \int_\Gamma \frac{e^iz} z dz  = \pi i,  \]

故而

\[\int_0^\infty \frac{\sin x}{x} dz = \frac 1 {2i} \int_{-\infty}^{+\infty} \frac{e^ix}{x}dx = \frac \pi 2. \]
///

/// remark
这实际上是著名的 Dirichlet 积分, 有许多证明方法和应用.
///

---
### Exercise 3
/// Question | Exercise 3  $\quad$ ( From Stein Ch2 ET3 )

Evaluate the integrals

\[\int_0^\infty e^{-ax}\cos bx\: \mathrm{d}x \quad\text{and}\quad \int_0^\infty e^{-ax}\sin bx\: \mathrm{d}x, \qquad a>0\]

by integrating $e^{-Ax}, A = \sqrt{a^2 + b^2}$, over an approxiate sector with angle $w$, with $\cos w = a / A.$

///

/// proof
首先有

\[int_0^\infty e^{-ax}\cos bx\: \mathrm{d}x + i \int_0^\infty e^{-ax}\sin bx\: \mathrm{d}x = \int_0^\infty e^{-(a-ib)x} \mathrm{d}x.\]

考虑函数 $e^{-Az}, A = \sqrt{a^2 + b^2}$, 取围道为: 以$[0, R]$ 和 $[0, Re^{i\theta}]$ 为边的扇形, 其中 $w = \arg (a-ib)$. 则在圆弧上有

\[\left|\int_C e^{-Az}dz \right| \le \int_0 ^ w e^{-AR\cos \theta}\mathrm{d}\theta \to 0, \quad R \to \infty, \]

其中用到 $\cos \theta \ge \cos w = \frac{a}{\sqrt{a^2 + b^2}} > 0$ 以及控制收敛定理. 于是有

\[\int_0^\infty e^{-(a-ib)}e^{iw} \mathrm{d}x = \int_0^\infty e^{-Ax}\mathrm{d}x = \frac 1A, \]

比较实部和虚部得

\begin{cases}
a\int_0^\infty e^{-ax}\cos bx \:\mathrm {d}x + b \int_0^\infty e^{-ax}\sin bx \: \mathrm{d}x  = 1,\\
\\
-b\int_0^\infty e^{-ax}\cos bx \:\mathrm {d}x + a \int_0^\infty e^{-ax}\sin bx \: \mathrm{d}x  = 0,\\
\end{cases}

解得

\[\int_0^\infty e^{-ax}\cos bx \:\mathrm {d}x = \frac a {a^2 + b^2}, \quad \int_0^\infty e^{-ax}\sin bx \:\mathrm {d}x = \frac b {a^2 + b^2}.\]
///

---
### Exercise 4
/// Question | Exercise 4  $\quad$ ( From Stein Ch2 ET4 )
Prove that for all $\xi \in \mathbb{C}$ we have 

$$e^{-\pi\xi^2} = \int_{-\infty}^{+\infty}e^{-\pi x ^ 2}e^{2\pi i x\xi} \:dx.$$
///

/// details | Tips
    type : tip
在正文部分的例题 P42 Example 1 证明了 

> if $\xi \in \mathbb{R}$, then
>
> \[e^{-\pi\xi^2} = \int_{-\infty}^{+\infty}e^{-\pi x ^ 2}e^{2\pi i x\xi} \:dx.\]
///

/// proof
设 $\xi = a + \mathrm{i} b \in \mathbb{C}$, 则

\begin{align}
\int_{-\infty}^{\infty}e^{-\pi x ^ 2}e^{2\pi i x\xi} \:dx &= \int_{-\infty}^{+\infty}e^{-\pi x ^ 2}e^{2\pi i xa} e^{-2\pi xb}\:dx\\
&= e^{\pi b^2}\int_{-\infty}^{\infty}e^{-\pi (x + b) ^ 2}e^{2\pi i xa} \:dx\\
&= e^{\pi b^2}\int_{-\infty}^{\infty}e^{-\pi x ^ 2}e^{2\pi i (x-b)a} \:dx\\
&= e^{\pi b^2} e^{-2\pi i ab} \int_{-\infty}^{\infty}e^{-\pi x ^ 2}e^{2\pi i xa} \:dx\\
&= e^{\pi b^2} e^{-2\pi i ab} e^{-\pi a^2}\\
&= e^{-\pi \xi^2}.
\end{align}
///