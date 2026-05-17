## 第一章 随机过程的基本概念

### §1.1 随机过程的定义

**定义（随机过程）**：设 $(\Omega, \mathcal{F}, P)$ 是一个概率空间，$T$ 是一个非空实数集（称为**指标集**或**参数集**）。如果对每个 $t \in T$，都有一个定义在该概率空间上的随机变量 $X(t, \omega)$ 与之对应，则称这族随机变量 $\{X(t, \omega), t \in T, \omega \in \Omega\}$ 为一个**随机过程**，简记为 $\{X(t), t \in T\}$。

随机过程可以看作是从 $\Omega \times T$ 到 $\mathbb{R}$ 的映射：$(\omega, t) \mapsto X(\omega, t)$，它有两种等价的解释：

1. **固定 $t$**：$X(\cdot, t)$ 是一个随机变量，表示过程在时刻 $t$ 的状态；
2. **固定 $\omega$**：$X(\omega, \cdot)$ 是一个定义在 $T$ 上的普通函数，称为随机过程对应于样本点 $\omega$ 的**样本函数**或**样本轨道**。

---

### §1.2 随机过程的分布

#### 一、有限维分布函数族

**定义（一维分布函数）**：设 $\{X(t), t \in T\}$ 是一个随机过程，对任意固定的 $t \in T$，称

$$
F_1(x; t) = P\{X(t) \leq x\}, \quad x \in \mathbb{R}
$$

为该随机过程的**一维分布函数**。

**定义（$n$ 维分布函数）**：对任意 $n \in \mathbb{N}^*$ 和任意 $t_1, t_2, \dots, t_n \in T$，称

$$
F_n(x_1, x_2, \dots, x_n; t_1, t_2, \dots, t_n) = P\{X(t_1) \leq x_1, X(t_2) \leq x_2, \dots, X(t_n) \leq x_n\}
$$

为该随机过程的 **$n$ 维分布函数**。

**定义（有限维分布函数族）**：随机过程 $\{X(t), t \in T\}$ 的所有有限维分布函数的全体

$$
\{ F_n(x_1, \dots, x_n; t_1, \dots, t_n) \mid n \in \mathbb{N}^*, t_i \in T, x_i \in \mathbb{R}, 1 \leq i \leq n \}
$$

称为该随机过程的**有限维分布函数族**。

#### 二、柯尔莫哥洛夫存在定理

有限维分布函数族具有以下两个基本性质：

1. **对称性**：对任意 $n$ 个不同时刻 $t_1, \dots, t_n$ 的任意排列 $\pi$，有

   $$
   F_n(x_1, \dots, x_n; t_1, \dots, t_n) = F_n(x_{\pi(1)}, \dots, x_{\pi(n)}; t_{\pi(1)}, \dots, t_{\pi(n)})
   $$

2. **相容性**：对任意 $m < n$，有

   $$
   F_m(x_1, \dots, x_m; t_1, \dots, t_m) = \lim_{x_{m+1}, \dots, x_n \to +\infty} F_n(x_1, \dots, x_n; t_1, \dots, t_n)
   $$

**定理（柯尔莫哥洛夫存在定理）**：一个定义在参数集 $T$ 上的有限维分布函数族 $\{F_n\}$ 是某个随机过程的有限维分布函数族的充要条件是它满足对称性和相容性。

#### 三、离散型与连续型随机过程

- **离散型随机过程**：对任意 $t \in T$，$X(t)$ 是离散型随机变量，其概率分布满足

  $$
  p_k(t) = P\{X(t) = x_k\} \geq 0, \quad \sum_{k=1}^{\infty} p_k(t) = 1
  $$

- **连续型随机过程**：对任意 $t \in T$，$X(t)$ 是连续型随机变量，存在非负可积函数 $f_1(x; t)$，使得

  $$
  F_1(x; t) = \int_{-\infty}^{x} f_1(y; t) \, dy
  $$

---

### §1.3 随机过程的数字特征

设 $\{X(t), t \in T\}$ 是一个随机过程，且所有必要的矩都存在。

1. **均值函数**：

   $$
   m_X(t) = E[X(t)], \quad t \in T
   $$

   表示随机过程在时刻 $t$ 的平均状态。

2. **均方值函数**：

   $$
   \psi_X^2(t) = E[X^2(t)], \quad t \in T
   $$

   表示随机过程在时刻 $t$ 的平均功率。

3. **方差函数**：

   $$
   D_X(t) = \operatorname{Var}[X(t)] = E\{[X(t) - m_X(t)]^2\} = \psi_X^2(t) - m_X^2(t), \quad t \in T
   $$

   表示随机过程在时刻 $t$ 的状态偏离均值的程度。

