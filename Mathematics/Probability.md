# 第一章 事件与概率

## §1.1 随机事件与样本空间

**样本空间**：随机现象的一切可能基本结果组成的集合称为样本空间，记作 $\Omega$。

**随机事件**：随机现象的某些样本点组成的集合称为随机事件，简称事件，通常用大写字母 $A,B,C,\cdots$ 表示。

**特殊事件**：

- **基本事件**：由单个样本点组成的事件
- **必然事件**：样本空间 $\Omega$ 本身
- **不可能事件**：空集 $\varnothing$

## §1.2 事件域

**定义**：设 $\Omega$ 为一样本空间，$\mathcal{F}$ 为 $\Omega$ 的某些子集所组成的集合类。如果 $\mathcal{F}$ 满足：

1. $\Omega \in \mathcal{F}$
2. 若 $A \in \mathcal{F}$，则对立事件 $\overline{A} \in \mathcal{F}$
3. 若 $A_n \in \mathcal{F}$，$n=1,2,\cdots$，则可列并 $\displaystyle\bigcup_{n=1}^{\infty} A_n \in \mathcal{F}$

则称 $\mathcal{F}$ 为一个**事件域**，又称为 $\sigma$ 代数。称 $(\Omega, \mathcal{F})$ 为**可测空间**。

## §1.3 概率的公理化定义

**定义**：设 $\Omega$ 为一个样本空间，$\mathcal{F}$ 为 $\Omega$ 的某些子集组成的一个事件域。如果对任一事件 $A \in \mathcal{F}$，定义在 $\mathcal{F}$ 上的一个实值函数 $P(A)$ 满足：

- **非负性公理**：若 $A \in \mathcal{F}$，则 $P(A) \geq 0$
- **正则性公理**：$P(\Omega) = 1$
- **可列可加性公理**：若 $A_1,A_2,\cdots,A_n,\cdots$ 互不相容，则

  $$
  P\!\left( \bigcup_{i=1}^{\infty} A_i \right) = \sum_{i=1}^{\infty} P(A_i)
  $$

则称 $P(A)$ 为事件 $A$ 的概率。称三元组 $(\Omega, \mathcal{F}, P)$ 为**概率空间**。

## §1.4 概率的性质

1. $P(\varnothing) = 0$

   **注**：概率为 $0$ 的事件不一定是不可能事件；概率为 $1$ 的事件不一定是必然事件。例：候车时间在 $0\sim 6$ 分钟内，候车时间刚好为 $3$ 分钟的概率为 $0$，但该事件可能发生。

2. **有限可加性**：若 $A_1,A_2,\cdots,A_n$ 两两互不相容，则

   $$
   P\!\left( \bigcup_{i=1}^{n} A_i \right) = \sum_{i=1}^{n} P(A_i)
   $$

3. **单调性**：若 $A \subset B$，则 $P(A) \leq P(B)$，且有

   $$
   P(B-A) = P(B) - P(A)
   $$

4. **一般减法公式**：

   $$
   P(B-A) = P(B) - P(AB)
   $$

5. **有界性**：对任何事件 $A$，都有 $0 \leq P(A) \leq 1$

6. **对立事件概率**：

   $$
   P(A) + P(\overline{A}) = 1
   $$

7. **加法公式**：

   - 两个事件：

     $$
     P(A \cup B) = P(A) + P(B) - P(AB)
     $$

   - 一般形式（容斥原理）：

     $$
     \begin{aligned}
     P\!\left( \bigcup_{i=1}^{n} A_i \right) &= \sum_{i=1}^{n} P(A_i) - \sum_{1 \leq i < j \leq n} P(A_i A_j) \\
     &\quad + \sum_{1 \leq i < j < k \leq n} P(A_i A_j A_k) - \cdots \\
     &\quad + (-1)^{n-1} P(A_1 A_2 \cdots A_n)
     \end{aligned}
     $$

## §1.5 概率的连续性

**事件列的极限**：

- **单调不减事件列**：若 $F_1 \subset F_2 \subset \cdots \subset F_n \subset \cdots$，则其极限事件为 $\displaystyle\lim_{n \to \infty} F_n = \bigcup_{n=1}^{\infty} F_n$
- **单调不增事件列**：若 $E_1 \supset E_2 \supset \cdots \supset E_n \supset \cdots$，则其极限事件为 $\displaystyle\lim_{n \to \infty} E_n = \bigcap_{n=1}^{\infty} E_n$

**概率的连续性**：

- **下连续**：若对任意单调不减集合序列 $\{F_n\}$，有 $P\!\left(\displaystyle\lim_{n \to \infty} F_n\right) = \displaystyle\lim_{n \to \infty} P(F_n)$
- **上连续**：若对任意单调不增集合序列 $\{E_n\}$，有 $P\!\left(\displaystyle\lim_{n \to \infty} E_n\right) = \displaystyle\lim_{n \to \infty} P(E_n)$

**定理**：若 $P$ 为事件域 $\mathcal{F}$ 上的概率，则 $P$ 既是下连续的，又是上连续的。

**定理**：若 $P$ 是 $\mathcal{F}$ 上满足 $P(\Omega)=1$ 的非负集合函数，则它具有可列可加性的充要条件是：

- 它是有限可加的
- 它是下连续的

## §1.6 条件概率

**定义**：设 $A$ 与 $B$ 是样本空间 $\Omega$ 中的两个事件，若 $P(B) > 0$，则称

$$
P(A|B) = \frac{P(AB)}{P(B)}
$$

为“在 $B$ 发生下 $A$ 的条件概率”，简称条件概率。

**性质**：条件概率是概率，即若 $P(B) > 0$，则

- **非负性**：$P(A|B) \geq 0, \quad \forall A \in \mathcal{F}$
- **正则性**：$P(\Omega|B) = 1$
- **可列可加性**：若 $A_1,A_2,\cdots,A_n,\cdots$ 互不相交，则

  $$
  P\!\left( \bigcup_{n=1}^{\infty} A_n \bigg| B \right) = \sum_{n=1}^{\infty} P(A_n|B)
  $$

**注**：条件概率满足概率的所有性质，如加法公式、减法公式等。

## §1.7 乘法公式

- 若 $P(B) > 0$，则

  $$
  P(AB) = P(B)P(A|B)
  $$

- 若 $P(A_1 A_2 \cdots A_{n-1}) > 0$，则

  $$
  P(A_1 A_2 \cdots A_n) = P(A_1)P(A_2|A_1)P(A_3|A_1 A_2)\cdots P(A_n|A_1 A_2 \cdots A_{n-1})
  $$

## §1.8 全概率公式

**定理**：设 $B_1,B_2,\cdots,B_n$ 为样本空间 $\Omega$ 的一个分割（即 $B_1,B_2,\cdots,B_n$ 互不相容且 $\bigcup_{i=1}^n B_i = \Omega$），如果 $P(B_i) > 0$，$i=1,2,\cdots,n$，则对任意事件 $A$ 有

$$
P(A) = \sum_{i=1}^{n} P(B_i)P(A|B_i)
$$

