## 第一章 基本概念

### §1.1 微分方程的定义与分类

#### 一、微分方程的定义

含有自变量、未知函数以及未知函数的某些阶导数（或微分）的关系式称为**微分方程**。

$n$ 阶微分方程的一般形式为：

$$
F(x, y, y', y'', \dots, y^{(n)}) = 0
$$

其中 $x$ 是自变量，$y$ 是未知函数，$y', y'', \dots, y^{(n)}$ 是未知函数的各阶导数。

#### 二、微分方程的分类

1. **按自变量个数分类**

   - **常微分方程**：只含有一个自变量的微分方程
   - **偏微分方程**：含有两个或两个以上自变量的微分方程

2. **按方程结构分类**

   - **线性微分方程**：方程左端是未知函数及其各阶导数的一次有理整式，右端是自变量的已知函数。

     $n$ 阶线性微分方程的一般形式为：

     $$
     a_0(x) y^{(n)} + a_1(x) y^{(n-1)} + \cdots + a_{n-1}(x) y' + a_n(x) y = g(x)
     $$

     其中 $a_0(x) \neq 0$。

   - **非线性微分方程**：不是线性微分方程的微分方程。

3. **按导数阶数分类**

   - **一阶微分方程**：最高阶导数为一阶的微分方程
   - **高阶微分方程**：最高阶导数为二阶及以上的微分方程

---

### §1.2 微分方程的解

#### 一、通解与特解

1. **解**：若将函数 $y = \varphi(x)$ 代入微分方程，能使方程成为恒等式，则称 $y = \varphi(x)$ 为该方程的解。

2. **通解**：$n$ 阶微分方程的解中含有 $n$ 个独立的任意常数 $C_1, C_2, \dots, C_n$，则称该解为通解。

   > 注："独立" 是指雅可比行列式
   > $$
   > \det \frac{\partial(\varphi, \varphi', \dots, \varphi^{(n-1)})}{\partial(C_1, C_2, \dots, C_n)} \neq 0
   > $$

3. **特解**：确定了通解中任意常数的解称为特解。

4. **初始条件**：用于确定通解中任意常数的条件称为初始条件。$n$ 阶微分方程的初始条件为：

   $$
   y(x_0) = y_0,\ y'(x_0) = y_1,\ \dots,\ y^{(n-1)}(x_0) = y_{n-1}
   $$

#### 二、解的几何意义

1. **积分曲线**：微分方程的解 $y = \varphi(x)$ 在 $xOy$ 平面上表示的光滑曲线称为积分曲线。

   > 注：积分曲线上每一点的切线斜率等于方程右端函数在该点的值，即 $\dfrac{dy}{dx} = f(x, y)$。

2. **方向场**：考虑一阶微分方程 $\dfrac{dy}{dx} = f(x, y)$，其中 $f(x, y)$ 在区域 $D$ 内有定义。在 $D$ 内每一点 $(x, y)$ 处画一个斜率为 $f(x, y)$ 的小线段，这些小线段构成的场称为方向场。

3. **等斜线**：方向场中斜率相同的点的轨迹称为等斜线，其方程为 $f(x, y) = k$（$k$ 为常数）。

   > 注：等斜线上各点的方向场斜率均为 $k$。

---

## 第二章 一阶微分方程的解法

### §2.1 变量分离法

#### 一、变量分离方程

形如

$$
\frac{dy}{dx} = f(x) g(y)
$$

的方程称为变量分离方程。

**解法步骤**：

1. 分离变量：$\dfrac{dy}{g(y)} = f(x) \, dx$（$g(y) \neq 0$）
2. 两边积分：$\displaystyle\int \frac{dy}{g(y)} = \int f(x) \, dx + C$
3. 得到通解：$G(y) = F(x) + C$，其中 $G(y)$ 和 $F(x)$ 分别是 $\frac{1}{g(y)}$ 和 $f(x)$ 的原函数。

> 注：若存在 $y_0$ 使得 $g(y_0) = 0$，则 $y = y_0$ 也是方程的解，称为奇解或特殊解，需要单独考虑。

**例 1**：解方程 $\dfrac{dy}{dx} = -\dfrac{y}{x}$

解：分离变量得 $\dfrac{dy}{y} = -\dfrac{dx}{x}$

两边积分得 $\dfrac{1}{2} y^2 = -\dfrac{1}{2} x^2 + C_1$

整理得通解 $x^2 + y^2 = C$（$C = 2C_1$ 为任意常数）。

#### 二、可化为变量分离的方程

1. **齐次微分方程**

   形如

   $$
   \frac{dy}{dx} = g\!\left( \frac{y}{x} \right)
   $$

   的方程称为齐次微分方程。

   **解法**：令 $u = \dfrac{y}{x}$，即 $y = ux$，则 $\dfrac{dy}{dx} = u + x \dfrac{du}{dx}$，代入原方程得：

   $$
   u + x \frac{du}{dx} = g(u)
   $$

   这是一个变量分离方程，分离变量得：

   $$
   \frac{du}{g(u) - u} = \frac{dx}{x}
   $$

   两边积分后再代回 $u = \dfrac{y}{x}$ 即可得到原方程的通解。

2. **可化为齐次的方程**

   形如

   $$
   \frac{dy}{dx} = f\!\left( \frac{a_1 x + b_1 y + c_1}{a_2 x + b_2 y + c_2} \right)
   $$

   的方程，其中 $a_1, b_1, c_1, a_2, b_2, c_2$ 为常数。

   **解法**：

   - 当 $\begin{vmatrix} a_1 & b_1 \\ a_2 & b_2 \end{vmatrix} \neq 0$ 时，解方程组 $\begin{cases} a_1 x + b_1 y + c_1 = 0 \\ a_2 x + b_2 y + c_2 = 0 \end{cases}$ 得交点 $(h, k)$，作变换 $x = X + h$，$y = Y + k$，则方程化为齐次方程：

     $$
     \frac{dY}{dX} = f\!\left( \frac{a_1 X + b_1 Y}{a_2 X + b_2 Y} \right)
     $$

   - 当 $\begin{vmatrix} a_1 & b_1 \\ a_2 & b_2 \end{vmatrix} = 0$ 时，令 $u = a_1 x + b_1 y$，则方程可化为变量分离方程。

3. **其他可化为变量分离的方程**

   形如 $\dfrac{dy}{dx} = f(ax + by + c)$（$a, b \neq 0$）的方程，令 $u = ax + by + c$，则 $\dfrac{du}{dx} = a + b \dfrac{dy}{dx}$，代入原方程得：

   $$
   \frac{du}{dx} = a + b f(u)
   $$

   这是一个变量分离方程。

**例 2**：解方程 $\dfrac{dy}{dx} = (x + y)^2$

解：令 $u = x + y$，则 $\dfrac{dy}{dx} = \dfrac{du}{dx} - 1 = u^2$

分离变量得 $\dfrac{du}{u^2 + 1} = dx$

两边积分得 $\arctan u = x + C$

代回 $u = x + y$ 得通解 $\arctan(x + y) = x + C$。

---

### §2.2 常数变易法

#### 一、一阶线性微分方程

形如

$$
\frac{dy}{dx} + P(x) y = Q(x)
$$

的方程称为一阶线性微分方程。

- 当 $Q(x) \equiv 0$ 时，称为**一阶齐次线性微分方程**
- 当 $Q(x) \not\equiv 0$ 时，称为**一阶非齐次线性微分方程**

#### 二、一阶齐次线性微分方程的解法

一阶齐次线性微分方程 $\dfrac{dy}{dx} + P(x) y = 0$ 是变量分离方程，分离变量得：

$$
\frac{dy}{y} = -P(x) \, dx
$$

两边积分得通解：

$$
y = C e^{-\int P(x) \, dx}
$$

其中 $C$ 为任意常数。

#### 三、一阶非齐次线性微分方程的解法（常数变易法）

**基本思想**：将齐次方程通解中的常数 $C$ 变为 $x$ 的函数 $C(x)$，即设非齐次方程的解为：

$$
y = C(x) e^{-\int P(x) \, dx}
$$

代入非齐次方程得：

$$
C'(x) e^{-\int P(x) \, dx} = Q(x)
$$

解得：

$$
C(x) = \int Q(x) e^{\int P(x) \, dx} \, dx + C
$$

因此，一阶非齐次线性微分方程的通解为：

$$
y = e^{-\int P(x) \, dx} \left( \int Q(x) e^{\int P(x) \, dx} \, dx + C \right)
$$

> 注：通解由两部分组成：齐次方程的通解 $C e^{-\int P(x) \, dx}$ 和非齐次方程的一个特解 $e^{-\int P(x) \, dx} \int Q(x) e^{\int P(x) \, dx} \, dx$。

**例 3**：解方程 $(x+1) \dfrac{dy}{dx} - n y = e^x (x+1)^{n+1}$

解：将方程化为标准形式：

$$
\frac{dy}{dx} - \frac{n}{x+1} y = e^x (x+1)^n
$$

其中 $P(x) = -\dfrac{n}{x+1}$，$Q(x) = e^x (x+1)^n$。

先求齐次方程的通解：

$$
y = C e^{\int \frac{n}{x+1} \, dx} = C (x+1)^n
$$

用常数变易法，设非齐次方程的解为 $y = C(x) (x+1)^n$，代入原方程得：

$$
C'(x) (x+1)^n = e^x (x+1)^n
$$

解得 $C'(x) = e^x$，积分得 $C(x) = e^x + C$。

因此，原方程的通解为：

$$
y = (e^x + C)(x+1)^n
$$

#### 四、伯努利 (Bernoulli) 方程

形如

$$
\frac{dy}{dx} + P(x) y = Q(x) y^n \quad (n \neq 0, 1)
$$

的方程称为伯努利方程。

**解法**：令 $z = y^{1-n}$，则 $\dfrac{dz}{dx} = (1-n) y^{-n} \dfrac{dy}{dx}$，代入原方程得：

$$
\frac{dz}{dx} + (1-n) P(x) z = (1-n) Q(x)
$$

这是一个一阶线性微分方程，用常数变易法求解后再代回 $z = y^{1-n}$ 即可得到原方程的通解。

> 注：当 $n = 0$ 时，方程是一阶线性微分方程；当 $n = 1$ 时，方程是变量分离方程。此外，$y = 0$ 通常也是伯努利方程的解。

**例 4**：解方程 $\dfrac{dy}{dx} = \dfrac{6y}{x} - x y^2$

解：这是 $n = 2$ 的伯努利方程，令 $z = y^{-1}$，则 $\dfrac{dz}{dx} = -y^{-2} \dfrac{dy}{dx}$，代入原方程得：

$$
\frac{dz}{dx} + \frac{6}{x} z = x
$$

这是一阶线性微分方程，其通解为：

$$
z = e^{-\int \frac{6}{x} \, dx} \left( \int x e^{\int \frac{6}{x} \, dx} \, dx + C \right) = \frac{1}{x^6} \left( \int x^7 \, dx + C \right) = \frac{x^2}{8} + \frac{C}{x^6}
$$

代回 $z = y^{-1}$ 得原方程的通解：

$$
\frac{1}{y} = \frac{x^2}{8} + \frac{C}{x^6} \quad \text{或} \quad \frac{x^6}{y} = \frac{x^8}{8} + C
$$

此外，$y = 0$ 也是方程的解。

---

### §2.3 积分因子法

#### 一、恰当微分方程

若存在二元函数 $u(x, y)$，使得

$$
du(x, y) = M(x, y) \, dx + N(x, y) \, dy
$$

则称方程

$$
M(x, y) \, dx + N(x, y) \, dy = 0
$$

为**恰当微分方程**（或全微分方程）。

此时，方程的通解为 $u(x, y) = C$，其中 $C$ 为任意常数。

**恰当微分方程的判别条件**：若 $M(x, y)$ 和 $N(x, y)$ 在单连通区域 $D$ 内具有连续的一阶偏导数，则方程 $M \, dx + N \, dy = 0$ 是恰当微分方程的充要条件是：

$$
\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}
$$

**求原函数 $u(x, y)$ 的方法**：

1. **曲线积分法**：

   $$
   u(x, y) = \int_{x_0}^{x} M(t, y_0) \, dt + \int_{y_0}^{y} N(x, s) \, ds
   $$

   或

   $$
   u(x, y) = \int_{y_0}^{y} N(x_0, s) \, ds + \int_{x_0}^{x} M(t, y) \, dt
   $$

2. **偏积分法**：

   由 $\dfrac{\partial u}{\partial x} = M(x, y)$，对 $x$ 积分得：

   $$
   u(x, y) = \int M(x, y) \, dx + \varphi(y)
   $$

   再由 $\dfrac{\partial u}{\partial y} = N(x, y)$ 确定 $\varphi(y)$。

3. **分项组合法**：将方程的各项重新组合，凑成已知函数的全微分。

**例 5**：解方程 $(3x^2 + 6xy^2) \, dx + (6x^2 y + 4y^3) \, dy = 0$

解：这里 $M = 3x^2 + 6xy^2$，$N = 6x^2 y + 4y^3$，因为

$$
\frac{\partial M}{\partial y} = 12xy = \frac{\partial N}{\partial x}
$$

所以方程是恰当微分方程。

用分项组合法：

$$
(3x^2 \, dx + 4y^3 \, dy) + (6xy^2 \, dx + 6x^2 y \, dy) = 0
$$

$$
d(x^3) + d(y^4) + d(3x^2 y^2) = 0
$$

$$
d(x^3 + 3x^2 y^2 + y^4) = 0
$$

因此，通解为 $x^3 + 3x^2 y^2 + y^4 = C$。

#### 二、积分因子

若存在连续可微函数 $\mu(x, y) \neq 0$，使得

$$
\mu(x, y) M(x, y) \, dx + \mu(x, y) N(x, y) \, dy = 0
$$

是恰当微分方程，则称 $\mu(x, y)$ 为方程 $M \, dx + N \, dy = 0$ 的**积分因子**。

**常见积分因子类型**：

1. **仅与 $x$ 有关的积分因子**：若 $\dfrac{\frac{\partial M}{\partial y} - \frac{\partial N}{\partial x}}{N} = P(x)$（仅与 $x$ 有关），则积分因子为：

   $$
   \mu(x) = e^{\int P(x) \, dx}
   $$

2. **仅与 $y$ 有关的积分因子**：若 $-\dfrac{\frac{\partial M}{\partial y} - \frac{\partial N}{\partial x}}{M} = Q(y)$（仅与 $y$ 有关），则积分因子为：

   $$
   \mu(y) = e^{\int Q(y) \, dy}
   $$

**例 6**：解方程 $y \, dx + (y - x) \, dy = 0$

解：这里 $M = y$，$N = y - x$，因为

$$
\frac{\partial M}{\partial y} = 1,\quad \frac{\partial N}{\partial x} = -1
$$

所以 $\dfrac{\partial M}{\partial y} \neq \dfrac{\partial N}{\partial x}$，方程不是恰当微分方程。

计算：

$$
-\frac{\frac{\partial M}{\partial y} - \frac{\partial N}{\partial x}}{M} = -\frac{1 - (-1)}{y} = -\frac{2}{y}
$$

仅与 $y$ 有关，所以积分因子为：

$$
\mu(y) = e^{\int -\frac{2}{y} \, dy} = \frac{1}{y^2}
$$

将方程乘以 $\dfrac{1}{y^2}$ 得：

$$
\frac{y \, dx - x \, dy}{y^2} + \frac{1}{y} \, dy = 0
$$

$$
d\!\left( \frac{x}{y} \right) + d(\ln|y|) = 0
$$

$$
d\!\left( \frac{x}{y} + \ln|y| \right) = 0
$$

因此，通解为 $\dfrac{x}{y} + \ln|y| = C$，此外 $y = 0$ 也是方程的解。

---

### §2.4 参数表示法

对于一阶隐式微分方程

$$
F(x, y, y') = 0
$$

如果难以解出 $y'$，或者解出后表达式过于复杂，可以使用参数表示法求解。

#### 一、可以解出 $y$ 或 $x$ 的方程

1. **解出 $y$ 的方程：$y = f(x, p)$**，其中 $p = y'$

   两边对 $x$ 求导得：

   $$
   p = \frac{\partial f}{\partial x} + \frac{\partial f}{\partial p} \cdot \frac{dp}{dx}
   $$

   这是一个关于 $x$ 和 $p$ 的一阶微分方程，若能求出其通解 $p = \varphi(x, C)$，则原方程的通解为：

   $$
   y = f(x, \varphi(x, C))
   $$

2. **解出 $x$ 的方程：$x = f(y, p)$**，其中 $p = y'$

   两边对 $y$ 求导得：

   $$
   \frac{1}{p} = \frac{\partial f}{\partial y} + \frac{\partial f}{\partial p} \cdot \frac{dp}{dy}
   $$

   这是一个关于 $y$ 和 $p$ 的一阶微分方程，若能求出其通解 $p = \psi(y, C)$，则原方程的通解为：

   $$
   x = f(y, \psi(y, C))
   $$

#### 二、不显含 $x$ 或 $y$ 的方程

1. **不显含 $x$ 的方程：$F(y, p) = 0$**，其中 $p = y'$

   引入参数 $t$，将方程表示为参数形式：

   $$
   y = \varphi(t), \quad p = \psi(t)
   $$

   由 $dy = p \, dx$ 得 $dx = \dfrac{dy}{p} = \dfrac{\varphi'(t)}{\psi(t)} \, dt$，积分得：

   $$
   x = \int \frac{\varphi'(t)}{\psi(t)} \, dt + C
   $$

   因此，原方程的参数形式通解为：

   $$
   \begin{cases}
   x = \displaystyle\int \frac{\varphi'(t)}{\psi(t)} \, dt + C \\[8pt]
   y = \varphi(t)
   \end{cases}
   $$

2. **不显含 $y$ 的方程：$F(x, p) = 0$**，其中 $p = y'$

   引入参数 $t$，将方程表示为参数形式：

   $$
   x = \varphi(t), \quad p = \psi(t)
   $$

   由 $dy = p \, dx$ 得 $dy = \psi(t) \varphi'(t) \, dt$，积分得：

   $$
   y = \int \psi(t) \varphi'(t) \, dt + C
   $$

   因此，原方程的参数形式通解为：

   $$
   \begin{cases}
   x = \varphi(t) \\
   y = \displaystyle\int \psi(t) \varphi'(t) \, dt + C
   \end{cases}
   $$

---

## 第三章 高阶微分方程

### §3.1 可降阶的高阶微分方程

对于某些特殊类型的高阶微分方程，可以通过适当的变量替换将其降为低阶微分方程求解。

#### 一、不显含未知函数 $y$ 的方程：$F(x, y^{(k)}, y^{(k+1)}, \dots, y^{(n)}) = 0$（$1 \leq k \leq n$）

**解法**：令 $z = y^{(k)}$，则方程化为关于 $z$ 的 $n-k$ 阶微分方程：

$$
F(x, z, z', \dots, z^{(n-k)}) = 0
$$

若能求出其通解 $z = \varphi(x, C_1, C_2, \dots, C_{n-k})$，则对 $z = y^{(k)}$ 积分 $k$ 次即可得到原方程的通解。

**例 1**：解方程 $x y'' + y' = 0$

解：令 $z = y'$，则方程化为 $x z' + z = 0$，这是变量分离方程，解得 $z = \dfrac{C_1}{x}$。

积分得 $y = \displaystyle\int \frac{C_1}{x} \, dx + C_2 = C_1 \ln|x| + C_2$。

#### 二、不显含自变量 $x$ 的方程：$F(y, y', y'', \dots, y^{(n)}) = 0$

**解法**：令 $p = y'$，并将 $y$ 视为自变量，则

$$
y'' = \frac{dp}{dx} = \frac{dp}{dy} \cdot \frac{dy}{dx} = p \frac{dp}{dy}
$$

$$
y''' = \frac{d}{dx}\!\left( p \frac{dp}{dy} \right) = p^2 \frac{d^2p}{dy^2} + p \left( \frac{dp}{dy} \right)^2
$$

以此类推，可将原方程化为关于 $y$ 和 $p$ 的 $n-1$ 阶微分方程。

**例 2**：解方程 $y y'' + (y')^2 = 0$

解：令 $p = y'$，则 $y'' = p \dfrac{dp}{dy}$，代入原方程得：

$$
y p \frac{dp}{dy} + p^2 = 0
$$

当 $p \neq 0$ 时，分离变量得 $\dfrac{dp}{p} = -\dfrac{dy}{y}$，积分得 $p = \dfrac{C_1}{y}$。

即 $\dfrac{dy}{dx} = \dfrac{C_1}{y}$，分离变量积分得 $y^2 = 2C_1 x + C_2$。

当 $p = 0$ 时，$y = C$ 也是方程的解，包含在上述通解中（令 $C_1 = 0$）。

#### 三、齐次线性微分方程已知部分解的降阶

设 $y_1(x)$ 是 $n$ 阶齐次线性微分方程

$$
y^{(n)} + a_1(x) y^{(n-1)} + \cdots + a_n(x) y = 0
$$

的一个非零解，作变换 $y = y_1(x) z$，则可将方程降为关于 $z'$ 的 $n-1$ 阶齐次线性微分方程。

特别地，对于二阶齐次线性微分方程 $y'' + P(x) y' + Q(x) y = 0$，若已知一个解 $y_1(x)$，则另一个线性无关的解为：

$$
y_2(x) = y_1(x) \int \frac{e^{-\int P(x) \, dx}}{y_1^2(x)} \, dx
$$

**例 3**：已知 $y_1 = \dfrac{\sin t}{t}$ 是方程 $x'' + \dfrac{2}{t} x' + x = 0$ 的一个解，求其通解。

解：这里 $P(t) = \dfrac{2}{t}$，由刘维尔公式，另一个线性无关的解为：

$$
y_2 = \frac{\sin t}{t} \int \frac{e^{-\int \frac{2}{t} \, dt}}{\left( \frac{\sin t}{t} \right)^2} \, dt = \frac{\sin t}{t} \int \frac{t^2}{\sin^2 t} \cdot \frac{1}{t^2} \, dt = \frac{\sin t}{t} \int \csc^2 t \, dt = -\frac{\cos t}{t}
$$

因此，通解为 $x = \dfrac{C_1 \sin t + C_2 \cos t}{t}$。

---

### §3.2 高阶线性微分方程的一般理论

#### 一、$n$ 阶线性微分方程的标准形式

$n$ 阶非齐次线性微分方程的标准形式为：

$$
y^{(n)} + a_1(x) y^{(n-1)} + \cdots + a_{n-1}(x) y' + a_n(x) y = f(x) \tag{1}
$$

对应的 $n$ 阶齐次线性微分方程为：

$$
y^{(n)} + a_1(x) y^{(n-1)} + \cdots + a_{n-1}(x) y' + a_n(x) y = 0 \tag{2}
$$

其中 $a_i(x)$ 和 $f(x)$ 在区间 $[a, b]$ 上连续。

#### 二、解的存在唯一性定理

**定理**：若 $a_i(x)$（$i = 1, 2, \dots, n$）和 $f(x)$ 在区间 $[a, b]$ 上连续，则对任意 $x_0 \in [a, b]$ 和任意常数 $y_0, y_0', \dots, y_0^{(n-1)}$，初值问题

$$
\begin{cases}
y^{(n)} + a_1(x) y^{(n-1)} + \cdots + a_n(x) y = f(x) \\
y(x_0) = y_0,\ y'(x_0) = y_0',\ \dots,\ y^{(n-1)}(x_0) = y_0^{(n-1)}
\end{cases}
$$

在区间 $[a, b]$ 上存在唯一解。

#### 三、齐次线性微分方程的解的性质

1. **叠加原理**：若 $y_1(x), y_2(x), \dots, y_k(x)$ 是方程 (2) 的解，则它们的任意线性组合

   $$
   C_1 y_1(x) + C_2 y_2(x) + \cdots + C_k y_k(x)
   $$

   也是方程 (2) 的解，其中 $C_1, C_2, \dots, C_k$ 为任意常数。

2. **线性相关与线性无关**：设 $y_1(x), y_2(x), \dots, y_n(x)$ 是定义在区间 $[a, b]$ 上的 $n$ 个函数，若存在不全为零的常数 $C_1, C_2, \dots, C_n$，使得

   $$
   C_1 y_1(x) + C_2 y_2(x) + \cdots + C_n y_n(x) \equiv 0,\quad \forall x \in [a, b]
   $$

   则称这 $n$ 个函数在 $[a, b]$ 上线性相关；否则称它们线性无关。

3. **Wronski 行列式**：$n$ 个函数 $y_1(x), y_2(x), \dots, y_n(x)$ 的 Wronski 行列式定义为：

   $$
   W(x) = \begin{vmatrix}
   y_1(x) & y_2(x) & \cdots & y_n(x) \\
   y_1'(x) & y_2'(x) & \cdots & y_n'(x) \\
   \vdots & \vdots & & \vdots \\
   y_1^{(n-1)}(x) & y_2^{(n-1)}(x) & \cdots & y_n^{(n-1)}(x)
   \end{vmatrix}
   $$

4. **Wronski 行列式的性质**：

   - 若 $y_1(x), y_2(x), \dots, y_n(x)$ 线性相关，则 $W(x) \equiv 0$ 在 $[a, b]$ 上成立。
   - 若 $y_1(x), y_2(x), \dots, y_n(x)$ 是方程 (2) 的解，则它们线性无关当且仅当 $W(x) \neq 0$ 在 $[a, b]$ 上成立。

5. **刘维尔 (Liouville) 公式**：设 $y_1(x), y_2(x), \dots, y_n(x)$ 是方程 (2) 的 $n$ 个解，则其 Wronski 行列式满足：

   $$
   W(x) = W(x_0) \, e^{-\int_{x_0}^{x} a_1(s) \, ds}
   $$

   其中 $x_0 \in [a, b]$。

#### 四、齐次线性微分方程的通解结构

**定理**：$n$ 阶齐次线性微分方程 (2) 存在 $n$ 个线性无关的解，称为基本解组。若 $y_1(x), y_2(x), \dots, y_n(x)$ 是方程 (2) 的一个基本解组，则方程 (2) 的通解为：

$$
y = C_1 y_1(x) + C_2 y_2(x) + \cdots + C_n y_n(x)
$$

其中 $C_1, C_2, \dots, C_n$ 为任意常数，且通解包含了方程 (2) 的所有解。

#### 五、非齐次线性微分方程的通解结构

**定理**：设 $\tilde{y}(x)$ 是非齐次线性微分方程 (1) 的一个特解，$y_1(x), y_2(x), \dots, y_n(x)$ 是对应的齐次方程 (2) 的一个基本解组，则方程 (1) 的通解为：

$$
y = C_1 y_1(x) + C_2 y_2(x) + \cdots + C_n y_n(x) + \tilde{y}(x)
$$

其中 $C_1, C_2, \dots, C_n$ 为任意常数，且通解包含了方程 (1) 的所有解。

#### 六、常数变易法

若已知齐次方程 (2) 的一个基本解组 $y_1(x), y_2(x), \dots, y_n(x)$，则非齐次方程 (1) 的一个特解可表示为：

$$
\tilde{y}(x) = \sum_{i=1}^{n} C_i(x) y_i(x)
$$

其中 $C_i(x)$（$i = 1, 2, \dots, n$）满足方程组：

$$
\begin{cases}
C_1'(x) y_1(x) + C_2'(x) y_2(x) + \cdots + C_n'(x) y_n(x) = 0 \\
C_1'(x) y_1'(x) + C_2'(x) y_2'(x) + \cdots + C_n'(x) y_n'(x) = 0 \\
\quad \vdots \\
C_1'(x) y_1^{(n-1)}(x) + C_2'(x) y_2^{(n-1)}(x) + \cdots + C_n'(x) y_n^{(n-1)}(x) = f(x)
\end{cases}
$$

解此方程组得 $C_i'(x)$，积分后即可得到 $C_i(x)$。

特别地，对于二阶非齐次线性微分方程 $y'' + P(x) y' + Q(x) y = f(x)$，若已知齐次方程的两个线性无关解 $y_1(x)$ 和 $y_2(x)$，则特解为：

$$
\tilde{y}(x) = -y_1(x) \int \frac{y_2(x) f(x)}{W(x)} \, dx + y_2(x) \int \frac{y_1(x) f(x)}{W(x)} \, dx
$$

其中 $W(x)$ 是 $y_1(x)$ 和 $y_2(x)$ 的 Wronski 行列式。

---

### §3.3 常系数线性微分方程

#### 一、常系数齐次线性微分方程

$n$ 阶常系数齐次线性微分方程的标准形式为：

$$
y^{(n)} + a_1 y^{(n-1)} + \cdots + a_{n-1} y' + a_n y = 0 \tag{3}
$$

其中 $a_1, a_2, \dots, a_n$ 为常数。

**特征方程**：代数方程

$$
\lambda^n + a_1 \lambda^{n-1} + \cdots + a_{n-1} \lambda + a_n = 0 \tag{4}
$$

称为方程 (3) 的特征方程，其根称为特征根。

根据特征根的不同情况，方程 (3) 的基本解组如下：

1. **特征根为单实根**：若 $\lambda_1, \lambda_2, \dots, \lambda_n$ 是 $n$ 个互不相同的实特征根，则基本解组为：

   $$
   e^{\lambda_1 x}, e^{\lambda_2 x}, \dots, e^{\lambda_n x}
   $$

2. **特征根为重实根**：若 $\lambda$ 是 $k$ 重实特征根，则对应 $k$ 个线性无关的解：

   $$
   e^{\lambda x}, x e^{\lambda x}, \dots, x^{k-1} e^{\lambda x}
   $$

3. **特征根为单复根**：若 $\lambda = \alpha + i\beta$ 和 $\lambda = \alpha - i\beta$ 是一对共轭复特征根，则对应两个线性无关的实值解：

   $$
   e^{\alpha x} \cos \beta x,\quad e^{\alpha x} \sin \beta x
   $$

4. **特征根为重复根**：若 $\lambda = \alpha + i\beta$ 和 $\lambda = \alpha - i\beta$ 是一对 $k$ 重共轭复特征根，则对应 $2k$ 个线性无关的实值解：

   $$
   e^{\alpha x} \cos \beta x, x e^{\alpha x} \cos \beta x, \dots, x^{k-1} e^{\alpha x} \cos \beta x
   $$
   $$
   e^{\alpha x} \sin \beta x, x e^{\alpha x} \sin \beta x, \dots, x^{k-1} e^{\alpha x} \sin \beta x
   $$

**例 4**：解方程 $y''' - 3y'' + 3y' - y = 0$

解：特征方程为 $\lambda^3 - 3\lambda^2 + 3\lambda - 1 = 0$，即 $(\lambda - 1)^3 = 0$，$\lambda = 1$ 是三重实根。

因此，基本解组为 $e^x, x e^x, x^2 e^x$，通解为 $y = (C_1 + C_2 x + C_3 x^2) e^x$。

#### 二、常系数非齐次线性微分方程

$n$ 阶常系数非齐次线性微分方程的标准形式为：

$$
y^{(n)} + a_1 y^{(n-1)} + \cdots + a_{n-1} y' + a_n y = f(x) \tag{5}
$$

求其特解常用**比较系数法**和**常数变易法**。

**比较系数法**：适用于 $f(x)$ 为以下两种类型的情况：

1. **类型 I**：$f(x) = P_m(x) e^{\lambda x}$，其中 $P_m(x)$ 是 $m$ 次多项式，$\lambda$ 是常数。

   此时，方程 (5) 有形如

   $$
   \tilde{y}(x) = x^k Q_m(x) e^{\lambda x}
   $$

   的特解，其中 $Q_m(x)$ 是与 $P_m(x)$ 同次的待定多项式，$k$ 是特征根 $\lambda$ 的重数（当 $\lambda$ 不是特征根时，$k = 0$）。

2. **类型 II**：$f(x) = e^{\alpha x} [P_m(x) \cos \beta x + Q_n(x) \sin \beta x]$，其中 $P_m(x)$ 和 $Q_n(x)$ 分别是 $m$ 次和 $n$ 次多项式，$\alpha, \beta$ 是常数。

   此时，方程 (5) 有形如

   $$
   \tilde{y}(x) = x^k e^{\alpha x} [R_l(x) \cos \beta x + S_l(x) \sin \beta x]
   $$

   的特解，其中 $l = \max\{m, n\}$，$R_l(x)$ 和 $S_l(x)$ 是 $l$ 次待定多项式，$k$ 是特征根 $\alpha + i\beta$ 的重数（当 $\alpha + i\beta$ 不是特征根时，$k = 0$）。

**例 5**：解方程 $y'' - 2y' + y = e^x$

解：对应的齐次方程为 $y'' - 2y' + y = 0$，特征方程为 $\lambda^2 - 2\lambda + 1 = 0$，$\lambda = 1$ 是二重实根，齐次通解为 $y = (C_1 + C_2 x) e^x$。

非齐次项 $f(x) = e^x$ 属于类型 I，$\lambda = 1$ 是二重特征根，故设特解为 $\tilde{y} = A x^2 e^x$。

代入原方程得 $2A e^x = e^x$，解得 $A = \dfrac{1}{2}$。

因此，原方程的通解为 $y = (C_1 + C_2 x) e^x + \dfrac{1}{2} x^2 e^x$。

---

### §3.4 欧拉 (Euler) 方程

形如

$$
x^n y^{(n)} + a_1 x^{n-1} y^{(n-1)} + \cdots + a_{n-1} x y' + a_n y = 0 \tag{6}
$$

的方程称为欧拉方程，其中 $a_1, a_2, \dots, a_n$ 为常数。

**解法**：作变量替换 $x = e^t$（即 $t = \ln x$），则

$$
x y' = \frac{dy}{dt},\quad x^2 y'' = \frac{d^2y}{dt^2} - \frac{dy}{dt},\quad x^3 y''' = \frac{d^3y}{dt^3} - 3\frac{d^2y}{dt^2} + 2\frac{dy}{dt},\ \dots
$$

一般地，$x^k y^{(k)} = D(D-1)\cdots(D-k+1)y$，其中 $D = \dfrac{d}{dt}$。

代入欧拉方程 (6)，可将其化为以 $t$ 为自变量的常系数线性微分方程，求解后再代回 $t = \ln x$ 即可得到原方程的解。

**例 6**：解方程 $x^2 y'' + 3x y' + y = 0$

解：令 $x = e^t$，则 $t = \ln x$，代入方程得：

$$
[D(D-1) + 3D + 1]y = 0 \Rightarrow (D^2 + 2D + 1)y = 0
$$

特征方程为 $\lambda^2 + 2\lambda + 1 = 0$，$\lambda = -1$ 是二重实根，通解为 $y = (C_1 + C_2 t) e^{-t}$。

代回 $t = \ln x$ 得原方程的通解为 $y = \dfrac{C_1 + C_2 \ln x}{x}$。

---

### §3.5 幂级数解法

对于变系数线性微分方程，当无法用初等方法求解时，可以考虑幂级数解法。

#### 一、普通点附近的幂级数解法

**定理**：若方程

$$
y'' + P(x) y' + Q(x) y = 0
$$

的系数 $P(x)$ 和 $Q(x)$ 在点 $x_0$ 处解析（即可以展开为 $x - x_0$ 的幂级数），则方程在 $x_0$ 的邻域内有幂级数解：

$$
y = \sum_{n=0}^{\infty} a_n (x - x_0)^n
$$

其收敛半径至少等于 $P(x)$ 和 $Q(x)$ 的幂级数展开式的收敛半径。

#### 二、正则奇点附近的幂级数解法（Frobenius 方法）

**定义**：若 $x_0$ 是 $P(x)$ 或 $Q(x)$ 的奇点，但 $(x - x_0) P(x)$ 和 $(x - x_0)^2 Q(x)$ 在 $x_0$ 处解析，则称 $x_0$ 是方程的正则奇点。

**定理**：若 $x_0$ 是方程的正则奇点，则方程在 $x_0$ 的去心邻域内有形如

$$
y = (x - x_0)^\rho \sum_{n=0}^{\infty} a_n (x - x_0)^n = \sum_{n=0}^{\infty} a_n (x - x_0)^{n+\rho}
$$

的解，其中 $\rho$ 是常数（称为指标根），$a_0 \neq 0$。

---

## 第四章 线性微分方程组

### §4.1 线性微分方程组的一般理论

#### 一、一阶线性微分方程组的标准形式

一阶非齐次线性微分方程组的标准形式为：

$$
\begin{cases}
\dfrac{dx_1}{dt} = a_{11}(t) x_1 + a_{12}(t) x_2 + \cdots + a_{1n}(t) x_n + f_1(t) \\[6pt]
\dfrac{dx_2}{dt} = a_{21}(t) x_1 + a_{22}(t) x_2 + \cdots + a_{2n}(t) x_n + f_2(t) \\
\quad \vdots \\
\dfrac{dx_n}{dt} = a_{n1}(t) x_1 + a_{n2}(t) x_2 + \cdots + a_{nn}(t) x_n + f_n(t)
\end{cases} \tag{7}
$$

对应的一阶齐次线性微分方程组为：

$$
\begin{cases}
\dfrac{dx_1}{dt} = a_{11}(t) x_1 + a_{12}(t) x_2 + \cdots + a_{1n}(t) x_n \\[6pt]
\dfrac{dx_2}{dt} = a_{21}(t) x_1 + a_{22}(t) x_2 + \cdots + a_{2n}(t) x_n \\
\quad \vdots \\
\dfrac{dx_n}{dt} = a_{n1}(t) x_1 + a_{n2}(t) x_2 + \cdots + a_{nn}(t) x_n
\end{cases} \tag{8}
$$

写成向量形式为：

$$
\frac{d\mathbf{x}}{dt} = A(t) \mathbf{x} + \mathbf{f}(t) \tag{7'}
$$

$$
\frac{d\mathbf{x}}{dt} = A(t) \mathbf{x} \tag{8'}
$$

其中

$$
\mathbf{x} = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix},\quad
A(t) = \begin{pmatrix}
a_{11}(t) & a_{12}(t) & \cdots & a_{1n}(t) \\
a_{21}(t) & a_{22}(t) & \cdots & a_{2n}(t) \\
\vdots & \vdots & & \vdots \\
a_{n1}(t) & a_{n2}(t) & \cdots & a_{nn}(t)
\end{pmatrix},\quad
\mathbf{f}(t) = \begin{pmatrix} f_1(t) \\ f_2(t) \\ \vdots \\ f_n(t) \end{pmatrix}
$$

#### 二、解的存在唯一性定理

**定理**：若矩阵 $A(t)$ 和向量 $\mathbf{f}(t)$ 在区间 $[a, b]$ 上连续，则对任意 $t_0 \in [a, b]$ 和任意常向量 $\mathbf{x}_0$，初值问题

$$
\begin{cases}
\dfrac{d\mathbf{x}}{dt} = A(t) \mathbf{x} + \mathbf{f}(t) \\[6pt]
\mathbf{x}(t_0) = \mathbf{x}_0
\end{cases}
$$

在区间 $[a, b]$ 上存在唯一解。

#### 三、齐次线性微分方程组的解的性质

1. **叠加原理**：若 $\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_k(t)$ 是方程组 (8') 的解，则它们的任意线性组合

   $$
   C_1 \mathbf{x}_1(t) + C_2 \mathbf{x}_2(t) + \cdots + C_k \mathbf{x}_k(t)
   $$

   也是方程组 (8') 的解，其中 $C_1, C_2, \dots, C_k$ 为任意常数。

2. **线性相关与线性无关**：设 $\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_n(t)$ 是定义在区间 $[a, b]$ 上的 $n$ 个向量函数，若存在不全为零的常数 $C_1, C_2, \dots, C_n$，使得

   $$
   C_1 \mathbf{x}_1(t) + C_2 \mathbf{x}_2(t) + \cdots + C_n \mathbf{x}_n(t) \equiv \mathbf{0},\quad \forall t \in [a, b]
   $$

   则称这 $n$ 个向量函数在 $[a, b]$ 上线性相关；否则称它们线性无关。

3. **Wronski 行列式**：$n$ 个向量函数 $\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_n(t)$ 的 Wronski 行列式定义为：

   $$
   W(t) = \begin{vmatrix}
   x_{11}(t) & x_{12}(t) & \cdots & x_{1n}(t) \\
   x_{21}(t) & x_{22}(t) & \cdots & x_{2n}(t) \\
   \vdots & \vdots & & \vdots \\
   x_{n1}(t) & x_{n2}(t) & \cdots & x_{nn}(t)
   \end{vmatrix}
   $$

   其中 $\mathbf{x}_i(t) = (x_{1i}(t), x_{2i}(t), \dots, x_{ni}(t))^T$。

4. **Wronski 行列式的性质**：

   - 若 $\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_n(t)$ 线性相关，则 $W(t) \equiv 0$ 在 $[a, b]$ 上成立。
   - 若 $\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_n(t)$ 是方程组 (8') 的解，则它们线性无关当且仅当 $W(t) \neq 0$ 在 $[a, b]$ 上成立。

5. **刘维尔 (Liouville) 公式**：设 $\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_n(t)$ 是方程组 (8') 的 $n$ 个解，则其 Wronski 行列式满足：

   $$
   W(t) = W(t_0) \, e^{\int_{t_0}^{t} \operatorname{tr} A(s) \, ds}
   $$

   其中 $\operatorname{tr} A(s) = a_{11}(s) + a_{22}(s) + \cdots + a_{nn}(s)$ 是矩阵 $A(s)$ 的迹。

#### 四、基解矩阵与通解结构

1. **基解矩阵**：以方程组 (8') 的 $n$ 个线性无关的解为列向量构成的矩阵 $\Phi(t) = [\mathbf{x}_1(t), \mathbf{x}_2(t), \dots, \mathbf{x}_n(t)]$ 称为方程组 (8') 的一个基解矩阵。

   > 注：基解矩阵的行列式在定义区间上恒不为零。

2. **标准基解矩阵**：满足 $\Phi(t_0) = I$（单位矩阵）的基解矩阵称为标准基解矩阵。

3. **齐次方程组的通解结构**：若 $\Phi(t)$ 是方程组 (8') 的一个基解矩阵，则方程组 (8') 的通解为：

   $$
   \mathbf{x}(t) = \Phi(t) \mathbf{C}
   $$

   其中 $\mathbf{C} = (C_1, C_2, \dots, C_n)^T$ 是任意常向量。

4. **非齐次方程组的通解结构**：若 $\Phi(t)$ 是对应的齐次方程组 (8') 的一个基解矩阵，$\tilde{\mathbf{x}}(t)$ 是非齐次方程组 (7') 的一个特解，则方程组 (7') 的通解为：

   $$
   \mathbf{x}(t) = \Phi(t) \mathbf{C} + \tilde{\mathbf{x}}(t)
   $$

   其中 $\mathbf{C}$ 是任意常向量。

#### 五、常数变易法

若 $\Phi(t)$ 是齐次方程组 (8') 的一个基解矩阵，则非齐次方程组 (7') 的一个特解为：

$$
\tilde{\mathbf{x}}(t) = \Phi(t) \int_{t_0}^{t} \Phi^{-1}(s) \mathbf{f}(s) \, ds
$$

因此，非齐次方程组 (7') 的通解为：

$$
\mathbf{x}(t) = \Phi(t) \mathbf{C} + \Phi(t) \int_{t_0}^{t} \Phi^{-1}(s) \mathbf{f}(s) \, ds
$$

---

### §4.2 常系数线性微分方程组

#### 一、常系数齐次线性微分方程组

一阶常系数齐次线性微分方程组的标准形式为：

$$
\frac{d\mathbf{x}}{dt} = A \mathbf{x} \tag{9}
$$

其中 $A$ 是 $n$ 阶常数矩阵。

**矩阵指数函数**：定义矩阵指数函数为

$$
e^{At} = \sum_{k=0}^{\infty} \frac{(At)^k}{k!} = I + At + \frac{A^2 t^2}{2!} + \cdots + \frac{A^k t^k}{k!} + \cdots
$$

它具有以下性质：

1. $e^{A(t+s)} = e^{At} e^{As}$
2. $(e^{At})^{-1} = e^{-At}$
3. $\dfrac{d}{dt} e^{At} = A e^{At} = e^{At} A$

**定理**：矩阵指数函数 $e^{At}$ 是方程组 (9) 的一个标准基解矩阵（满足 $e^{A \cdot 0} = I$）。因此，方程组 (9) 的通解为：

$$
\mathbf{x}(t) = e^{At} \mathbf{C}
$$

其中 $\mathbf{C}$ 是任意常向量。

#### 二、基解矩阵的求法

1. **$A$ 可对角化的情况**：若 $A$ 有 $n$ 个线性无关的特征向量 $\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_n$，对应的特征值为 $\lambda_1, \lambda_2, \dots, \lambda_n$，则方程组 (9) 的一个基解矩阵为：

   $$
   \Phi(t) = [e^{\lambda_1 t} \mathbf{v}_1, e^{\lambda_2 t} \mathbf{v}_2, \dots, e^{\lambda_n t} \mathbf{v}_n]
   $$

2. **$A$ 不可对角化的情况**：若 $A$ 不可对角化，则存在可逆矩阵 $P$，使得 $P^{-1}AP = J$，其中 $J$ 是 $A$ 的约当标准形。此时，

   $$
   e^{At} = P e^{Jt} P^{-1}
   $$

   对于约当块

   $$
   J_i = \begin{pmatrix}
   \lambda_i & 1 & & \\
   & \lambda_i & \ddots & \\
   & & \ddots & 1 \\
   & & & \lambda_i
   \end{pmatrix}_{n_i \times n_i}
   $$

   有

   $$
   e^{J_i t} = e^{\lambda_i t}
   \begin{pmatrix}
   1 & t & \frac{t^2}{2!} & \cdots & \frac{t^{n_i-1}}{(n_i-1)!} \\
   & 1 & t & \cdots & \frac{t^{n_i-2}}{(n_i-2)!} \\
   & & \ddots & \ddots & \vdots \\
   & & & \ddots & t \\
   & & & & 1
   \end{pmatrix}
   $$

#### 三、复值解转化为实值解

若方程组 (9) 有复值解 $\mathbf{x}(t) = \mathbf{u}(t) + i \mathbf{v}(t)$，则其实部 $\mathbf{u}(t)$ 和虚部 $\mathbf{v}(t)$ 都是方程组 (9) 的实值解。

#### 四、常系数非齐次线性微分方程组

一阶常系数非齐次线性微分方程组的标准形式为：

$$
\frac{d\mathbf{x}}{dt} = A \mathbf{x} + \mathbf{f}(t) \tag{10}
$$

其通解为齐次方程组的通解加上非齐次方程组的一个特解。特解可通过**常数变易法**求得：

$$
\tilde{\mathbf{x}}(t) = e^{At} \int_{t_0}^{t} e^{-As} \mathbf{f}(s) \, ds
$$

## 第五章 解的基本理论

### §5.1 解的存在唯一性定理（皮卡 - 林德勒夫定理）

#### 一、定理内容

考虑一阶微分方程的初值问题（柯西问题）：

$$
\begin{cases}
\dfrac{dy}{dx} = f(x, y) \\[6pt]
y(x_0) = y_0
\end{cases} \tag{1}
$$

**定理**：若函数 $f(x, y)$ 满足以下两个条件：

1. **连续性**：$f(x, y)$ 在闭矩形区域

   $$
   R = \{ (x, y) \mid |x - x_0| \leq a,\ |y - y_0| \leq b \}
   $$

   上连续；

2. **利普希茨 (Lipschitz) 条件**：$f(x, y)$ 关于 $y$ 在 $R$ 上满足利普希茨条件，即存在常数 $L > 0$，使得对任意 $(x, y_1), (x, y_2) \in R$，有

   $$
   |f(x, y_1) - f(x, y_2)| \leq L |y_1 - y_2|
   $$

则初值问题 (1) 在区间 $|x - x_0| \leq h$ 上存在唯一解，其中

$$
h = \min\left\{ a, \frac{b}{M} \right\},\quad M = \max_{(x, y) \in R} |f(x, y)|
$$

> 注：
> 1. 条件 $\dfrac{\partial f}{\partial y}$ 在 $R$ 上连续是利普希茨条件的充分条件，但不是必要条件。反例：$f(x, y) = |y|$ 满足利普希茨条件，但 $\dfrac{\partial f}{\partial y}$ 在 $y = 0$ 处不连续。
> 2. 定理中的两个条件是解存在唯一的**充分条件**，而非必要条件。

#### 二、定理的证明思路（皮卡迭代法）

1. **等价积分方程**：初值问题 (1) 等价于积分方程

   $$
   y(x) = y_0 + \int_{x_0}^{x} f(s, y(s)) \, ds
   $$

2. **构造皮卡迭代序列**：

   $$
   \begin{cases}
   \varphi_0(x) = y_0 \\
   \varphi_n(x) = y_0 + \displaystyle\int_{x_0}^{x} f(s, \varphi_{n-1}(s)) \, ds,\quad n = 1, 2, \dots
   \end{cases}
   $$

3. **证明迭代序列一致收敛**：利用数学归纳法证明 $|\varphi_n(x) - \varphi_{n-1}(x)| \leq \dfrac{M L^{n-1}}{n!} |x - x_0|^n$，从而序列 $\{\varphi_n(x)\}$ 在 $|x - x_0| \leq h$ 上一致收敛。

4. **证明极限函数是解**：证明极限函数 $\varphi(x) = \lim_{n \to \infty} \varphi_n(x)$ 满足积分方程，从而是初值问题的解。

5. **证明唯一性**：利用格朗沃尔 (Gronwall) 不等式证明解的唯一性。

#### 三、格朗沃尔 (Gronwall) 不等式

**不等式**：设 $k \geq 0$，$f(t)$ 和 $g(t)$ 是区间 $[a, b]$ 上的非负连续函数，且满足

$$
f(t) \leq k + \int_{a}^{t} f(s) g(s) \, ds,\quad \forall t \in [a, b]
$$

则

$$
f(t) \leq k \, e^{\int_{a}^{t} g(s) \, ds},\quad \forall t \in [a, b]
$$

#### 四、近似计算与误差估计

第 $n$ 次近似解 $\varphi_n(x)$ 与精确解 $\varphi(x)$ 之间的误差估计为：

$$
|\varphi_n(x) - \varphi(x)| \leq \frac{M L^n}{(n+1)!} h^{n+1}
$$

---

### §5.2 解的延拓定理

#### 一、局部解与延拓的概念

皮卡存在唯一性定理给出的是**局部解**，即解只在 $x_0$ 的一个小邻域内存在。我们希望将解尽可能地向左右两边延拓，得到更大范围的解。

**定义**：设 $y = \varphi(x)$ 是初值问题 (1) 在区间 $[a, b]$ 上的解，若存在区间 $[a_1, b_1] \supset [a, b]$，以及定义在 $[a_1, b_1]$ 上的解 $y = \psi(x)$，使得当 $x \in [a, b]$ 时，$\psi(x) = \varphi(x)$，则称解 $\varphi(x)$ 可以**延拓**到区间 $[a_1, b_1]$ 上，并称 $\psi(x)$ 是 $\varphi(x)$ 的一个**延拓**。

#### 二、饱和解

**定义**：无法再继续延拓的解称为**饱和解**，饱和解的最大存在区间称为**最大存在区间**。

**性质**：在开区域 $G$ 内满足局部利普希茨条件的方程，其饱和解的最大存在区间必为**开区间**。

#### 三、解的延拓定理

**定理**：设函数 $f(x, y)$ 在开区域 $G \subset \mathbb{R}^2$ 内连续，且关于 $y$ 满足局部利普希茨条件，则对任意 $(x_0, y_0) \in G$，初值问题 (1) 的解 $y = \varphi(x)$ 可以延拓，直到点 $(x, \varphi(x))$ 任意接近区域 $G$ 的边界。

#### 四、无界区域上的延拓

若 $G$ 是无界区域，则初值问题的解向 $x$ 增大的方向延拓时，有以下两种情况：

1. 解可以延拓到区间 $[x_0, +\infty)$；
2. 解只能延拓到有限区间 $[x_0, m)$，此时当 $x \to m^-$ 时，要么 $y = \varphi(x)$ 无界，要么 $(x, \varphi(x))$ 趋于 $G$ 的边界。

---

### §5.3 解对初值和参数的连续依赖性

#### 一、解对初值的连续依赖性

**定理**：设函数 $f(x, y)$ 在区域 $G$ 内连续，且关于 $y$ 满足局部利普希茨条件，$(x_0, y_0) \in G$，$y = \varphi(x, x_0, y_0)$ 是初值问题 (1) 的解，定义在区间 $[a, b]$ 上。则对任意 $\varepsilon > 0$，存在 $\delta > 0$，使得当

$$
(\bar{x}_0 - x_0)^2 + (\bar{y}_0 - y_0)^2 < \delta^2
$$

时，初值问题

$$
\begin{cases}
\dfrac{dy}{dx} = f(x, y) \\[6pt]
y(\bar{x}_0) = \bar{y}_0
\end{cases}
$$

的解 $y = \varphi(x, \bar{x}_0, \bar{y}_0)$ 也定义在区间 $[a, b]$ 上，且

$$
|\varphi(x, \bar{x}_0, \bar{y}_0) - \varphi(x, x_0, y_0)| < \varepsilon,\quad \forall x \in [a, b]
$$

#### 二、解对参数的连续依赖性

考虑含参数 $\lambda$ 的微分方程初值问题：

$$
\begin{cases}
\dfrac{dy}{dx} = f(x, y, \lambda) \\[6pt]
y(x_0) = y_0
\end{cases} \tag{2}
$$

**定理**：设函数 $f(x, y, \lambda)$ 在区域

$$
G_\lambda = \{ (x, y, \lambda) \mid (x, y) \in G,\ |\lambda - \lambda_0| \leq c \}
$$

内连续，且关于 $y$ 满足对 $x$ 和 $\lambda$ 一致的利普希茨条件，则初值问题 (2) 的解 $y = \varphi(x, \lambda)$ 作为 $x, \lambda$ 的函数是连续的。

#### 三、解对初值和参数的可微性

**定理**：若函数 $f(x, y, \lambda)$ 及其偏导数 $\dfrac{\partial f}{\partial y}, \dfrac{\partial f}{\partial \lambda}$ 在区域 $G_\lambda$ 内连续，则初值问题 (2) 的解 $y = \varphi(x, \lambda)$ 对 $x_0, y_0$ 和 $\lambda$ 是连续可微的。

---

## 第六章 奇解

### §6.1 奇解的定义与几何意义

#### 一、奇解的定义

**定义**：微分方程的**奇解**是指在该解的每一点上，都有方程的另一个解与它相切。换句话说，奇解是方程的积分曲线族的**包络**。

> 注：奇解本身是方程的解，但它不满足解的唯一性，即在奇解的每一点处，解都不唯一。

#### 二、包络的定义

**定义**：给定单参数曲线族 $\Phi(x, y, C) = 0$，若存在一条连续可微曲线 $\Gamma$，它本身不包含在曲线族中，但在 $\Gamma$ 的每一点处，都有曲线族中的一条曲线与它相切，则称 $\Gamma$ 是该曲线族的**包络**。

---

### §6.2 求奇解的方法

#### 一、P - 判别式法

对于一阶隐式微分方程

$$
F(x, y, y') = 0 \tag{3}
$$

令 $p = y'$，则方程组

$$
\begin{cases}
F(x, y, p) = 0 \\
F_p(x, y, p) = 0
\end{cases} \tag{4}
$$

所确定的曲线称为方程 (3) 的**P - 判别曲线**。

**定理**：若方程 (3) 的奇解存在，则它必包含在 P - 判别曲线中。

> 注：P - 判别曲线不一定是奇解，需要验证它是否是方程的解，以及在该曲线上的每一点处解是否不唯一。

#### 二、C - 判别式法

若已知方程 (3) 的通解为 $\Phi(x, y, C) = 0$，则方程组

$$
\begin{cases}
\Phi(x, y, C) = 0 \\
\Phi_C(x, y, C) = 0
\end{cases} \tag{5}
$$

所确定的曲线称为**C - 判别曲线**。

**定理**：若曲线族 $\Phi(x, y, C) = 0$ 有包络，则包络必包含在 C - 判别曲线中。

**包络的充分条件**：若 C - 判别曲线 $x = x(C), y = y(C)$ 连续可微，且满足

$$
(\Phi_x(x(C), y(C), C))^2 + (\Phi_y(x(C), y(C), C))^2 \neq 0
$$

则该 C - 判别曲线是曲线族的包络，从而是方程的奇解。

**例 1**：求方程 $y = (y')^2 - x y' + \dfrac{x^2}{2}$ 的奇解。

解：令 $p = y'$，则方程为 $y = p^2 - x p + \dfrac{x^2}{2}$。

P - 判别式为：

$$
\begin{cases}
y = p^2 - x p + \dfrac{x^2}{2} \\[6pt]
2p - x = 0
\end{cases}
$$

解得 $p = \dfrac{x}{2}$，代入第一个方程得 $y = \dfrac{x^2}{4}$。

验证：将 $y = \dfrac{x^2}{4}$ 代入原方程，左边 $= \dfrac{x^2}{4}$，右边 $= \left( \dfrac{x}{2} \right)^2 - x \cdot \dfrac{x}{2} + \dfrac{x^2}{2} = \dfrac{x^2}{4}$，等式成立。

又因为在曲线 $y = \dfrac{x^2}{4}$ 上的每一点处，都有通解中的曲线 $y = \dfrac{x^2}{2} - Cx + C^2$ 与它相切，所以 $y = \dfrac{x^2}{4}$ 是方程的奇解。

---

## 第七章 拉普拉斯 (Laplace) 变换法

### §7.1 拉普拉斯变换的定义与存在性

#### 一、拉普拉斯变换的定义

**定义**：设函数 $f(t)$ 在 $[0, +\infty)$ 上有定义，若广义积分

$$
F(s) = \int_{0}^{+\infty} e^{-st} f(t) \, dt
$$

在复平面 $s$ 的某一区域内收敛，则称 $F(s)$ 为 $f(t)$ 的**拉普拉斯变换**，记为 $\mathcal{L}[f(t)] = F(s)$，并称 $f(t)$ 为 $F(s)$ 的**原函数**，$F(s)$ 为 $f(t)$ 的**象函数**。

#### 二、拉普拉斯变换的存在性定理

**定理**：若函数 $f(t)$ 满足以下两个条件：

1. $f(t)$ 在 $[0, +\infty)$ 上分段连续；
2. $f(t)$ 是指数增长的，即存在常数 $M > 0$ 和 $s_0 \geq 0$，使得

   $$
   |f(t)| \leq M e^{s_0 t},\quad \forall t \geq 0
   $$

则 $f(t)$ 的拉普拉斯变换 $F(s)$ 在 $\operatorname{Re}(s) > s_0$ 上存在且解析。

---

### §7.2 拉普拉斯变换的基本性质

设 $\mathcal{L}[f(t)] = F(s)$，$\mathcal{L}[g(t)] = G(s)$，则有以下性质：

1. **线性性质**：

   $$
   \mathcal{L}[\alpha f(t) + \beta g(t)] = \alpha F(s) + \beta G(s), \quad \alpha, \beta \text{ 为常数}
   $$

2. **微分性质**：

   $$
   \mathcal{L}[f'(t)] = s F(s) - f(0)
   $$

   更一般地，

   $$
   \mathcal{L}[f^{(n)}(t)] = s^n F(s) - s^{n-1} f(0) - s^{n-2} f'(0) - \cdots - f^{(n-1)}(0)
   $$

3. **积分性质**：

   $$
   \mathcal{L}\!\left[ \int_{0}^{t} f(\tau) \, d\tau \right] = \frac{1}{s} F(s)
   $$

4. **位移性质**：

   $$
   \mathcal{L}[e^{at} f(t)] = F(s - a)
   $$

5. **延迟性质**：

   $$
   \mathcal{L}[f(t - \tau) u(t - \tau)] = e^{-s\tau} F(s), \quad \tau \geq 0
   $$

   其中 $u(t)$ 是单位阶跃函数。

6. **象函数的微分性质**：

   $$
   \mathcal{L}[t^n f(t)] = (-1)^n F^{(n)}(s)
   $$

7. **卷积性质**：

   $$
   \mathcal{L}[(f * g)(t)] = F(s) G(s)
   $$

   其中卷积 $(f * g)(t) = \displaystyle\int_{0}^{t} f(\tau) g(t - \tau) \, d\tau$。

---

### §7.3 常见函数的拉普拉斯变换

| 原函数 $f(t)$ | 象函数 $F(s)$ | 收敛域 |
|---|---|---|
| $1$ | $\dfrac{1}{s}$ | $\operatorname{Re}(s) > 0$ |
| $t^n$（$n$ 为正整数） | $\dfrac{n!}{s^{n+1}}$ | $\operatorname{Re}(s) > 0$ |
| $e^{at}$ | $\dfrac{1}{s - a}$ | $\operatorname{Re}(s) > \operatorname{Re}(a)$ |
| $\sin \omega t$ | $\dfrac{\omega}{s^2 + \omega^2}$ | $\operatorname{Re}(s) > 0$ |
| $\cos \omega t$ | $\dfrac{s}{s^2 + \omega^2}$ | $\operatorname{Re}(s) > 0$ |
| $t e^{at}$ | $\dfrac{1}{(s - a)^2}$ | $\operatorname{Re}(s) > \operatorname{Re}(a)$ |
| $t^n e^{at}$（$n$ 为正整数） | $\dfrac{n!}{(s - a)^{n+1}}$ | $\operatorname{Re}(s) > \operatorname{Re}(a)$ |
| $e^{at} \sin \omega t$ | $\dfrac{\omega}{(s - a)^2 + \omega^2}$ | $\operatorname{Re}(s) > \operatorname{Re}(a)$ |
| $e^{at} \cos \omega t$ | $\dfrac{s - a}{(s - a)^2 + \omega^2}$ | $\operatorname{Re}(s) > \operatorname{Re}(a)$ |

---

### §7.4 拉普拉斯逆变换

**定义**：若 $F(s)$ 是 $f(t)$ 的拉普拉斯变换，则称 $f(t)$ 为 $F(s)$ 的**拉普拉斯逆变换**，记为 $\mathcal{L}^{-1}[F(s)] = f(t)$。

**求逆变换的常用方法**：

1. **部分分式分解法**：将有理函数 $F(s)$ 分解为部分分式之和，然后利用常见函数的拉普拉斯变换表求逆变换。
2. **卷积定理**：利用卷积性质求逆变换。

---

### §7.5 用拉普拉斯变换解常微分方程初值问题

**基本思想**：通过拉普拉斯变换将微分方程转化为代数方程，求解代数方程得到象函数，再通过拉普拉斯逆变换得到原方程的解。

**求解步骤**：

1. 对微分方程两边取拉普拉斯变换，利用微分性质将其转化为关于象函数 $Y(s)$ 的代数方程；
2. 解代数方程，求出象函数 $Y(s)$；
3. 对 $Y(s)$ 取拉普拉斯逆变换，得到原方程的解 $y(t)$。

**例 2**：用拉普拉斯变换解初值问题

$$
\begin{cases}
y'' + y = \sin t \\[4pt]
y(0) = 0,\ y'(0) = -\dfrac{1}{2}
\end{cases}
$$

解：对方程两边取拉普拉斯变换，得

$$
s^2 Y(s) - s y(0) - y'(0) + Y(s) = \frac{1}{s^2 + 1}
$$

代入初始条件 $y(0) = 0,\ y'(0) = -\dfrac{1}{2}$，得

$$
s^2 Y(s) + \frac{1}{2} + Y(s) = \frac{1}{s^2 + 1}
$$

整理得

$$
(s^2 + 1) Y(s) = \frac{1}{s^2 + 1} - \frac{1}{2}
$$

解得

$$
Y(s) = \frac{1}{(s^2 + 1)^2} - \frac{1}{2(s^2 + 1)}
$$

取拉普拉斯逆变换，利用公式

$$
\mathcal{L}^{-1}\!\left[ \frac{1}{(s^2 + \omega^2)^2} \right] = \frac{1}{2\omega^3} (\sin \omega t - \omega t \cos \omega t)
$$

得

$$
y(t) = \frac{1}{2} (\sin t - t \cos t) - \frac{1}{2} \sin t = -\frac{t}{2} \cos t
$$