4. **自相关函数**：

   $$
   R_X(s, t) = E[X(s) X(t)], \quad s, t \in T
   $$

   描述随机过程在两个不同时刻状态之间的线性相关程度。

5. **自协方差函数**：

   $$
   C_X(s, t) = \operatorname{Cov}[X(s), X(t)] = E\{[X(s) - m_X(s)][X(t) - m_X(t)]\} = R_X(s, t) - m_X(s) m_X(t), \quad s, t \in T
   $$

   描述随机过程在两个不同时刻的状态偏离均值之间的线性相关程度。

---

### §1.4 特征函数

**定义（一维特征函数）**：随机过程 $\{X(t), t \in T\}$ 的一维特征函数定义为

$$
\varphi_X(v; t) = E[e^{i v X(t)}], \quad v \in \mathbb{R}, \; t \in T
$$

**定义（$n$ 维特征函数）**：对任意 $n \in \mathbb{N}^*$ 和任意 $t_1, \dots, t_n \in T$，$n$ 维特征函数定义为

$$
\varphi_X(v_1, \dots, v_n; t_1, \dots, t_n) = E\!\left[ \exp\!\left( i \sum_{k=1}^{n} v_k X(t_k) \right) \right], \quad v_k \in \mathbb{R}
$$

**定义（有限维特征函数族）**：随机过程的所有有限维特征函数的全体称为其**有限维特征函数族**，它与有限维分布函数族一一对应。

---

### §1.5 复随机过程与二维随机过程

#### 一、复随机过程

**定义（复随机过程）**：设 $\{X(t), t \in T\}$ 和 $\{Y(t), t \in T\}$ 是两个实随机过程，则称

$$
Z(t) = X(t) + i Y(t), \quad t \in T
$$

为**复随机过程**，其中 $i = \sqrt{-1}$。

复随机过程的数字特征定义如下：

1. **均值函数**：$m_Z(t) = E[Z(t)] = m_X(t) + i m_Y(t)$
2. **均方值函数**：$\psi_Z^2(t) = E[|Z(t)|^2] = E[Z(t) \overline{Z(t)}] = \psi_X^2(t) + \psi_Y^2(t)$
3. **方差函数**：$D_Z(t) = E[|Z(t) - m_Z(t)|^2] = D_X(t) + D_Y(t)$
4. **自相关函数**：$R_Z(s, t) = E[Z(s) \overline{Z(t)}]$（必须取共轭）
5. **自协方差函数**：$C_Z(s, t) = E\{[Z(s) - m_Z(s)] \overline{[Z(t) - m_Z(t)]}\} = R_Z(s, t) - m_Z(s) \overline{m_Z(t)}$

#### 二、二维随机过程

**定义（二维随机过程）**：若对任意 $s \in S, t \in T$，$(X(s), Y(t))$ 是概率空间 $(\Omega, \mathcal{F}, P)$ 上的二维随机变量，则称 $\{(X(s), Y(t)), s \in S, t \in T\}$ 为**二维随机过程**。

二维随机过程的互相关函数和互协方差函数定义为：

1. **互相关函数**：$R_{XY}(s, t) = E[X(s) Y(t)]$
2. **互协方差函数**：$C_{XY}(s, t) = \operatorname{Cov}[X(s), Y(t)] = E\{[X(s) - m_X(s)][Y(t) - m_Y(t)]\} = R_{XY}(s, t) - m_X(s) m_Y(t)$

若对任意 $s \in S, t \in T$，都有 $C_{XY}(s, t) = 0$，则称随机过程 $\{X(s)\}$ 与 $\{Y(t)\}$ **不相关**。

若对任意 $m, n \in \mathbb{N}^*$，任意 $s_1, \dots, s_m \in S$，任意 $t_1, \dots, t_n \in T$，随机向量 $(X(s_1), \dots, X(s_m))$ 与 $(Y(t_1), \dots, Y(t_n))$ 相互独立，则称随机过程 $\{X(s)\}$ 与 $\{Y(t)\}$ **相互独立**。

---

### §1.6 随机过程的分类

#### 一、按参数集与状态空间分类

| 参数集 \ 状态空间 | 离散（状态取有限或可列个值） | 连续（状态取连续值） |
|---|---|---|
| **离散**（参数取有限或可列个值） | 随机序列（离散时间离散状态） | 离散参数过程（离散时间连续状态） |
| **连续**（参数取连续值） | 连续参数链（连续时间离散状态） | 随机过程（连续时间连续状态） |

#### 二、按统计特性分类

1. **二阶矩过程**：若对任意 $t \in T$，$E[|X(t)|^2] < \infty$，则称 $\{X(t), t \in T\}$ 为**二阶矩过程**。

   > 注：由柯西 - 施瓦茨不等式，二阶矩有限蕴含一阶矩有限，因此二阶矩过程的均值函数、自相关函数等数字特征都存在。