**注**：

- 若 $B_1,B_2,\cdots,B_n$ 互不相容且 $A \subset \bigcup_{i=1}^n B_i$，全概率公式仍然成立
- 对可列个事件 $B_1,B_2,\cdots$，全概率公式也成立

## §1.9 贝叶斯公式

**定理**：设 $B_1,B_2,\cdots,B_n$ 是样本空间 $\Omega$ 的一个分割，如果 $P(A) > 0$，$P(B_i) > 0$，$i=1,2,\cdots,n$，则

$$
P(B_i|A) = \frac{P(A|B_i)P(B_i)}{\displaystyle\sum_{j=1}^{n} P(A|B_j)P(B_j)}, \quad i=1,2,\cdots,n
$$

## §1.10 独立性

**定义（两个事件独立）**：如果 $P(AB) = P(A)P(B)$，则称事件 $A$ 与 $B$ 相互独立，简称 $A$ 与 $B$ 独立。否则称 $A$ 与 $B$ 不独立或相依。

**注**：

- 若 $P(A) > 0$，则 $P(AB) = P(A)P(B) \Leftrightarrow P(B|A) = P(B)$
- 独立与互不相容是两个完全不同的概念：
  - 若 $P(A) > 0$ 且 $P(B) > 0$，则独立与互不相容不能同时成立
  - 互不相容意味着 $AB = \varnothing$，而独立意味着 $P(AB) = P(A)P(B)$

**性质（对立事件的独立性）**：若 $A$ 与 $B$ 独立，则 $A$ 与 $\overline{B}$、$\overline{A}$ 与 $B$、$\overline{A}$ 与 $\overline{B}$ 也相互独立。

**定义（三个事件独立）**：设 $A,B,C$ 是三个事件，如果有

$$
\begin{cases}
P(AB) = P(A)P(B) \\
P(AC) = P(A)P(C) \\
P(BC) = P(B)P(C)
\end{cases}
$$

则称 $A,B,C$ **两两独立**。若还有 $P(ABC) = P(A)P(B)P(C)$，则称 $A,B,C$ **相互独立**。

**定义（$n$ 个事件独立）**：设有 $n$ 个事件 $A_1,A_2,\cdots,A_n$，对任意的 $1 \leq i_1 < i_2 < \cdots < i_k \leq n$（$k=2,3,\cdots,n$），都有

$$
P(A_{i_1} A_{i_2} \cdots A_{i_k}) = P(A_{i_1})P(A_{i_2})\cdots P(A_{i_k})
$$

则称 $A_1,A_2,\cdots,A_n$ 相互独立。

**注**：$n$ 个事件相互独立需要满足 $2^n - n - 1$ 个等式。

---

# 第二章 随机变量及其分布

## §2.1 随机变量及其分布函数

**定义（随机变量）**：定义在样本空间 $\Omega$ 上的实值函数 $X = X(\omega)$ 称为随机变量。

**定义（分布函数）**：设 $X$ 是一个随机变量，对任意实数 $x$，称

$$
F(x) = P(X \leq x)
$$

为随机变量 $X$ 的分布函数，且称 $X$ 服从 $F(x)$，记为 $X \sim F(x)$。

**定理（分布函数的性质）**：

1. **单调性**：单调不减，即 $\forall x_1 < x_2$，有 $F(x_1) \leq F(x_2)$
2. **有界性**：$\forall x \in \mathbb{R}$，$0 \leq F(x) \leq 1$，且

   $$
   F(-\infty) = \lim_{x \to -\infty} F(x) = 0, \quad F(+\infty) = \lim_{x \to +\infty} F(x) = 1
   $$

3. **右连续性**：$\forall x_0 \in \mathbb{R}$，$F(x_0 + 0) = \displaystyle\lim_{x \to x_0^+} F(x) = F(x_0)$

**注**：这三条性质是判别某个函数能否成为分布函数的充要条件。

## §2.2 离散型随机变量

**定义**：若随机变量 $X$ 的所有可能取值是有限个或可列个，则称 $X$ 为离散型随机变量。

**定义（分布列）**：设离散型随机变量 $X$ 的所有可能取值为 $x_1,x_2,\cdots,x_n,\cdots$，则称

$$
p_i = P(X = x_i), \quad i=1,2,\cdots
$$

为 $X$ 的概率分布列，简称分布列，记为 $X \sim \{p_i\}$。

**性质**：

- **非负性**：$p_i \geq 0, \quad i=1,2,\cdots$
- **正则性**：$\displaystyle\sum_{i=1}^{\infty} p_i = 1$

**分布函数与分布列的关系**：

$$
F(x) = \sum_{x_i \leq x} p_i
$$

## §2.3 连续型随机变量

**定义**：设随机变量 $X$ 的分布函数为 $F(x)$，如果存在实数轴上的一个非负可积函数 $p(x)$，使得对任意实数 $x$，有

$$
F(x) = \int_{-\infty}^{x} p(t)\,\mathrm{d}t
$$

则称 $p(x)$ 为 $X$ 的概率密度函数，简称密度函数。同时称 $X$ 为连续型随机变量。

**性质**：

- **非负性**：$p(x) \geq 0$
- **正则性**：$\displaystyle\int_{-\infty}^{+\infty} p(x)\,\mathrm{d}x = 1$
- 对任意实数 $a < b$，有 $P(a < X \leq b) = \displaystyle\int_{a}^{b} p(x)\,\mathrm{d}x$
- 在 $p(x)$ 的连续点处，有 $F'(x) = p(x)$

**注**：连续型随机变量取任意单点值的概率为 $0$，即 $P(X = a) = 0$。

## §2.4 随机变量的数学期望

**定义（离散型）**：设离散型随机变量 $X$ 的分布列为 $P(X = x_i) = p_i$，$i=1,2,\cdots$。如果

$$
\sum_{i=1}^{\infty} |x_i| p_i < \infty
$$

则称

$$
E(X) = \sum_{i=1}^{\infty} x_i p_i
$$

为随机变量 $X$ 的数学期望，简称期望或均值。若上述级数不绝对收敛，则称 $X$ 的数学期望不存在。

**定义（连续型）**：设连续型随机变量 $X$ 的密度函数为 $p(x)$。如果

$$
\int_{-\infty}^{+\infty} |x| p(x)\,\mathrm{d}x < \infty
$$

则称

$$
E(X) = \int_{-\infty}^{+\infty} x p(x)\,\mathrm{d}x
$$

为随机变量 $X$ 的数学期望。若上述积分不绝对收敛，则称 $X$ 的数学期望不存在。

**定理（随机变量函数的期望）**：若随机变量 $X$ 的分布用分布列 $p_i$ 或密度函数 $p(x)$ 表示，则 $X$ 的某一函数 $g(X)$ 的数学期望为

$$
E[g(X)] = \begin{cases}
\displaystyle\sum_{i} g(x_i) p_i, & \text{离散型} \\[12pt]
\displaystyle\int_{-\infty}^{+\infty} g(x) p(x)\,\mathrm{d}x, & \text{连续型}
\end{cases}
$$

