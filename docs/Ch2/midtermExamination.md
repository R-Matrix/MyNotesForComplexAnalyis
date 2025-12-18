---
time : "2025-12-06"
---
# 复分析期中考试

课程代码 : MATH 2609-02

参考书籍 : 谭小江, 伍胜健. 复变函数简明教程. 北京大学出版社, 2006

主要内容(以复变函数简明教程为准) : 

1. 第一章(复数和复数域)
2. 第二章(解析函数)
3. 第三章(Cauchy定理和Cauchy公式) 

## **声明** : 

- ***由于笔者本人是B卷, 所以下面的题号顺序以B卷为例***
- ***下面的内容为笔者本人的答案及感悟, 不确为标准答案, 请读者自已判断对误和以自己情况吸收. 笔者本人对其答案不作担保或其他责任.*** *如果您认为下面的内容有问题或者有其他更好的想法, 欢迎在 github 上提 issue 或者 [发邮件到该邮箱](mailto: dsq1961248553@outlook.com)*

## 主要试题内容及解析

### 第一题(12分)
/// question
设曲线 $\gamma(t) = te^{it}$, 方向为从 $t = 0$ 到 $t = \pi$. 分别计算以下曲线积分

(1) $\int_\gamma \bar z dz;\quad$  
(2) $\int_\gamma |z| dz;\quad$  
(3) $\int_\gamma |z||dz|; \quad$  
(4) $\int_\gamma z(1+|z|^2)^{-1/2}|dz|.$
///

/// details | 解答
    type : proof
$z = \gamma(t) = te^{it}(t \in [0, \pi])$, $\quad dz = (1+it)e^{it}dt$, 

$|z| = |te^{it}| = t$, $\quad |dz| = |\gamma'(t)|dt = \sqrt {1 + t^2} dt$

--- 

(1)

\[\int_\gamma \bar z dz = \int_0 ^ \pi te^{it}(1+it)e^{it} dt = \int_0^\pi t + it^2 dt = (\frac 12 t^2 + \frac i 3 t^3 )\bigg| _0 ^ \pi = \frac 12 \pi^2 + i \frac 3 {\pi^2}. \]

---

(2)

\[\int_\gamma |z|dz = \int_0^\pi t(1+it)e^{it} dt \overset {\text{两次分部积分}}{===} 2 - \pi ^ 2 - i \pi.\]

---

(3)

\[\int_\gamma |z||dz| = \int_0 ^ \pi t\sqrt{1 + t^2}  dt = \frac 13 (1 + t^2)^{\frac 3 2} \bigg| _ 0 ^ \pi = \frac 13 [(1 + \pi ^ 2)^{\frac 32} - 1]\]

---

(4)

\[\int_\gamma z(1+|z|^2)^{-1/2}|dz| = \int_0^\pi te^{it}dt = -2 + i \pi\]
///


---


### 第二题(10分)

/// question
假设 $f : D(0, 1) \to D(0, 1)$ 是解析映射.

(1) 证明 : 对任意 $z \in D(0, 1)$ 都成立 $|f(z) - f(-z)| \le 2|z|.$

(2)上式对某 $z_0 \in D(0, 1)\backslash \{0\}$ 成立等号的充要条件是什么?
///

/// details | 解答
    type : proof
(1) 令 $g(z) = \frac{f(z) - f(-z)}{2}$, 那么 $g : D(0, 1) \to D(0, 1)$ 且 $g(0) = 0$.

由 **Schwarz** 引理得, $|g(z)| \le |z|$, 即 $|f(z) - f(-z)| \le 2|z|.$

(2) 若上式等号成立, 充要条件为 $g(z) = e^{i\theta}z$, 其中 $\theta \in[0, 2\pi]$ 为常数. 下面证明 $f(z) = e^{i\theta}z$ 为充分必要条件.

必要性是容易验证的.

对于充分性, 我们利用 $2g(z) = f(z) - f(-z)$ 两边同时求导, 有 $f'(0) = e^{i\theta}.$

而对于从单位圆盘到单位圆盘的解析映射 $h$ 一定形如 $h(z) = \frac {f(0) + e^{i\theta}z}{1 + \overline{f(0)}e^{i\theta}z}.$ 因此得 $f(0) = 0$, 从而 $f(z) = e^{i\theta}z.$
///