2. **独立过程**：若对任意 $n \in \mathbb{N}^*$ 和任意 $t_1 < t_2 < \cdots < t_n \in T$，随机变量 $X(t_1), X(t_2), \dots, X(t_n)$ 相互独立，则称 $\{X(t), t \in T\}$ 为**独立过程**。

3. **独立增量过程**：若对任意 $n \geq 3$ 和任意 $t_1 < t_2 < \cdots < t_n \in T$，增量 $X(t_2) - X(t_1), X(t_3) - X(t_2), \dots, X(t_n) - X(t_{n-1})$ 相互独立，则称 $\{X(t), t \in T\}$ 为**独立增量过程**（或可加过程）。

   > 注：独立过程一定是独立增量过程，但独立增量过程不一定是独立过程。

4. **平稳增量过程**：若对任意 $s, t, h \in T$，增量 $X(t+h) - X(s+h)$ 与 $X(t) - X(s)$ 同分布，则称 $\{X(t), t \in T\}$ 为**平稳增量过程**（或齐次增量过程）。

   **性质**：设 $\{X(t), t \geq 0\}$ 是具有平稳独立增量的二阶矩过程，且 $X(0) = 0$，则

   - $D[X(t) - X(s)] = \sigma^2 |t - s|$（绝对齐性）
   - $C_X(s, t) = \sigma^2 \min(s, t)$

   其中 $\sigma^2 = D[X(1)]$。

5. **正交增量过程**：设 $\{X(t), t \in T\}$ 是二阶矩过程，若对任意 $t_1 < t_2 \leq t_3 < t_4 \in T$，有

   $$
   E\{[X(t_2) - X(t_1)] \overline{[X(t_4) - X(t_3)]}\} = 0
   $$

   则称 $\{X(t), t \in T\}$ 为**正交增量过程**。

   **性质**：设 $\{X(t), t \in [a, b]\}$ 是正交增量过程，且 $X(a) = 0$，则

   - $R_X(s, t) = R_X(\min(s, t), \min(s, t))$
   - $R_X(t, t)$ 是 $[a, b]$ 上的单调不减函数。

6. **正态过程（高斯过程）**：若随机过程 $\{X(t), t \in T\}$ 的任意有限维分布都是正态分布，则称它为**正态过程**。

   > 注：正态过程的有限维分布完全由其均值函数和自协方差函数确定。

7. **布朗运动（维纳过程）**：若随机过程 $\{B(t), t \geq 0\}$ 满足：

   8. $B(0) = 0$ a.s.；
   9. 具有独立增量；
   10. 对任意 $s < t$，$B(t) - B(s) \sim N(0, \sigma^2 (t - s))$（平稳增量）。

   则称 $\{B(t)\}$ 为参数是 $\sigma^2$ 的**布朗运动**。当 $\sigma = 1$ 时，称为**标准布朗运动**。

   **性质**：

   - 布朗运动是具有平稳独立增量的正态过程；
   - 标准布朗运动的自协方差函数为 $C_B(s, t) = \min(s, t)$；
   - 对任意 $n \in \mathbb{N}^*$ 和任意 $t_1 < t_2 < \cdots < t_n$，$(B(t_1), B(t_2), \dots, B(t_n))$ 服从 $n$ 维正态分布，其协方差矩阵 $\Sigma$ 满足 $\Sigma_{ij} = \min(t_i, t_j)$。

---

## 第二章 均方微积分

均方微积分是研究二阶矩过程的微积分理论，它以均方极限为基础，定义了均方连续、均方导数和均方积分等概念。

---

### §2.1 二阶矩变量空间

**定义（二阶矩变量空间）**：所有二阶矩存在的随机变量的全体组成的集合称为**二阶矩变量空间**，记为

$$
H = \{ X \mid E[|X|^2] < +\infty \}
$$

**定理**：$H$ 是一个完备的赋范线性空间（Banach 空间），其中范数定义为

$$
\|X\| = \sqrt{E[|X|^2]}
$$

该范数满足以下性质：

1. **非负性**：$\|X\| \geq 0$，且 $\|X\| = 0 \iff X = 0$ a.s.
2. **绝对齐性**：对任意常数 $a \in \mathbb{C}$，$\|aX\| = |a| \|X\|$
3. **三角不等式**：$\|X + Y\| \leq \|X\| + \|Y\|$

在 $H$ 中，有以下重要不等式：

- **柯西 - 施瓦茨 (Cauchy-Schwarz) 不等式**：对任意 $X, Y \in H$，有

  $$
  |E[X \overline{Y}]| \leq \|X\| \|Y\|
  $$

- **延森 (Jensen) 不等式**：对任意 $X \in H$，有

  $$
  |E[X]| \leq E[|X|] \leq \|X\|
  $$