要求上述级数或积分绝对收敛。

**性质**：

- 若 $c$ 是常数，则 $E(c) = c$
- 对任意常数 $a$，有 $E(aX) = aE(X)$
- 对任意的两个函数 $g_1(X)$ 和 $g_2(X)$，有

  $$
  E[g_1(X) \pm g_2(X)] = E[g_1(X)] \pm E[g_2(X)]
  $$

- 推论：$E(aX + b) = aE(X) + b$

## §2.5 随机变量的方差与标准差

**定义**：若随机变量 $X^2$ 的数学期望 $E(X^2)$ 存在，则称偏差平方 $(X-E(X))^2$ 的数学期望

$$
\operatorname{Var}(X) = E\bigl[(X - E(X))^2\bigr]
$$

为随机变量 $X$（或相应分布）的方差。称 $\sqrt{\operatorname{Var}(X)}$ 为随机变量 $X$ 的标准差，记为 $\sigma(X)$。

**计算公式**：

$$
\operatorname{Var}(X) = E(X^2) - [E(X)]^2
$$

**性质**：

- 常数的方差为 $0$，即 $\operatorname{Var}(c) = 0$，其中 $c$ 是常数
- 若 $a,b$ 是常数，则 $\operatorname{Var}(aX + b) = a^2 \operatorname{Var}(X)$

**定义（中心化与标准化）**：

- **中心化**：$X' = X - E(X)$
- **标准化**：$X^* = \dfrac{X - E(X)}{\sqrt{\operatorname{Var}(X)}}$

  **注**：标准化可以去除量纲的影响。

**定理（切比雪夫不等式）**：设随机变量 $X$ 的数学期望和方差均存在，则对任意常数 $\varepsilon > 0$，有

$$
P\bigl(|X - E(X)| \geq \varepsilon\bigr) \leq \frac{\operatorname{Var}(X)}{\varepsilon^2}
$$

或等价地

$$
P\bigl(|X - E(X)| < \varepsilon\bigr) \geq 1 - \frac{\operatorname{Var}(X)}{\varepsilon^2}
$$

## §2.6 常用离散分布

### 一、二项分布 $X \sim b(n,p)$

- **背景**：$n$ 重伯努利试验中成功的次数
- **分布列**：

  $$
  P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}, \quad k=0,1,\cdots,n
  $$

- **期望**：$E(X) = np$
- **方差**：$\operatorname{Var}(X) = np(1-p)$

### 二、二点分布（0-1 分布）

- **背景**：一次伯努利试验的结果
- **分布列**：

  $$
  P(X = x) = p^x (1-p)^{1-x}, \quad x=0,1
  $$

- **期望**：$E(X) = p$
- **方差**：$\operatorname{Var}(X) = p(1-p)$

**注**：二点分布是 $n=1$ 时的二项分布。

### 三、泊松分布 $X \sim P(\lambda)$（或 $\operatorname{Poisson}(\lambda)$）

- **背景**：单位时间（或单位面积）内稀有事件发生的次数
- **分布列**：

  $$
  P(X = k) = \frac{\lambda^k}{k!} e^{-\lambda}, \quad k=0,1,2,\cdots
  $$

- **期望**：$E(X) = \lambda$
- **方差**：$\operatorname{Var}(X) = \lambda$

**定理（泊松定理）**：在 $n$ 重伯努利试验中，记事件 $A$ 在一次试验中发生的概率为 $p_n$。如果当 $n \to \infty$ 时，有 $np_n \to \lambda$（$\lambda > 0$ 为常数），则

$$
\lim_{n \to \infty} \binom{n}{k} p_n^k (1-p_n)^{n-k} = \frac{\lambda^k}{k!} e^{-\lambda}
$$

**注**：二项分布 $b(n,p)$ 当 $n$ 很大、$p$ 很小且 $np$ 适中时，可以用泊松分布近似。

### 四、几何分布 $X \sim \operatorname{Ge}(p)$

- **背景**：首次成功所需的试验次数
- **分布列**：

  $$
  P(X = k) = p(1-p)^{k-1}, \quad k=1,2,\cdots
  $$

- **期望**：$E(X) = \dfrac{1}{p}$
- **方差**：$\operatorname{Var}(X) = \dfrac{1-p}{p^2}$

**性质（无记忆性）**：对任意正整数 $m,n$，有

$$
P(X > m+n \mid X > m) = P(X > n)
$$

**注**：几何分布是唯一具有无记忆性的离散型分布。

### 五、负二项分布 $X \sim \operatorname{Nb}(r,p)$

- **背景**：第 $r$ 次成功所需的试验次数
- **分布列**：

  $$
  P(X = k) = \binom{k-1}{r-1} p^r (1-p)^{k-r}, \quad k=r,r+1,\cdots
  $$

- **期望**：$E(X) = \dfrac{r}{p}$
- **方差**：$\operatorname{Var}(X) = \dfrac{r(1-p)}{p^2}$

**与几何分布的关系**：若 $X_1,X_2,\cdots,X_r$ 独立同分布，且 $X_i \sim \operatorname{Ge}(p)$，则

$$
X = X_1 + X_2 + \cdots + X_r \sim \operatorname{Nb}(r,p)
$$

### 六、超几何分布 $X \sim h(n,N,M)$

- **背景**：不放回抽样中次品的个数
- **分布列**：

  $$
  P(X = k) = \frac{\binom{M}{k} \binom{N-M}{n-k}}{\binom{N}{n}}, \quad k=0,1,\cdots,\min\{M,n\}
  $$

- **期望**：$E(X) = n \cdot \dfrac{M}{N}$
- **方差**：$\operatorname{Var}(X) = n \cdot \dfrac{M}{N} \cdot \dfrac{N-M}{N} \cdot \dfrac{N-n}{N-1}$

**二项近似**：当 $n \ll N$ 时，不放回抽样可以近似为放回抽样，超几何分布 $h(n,N,M)$ 可以用二项分布 $b\!\left(n, \dfrac{M}{N}\right)$ 近似。

### §2.7 常用连续分布

#### 一、均匀分布 $X\sim U(a,b)$

- **背景**：在区间 $(a,b)$ 上随机取值，每个点的可能性相同
- **密度函数**：

  $$
  p(x)=\begin{cases}
  \dfrac{1}{b-a}, & a<x<b \\[6pt]
  0, & \text{其他}
  \end{cases}
  $$

- **分布函数**：

  $$
  F(x)=\begin{cases}
  0, & x<a \\[6pt]
  \dfrac{x-a}{b-a}, & a\le x<b \\[6pt]
  1, & x\ge b
  \end{cases}
  $$

- **期望**：$E(X)=\dfrac{a+b}{2}$
- **方差**：$\operatorname{Var}(X)=\dfrac{(b-a)^2}{12}$

#### 二、指数分布 $X\sim \operatorname{Exp}(\lambda)$

- **背景**：独立事件发生的时间间隔（如设备寿命、等待时间）
- **密度函数**：

  $$
  p(x)=\begin{cases}
  \lambda e^{-\lambda x}, & x\ge 0 \\
  0, & x<0
  \end{cases}\qquad(\lambda>0)
  $$