/// remark
关于教材的Schwarz引理在[第109页](../RefSource/Complex_Analysis_zh_cn.pdf/#page=109 "这里不知道为什么无法跳转指定页码, 这里的功能有待查询")
///

---

### 第三题(12分)

///question
求将 $1, 0, -1$ 分别映射至 $i, 1 + i, 1$ 的分式线性映射 $L(z)$, 并求

(1) 单位圆周 $\{|z| = 1\}$;  
(2) 单位开圆盘 $\{|z| < 1\}$;  
(3) 虚轴 $\mathfrak{R}z = 0$

在 $L$ 映射下的像.
///

/// details | 解答
    type : proof
我们这里当然可以设四个系数进行方程组求解, 这里使用分式线性变换保持交比进行计算.

$$(z, 1, 0, -1) = (L(z), i, 1 + i, 1)$$

即

\[\frac{(z - 0)(1 - (-1))}{(z - (-1))(1 - 0)} = \frac {(L(z) - (1 + i))(i - 1)}{(L(z) - 1)(i - (1 + i))}\]

化简得

\[L(z) = -\frac{1 + i}{iz - 1}.\]

由于分式线性变换把圆和直线映为圆或直线, 从而再考虑点 $z = i$, $L(i) = \frac{1 + i}{2} := w_4$, 发现 $w_1 = i, w_3 = 1$ 与 $w_4$ 三点共线($w_4$ 恰为 $w_1$ 与 $w_3$ 中点), 因此 $L$ 把单位圆周映为直线 $l_1 : x + y - 1 = 0$.

由于分式线性变换在 $\overline {\mathbb C}$ 是解析的, 具有保向性, 从而只需要判断把单位圆盘内部映为直线上方或下方. 考虑 $L(0) = 1 + i$, 因此把单位圆盘映为 $x + y - 1 > 0$ 的区域.

不妨设 $z = it, t \in \mathbb R$, 那么 $L(z) = \frac {1 + i}{1 + t} = \frac {1}{1 + t} + i \frac {1}{1 + t}$, 其满足 $\text{Im}(L(z)) = \text{Re}(L(z))$ , 从而 $L$ 把虚轴映为直线 $x - y = 0$.
///

---

### 第四题(26分)

判断下列命题是否正确

/// question | Question 1
$\mathbb C$ 中的有界无穷集合必包含收敛序列.
///
/// details | 解答
    type : proof
正确.

这是 B-W 定理, 有界数列一定有收敛子列.
///

///question | Question 2
扩充复平面 $\overline{\mathbb C}$ 中的无穷集合必包含收敛序列.
///
/// details | 解答
    type : proof
正确.

由于扩充复平面 $\overline{\mathbb{C}}$ 是紧集, 利用 B-W 定理.
///

/// Question | Question 3
若 $D \subset \mathbb C$ 是连通的, 则 $D$ 是道路连通的.
///
/// details | 解答
    type : proof
错误.

反例可取 $\{z = x + iy \mid y = \sin \frac 1 x, 0 < x < 1\} \cup \{z = iy \mid -1 \le y \le 1\}$, 其连通但不道路连通.  
反过来, 道路连通一定连通.
///

/// Question | Question 4
若 $D \subset \mathbb C$ 是连通的, $f$ 是 $D$ 上的复值连续函数, 则 $f(D)$ 是连通的.
///
/// details | 解答
    type : proof
正确.

连续函数把连通集映成连通集.
///

/// Question | Question 5
$\sin z$ 和 $\cos z$ 是 $\mathbb C$ 上的有界函数.
///
/// details | 解答
    type : proof
错误.

事实上, 他们是可取遍 $\mathbb C$ 的整函数.没有 Picard 例外值  
另一方面, 由 Liouville 定理, 有界整函数一定是常函数.
///

/// Question | Question 6
若 $\mathbb C$ 上的解析函数 $f, g$ 具有相同的实部, 则 $f$ 与 $g$ 仅相差一个常数.
///
/// details | 解答
    type : proof
正确.

考虑 $h := f - g$ 的实部为0. 假设存在 $z_0 \in \mathbb C$ 使得 $h'(z_0) \ne 0$, 那么像集 $f(\mathbb C)$ 包含内点, 但 $\mathbb R^2$ 中的集合 $\{(u, v)\mid u = 0\}$ 无内点, 矛盾!  
从而 $h$ 为常数.
///

/// Question | Question 7
区域 $D$ 中的任意调和函数, 都存在共轭调和函数, 且在相差一个常数意义下唯一.
///
/// details | 解答
    type : proof
错误.

缺少单连通这一条件. 单连通是必须的, 例如令 $u(x, y) = \ln (x^2 + y^2)$, 则 $u(x, y)$ 是 $\Omega = \mathbb C - \{0\}$ 上的调和函数, 但其在 $\Omega$ 上并无共轭调和函数, 由于 $\text{Ln} z$ 的多值性.
///

/// Question | Question 8
从区域 $\Omega_1$ 到区域$\Omega_2$ 的任意解析映射都是保向的.
///
/// details | 解答
    type : proof
正确.

解析函数的 Jacobi 行列式为 $|f'(z)|^2$ 处处大于等于0, 因而保向.
///

/// Question | Question 9
设幂级数 $\sum_{n = 0} ^ \infty a_nz^n$ 的收敛半径是 $R$, 则其一定在开圆盘 $D(0, R)$ 上内闭一致收敛.
///
/// details | 解答
    type : proof
正确.

这就是 Abel 定理的表述.
///

/// Question | Question 10
若分式线性变换 $L(z)$ 不是恒等映射, 则其至多有两个不动点. 
///
/// details | 解答
    type : proof
正确.

去掉非恒等映射可能不对.
///

/// Question | Question 11
$f$ 为区域 $D$ 上的解析函数, 当且仅当对任意 $z_0 \in D$, $f(z)$ 都可以在 $z_0$ 附近展开为 $z - z_0$ 的幂级数.
///
/// details | 解答
    type : proof
正确.

课本教材原话. 充分性利用定义, 必要性利用 Cauchy 定理.
///

/// Question | Question 12
设 $f$ 为区域 $D$ 上的解析函数, 则对 $D$ 中任意简单闭曲线 $\gamma$ 都有 $\int_\gamma f(z) dz = 0$. 
///
/// details | 解答
    type : proof
错误.

应该为 $\int_{\partial \Omega} f(z) dz = 0.$ 或者应该保证 $\gamma$ 所围区域 $D' \subset D.$
///

/// Question | Question 13
若 $f$ 在区域 $D$ 上解析且在 $D$ 中的一个小圆盘 $D(0, \varepsilon)$ 上为常值, 则 $f$ 在 $D$ 上为常值.
///
/// details | 解答
    type : proof
正确.

利用解析函数唯一性定理即可.
///

---

### 第五题(8分)

/// question
设 $f$ 在平面区域 $\Omega \subset \mathbb C$ 上解析, 证明 : $g(z) = \overline{f(\overline{z})}$ 在区域 $\Omega ^ * = \{\overline z : z \in \Omega\}$ 上解析, 且 $g'(z) = \overline{f'(\overline{z})}$.
///
/// details | 解答
    type : proof