---

### §2.2 均方极限

#### 一、均方极限的定义

**定义（均方极限）**：设 $\{X_n, n \geq 1\}$ 是 $H$ 中的随机变量序列，若存在 $X \in H$，使得

$$
\lim_{n \to \infty} E[|X_n - X|^2] = 0 \iff \lim_{n \to \infty} \|X_n - X\| = 0
$$

则称序列 $\{X_n\}$ **均方收敛**于 $X$，或称 $X$ 是 $\{X_n\}$ 的**均方极限**，记为

$$
\operatorname*{l.i.m.}_{n \to \infty} X_n = X \quad \text{或} \quad X_n \xrightarrow{m.s.} X
$$

#### 二、均方极限的性质

1. **唯一性**：若 $X_n \xrightarrow{m.s.} X$ 且 $X_n \xrightarrow{m.s.} Y$，则 $P(X = Y) = 1$。

2. **线性性**：若 $X_n \xrightarrow{m.s.} X$，$Y_n \xrightarrow{m.s.} Y$，则对任意常数 $a, b \in \mathbb{C}$，有

   $$
   aX_n + bY_n \xrightarrow{m.s.} aX + bY
   $$

3. **与期望可换序**：若 $X_n \xrightarrow{m.s.} X$，$Y_n \xrightarrow{m.s.} Y$，则

   - $\lim_{n \to \infty} E[X_n] = E\!\left[ \operatorname*{l.i.m.}_{n \to \infty} X_n \right] = E[X]$
   - $\lim_{n \to \infty} E[X_n \overline{Y_n}] = E\!\left[ \operatorname*{l.i.m.}_{n \to \infty} X_n \cdot \overline{\operatorname*{l.i.m.}_{n \to \infty} Y_n} \right] = E[X \overline{Y}]$
   - $\lim_{n \to \infty} D[X_n] = D\!\left[ \operatorname*{l.i.m.}_{n \to \infty} X_n \right] = D[X]$

4. **与特征函数可换序**：若 $X_n \xrightarrow{m.s.} X$，则对任意 $v \in \mathbb{R}$，有

   $$
   \lim_{n \to \infty} \varphi_{X_n}(v) = \varphi_X(v)
   $$

5. **与其他收敛的关系**：

   - 均方收敛 ⇒ 依概率收敛 ⇒ 依分布收敛
   - 以概率 $1$ 收敛 ⇒ 依概率收敛 ⇒ 依分布收敛
   - 均方收敛与以概率 $1$ 收敛之间无蕴含关系

#### 三、均方收敛的判别准则

1. **柯西 (Cauchy) 收敛准则**：$\{X_n\}$ 均方收敛的充要条件是 $\{X_n\}$ 是 $H$ 中的柯西列，即

   $$
   \lim_{\substack{m \to \infty \\ n \to \infty}} E[|X_m - X_n|^2] = 0
   $$

2. **勒夫 (Loève) 准则**：$\{X_n\}$ 均方收敛的充要条件是极限

   $$
   \lim_{\substack{m \to \infty \\ n \to \infty}} E[X_m \overline{X_n}]
   $$

   存在且有限。

#### 四、均方大数定律

**定理（均方大数定律）**：设 $\{X_n, n \geq 1\}$ 是独立同分布的随机变量序列，且 $E[X_1] = \mu$，$D[X_1] = \sigma^2 < \infty$，则

$$
\frac{1}{n} \sum_{k=1}^n X_k \xrightarrow{m.s.} \mu
$$

---

### §2.3 均方连续

**定义（均方连续）**：设 $\{X(t), t \in T\}$ 是二阶矩过程，$t_0 \in T$。若

$$
\lim_{t \to t_0} \|X(t) - X(t_0)\| = 0
$$

即对任意 $\varepsilon > 0$，存在 $\delta > 0$，使得当 $|t - t_0| < \delta$ 时，有

$$
E[|X(t) - X(t_0)|^2] < \varepsilon
$$

则称 $X(t)$ 在 $t_0$ 处**均方连续**。若 $X(t)$ 在 $T$ 上每一点都均方连续，则称 $X(t)$ 在 $T$ 上**均方连续**。

**定理（均方连续准则）**：二阶矩过程 $X(t)$ 在 $t_0$ 处均方连续的充要条件是其自相关函数 $R_X(s, t)$ 在点 $(t_0, t_0)$ 处连续。

**推论**：

1. 二阶矩过程 $X(t)$ 在 $T$ 上均方连续 $\Leftrightarrow$ 其自相关函数 $R_X(s, t)$ 在 $T \times T$ 上连续。
2. 若二阶矩过程 $X(t)$ 在 $T$ 上均方连续，则其均值函数 $m_X(t)$ 和方差函数 $D_X(t)$ 也在 $T$ 上连续。