- **分布函数**：

  $$
  F(x)=\begin{cases}
  1-e^{-\lambda x}, & x\ge 0 \\
  0, & x<0
  \end{cases}
  $$

- **可靠度函数**：$R(t)=P(X>t)=1-F(t)=e^{-\lambda t},\;t>0$
- **期望**：$E(X)=\dfrac{1}{\lambda}$
- **方差**：$\operatorname{Var}(X)=\dfrac{1}{\lambda^2}$

**性质（无记忆性）**：对任意 $s,t>0$，有

$$
P(X>s+t \mid X>s)=P(X>t)
$$

> 注：指数分布是唯一具有无记忆性的连续型分布。

#### 三、正态分布 $X\sim N(\mu,\sigma^2)$

- **背景**：大量独立随机因素共同作用的结果（中心极限定理）
- **密度函数**：

  $$
  p(x)=\frac{1}{\sqrt{2\pi}\,\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}},\quad x\in\mathbb{R}
  $$

  其中 $\mu\in\mathbb{R}$ 为位置参数，$\sigma>0$ 为尺度参数。

- **图形特征**：
  1. 关于 $x=\mu$ 对称，即 $\forall h>0$，有 $p(\mu-h)=p(\mu+h)$
  2. 在 $x=\mu$ 处取得最大值 $\dfrac{1}{\sqrt{2\pi}\,\sigma}$
  3. $\sigma$ 越大，曲线越平缓；$\sigma$ 越小，曲线越陡峭

- **分布函数**：

  $$
  F(x)=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}\,\sigma}e^{-\frac{(t-\mu)^2}{2\sigma^2}}\,\mathrm{d}t
  $$

**标准正态分布**：当 $\mu=0,\sigma=1$ 时，称 $X$ 服从标准正态分布，记为 $X\sim N(0,1)$，其密度函数和分布函数分别记为 $\varphi(x)$ 和 $\Phi(x)$：

$$
\varphi(x)=\frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}},\qquad
\Phi(x)=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-\frac{t^2}{2}}\,\mathrm{d}t
$$

**性质**：

1. 对称性：$\Phi(-x)=1-\Phi(x)$
2. $\Phi(0)=0.5$

**标准化定理**：若 $X\sim N(\mu,\sigma^2)$，则

$$
Z=\frac{X-\mu}{\sigma}\sim N(0,1)
$$

且

$$
F(x)=\Phi\!\left(\frac{x-\mu}{\sigma}\right)
$$

- **期望**：$E(X)=\mu$
- **方差**：$\operatorname{Var}(X)=\sigma^2$

#### 四、伽马分布 $X\sim \operatorname{Ga}(\alpha,\lambda)$

- **背景**：$n$ 个独立同分布指数分布随机变量的和
- **伽马函数定义**：

  $$
  \Gamma(\alpha)=\int_{0}^{+\infty}x^{\alpha-1}e^{-x}\,\mathrm{d}x,\quad\alpha>0
  $$

  性质：$\Gamma(\alpha+1)=\alpha\Gamma(\alpha)$，$\Gamma(n)=(n-1)!$，$\Gamma(1/2)=\sqrt{\pi}$

- **密度函数**：

  $$
  p(x)=\begin{cases}
  \dfrac{\lambda^{\alpha}}{\Gamma(\alpha)}x^{\alpha-1}e^{-\lambda x}, & x\ge 0 \\[8pt]
  0, & x<0
  \end{cases}\qquad(\alpha>0,\lambda>0)
  $$

- **特殊情况**：
  1. $\operatorname{Ga}(1,\lambda)=\operatorname{Exp}(\lambda)$
  2. $\operatorname{Ga}(n/2,1/2)=\chi^2(n)$（自由度为 $n$ 的卡方分布）

- **期望**：$E(X)=\dfrac{\alpha}{\lambda}$
- **方差**：$\operatorname{Var}(X)=\dfrac{\alpha}{\lambda^2}$

#### 五、贝塔分布 $X\sim \operatorname{Be}(a,b)$

- **背景**：取值在 $(0,1)$ 区间的随机变量（如比例、概率）
- **贝塔函数定义**：

  $$
  B(a,b)=\int_{0}^{1}x^{a-1}(1-x)^{b-1}\,\mathrm{d}x,\quad a>0,b>0
  $$

  性质：$B(a,b)=B(b,a)$，$B(a,b)=\dfrac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}$

- **密度函数**：

  $$
  p(x)=\begin{cases}
  \dfrac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)}x^{a-1}(1-x)^{b-1}, & 0<x<1 \\[8pt]
  0, & \text{其他}
  \end{cases}
  $$

- **特殊情况**：$\operatorname{Be}(1,1)=U(0,1)$
- **期望**：$E(X)=\dfrac{a}{a+b}$
- **方差**：$\operatorname{Var}(X)=\dfrac{ab}{(a+b)^2(a+b+1)}$

---

### §2.8 随机变量函数的分布

#### 一、离散型随机变量函数的分布

设离散型随机变量 $X$ 的分布列为

$$
P(X=x_i)=p_i,\quad i=1,2,\cdots
$$

则 $Y=g(X)$ 也是离散型随机变量，其分布列为

$$
P(Y=y_j)=\sum_{i:\,g(x_i)=y_j} p_i,\quad j=1,2,\cdots
$$

> 注：当 $g(x_i)$ 有重复值时，将对应概率相加。

#### 二、连续型随机变量函数的分布

**定理（严格单调函数）**：设 $X$ 是连续型随机变量，其密度函数为 $p_X(x)$。若 $y=g(x)$ 是严格单调可微函数，其反函数 $x=h(y)$ 有连续导数，则 $Y=g(X)$ 的密度函数为

$$
p_Y(y)=\begin{cases}
p_X\!\bigl(h(y)\bigr)\cdot |h'(y)|, & y\in I \\
0, & \text{其他}
\end{cases}
$$

其中 $I$ 是 $g(x)$ 的值域。

**重要推论**：

1. **一维正态分布的线性不变性**：若 $X\sim N(\mu,\sigma^2)$，则对任意常数 $a\neq 0,b$，有

   $$
   Y=aX+b\sim N(a\mu+b,\,a^2\sigma^2)
   $$

2. **对数正态分布**：若 $X\sim N(\mu,\sigma^2)$，则 $Y=e^X$ 服从对数正态分布，其密度函数为

   $$
   p_Y(y)=\begin{cases}
   \dfrac{1}{\sqrt{2\pi}\,\sigma y}\,e^{-\frac{(\ln y-\mu)^2}{2\sigma^2}}, & y>0 \\[8pt]
   0, & y\le 0
   \end{cases}
   $$

3. **伽马分布的尺度变换**：若 $X\sim \operatorname{Ga}(\alpha,\lambda)$，则对任意常数 $k>0$，有

   $$
   Y=kX\sim \operatorname{Ga}\!\left(\alpha,\frac{\lambda}{k}\right)
   $$