设 $f(z) = u(x, y) + iv(x, y)$, $g(z) = U(x, y) + iV(x, y)$, 那么

\[U(x, y) = u(x, -y),\quad V(x, y) = -v(x, -y) \]

因此

\[\frac{\partial U}{\partial x} = \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} = \frac{\partial V}{\partial y}.\]

\[\frac{\partial V}{\partial x} = -\frac{\partial v}{\partial x} = \frac{\partial u}{\partial y} = -\frac{\partial U}{\partial y}.\]

又 $U, V$ 在 $\Omega^*$ 上连续可微, 因此 $g$ 在 $\Omega^*$ 上解析.

$$g'(z) = \lim_{z_0 \to z} \frac {g(z) - g(z_0)}{z - z_0} = \lim_{z \to z_0} \frac {\overline{f(\overline{z}) - f(\overline{z_0})}}{z - z_0} = \lim_{z \to z_0} \overline {\left(\frac {{f(\overline{z}) - f(\overline{z_0})}}{\overline z - \overline {z_0}}\right)} = \overline{f'(\overline{z})}$$
///

---

### 第六题(10分)

/// question
假设 $f \in C(\overline{D(0, R)})$ 在 $D(0, R)$ 上解析, 可展开为幂级数

\[f(z) = \sum_{n = 0}^\infty a_n  z^n, \quad \forall z \in D(0, R).\]

记其部分和函数 $S_n(z) = \sum_{k = 0} ^ n a_kz^k$.

(1) 证明

\[f(z) - S_n(z) = \frac {z^{n+1}}{2\pi i}\int_{|\zeta| = R} \frac {f(\zeta)}{\zeta^{n+1}(\zeta - z)}d\zeta,\quad \forall z \in D(0, R).\]

(2) 证明如下的误差估计

\[|f(z) - S_n(z)| \le \frac{\max_{\zeta \in D}|f(\zeta)|}{R^n(R - |z|)}|z|^{n+1}, \quad, \forall z \in D(0, R).\]
///

///details | 解答
    type : proof
    open : True

(1) 考虑

\[f(z) = \frac{1}{2\pi i}\int_{|\zeta| = R} \frac{f(\zeta)}{\zeta - z}d\zeta.\]

和

\[a_n = \frac{1}{2\pi i}\int_{|\zeta| = R} \frac{f(\zeta)}{\zeta^{n+1}}d\zeta.\]

因此

\begin{align*}
S_n = \sum_{k = 0}^n a_kz^k &= \frac{1}{2\pi i}\int_{|\zeta| = R}\sum_{k=0}^n \frac{z^kf(\zeta)}{\zeta^{k+1}}d\zeta\\
&= \frac {1}{2\pi i}\int_{|\zeta| = R} \frac{f(\zeta)}{\zeta}\sum_{k=0}^n\left(\frac z \zeta\right)^k d\zeta\\
&= \frac {1}{2\pi i}\int_{|\zeta| = R} {f(\zeta)}\frac{\zeta^{n+1}-z^{n+1}}{\zeta^{n+1}(\zeta - z)} d\zeta
\end{align*}

带入即得.
///

---

### 第七题(10分)

/// question
设 $m \ge 1$ 是整数. 假设 $f$ 是整函数且满足

\[|f(z)| \le C(1 + |z|^m), \quad \forall z \in \mathbb C.\]

利用高阶导数的 Cauchy 不等式证明 $f$ 是次数不超过 $m$ 的多项式.
///

### 第八题(12分)

/// question
设 $f = u + iv : \mathbb C \to \mathbb C$ 是解析函数, 证明在以下两种情形下的 $f$ 都一定是常数 
///