> 注：均方连续是过程的统计平均性质，并不意味着每个样本函数都连续。例如，布朗运动是均方连续的，但它的几乎所有样本函数都是处处连续且处处不可导的。

---

### §2.4 均方导数

#### 一、均方导数的定义

**定义（均方导数）**：设 $\{X(t), t \in T\}$ 是二阶矩过程，$t_0 \in T$。若均方极限

$$
\operatorname*{l.i.m.}_{\Delta t \to 0} \frac{X(t_0 + \Delta t) - X(t_0)}{\Delta t}
$$

存在，则称 $X(t)$ 在 $t_0$ 处**均方可导**，并称该极限为 $X(t)$ 在 $t_0$ 处的**均方导数**，记为 $X'(t_0)$ 或 $\dfrac{dX(t)}{dt}\bigg|_{t = t_0}$。

若 $X(t)$ 在 $T$ 上每一点都均方可导，则称 $X(t)$ 在 $T$ 上**均方可导**，并称 $\{X'(t), t \in T\}$ 为 $X(t)$ 的**导数过程**。

高阶均方导数可递推定义：

$$
X^{(n)}(t) = \operatorname*{l.i.m.}_{\Delta t \to 0} \frac{X^{(n-1)}(t + \Delta t) - X^{(n-1)}(t)}{\Delta t}
$$

#### 二、广义二阶可导

为了给出均方可导的判别准则，我们先引入二元函数的广义二阶可导概念。

**定义（广义二阶可导）**：设 $f(s, t)$ 是定义在 $\mathbb{R}^2$ 上的二元函数，若极限

$$
\lim_{\substack{h \to 0 \\ k \to 0}} \frac{f(s+h, t+k) - f(s+h, t) - f(s, t+k) + f(s, t)}{hk}
$$

存在，则称 $f(s, t)$ 在点 $(s, t)$ 处**广义二阶可导**，并称该极限为 $f(s, t)$ 在点 $(s, t)$ 处的**广义二阶导数**。

> 注：若 $f(s, t)$ 的二阶混合偏导数 $\dfrac{\partial^2 f}{\partial s \partial t}$ 和 $\dfrac{\partial^2 f}{\partial t \partial s}$ 存在且连续，则 $f(s, t)$ 一定广义二阶可导，且广义二阶导数等于二阶混合偏导数。

#### 三、均方可导准则

**定理（均方可导准则）**：二阶矩过程 $X(t)$ 在 $t_0$ 处均方可导的充要条件是其自相关函数 $R_X(s, t)$ 在点 $(t_0, t_0)$ 处广义二阶可导。

**推论**：

1. 二阶矩过程 $X(t)$ 在 $T$ 上均方可导 $\Leftrightarrow$ 其自相关函数 $R_X(s, t)$ 在 $T \times T$ 上广义二阶可导。
2. 若 $X(t)$ 均方可导，则其自相关函数的各阶偏导数存在，且有：

   - $E[X'(s) \overline{X(t)}] = \dfrac{\partial R_X(s, t)}{\partial s}$
   - $E[X(s) \overline{X'(t)}] = \dfrac{\partial R_X(s, t)}{\partial t}$
   - $E[X'(s) \overline{X'(t)}] = \dfrac{\partial^2 R_X(s, t)}{\partial s \partial t} = \dfrac{\partial^2 R_X(s, t)}{\partial t \partial s}$

#### 四、均方导数的性质

1. 若 $X(t)$ 在 $t_0$ 处均方可导，则 $X(t)$ 在 $t_0$ 处必均方连续。
2. **线性性**：若 $X(t)$ 和 $Y(t)$ 均方可导，则对任意常数 $a, b \in \mathbb{C}$，$aX(t) + bY(t)$ 也均方可导，且

   $$
   [aX(t) + bY(t)]' = aX'(t) + bY'(t)
   $$

3. 均方导数的均值函数等于均值函数的导数：

   $$
   m_{X'}(t) = E[X'(t)] = \frac{d}{dt} E[X(t)] = m_X'(t)
   $$

4. 若两个随机过程的均方导数相等，则它们只相差一个随机变量。
5. **乘积法则**：若 $f(t)$ 是普通可导函数，$X(t)$ 均方可导，则 $f(t)X(t)$ 也均方可导，且

   $$
   [f(t)X(t)]' = f'(t)X(t) + f(t)X'(t)
   $$

---

### §2.5 均方积分

#### 一、均方积分的定义

**定义（均方积分）**：设 $\{X(t), t \in [a, b]\}$ 是二阶矩过程，对区间 $[a, b]$ 作分割：

$$
a = t_0 < t_1 < \dots < t_n = b
$$

令 $\Delta t_k = t_k - t_{k-1}$，$\Delta = \max_{1 \leq k \leq n} \Delta t_k$，在每个小区间 $[t_{k-1}, t_k]$ 上任取一点 $s_k$，作和式

$$
Y_n = \sum_{k=1}^n X(s_k) \Delta t_k
$$

若当 $\Delta \to 0$ 时，$Y_n$ 均方收敛于某个随机变量 $Y$，则称 $X(t)$ 在 $[a, b]$ 上**均方可积**，并称 $Y$ 为 $X(t)$ 在 $[a, b]$ 上的**均方积分**，记为

$$
Y = \int_a^b X(t) \, dt
$$

#### 二、均方可积准则

**定理（均方可积准则）**：二阶矩过程 $X(t)$ 在 $[a, b]$ 上均方可积的充要条件是二重积分

$$
\int_a^b \int_a^b R_X(s, t) \, ds \, dt
$$

存在且有限。

此时，有

$$
E\!\left[ \left| \int_a^b X(t) \, dt \right|^2 \right] = \int_a^b \int_a^b R_X(s, t) \, ds \, dt
$$

#### 三、均方积分的性质

1. **唯一性**：若 $X(t)$ 在 $[a, b]$ 上均方可积，则其均方积分唯一（以概率 $1$ 相等）。
2. **线性性**：若 $X(t)$ 和 $Y(t)$ 均方可积，则对任意常数 $a, b \in \mathbb{C}$，$aX(t) + bY(t)$ 也均方可积，且

   $$
   \int_a^b [aX(t) + bY(t)] \, dt = a \int_a^b X(t) \, dt + b \int_a^b Y(t) \, dt
   $$

3. **可加性**：对任意 $c \in (a, b)$，有

   $$
   \int_a^b X(t) \, dt = \int_a^c X(t) \, dt + \int_c^b X(t) \, dt
   $$

4. **与期望可换序**：若 $X(t)$ 均方可积，则

   $$
   E\!\left[ \int_a^b X(t) \, dt \right] = \int_a^b E[X(t)] \, dt
   $$

5. **牛顿 - 莱布尼茨公式**：若 $X(t)$ 在 $[a, b]$ 上均方可导，则

   $$
   \int_a^b X'(t) \, dt = X(b) - X(a)
   $$

6. **连续必可积**：若 $X(t)$ 在 $[a, b]$ 上均方连续，则 $X(t)$ 在 $[a, b]$ 上必均方可积，且

   $$
   E\!\left[ \left| \int_a^b X(t) \, dt \right|^2 \right] \leq M(b - a)^2
   $$

   其中 $M = \max_{t \in [a, b]} E[|X(t)|^2]$。

7. **积分的协方差公式**：

   $$
   \operatorname{Cov}\!\left( \int_a^b X(s) \, ds, \int_a^b X(t) \, dt \right) = \int_a^b \int_a^b C_X(s, t) \, ds \, dt
   $$

---

### §2.6 正态过程的均方微积分

正态过程在均方微积分运算下具有良好的封闭性，即正态性在均方极限下保持不变。

**定理 1**：若 $\{X_n, n \geq 1\}$ 是正态随机变量序列，且 $X_n \xrightarrow{m.s.} X$，则 $X$ 也是正态随机变量。

**定理 2**：若 $\{X(t), t \in T\}$ 是正态过程，且 $X(t)$ 均方可导，则其导数过程 $\{X'(t), t \in T\}$ 也是正态过程。

**定理 3**：若 $\{X(t), t \in [a, b]\}$ 是正态过程，且 $X(t)$ 均方可积，则其积分过程

$$
Y(t) = \int_a^t X(s) \, ds, \quad t \in [a, b]
$$

也是正态过程。

> 注：布朗运动是正态过程，它是均方连续的，但处处均方不可导。这是因为布朗运动的自相关函数 $R_B(s, t) = \min(s, t)$ 在对角线上不广义二阶可导。

---

### §2.7 随机微分方程简介

**定义（一阶线性随机微分方程）**：形如

$$
\begin{cases}
\dfrac{dY(t)}{dt} + a(t) Y(t) = X(t) \\[6pt]
Y(t_0) = Y_0
\end{cases}
$$

的方程称为**一阶线性随机微分方程**，其中 $a(t)$ 是普通确定性函数，$X(t)$ 是二阶矩过程，$Y_0$ 是二阶矩随机变量。

**定理（解的存在唯一性）**：若 $a(t)$ 在 $[t_0, T]$ 上连续，$X(t)$ 在 $[t_0, T]$ 上均方连续，$Y_0$ 是二阶矩随机变量，则上述一阶线性随机微分方程存在唯一解，且解为

$$
Y(t) = Y_0 e^{-\int_{t_0}^t a(s) \, ds} + \int_{t_0}^t X(s) e^{-\int_s^t a(u) \, du} \, ds
$$

**证明思路**：先解对应的齐次方程 $\dfrac{dY(t)}{dt} + a(t)Y(t) = 0$，得到齐次解 $Y_h(t) = C e^{-\int_{t_0}^t a(s) \, ds}$，再用常数变易法求非齐次方程的特解。

# 第三章 泊松过程

## 3.1 计数过程

**Def（计数过程）**

称 $\{N(t), t \ge 0\}$ 是一个**计数过程**，如果满足：

1. $\forall t \ge 0$，$N(t)$ 为非负整数；
2. $\forall 0 \le s < t$，$N(s) \le N(t)$；
3. $\forall 0 \le s < t$，$N(t) - N(s)$ 表示时间段 $(s, t]$ 内事件发生的次数。

## 3.2 泊松过程

### 3.2.1 泊松过程（定义一：平稳独立增量型）

**Def（泊松过程）**

若计数过程 $\{N(t), t \ge 0\}$ 满足：

1. $N(0) = 0$，a.s.；
2. $\{N(t), t \ge 0\}$ 具有**独立增量**；
3. $\forall t \ge 0, \Delta t > 0$，增量 $N(t + \Delta t) - N(t) \sim P(\lambda \Delta t)$（**平稳增量**），其中 $\lambda > 0$。

则称 $\{N(t), t \ge 0\}$ 为**强度为 $\lambda$ 的齐次泊松过程**。

注：$\displaystyle \lim_{\Delta t \to 0} \frac{E[N(t + \Delta t) - N(t)]}{\Delta t} = \lambda$，$\lambda$ 称为过程强度。

### 3.2.2 泊松过程（定义二：无穷小增量型）

**Def（泊松过程）**

若计数过程 $\{N(t), t \ge 0\}$ 满足：

1. $N(0) = 0$，a.s.；
2. $\{N(t), t \ge 0\}$ 具有**独立增量**；
3. $\{N(t), t \ge 0\}$ 具有**平稳增量**，且当 $\Delta t \to 0$ 时：

$$
\begin{cases}
P(N(\Delta t) = 0) = 1 - \lambda \Delta t + o(\Delta t) \\
P(N(\Delta t) = 1) = \lambda \Delta t + o(\Delta t) \\
P(N(\Delta t) \ge 2) = o(\Delta t)
\end{cases}
$$

其中 $\lambda > 0$。

则称 $\{N(t), t \ge 0\}$ 为**强度为 $\lambda$ 的齐次泊松过程**。

## 3.3 泊松过程的数字特征

**Prop（泊松过程的数字特征）**

设 $\{N(t), t \ge 0\}$ 是强度为 $\lambda$ 的泊松过程，则：

- 均值函数：$m_N(t) = E[N(t)] = \lambda t$
- 方差函数：$D_N(t) = \operatorname{Var}[N(t)] = \lambda t$
- 自相关函数：$R_N(t_1, t_2) = E[N(t_1) N(t_2)] = \lambda^2 t_1 t_2 + \lambda (t_1 \wedge t_2)$
- 自协方差函数：$C_N(t_1, t_2) = \operatorname{Cov}[N(t_1), N(t_2)] = \lambda (t_1 \wedge t_2)$
- 特征函数：$\varphi_N(t; v) = E[e^{i v N(t)}] = \exp[\lambda t (e^{i v} - 1)]$

注：泊松过程均值与方差相等，从 $0$ 时刻开始计数。

## 3.4 复合泊松过程

**Def（复合泊松过程）**

设 $\{N(t), t \ge 0\}$ 是强度为 $\lambda$ 的泊松过程，$\{X_n, n \in \mathbb{N}^*\}$ 是独立同分布（i.i.d.）随机变量列，且 $\{N(t)\}$ 与 $\{X_n\}$ 相互独立。

称随机过程

$$
Y(t) = \sum_{n=1}^{N(t)} X_n, \quad t \ge 0
$$

为**复合泊松过程**。

注：约定 $\displaystyle \sum_{n=1}^{0} X_n = 0$；泊松过程是复合泊松过程的特例（取 $X_n \equiv 1$），即 $N(t) = \displaystyle \sum_{n=1}^{N(t)} 1$。

**Prop（复合泊松过程的性质）**

设 $\{Y(t) = \displaystyle \sum_{n=1}^{N(t)} X_n, t \ge 0\}$ 为复合泊松过程，则：

1. $\{Y(t), t \ge 0\}$ 具有**平稳独立增量**；
2. $Y(t)$ 的特征函数：$\varphi_Y(t; v) = \exp\{\lambda t [\varphi_X(v) - 1]\}$，其中 $\varphi_X(v) = E[e^{i v X_1}]$；
3. 若 $E[|X_1|] < +\infty$，则均值：$m_Y(t) = E[Y(t)] = \lambda t E[X_1]$；
4. 若 $E[X_1^2] < +\infty$，则方差：$D_Y(t) = \operatorname{Var}[Y(t)] = \lambda t E[X_1^2]$。

## 3.5 泊松过程的叠加

**Thm（泊松过程的叠加）**

设 $\{N_1(t), t \ge 0\}$ 与 $\{N_2(t), t \ge 0\}$ 是**相互独立**、强度分别为 $\lambda_1$ 和 $\lambda_2$ 的泊松过程，则

$$
N(t) = N_1(t) + N_2(t), \quad t \ge 0
$$

仍是泊松过程，强度为 $\lambda = \lambda_1 + \lambda_2$。

**Thm（泊松过程叠加的推广）**

若 $\{N_k(t), t \ge 0\}\ (k = 1, 2, \dots, n)$ 是 $n$ 个**相互独立**、强度分别为 $\lambda_1, \lambda_2, \dots, \lambda_n$ 的泊松过程，则

$$
N(t) = \sum_{k=1}^{n} N_k(t), \quad t \ge 0
$$

是强度为 $\displaystyle \lambda = \sum_{k=1}^{n} \lambda_k$ 的泊松过程。

注：

1. 仅当 $\{N_1(t)\}$ 与 $\{N_2(t)\}$ **相互独立**时，叠加才是泊松过程；
2. 不独立时，$N_1(t) + N_2(t)$ 不一定是泊松过程；
3. $N_1(t) - N_2(t)$ 一定不是泊松过程。

**Example**

设 $\{N_1(t)\}, \{N_2(t)\}$ 独立，强度为 $\lambda_1, \lambda_2$，对不全为 $0$ 的实数 $\alpha_1, \alpha_2$：

1. $\alpha_1 N_1(t) + \alpha_2 N_2(t)$ 是**复合泊松过程**；
2. $\alpha_1 N_1(t) + \alpha_2 N_2(t)$ 为泊松过程 $\iff$ 仅一项系数为 $1$、另一为 $0$。

## 3.6 泊松过程的分解

**Thm（泊松过程的分解）**

设 $\{N(t), t \ge 0\}$ 是强度为 $\lambda$ 的泊松过程，每个事件独立地以概率 $p$ 进入子系统 $A$、概率 $1-p$ 进入子系统 $B$，记：

- $N_1(t)$：$[0, t]$ 内进入 $A$ 的事件数；
- $N_2(t)$：$[0, t]$ 内进入 $B$ 的事件数。

则 $\{N_1(t)\}$ 与 $\{N_2(t)\}$ **相互独立**，且分别为强度 $\lambda_1 = \lambda p$、$\lambda_2 = \lambda (1-p)$ 的泊松过程。

## 3.7 到达时间与时间间隔

### 3.7.1 基本定义

记：

- $\tau_n$：第 $n$ 次事件发生的**到达时间**；
- $T_n = \tau_n - \tau_{n-1}$：第 $n-1$ 次到第 $n$ 次事件的**时间间隔**（$\tau_0 = 0$）。

计数过程与到达时间关系：

$$
N(t) = \sup\{n : \tau_n \le t\}, \quad \tau_n = \inf\{t : N(t) \ge n\} = \sum_{k=1}^{n} T_k
$$

### 3.7.2 到达时间 $\tau_n$ 的分布

**Thm**

设 $\{N(t), t \ge 0\}$ 是强度为 $\lambda$ 的泊松过程，则到达时间 $\tau_n$ 服从 **Gamma 分布 $\Gamma(n, \lambda)$**，概率密度为：

$$
f_{\tau_n}(t) = \frac{\lambda^n t^{n-1}}{(n-1)!} e^{-\lambda t}, \quad t > 0
$$

分布函数：

$$
F_{\tau_n}(t) = 1 - \sum_{k=0}^{n-1} \frac{(\lambda t)^k}{k!} e^{-\lambda t}, \quad t > 0
$$

**Prop**

$\tau_n$ 的数字特征：

- 均值：$E[\tau_n] = \dfrac{n}{\lambda}$
- 方差：$D[\tau_n] = \dfrac{n}{\lambda^2}$
- 特征函数：$\varphi_{\tau_n}(v) = \left( \dfrac{\lambda}{\lambda - i v} \right)^n$

### 3.7.3 时间间隔 $T_n$ 的分布

**Thm**

计数过程 $\{N(t), t \ge 0\}$ 是**强度为 $\lambda$ 的泊松过程** $\iff$ 时间间隔 $\{T_n, n \in \mathbb{N}^*\}$ **独立同分布**，且服从**指数分布 $\operatorname{Exp}(\lambda)$**，概率密度：

$$
f_{T}(x) = \lambda e^{-\lambda x}, \quad x > 0
$$