4. **均匀分布的性质**：若随机变量 $X$ 的分布函数 $F(x)$ 是严格单调的连续函数，则

   $$
   Y=F(X)\sim U(0,1)
   $$

---

### §2.9 分布的其他特征数

#### 一、矩

**定义（$k$ 阶原点矩）**：设 $X$ 为随机变量，$k$ 为正整数，若 $E(X^k)$ 存在，则称

$$
\mu_k = E(X^k)
$$

为 $X$ 的 $k$ 阶原点矩。

**定义（$k$ 阶中心矩）**：设 $X$ 为随机变量，$k$ 为正整数，若 $E[(X-E(X))^k]$ 存在，则称

$$
v_k = E\bigl[(X-E(X))^k\bigr]
$$

为 $X$ 的 $k$ 阶中心矩。

> 注：
> 
> - $1$ 阶原点矩 $\mu_1=E(X)$ 是数学期望
> - $2$ 阶中心矩 $v_2=\operatorname{Var}(X)$ 是方差

#### 二、变异系数

**定义**：设随机变量 $X$ 的二阶矩存在，且 $E(X)\neq 0$，则称

$$
C_v(X)=\frac{\sqrt{\operatorname{Var}(X)}}{|E(X)|}=\frac{\sigma(X)}{|E(X)|}
$$

为 $X$ 的变异系数。

> 注：变异系数是无量纲的量，用于比较不同量纲或均值差异较大的随机变量的离散程度。

#### 三、分位数

**定义（下侧 $p$ 分位数）**：设 $0<p<1$，若实数 $x_p$ 满足

$$
F(x_p)=P(X\le x_p)=p
$$

则称 $x_p$ 为 $X$ 的下侧 $p$ 分位数，简称 $p$ 分位数。

**定义（上侧 $p$ 分位数）**：设 $0<p<1$，若实数 $x_{1-p}$ 满足

$$
P(X\ge x_{1-p})=1-F(x_{1-p})=p
$$

则称 $x_{1-p}$ 为 $X$ 的上侧 $p$ 分位数。

> 注：中位数是 $p=0.5$ 时的分位数，记为 $x_{0.5}$。

#### 四、偏度系数

**定义**：设随机变量 $X$ 的前三阶矩存在，则称

$$
\beta_s = \frac{v_3}{v_2^{3/2}} = \frac{E\bigl[(X-E(X))^3\bigr]}{\bigl[\operatorname{Var}(X)\bigr]^{3/2}}
$$

为 $X$ 的偏度系数，简称偏度。

**意义**：

- $\beta_s=0$：分布关于均值对称
- $\beta_s>0$：分布正偏（右偏），长尾在右侧
- $\beta_s<0$：分布负偏（左偏），长尾在左侧

#### 五、峰度系数

**定义**：设随机变量 $X$ 的前四阶矩存在，则称

$$
\beta_k = \frac{v_4}{v_2^2} - 3 = \frac{E\bigl[(X-E(X))^4\bigr]}{\bigl[\operatorname{Var}(X)\bigr]^2} - 3
$$

为 $X$ 的峰度系数，简称峰度。

**意义**：

- 以标准正态分布为基准（$\beta_k=0$）
- $\beta_k>0$：分布比正态分布更尖峭，尾部更厚
- $\beta_k<0$：分布比正态分布更平缓，尾部更薄

> 注：标准正态分布的四阶矩 $E(Z^4)=3$，因此峰度系数减去 $3$。

# 第三章 多维随机变量及其分布

## §3.1 多维随机变量及其联合分布

**定义（$n$ 维随机变量）**：设 $\Omega$ 为样本空间，$X_1,X_2,\cdots,X_n$ 是定义在 $\Omega$ 上的 $n$ 个随机变量，则称向量 $(X_1,X_2,\cdots,X_n)$ 为 $n$ 维随机变量或 $n$ 维随机向量。

**定义（联合分布函数）**：对任意 $n$ 个实数 $x_1,x_2,\cdots,x_n$，称

$$
F(x_1,x_2,\cdots,x_n) = P(X_1 \le x_1,\, X_2 \le x_2,\cdots,\, X_n \le x_n)
$$

为 $n$ 维随机变量 $(X_1,X_2,\cdots,X_n)$ 的联合分布函数。

**性质**：

1. **单调性**：对每个变量单调不减
2. **有界性**：$0 \le F(x_1,x_2,\cdots,x_n) \le 1$，且

   $$
   F(-\infty,-\infty,\cdots,-\infty)=0,\qquad F(+\infty,+\infty,\cdots,+\infty)=1
   $$

3. **右连续性**：对每个变量右连续
4. **非负性（二增性）**：对任意 $a_i < b_i$（$i=1,2,\cdots,n$），有

   $$
   P(a_1 < X_1 \le b_1,\cdots, a_n < X_n \le b_n) \ge 0
   $$

---

## §3.2 二维离散型随机变量

**定义**：若二维随机变量 $(X,Y)$ 的所有可能取值是有限个或可列个数对，则称 $(X,Y)$ 为二维离散型随机变量。

**定义（联合分布列）**：设 $(X,Y)$ 的所有可能取值为 $(x_i,y_j)$，$i,j=1,2,\cdots$，则称

$$
p_{ij} = P(X=x_i,\, Y=y_j),\quad i,j=1,2,\cdots
$$

为 $(X,Y)$ 的联合分布列。

**性质**：

1. **非负性**：$p_{ij} \ge 0$
2. **正则性**：$\displaystyle\sum_{i=1}^{\infty}\sum_{j=1}^{\infty} p_{ij} = 1$

**边缘分布列**：

- $X$ 的边缘分布列：$p_{i\cdot} = P(X=x_i) = \displaystyle\sum_{j=1}^{\infty} p_{ij},\quad i=1,2,\cdots$
- $Y$ 的边缘分布列：$p_{\cdot j} = P(Y=y_j) = \displaystyle\sum_{i=1}^{\infty} p_{ij},\quad j=1,2,\cdots$

---

## §3.3 二维连续型随机变量

**定义**：设二维随机变量 $(X,Y)$ 的联合分布函数为 $F(x,y)$，如果存在非负可积函数 $p(x,y)$，使得对任意实数 $x,y$，有

$$
F(x,y) = \int_{-\infty}^{x}\int_{-\infty}^{y} p(u,v)\,\mathrm{d}u\mathrm{d}v
$$

则称 $(X,Y)$ 为二维连续型随机变量，称 $p(x,y)$ 为联合概率密度函数。

**性质**：

1. **非负性**：$p(x,y) \ge 0$
2. **正则性**：$\displaystyle\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty} p(x,y)\,\mathrm{d}x\mathrm{d}y = 1$
3. 在 $p(x,y)$ 的连续点处，有 $\dfrac{\partial^2 F(x,y)}{\partial x\partial y} = p(x,y)$
4. 对任意平面区域 $G$，有 $P\bigl((X,Y)\in G\bigr) = \displaystyle\iint_{G} p(x,y)\,\mathrm{d}x\mathrm{d}y$

**边缘密度函数**：

- $X$ 的边缘密度函数：$p_X(x) = \displaystyle\int_{-\infty}^{+\infty} p(x,y)\,\mathrm{d}y$
- $Y$ 的边缘密度函数：$p_Y(y) = \displaystyle\int_{-\infty}^{+\infty} p(x,y)\,\mathrm{d}x$

---

## §3.4 常用多维分布

### 一、二维均匀分布

设 $D$ 是平面上的有界区域，面积为 $A$，若 $(X,Y)$ 的联合密度函数为

$$
p(x,y) = \begin{cases}
\dfrac{1}{A}, & (x,y) \in D \\[6pt]
0, & \text{其他}
\end{cases}
$$

则称 $(X,Y)$ 服从区域 $D$ 上的二维均匀分布。

### 二、二维正态分布 $(X,Y) \sim N(\mu_1,\mu_2,\sigma_1^2,\sigma_2^2,\rho)$

联合密度函数为：

$$
p(x,y) = \frac{1}{2\pi\sigma_1\sigma_2\sqrt{1-\rho^2}} \exp\!\left\{ -\frac{1}{2(1-\rho^2)} \left[ \frac{(x-\mu_1)^2}{\sigma_1^2} - 2\rho\frac{(x-\mu_1)(y-\mu_2)}{\sigma_1\sigma_2} + \frac{(y-\mu_2)^2}{\sigma_2^2} \right] \right\}
$$

其中 $\mu_1,\mu_2 \in \mathbb{R}$，$\sigma_1,\sigma_2 > 0$，$-1 < \rho < 1$。

**性质**：

1. 边缘分布：$X \sim N(\mu_1,\sigma_1^2)$，$Y \sim N(\mu_2,\sigma_2^2)$
2. 相关系数：$\rho_{XY} = \rho$
3. 独立与不相关等价：$X$ 与 $Y$ 独立 $\Leftrightarrow$ $X$ 与 $Y$ 不相关（$\rho = 0$）

---

## §3.5 随机变量的独立性

**定义**：设 $n$ 维随机变量 $(X_1,X_2,\cdots,X_n)$ 的联合分布函数为 $F(x_1,x_2,\cdots,x_n)$，边缘分布函数为 $F_i(x_i)$（$i=1,2,\cdots,n$）。如果对任意实数 $x_1,x_2,\cdots,x_n$，有

$$
F(x_1,x_2,\cdots,x_n) = \prod_{i=1}^{n} F_i(x_i)
$$

则称 $X_1,X_2,\cdots,X_n$ 相互独立。

- **离散型**：$X$ 与 $Y$ 独立 $\Leftrightarrow$ 对所有 $i,j$，有 $p_{ij} = p_{i\cdot}\,p_{\cdot j}$
- **连续型**：$X$ 与 $Y$ 独立 $\Leftrightarrow$ 几乎处处有 $p(x,y) = p_X(x)\,p_Y(y)$

**性质**：若 $X_1,X_2,\cdots,X_n$ 相互独立，则

1. 它们的函数 $g_1(X_1),g_2(X_2),\cdots,g_n(X_n)$ 也相互独立
2. 联合分布由边缘分布唯一确定

---

## §3.6 多维随机变量函数的分布

### 一、离散型

设 $(X,Y)$ 是二维离散型随机变量，联合分布列为 $p_{ij}$，则 $Z = g(X,Y)$ 的分布列为

$$
P(Z = z_k) = \sum_{(i,j):\,g(x_i,y_j)=z_k} p_{ij},\quad k=1,2,\cdots
$$

**可加性**：

1. **二项分布**：若 $X \sim b(n,p)$，$Y \sim b(m,p)$，且 $X$ 与 $Y$ 独立，则 $X+Y \sim b(n+m,p)$
2. **泊松分布**：若 $X \sim P(\lambda_1)$，$Y \sim P(\lambda_2)$，且 $X$ 与 $Y$ 独立，则 $X+Y \sim P(\lambda_1+\lambda_2)$

### 二、连续型

1. **最大值与最小值分布**

   设 $X,Y$ 独立，分布函数分别为 $F_X(x),F_Y(y)$，则

   - $M = \max\{X,Y\}$ 的分布函数：$F_M(z) = F_X(z)F_Y(z)$
   - $N = \min\{X,Y\}$ 的分布函数：$F_N(z) = 1 - \bigl(1-F_X(z)\bigr)\bigl(1-F_Y(z)\bigr)$

2. **和的分布（卷积公式）**

   设 $X,Y$ 独立，密度函数分别为 $p_X(x),p_Y(y)$，则 $Z = X+Y$ 的密度函数为

   $$
   p_Z(z) = \int_{-\infty}^{+\infty} p_X(x)\,p_Y(z-x)\,\mathrm{d}x = \int_{-\infty}^{+\infty} p_X(z-y)\,p_Y(y)\,\mathrm{d}y
   $$

**可加性**：

1. **正态分布**：若 $X \sim N(\mu_1,\sigma_1^2)$，$Y \sim N(\mu_2,\sigma_2^2)$，且 $X$ 与 $Y$ 独立，则 $X+Y \sim N(\mu_1+\mu_2,\,\sigma_1^2+\sigma_2^2)$
2. **伽马分布**：若 $X \sim \operatorname{Ga}(\alpha_1,\lambda)$，$Y \sim \operatorname{Ga}(\alpha_2,\lambda)$，且 $X$ 与 $Y$ 独立，则 $X+Y \sim \operatorname{Ga}(\alpha_1+\alpha_2,\lambda)$

3. **变量变换法**

   设二维随机变量 $(X,Y)$ 的联合密度函数为 $p_{X,Y}(x,y)$，变换

   $$
   \begin{cases}
   u = g_1(x,y)\\
   v = g_2(x,y)
   \end{cases}
   $$

   有连续偏导数，且存在唯一反函数

   $$
   \begin{cases}
   x = x(u,v)\\
   y = y(u,v)
   \end{cases}
   $$

   雅可比行列式 $J = \det\dfrac{\partial(x,y)}{\partial(u,v)} \neq 0$，则 $(U,V)$ 的联合密度函数为

   $$
   p_{U,V}(u,v) = p_{X,Y}\!\bigl(x(u,v),y(u,v)\bigr) \cdot |J|
   $$

**常用公式**：

- 积的分布：$Z = XY$，$p_Z(z) = \displaystyle\int_{-\infty}^{+\infty} p_X\!\left(\frac{z}{v}\right)p_Y(v)\,\frac{1}{|v|}\,\mathrm{d}v$
- 商的分布：$Z = \dfrac{X}{Y}$，$p_Z(z) = \displaystyle\int_{-\infty}^{+\infty} p_X(zv)\,p_Y(v)\,|v|\,\mathrm{d}v$

---

# 第四章 多维随机变量的特征数

## §4.1 多维随机变量函数的数学期望

**定理**：设 $(X,Y)$ 是二维随机变量，$g(X,Y)$ 是二元函数，则

- **离散型**：$E[g(X,Y)] = \displaystyle\sum_{i=1}^{\infty}\sum_{j=1}^{\infty} g(x_i,y_j)\,p_{ij}$
- **连续型**：$E[g(X,Y)] = \displaystyle\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty} g(x,y)\,p(x,y)\,\mathrm{d}x\mathrm{d}y$

要求上述级数或积分绝对收敛。

---

## §4.2 数学期望与方差的性质

1. **加法法则**：

   $$
   E\!\left(\sum_{k=1}^{n} X_k\right) = \sum_{k=1}^{n} E(X_k)
   $$

   $$
   \operatorname{Var}\!\left(\sum_{k=1}^{n} X_k\right) = \sum_{k=1}^{n} \operatorname{Var}(X_k) + 2\sum_{1 \le i < j \le n} \operatorname{Cov}(X_i,X_j)
   $$

   若 $X_1,X_2,\cdots,X_n$ 相互独立，则

   $$
   \operatorname{Var}\!\left(\sum_{k=1}^{n} X_k\right) = \sum_{k=1}^{n} \operatorname{Var}(X_k)
   $$

2. **乘法法则**：若 $X_1,X_2,\cdots,X_n$ 相互独立，则

   $$
   E\!\left(\prod_{k=1}^{n} X_k\right) = \prod_{k=1}^{n} E(X_k)
   $$

3. **柯西-施瓦茨不等式**：

   $$
   \bigl[E(XY)\bigr]^2 \le E(X^2)E(Y^2)
   $$

   等号成立当且仅当存在常数 $a,b$，使得 $P(Y = aX + b) = 1$。

---

## §4.3 协方差与相关系数

**定义（协方差）**：设 $(X,Y)$ 是二维随机变量，若 $E\bigl[(X-E(X))(Y-E(Y))\bigr]$ 存在，则称

$$
\operatorname{Cov}(X,Y) = E\bigl[(X-E(X))(Y-E(Y))\bigr]
$$

为 $X$ 与 $Y$ 的协方差。

**计算公式**：

$$
\operatorname{Cov}(X,Y) = E(XY) - E(X)E(Y)
$$

**性质**：

1. $\operatorname{Cov}(X,Y) = \operatorname{Cov}(Y,X)$
2. $\operatorname{Cov}(aX,bY) = ab\operatorname{Cov}(X,Y)$
3. $\operatorname{Cov}(X_1+X_2,Y) = \operatorname{Cov}(X_1,Y) + \operatorname{Cov}(X_2,Y)$
4. $|\operatorname{Cov}(X,Y)| \le \sqrt{\operatorname{Var}(X)} \cdot \sqrt{\operatorname{Var}(Y)}$
5. 若 $X$ 与 $Y$ 独立，则 $\operatorname{Cov}(X,Y) = 0$

**定义（相关系数）**：设 $\operatorname{Var}(X) > 0$，$\operatorname{Var}(Y) > 0$，则称

$$
\rho_{XY} = \frac{\operatorname{Cov}(X,Y)}{\sqrt{\operatorname{Var}(X)}\sqrt{\operatorname{Var}(Y)}}
$$

为 $X$ 与 $Y$ 的（线性）相关系数。

**性质**：

1. $|\rho_{XY}| \le 1$
2. $|\rho_{XY}| = 1 \Leftrightarrow$ 存在常数 $a,b$，使得 $P(Y = aX + b) = 1$
3. 若 $X$ 与 $Y$ 独立，则 $\rho_{XY} = 0$（不相关）

> **注**：独立一定不相关，但不相关不一定独立。只有二维正态分布是例外。

---

## §4.4 协方差矩阵

**定义**：设 $n$ 维随机变量 $\boldsymbol{X} = (X_1,X_2,\cdots,X_n)^{\mathrm{T}}$，记

$$
\sigma_{ij} = \operatorname{Cov}(X_i,X_j),\quad i,j = 1,2,\cdots,n
$$

则称矩阵

$$
\operatorname{Cov}(\boldsymbol{X}) = \begin{pmatrix}
\sigma_{11} & \sigma_{12} & \cdots & \sigma_{1n} \\
\sigma_{21} & \sigma_{22} & \cdots & \sigma_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
\sigma_{n1} & \sigma_{n2} & \cdots & \sigma_{nn}
\end{pmatrix}
$$

为 $\boldsymbol{X}$ 的协方差矩阵。

**性质**：协方差矩阵是对称非负定矩阵。

---

## §4.5 $n$ 维正态分布

**定义**：若 $n$ 维随机变量 $\boldsymbol{X} = (X_1,X_2,\cdots,X_n)^{\mathrm{T}}$ 的联合密度函数为

$$
p(\boldsymbol{x}) = \frac{1}{(2\pi)^{n/2}|\Sigma|^{1/2}} \exp\!\left\{ -\frac{1}{2}(\boldsymbol{x}-\boldsymbol{\mu})^{\mathrm{T}}\Sigma^{-1}(\boldsymbol{x}-\boldsymbol{\mu}) \right\}
$$

其中 $\boldsymbol{\mu} = (\mu_1,\mu_2,\cdots,\mu_n)^{\mathrm{T}}$ 是均值向量，$\Sigma$ 是 $n$ 阶正定协方差矩阵，则称 $\boldsymbol{X}$ 服从 $n$ 维正态分布，记为 $\boldsymbol{X} \sim N(\boldsymbol{\mu},\Sigma)$。

**性质**：

1. $\boldsymbol{X}$ 的任意线性组合仍服从正态分布
2. $\boldsymbol{X}$ 的任意子向量仍服从正态分布
3. $X_1,X_2,\cdots,X_n$ 相互独立 $\Leftrightarrow$ 两两不相关 $\Leftrightarrow$ $\Sigma$ 是对角矩阵

---

# 第五章 条件分布与条件期望

## §5.1 条件分布

### 一、离散型

设 $(X,Y)$ 是二维离散型随机变量，对固定的 $j$，若 $p_{\cdot j} = P(Y = y_j) > 0$，则称

$$
P(X = x_i \mid Y = y_j) = \frac{p_{ij}}{p_{\cdot j}},\quad i = 1,2,\cdots
$$

为在 $Y = y_j$ 条件下 $X$ 的条件分布列。

### 二、连续型

设 $(X,Y)$ 是二维连续型随机变量，对固定的 $y$，若 $p_Y(y) > 0$，则称

$$
p_{X|Y}(x|y) = \frac{p(x,y)}{p_Y(y)}
$$

为在 $Y = y$ 条件下 $X$ 的条件密度函数。

**全概率公式（密度形式）**：

$$
p_X(x) = \int_{-\infty}^{+\infty} p_Y(y)\,p_{X|Y}(x|y)\,\mathrm{d}y
$$

**贝叶斯公式（密度形式）**：

$$
p_{Y|X}(y|x) = \frac{p_Y(y)\,p_{X|Y}(x|y)}{\displaystyle\int_{-\infty}^{+\infty} p_Y(y)\,p_{X|Y}(x|y)\,\mathrm{d}y}
$$

---

## §5.2 条件期望

**定义**：

- **离散型**：$E(X \mid Y = y_j) = \displaystyle\sum_{i=1}^{\infty} x_i\,P(X = x_i \mid Y = y_j)$
- **连续型**：$E(X \mid Y = y) = \displaystyle\int_{-\infty}^{+\infty} x\,p_{X|Y}(x|y)\,\mathrm{d}x$

**性质**：

1. 若 $X$ 与 $Y$ 独立，则 $E(X \mid Y) = E(X)$
2. **重期望公式**：$E(X) = E\bigl[E(X \mid Y)\bigr]$
3. $E\bigl(g(Y)X \mid Y\bigr) = g(Y)E(X \mid Y)$
4. $E\bigl(g(Y)X\bigr) = E\bigl[g(Y)E(X \mid Y)\bigr]$
5. $E(c \mid Y) = c$（$c$ 为常数）
6. $E\bigl(g(Y) \mid Y\bigr) = g(Y)$
7. $E(aX + bY \mid Z) = aE(X \mid Z) + bE(Y \mid Z)$
8. 对任意函数 $g$，有 $E\!\left\{ \bigl[X - E(X \mid Y)\bigr]^2 \right\} \le E\!\left\{ \bigl[X - g(Y)\bigr]^2 \right\}$

---

# 第六章 大数定律与中心极限定理

## §6.1 随机变量序列的两种收敛性

### 一、依概率收敛

**定义**：设 $\{X_n\}$ 是随机变量序列，$X$ 是随机变量。若对任意 $\varepsilon > 0$，有

$$
\lim_{n \to \infty} P\bigl(|X_n - X| < \varepsilon\bigr) = 1
$$

则称 $\{X_n\}$ 依概率收敛于 $X$，记为 $X_n \xrightarrow{P} X$。

**性质**：若 $X_n \xrightarrow{P} a$，$Y_n \xrightarrow{P} b$，则

1. $X_n \pm Y_n \xrightarrow{P} a \pm b$
2. $X_n Y_n \xrightarrow{P} ab$
3. $X_n / Y_n \xrightarrow{P} a/b$（$b \neq 0$）

### 二、依分布收敛

**定义**：设 $\{X_n\}$ 的分布函数为 $F_n(x)$，$X$ 的分布函数为 $F(x)$。若在 $F(x)$ 的所有连续点 $x$ 处，有

$$
\lim_{n \to \infty} F_n(x) = F(x)
$$

则称 $\{X_n\}$ 依分布收敛于 $X$，记为 $X_n \xrightarrow{L} X$。

**关系**：$X_n \xrightarrow{P} X \Rightarrow X_n \xrightarrow{L} X$；反之不成立。

> **注**：若 $X$ 是常数 $a$，则 $X_n \xrightarrow{P} a \Leftrightarrow X_n \xrightarrow{L} a$。

---

## §6.2 特征函数

**定义**：设 $X$ 是随机变量，称

$$
\varphi(t) = E(e^{itX}),\quad t \in \mathbb{R}
$$

为 $X$ 的特征函数。

**性质**：

1. $|\varphi(t)| \le \varphi(0) = 1$
2. $\varphi(-t) = \overline{\varphi(t)}$（共轭）
3. $\varphi_{aX+b}(t) = e^{ibt}\varphi(at)$
4. 若 $X$ 与 $Y$ 独立，则 $\varphi_{X+Y}(t) = \varphi_X(t)\varphi_Y(t)$
5. 若 $E(X^k)$ 存在，则 $\varphi^{(k)}(0) = i^k E(X^k)$

**重要定理**：

1. **唯一性定理**：分布函数与特征函数一一对应
2. **连续性定理**：$X_n \xrightarrow{L} X \Leftrightarrow \varphi_n(t) \to \varphi(t)$ 对所有 $t$ 成立

---

## §6.3 大数定律

**定义**：设 $\{X_n\}$ 是随机变量序列，数学期望 $E(X_n)$ 存在。令 $\bar{X}_n = \dfrac{1}{n}\displaystyle\sum_{k=1}^{n} X_k$，若对任意 $\varepsilon > 0$，有

$$
\lim_{n \to \infty} P\bigl(|\bar{X}_n - E(\bar{X}_n)| \ge \varepsilon\bigr) = 0
$$

则称 $\{X_n\}$ 服从大数定律。

**常用大数定律**：

1. **伯努利大数定律**：设 $S_n$ 是 $n$ 重伯努利试验中事件 $A$ 发生的次数，$p = P(A)$，则

   $$
   \frac{S_n}{n} \xrightarrow{P} p
   $$

2. **切比雪夫大数定律**：设 $\{X_n\}$ 两两不相关，方差存在且有共同上界，则 $\{X_n\}$ 服从大数定律。

3. **马尔可夫大数定律**：若 $\{X_n\}$ 满足

   $$
   \frac{1}{n^2}\operatorname{Var}\!\left(\sum_{k=1}^{n} X_k\right) \to 0 \quad (n \to \infty)
   $$

   则 $\{X_n\}$ 服从大数定律。

4. **辛钦大数定律**：设 $\{X_n\}$ 独立同分布，且数学期望 $E(X_1) = \mu$ 存在，则

   $$
   \bar{X}_n \xrightarrow{P} \mu
   $$

---

## §6.4 中心极限定理

**定义**：设 $\{X_n\}$ 是独立随机变量序列，数学期望和方差存在。令

$$
S_n = \sum_{k=1}^{n} X_k,\qquad Y_n^* = \frac{S_n - E(S_n)}{\sqrt{\operatorname{Var}(S_n)}}
$$

若对任意 $x \in \mathbb{R}$，有

$$
\lim_{n \to \infty} P(Y_n^* \le x) = \Phi(x)
$$

则称 $\{X_n\}$ 服从中心极限定理。

**常用中心极限定理**：

1. **棣莫弗-拉普拉斯中心极限定理**：设 $S_n \sim b(n,p)$，则

   $$
   \frac{S_n - np}{\sqrt{np(1-p)}} \xrightarrow{L} N(0,1)
   $$

2. **林德伯格-莱维中心极限定理（独立同分布）**：设 $\{X_n\}$ 独立同分布，$E(X_1) = \mu$，$\operatorname{Var}(X_1) = \sigma^2 > 0$，则

   $$
   \frac{\displaystyle\sum_{k=1}^{n} X_k - n\mu}{\sqrt{n}\,\sigma} \xrightarrow{L} N(0,1)
   $$

3. **李雅普诺夫中心极限定理（独立不同分布）**：设 $\{X_n\}$ 独立，若存在 $\delta > 0$，使得

   $$
   \lim_{n \to \infty} \frac{1}{B_n^{2+\delta}} \sum_{k=1}^{n} E\bigl(|X_k - \mu_k|^{2+\delta}\bigr) = 0
   $$

   其中 $B_n^2 = \displaystyle\sum_{k=1}^{n} \sigma_k^2$，则

   $$
   \frac{\displaystyle\sum_{k=1}^{n} X_k - \sum_{k=1}^{n} \mu_k}{B_n} \xrightarrow{L} N(0,1)
   $$