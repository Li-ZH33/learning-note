## §1 偏导数与全微分

### 1.1 一元函数导数回顾

一元实值函数 $y=f(x)$ 在 $x_0$ 附近有定义（在某个 $(x_0-\delta,x_0+\delta)$ 有定义），称 $f$ 在 $x_0$ 处可导，如果极限

$$
\lim_{\Delta x\to 0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}
$$

存在（有限数）。

### 1.2 二元函数方向导数

二元函数 $z=f(\boldsymbol{u})=f(x,y)$ 在 $\boldsymbol{u}_0=(x_0,y_0)$ 附近有定义（在某个 $B(\boldsymbol{u}_0,\delta)$ 上有定义），$\forall\boldsymbol{v}\in\mathbb{R}^2$，若

$$
\lim_{t\to 0}\frac{f(\boldsymbol{u}_0+t\boldsymbol{v})-f(\boldsymbol{u}_0)}{t}
$$

存在（有限数），则称其为 $f$ 在 $\boldsymbol{u}_0$ 处沿 $\boldsymbol{v}$ 的方向导数，记作 $Df(\boldsymbol{u}_0,\boldsymbol{v})$ 或 $\displaystyle\left.\frac{\partial f}{\partial\boldsymbol{v}}\right|_{\boldsymbol{u}_0}$。

**注**：本定义与教材有两点不同：

1. $t\to 0$ 允许沿 $\boldsymbol{v}$ 方向两侧趋于 $\boldsymbol{u}_0$；教材中 $t\to 0^+$，只允许沿 $\boldsymbol{v}$ 方向单侧趋于 $\boldsymbol{u}_0$。
2. $\boldsymbol{v}$ 不要求为单位向量，关键是方向，相差一个常数倍不影响方向。

### 1.3 偏导数

特别地，取 $\boldsymbol{v}=\boldsymbol{e}_1=(1,0)$，则 $Df(\boldsymbol{u}_0,\boldsymbol{e}_1)$ 就是 $f$ 在 $\boldsymbol{u}_0$ 处关于 $x$ 的偏导数。

**定义**：二元函数 $z=f(x,y)$ 在 $\boldsymbol{u}_0=(x_0,y_0)$ 附近有定义，若

$$
\lim_{\Delta x\to 0}\frac{f(x_0+\Delta x,y_0)-f(x_0,y_0)}{\Delta x}
$$

存在（有限数），则称其为 $f$ 在 $\boldsymbol{u}_0$ 处关于 $x$ 的偏导数，记作 $\displaystyle\frac{\partial f}{\partial x}(x_0,y_0)$ 或 $f_x(x_0,y_0)$。

同理可定义 $f$ 在 $\boldsymbol{u}_0$ 处关于 $y$ 的偏导数 $\displaystyle\frac{\partial f}{\partial y}(x_0,y_0)$ 或 $f_y(x_0,y_0)$。

若 $\forall\boldsymbol{u}\in D$，$f$ 在 $\boldsymbol{u}$ 处均可偏导，则称 $f$ 在 $D$ 上可偏导。

### 1.4 Gâteaux 导数

假设 $f$ 在 $\boldsymbol{u}_0$ 处沿任一方向的方向导数都存在，可定义映射 $T:\mathbb{R}^2\to\mathbb{R}$，$T(\boldsymbol{v})=Df(\boldsymbol{u}_0,\boldsymbol{v})$。容易证得 $T(\lambda\boldsymbol{v})=\lambda T(\boldsymbol{v})$（$T$ 是齐次的），但 $T(\boldsymbol{v}_1+\boldsymbol{v}_2)=T(\boldsymbol{v}_1)+T(\boldsymbol{v}_2)$ 不一定成立。

**定义**：若 $f$ 在 $\boldsymbol{u}_0$ 处沿任一方向的方向导数都存在，且 $T:\mathbb{R}^2\to\mathbb{R}$ 是线性的，则称 $f$ 在 $\boldsymbol{u}_0$ 处 **Gâteaux 可微**（G-可微），此时 $T$ 称为 $f$ 在 $\boldsymbol{u}_0$ 处的 Gâteaux 导数，记作 $Df(\boldsymbol{u}_0)$。

**注**：

- $T$ 是线性的 $\Leftrightarrow\exists$ 矩阵 $A$，使得 $T(\boldsymbol{v})=Df(\boldsymbol{u}_0,\boldsymbol{v})=A\boldsymbol{v},\forall\boldsymbol{v}\in\mathbb{R}^2$，因此也可将 $A$ 称为 $f$ 在 $\boldsymbol{u}_0$ 处的 Gâteaux 导数。
- G-可微不能推出 $f$ 在该点连续。

**性质**：若 $f$ 在 $\boldsymbol{u}_0$ 处是 G-可微的，则

$$
Df(\boldsymbol{u}_0)=\left(\frac{\partial f}{\partial x}(\boldsymbol{u}_0),\ \frac{\partial f}{\partial y}(\boldsymbol{u}_0)\right)
$$

于是

$$
Df(\boldsymbol{u}_0,\boldsymbol{v})=\frac{\partial f}{\partial x}(\boldsymbol{u}_0)\cdot v_1+\frac{\partial f}{\partial y}(\boldsymbol{u}_0)\cdot v_2
$$

### 1.5 Fréchet 可微

**定义**：开集 $D\subset\mathbb{R}^2$，$\boldsymbol{u}_0\in D$，$f:D\to\mathbb{R}$。称 $f$ 在 $\boldsymbol{u}_0$ 处是 **Fréchet 可微**（F-可微），如果存在与 $\boldsymbol{u}_0$ 有关但与 $\Delta\boldsymbol{u}$ 无关的 $A\in M_{1\times 2}(\mathbb{R})$，使得

$$
f(\boldsymbol{u}_0+\Delta\boldsymbol{u})-f(\boldsymbol{u}_0)=A\Delta\boldsymbol{u}+o(\|\Delta\boldsymbol{u}\|)
$$

此时 $A$ 是 $f$ 在 $\boldsymbol{u}_0$ 处的 Fréchet 导数，记作 $f'(\boldsymbol{u}_0)$。

**全微分形式**：

$$
dz = \frac{\partial f}{\partial x}(\boldsymbol{u}_0)\,dx + \frac{\partial f}{\partial y}(\boldsymbol{u}_0)\,dy
$$

**性质**：

1. F-可微 $\Rightarrow$ 连续
2. F-可微 $\Rightarrow$ G-可微 $\Rightarrow$ 任意方向导数存在 $\Rightarrow$ 可偏导
3. 若 $f$ 在 $\boldsymbol{u}_0$ 处是 Fréchet 可微，则在 $\boldsymbol{u}_0$ 也是 G-可微，且

$$
f'(\boldsymbol{u}_0)=Df(\boldsymbol{u}_0)=\left(\frac{\partial f}{\partial x}(\boldsymbol{u}_0),\ \frac{\partial f}{\partial y}(\boldsymbol{u}_0)\right)
$$

**几个重要例子**：

1.  $$
    f(x,y)=\begin{cases}
    \dfrac{x^2 y}{x^4+y^2}, & (x,y)\neq(0,0)\\[6pt]
    0, & (x,y)=(0,0)
    \end{cases}
    $$
    $f$ 在 $(0,0)$ 处不连续，因此不是 F-可微，但是 G-可微。

2.  $$
    f(x,y)=\begin{cases}
    \dfrac{xy}{x^2+y^2}, & (x,y)\neq(0,0)\\[6pt]
    0, & (x,y)=(0,0)
    \end{cases}
    $$
    $f$ 在 $(0,0)$ 处不连续，因此不是 F-可微，也不是 G-可微，但可偏导。

3.  $$
    f(x,y)=\begin{cases}
    \dfrac{2xy^3}{x^2+y^4}, & (x,y)\neq(0,0)\\[6pt]
    0, & (x,y)=(0,0)
    \end{cases}
    $$
    $f$ 在 $(0,0)$ 处不是 F-可微，但是连续且 G-可微。

**充分条件**：若 $z=f(x,y)$ 在 $\boldsymbol{u}_0$ 附近都存在偏导数且偏导数在 $\boldsymbol{u}_0$ 处连续，则 $f$ 在 $\boldsymbol{u}_0$ 处 F-可微。

### 1.6 向量值函数的微分

开集 $D\subset\mathbb{R}^n$，$\boldsymbol{x}_0=(x_1^0,x_2^0,\cdots,x_n^0)\in D$，$\boldsymbol{f}:D\to\mathbb{R}^m$，$\boldsymbol{f}(\boldsymbol{x})=(f_1(\boldsymbol{x}),f_2(\boldsymbol{x}),\cdots,f_m(\boldsymbol{x}))$。

**定义**：称 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处 G-可微，如果 $\exists A\in M_{m\times n}(\mathbb{R})$，使得

$$
D\boldsymbol{f}(\boldsymbol{x}_0,\boldsymbol{v})=\lim_{t\to 0}\frac{\boldsymbol{f}(\boldsymbol{x}_0+t\boldsymbol{v})-\boldsymbol{f}(\boldsymbol{x}_0)}{t}=A\boldsymbol{v},\quad \forall\boldsymbol{v}\in\mathbb{R}^n
$$

此时 $A$ 称为 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处的 G-导数，记作 $D\boldsymbol{f}(\boldsymbol{x}_0)$。

特别地，$D\boldsymbol{f}(\boldsymbol{x}_0,\boldsymbol{e}_j)=\dfrac{\partial\boldsymbol{f}}{\partial x_j}(\boldsymbol{x}_0)$，即 $\boldsymbol{f}$ 关于 $x_j$ 的偏导数。

**定义**：称 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处 Fréchet 可微，如果 $\exists A\in M_{m\times n}(\mathbb{R})$，使得

$$
\boldsymbol{f}(\boldsymbol{x}_0+\Delta\boldsymbol{x})-\boldsymbol{f}(\boldsymbol{x}_0)=A\Delta\boldsymbol{x}+o(\|\Delta\boldsymbol{x}\|)
$$

此时 $A$ 是 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处的 Fréchet 导数，记作 $\boldsymbol{f}'(\boldsymbol{x}_0)$。

**性质**：

- $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处 G-可微 $\Leftrightarrow$ 每个分量 $f_i$ 在 $\boldsymbol{x}_0$ 处 G-可微
- 若 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处 G-可微，则

$$
D\boldsymbol{f}(\boldsymbol{x}_0)=A=\left(\frac{\partial f_i}{\partial x_j}(\boldsymbol{x}_0)\right)_{m\times n}
$$

**定义（Jacobi 矩阵）**：$\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处可偏导，称矩阵 $\displaystyle\left(\frac{\partial f_i}{\partial x_j}(\boldsymbol{x}_0)\right)_{m\times n}$ 为 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处的 Jacobi 矩阵，记作 $J_{\boldsymbol{f}}(\boldsymbol{x}_0)$。

**性质**：若 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处 F-可微，则 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 处连续且 G-可微，而且 $\boldsymbol{f}'(\boldsymbol{x}_0)=J_{\boldsymbol{f}}(\boldsymbol{x}_0)$。

### 1.7 高阶偏导数与高阶微分

**定义（二阶偏导数）**：设 $f:D\to\mathbb{R}$ 在 $D$ 上有一阶偏导数 $f_x(x,y)$ 和 $f_y(x,y)$，若这两个偏导数在 $D$ 上也可偏导，则称 $f$ 在 $D$ 上二阶可偏导，记：

- $\dfrac{\partial}{\partial x}\!\left(\dfrac{\partial f}{\partial x}\right)=\dfrac{\partial^2 f}{\partial x^2}=f_{xx}$
- $\dfrac{\partial}{\partial y}\!\left(\dfrac{\partial f}{\partial x}\right)=\dfrac{\partial^2 f}{\partial y\partial x}=f_{xy}$
- $\dfrac{\partial}{\partial x}\!\left(\dfrac{\partial f}{\partial y}\right)=\dfrac{\partial^2 f}{\partial x\partial y}=f_{yx}$
- $\dfrac{\partial}{\partial y}\!\left(\dfrac{\partial f}{\partial y}\right)=\dfrac{\partial^2 f}{\partial y^2}=f_{yy}$

**定理（混合偏导数相等）**：若 $f_{xy}$ 与 $f_{yx}$ 在 $\boldsymbol{u}_0=(x_0,y_0)$ 连续，则

$$
f_{xy}(x_0,y_0)=f_{yx}(x_0,y_0)
$$

**定义（二阶微分）**：$z=f(x,y)$ 在 $D\subset\mathbb{R}^2$ 上有一阶连续偏导数，则 $dz$ 的微分称为 $z$ 的二阶微分，记作 $d^2z$。

**定义（高阶微分）**：二阶及二阶以上的微分称为高阶微分，

$$
d^k z = \left(dx\cdot\frac{\partial}{\partial x}+dy\cdot\frac{\partial}{\partial y}\right)^{\!k} z
$$

### 1.8 梯度与方向导数

**定义（梯度向量）**：$z=f(x,y)$ 在 $D\subset\mathbb{R}^2$ 上可偏导，称

$$
\nabla f(x,y) = \bigl(f_x(x,y),\,f_y(x,y)\bigr)
$$

为 $f$ 的梯度向量。

**方向导数与梯度的关系**：设 $f$ 在 $\boldsymbol{u}_0=(x_0,y_0)$ 是 G-可微的，$\forall\boldsymbol{v}=(v_1,v_2)\in\mathbb{R}^2$ 且 $\|\boldsymbol{v}\|=1$，则

$$
\frac{\partial f}{\partial\boldsymbol{v}}(x_0,y_0)=Df(\boldsymbol{u}_0,\boldsymbol{v})=\nabla f(x_0,y_0)\cdot\boldsymbol{v}
= \|\nabla f(x_0,y_0)\|\cos\theta
$$

其中 $\theta$ 是 $\nabla f(x_0,y_0)$ 与 $\boldsymbol{v}$ 的夹角。

**结论**：

- 当 $\theta=0$（$\boldsymbol{v}$ 与梯度同向）时，方向导数最大，为 $\|\nabla f(x_0,y_0)\|$
- 当 $\theta=\pi$（$\boldsymbol{v}$ 与梯度反向）时，方向导数最小，为 $-\|\nabla f(x_0,y_0)\|$

**定义（增长最快方向）**：称 $\boldsymbol{v}\in S^2=\{\boldsymbol{x}\in\mathbb{R}^2\mid\|\boldsymbol{x}\|=1\}$ 是 $f$ 在 $\boldsymbol{u}_0$ 处增长最快的方向，如果存在 $\delta>0$，使得当 $t\in(0,\delta)$ 时，有

$$
f(\boldsymbol{u}_0+t\boldsymbol{v})-f(\boldsymbol{u}_0)\ge f(\boldsymbol{u}_0+t\boldsymbol{u}')-f(\boldsymbol{u}_0),\quad \forall\boldsymbol{u}'\in S^2
$$

---

## §2 多元复合函数的求导法则

### 2.1 链式法则

设 $D_g\xrightarrow{g}D_f\xrightarrow{f}\mathbb{R}$，其中 $(u,v)\mapsto\bigl(x(u,v),y(u,v)\bigr)\mapsto f\bigl(x(u,v),y(u,v)\bigr)$，$D_g,D_f$ 是 $\mathbb{R}^2$ 中的开集。

**定理**：若 $g$ 在 $(u_0,v_0)$ 处可偏导且 $f$ 在 $(x_0,y_0)=\bigl(x(u_0,v_0),y(u_0,v_0)\bigr)$ 处 Fréchet 可微，则 $f\circ g$ 在 $(u_0,v_0)$ 处可偏导，并且有

$$
\frac{\partial z}{\partial u}(u_0,v_0)=
\frac{\partial z}{\partial x}(x_0,y_0)\cdot\frac{\partial x}{\partial u}(u_0,v_0)+
\frac{\partial z}{\partial y}(x_0,y_0)\cdot\frac{\partial y}{\partial u}(u_0,v_0)
$$

$$
\frac{\partial z}{\partial v}(u_0,v_0)=
\frac{\partial z}{\partial x}(x_0,y_0)\cdot\frac{\partial x}{\partial v}(u_0,v_0)+
\frac{\partial z}{\partial y}(x_0,y_0)\cdot\frac{\partial y}{\partial v}(u_0,v_0)
$$

**雅可比矩阵形式**：

$$
J_{f\circ g}(u_0,v_0)=f'(x_0,y_0)\cdot J_g(u_0,v_0)
$$

### 2.2 一般情形的推广

设 $z=f(y_1,y_2,\cdots,y_m)$，$\boldsymbol{y}=\boldsymbol{g}(\boldsymbol{x})=\bigl(y_1(x_1,\cdots,x_n),\cdots,y_m(x_1,\cdots,x_n)\bigr)$，$D_{\boldsymbol{g}}\xrightarrow{\boldsymbol{g}}D_{\boldsymbol{f}}\xrightarrow{\boldsymbol{f}}\mathbb{R}$。

**定理**：若 $\boldsymbol{g}$ 在 $\boldsymbol{x}_0$ 处可偏导，$f$ 在 $\boldsymbol{y}_0=\boldsymbol{g}(\boldsymbol{x}_0)$ 处 F-可微，则 $f\circ\boldsymbol{g}$ 在 $\boldsymbol{x}_0$ 处可偏导，并有

$$
\frac{\partial z}{\partial x_i}(\boldsymbol{x}_0)=\sum_{j=1}^{m}
\frac{\partial z}{\partial y_j}(\boldsymbol{y}_0)\cdot\frac{\partial y_j}{\partial x_i}(\boldsymbol{x}_0),\quad i=1,2,\cdots,n
$$

**雅可比矩阵形式**：

$$
J_{f\circ\boldsymbol{g}}(\boldsymbol{x}_0)=f'(\boldsymbol{y}_0)\cdot J_{\boldsymbol{g}}(\boldsymbol{x}_0)
$$

### 2.3 一阶微分形式不变性

设 $z=f(x,y)$，$(x,y)=\boldsymbol{g}(u,v)$，假设 $f,\boldsymbol{g}$ 有连续偏导数，则

$$
dz = \frac{\partial z}{\partial u}du+\frac{\partial z}{\partial v}dv
    = \frac{\partial z}{\partial x}dx+\frac{\partial z}{\partial y}dy
$$

即无论 $x,y$ 是自变量还是中间变量，一阶微分的形式保持不变。

### 2.4 中值定理

**定理**：设 $D\subset\mathbb{R}^2$ 是凸开集，$f$ 在 $D$ 上 F-可微，$(x_0,y_0),(x_0+\Delta x,y_0+\Delta y)\in D$，则存在 $\theta\in(0,1)$，使得

$$
f(x_0+\Delta x,y_0+\Delta y)-f(x_0,y_0)=
f_x(x_0+\theta\Delta x,y_0+\theta\Delta y)\Delta x+
f_y(x_0+\theta\Delta x,y_0+\theta\Delta y)\Delta y
$$

**推论**：若 $f$ 在 $D$ 上的偏导数恒为 $0$，则 $f$ 在 $D$ 上是常值函数。

---

## §3 Taylor 公式

### 3.1 基本概念

**定义（$k$ 阶连续偏导数）**：$D\subset\mathbb{R}^n$，$\boldsymbol{f}:D\to\mathbb{R}^m$。如果 $\boldsymbol{f}$ 在 $D$ 上具有 $k$ 阶连续偏导数，则记 $\boldsymbol{f}\in C^k(D)$。

### 3.2 二元函数的 Taylor 公式

**定理（带 Lagrange 余项的 Taylor 公式）**：设 $f(x,y)$ 在 $(x_0,y_0)$ 的某个邻域 $U$ 上有 $k+1$ 阶连续偏导数（即 $f\in C^{k+1}(U)$），则对任意 $(x_0+\Delta x,y_0+\Delta y)\in U$，有

$$
\begin{aligned}
f(x_0+\Delta x,y_0+\Delta y)=&
f(x_0,y_0) \\
&+\left(\Delta x\frac{\partial}{\partial x}+\Delta y\frac{\partial}{\partial y}\right)f(x_0,y_0) \\
&+\frac{1}{2!}\left(\Delta x\frac{\partial}{\partial x}+\Delta y\frac{\partial}{\partial y}\right)^{\!2}f(x_0,y_0) \\
&+\cdots \\
&+\frac{1}{k!}\left(\Delta x\frac{\partial}{\partial x}+\Delta y\frac{\partial}{\partial y}\right)^{\!k}f(x_0,y_0) \\
&+\frac{1}{(k+1)!}\left(\Delta x\frac{\partial}{\partial x}+\Delta y\frac{\partial}{\partial y}\right)^{\!k+1}f(x_0+\theta\Delta x,y_0+\theta\Delta y)
\end{aligned}
$$

其中 $\theta\in(0,1)$，最后一项称为 Lagrange 余项。

**定理（带 Peano 余项的 Taylor 公式）**：设二元函数 $f(x,y)$ 在 $(x_0,y_0)$ 附近是 $C^k$ 的，则

$$
f(x_0+\Delta x,y_0+\Delta y)=
\sum_{j=0}^{k}\frac{1}{j!}\left(\Delta x\frac{\partial}{\partial x}+\Delta y\frac{\partial}{\partial y}\right)^{\!j}f(x_0,y_0)
+o\!\left((\Delta x^2+\Delta y^2)^{k}\right)
$$

其中最后一项称为 Peano 余项。

---

## §4 隐函数

### 4.1 隐函数的概念

若给定 $x$，有唯一的一个 $y=y(x)$ 满足 $F(x,y(x))=0$，则称 $y=y(x)$ 是由方程 $F(x,y)=0$ 确定的隐函数。

**例**：对隐函数 $F(x,y)=y-x-\sin y=0$ 求 $y'$。

解：两边对 $x$ 求导，得

$$
F_x+F_y\cdot y'=0 \quad\Longrightarrow\quad y'=-\frac{F_x}{F_y}=\frac{1}{1-\cos y}
$$

### 4.2 隐函数存在定理

**定理（二元隐函数存在定理）**：二元函数 $F(x,y)$ 满足

1. $F(x_0,y_0)=0$
2. 存在 $(x_0,y_0)$ 的邻域 $U$，使得 $F\in C^1(U)$
3. $F_y(x_0,y_0)\neq 0$

则在 $(x_0,y_0)$ 附近可以从方程 $F(x,y)=0$ 唯一确定隐函数 $y=y(x)$，满足：

- $F(x,y(x))=0$ 且 $y_0=y(x_0)$
- $y=y(x)$ 在 $x_0$ 附近是 $C^1$ 的
- $y'(x)=-\dfrac{F_x(x,y)}{F_y(x,y)}$

**注**：

1. 若 $F\in C^k(U)$，则可推出 $y=y(x)$ 在 $x_0$ 附近是 $C^k$ 的。
2. 条件 3 中 $F_y(x_0,y_0)\neq 0$ 是关键，它保证了在局部可以解出 $y$ 关于 $x$ 的表达式。

### 4.3 隐函数存在定理的推广

**定理（$n$ 元 $m$ 个方程的隐函数存在定理）**：设 $\boldsymbol{x}=(x_1,\cdots,x_n)\in\mathbb{R}^n$，$\boldsymbol{y}=(y_1,\cdots,y_m)\in\mathbb{R}^m$，$\boldsymbol{F}(\boldsymbol{x},\boldsymbol{y})=(F_1(\boldsymbol{x},\boldsymbol{y}),\cdots,F_m(\boldsymbol{x},\boldsymbol{y}))$ 满足

1. $\boldsymbol{F}(\boldsymbol{x}_0,\boldsymbol{y}_0)=\boldsymbol{0}$
2. 存在 $(\boldsymbol{x}_0,\boldsymbol{y}_0)$ 的一个邻域 $U$，使得 $\boldsymbol{F}\in C^1(U)$
3. 雅可比矩阵 $\displaystyle\boldsymbol{F}_{\boldsymbol{y}}(\boldsymbol{x}_0,\boldsymbol{y}_0)=\left(\frac{\partial F_i}{\partial y_j}(\boldsymbol{x}_0,\boldsymbol{y}_0)\right)_{m\times m}$ 可逆

则存在 $\boldsymbol{x}_0$ 的一个邻域 $V$，使得在 $V$ 中 $\boldsymbol{F}(\boldsymbol{x},\boldsymbol{y})=\boldsymbol{0}$ 可以唯一确定一个关于 $\boldsymbol{x}$ 的隐函数 $\boldsymbol{y}=\boldsymbol{y}(\boldsymbol{x}):\mathbb{R}^n\to\mathbb{R}^m$，满足：

- $\boldsymbol{F}(\boldsymbol{x},\boldsymbol{y}(\boldsymbol{x}))=\boldsymbol{0}$ 且 $\boldsymbol{y}_0=\boldsymbol{y}(\boldsymbol{x}_0)$
- $\boldsymbol{y}=\boldsymbol{y}(\boldsymbol{x})$ 在 $V$ 中是 $C^1$ 的
- $J_{\boldsymbol{y}}(\boldsymbol{x})=-\bigl[\boldsymbol{F}_{\boldsymbol{y}}(\boldsymbol{x},\boldsymbol{y}(\boldsymbol{x}))\bigr]^{-1}\cdot\boldsymbol{F}_{\boldsymbol{x}}(\boldsymbol{x},\boldsymbol{y}(\boldsymbol{x}))$

### 4.4 反函数与逆映射定理

**定理（反函数定理）**：设 $y=f(x)$ 在 $x_0$ 附近是 $C^1$ 的，且 $f'(x_0)\neq 0$，则 $f$ 在 $x_0$ 附近有反函数 $x=f^{-1}(y)$，且

$$
(f^{-1})'\bigl(f(x_0)\bigr)\cdot f'(x_0)=1
$$

**定理（逆映射定理）**：设 $\boldsymbol{f}:D\to\mathbb{R}^n$，$\boldsymbol{f}\in C^1(D)$，$\boldsymbol{x}_0\in D$ 满足 $\boldsymbol{f}'(\boldsymbol{x}_0)$ 可逆，则 $\boldsymbol{f}$ 在 $\boldsymbol{x}_0$ 附近有逆映射 $\boldsymbol{x}=\boldsymbol{f}^{-1}(\boldsymbol{y})$，且 $\boldsymbol{f}^{-1}\in C^1$。

---

## §5 偏导数在几何中的应用

### 5.1 曲线的切线与法平面

#### 5.1.1 参数形式的曲线

设曲线 $L$ 的参数方程为

$$
\begin{cases}
x=x(t)\\
y=y(t)\\
z=z(t)
\end{cases},\quad t\in[\alpha,\beta]
$$

其中 $x(t),y(t),z(t)$ 是 $C^1$ 的，且 $x'(t_0),y'(t_0),z'(t_0)$ 不同时为 $0$。

- **切向量**：曲线在点 $P_0\bigl(x(t_0),y(t_0),z(t_0)\bigr)$ 处的切向量为

  $$
  \boldsymbol{T}=\bigl(x'(t_0),y'(t_0),z'(t_0)\bigr)
  $$

- **切线方程**：

  $$
  \frac{x-x_0}{x'(t_0)}=\frac{y-y_0}{y'(t_0)}=\frac{z-z_0}{z'(t_0)}
  $$

- **法平面方程**：过点 $P_0$ 且与切线垂直的平面称为法平面，其方程为

  $$
  x'(t_0)(x-x_0)+y'(t_0)(y-y_0)+z'(t_0)(z-z_0)=0
  $$

#### 5.1.2 一般形式的曲线（两个曲面的交线）

设曲线 $L$ 是两个曲面的交线：

$$
\begin{cases}
F(x,y,z)=0\\
G(x,y,z)=0
\end{cases}
$$

$P_0(x_0,y_0,z_0)$ 是 $L$ 上的点，且雅可比矩阵

$$
J=\begin{pmatrix}
F_x & F_y & F_z\\
G_x & G_y & G_z
\end{pmatrix}_{P_0}
$$

的秩为 $2$。不妨设 $\begin{vmatrix}F_y & F_z\\ G_y & G_z\end{vmatrix}\neq 0$，则曲线在 $P_0$ 处的切向量为

$$
\boldsymbol{T}=\left(
\begin{vmatrix}F_y & F_z\\ G_y & G_z\end{vmatrix},\ 
\begin{vmatrix}F_z & F_x\\ G_z & G_x\end{vmatrix},\ 
\begin{vmatrix}F_x & F_y\\ G_x & G_y\end{vmatrix}
\right)_{P_0}
$$

### 5.2 曲面的切平面与法线

#### 5.2.1 一般形式的曲面

设曲面 $S$ 的方程为 $F(x,y,z)=0$，$F$ 是 $C^1$ 的且 $F_x,F_y,F_z$ 不同时为 $0$。

- **法向量**：曲面在点 $P_0(x_0,y_0,z_0)$ 处的法向量为

  $$
  \boldsymbol{n}=\nabla F(x_0,y_0,z_0)=\bigl(F_x(x_0,y_0,z_0),F_y(x_0,y_0,z_0),F_z(x_0,y_0,z_0)\bigr)
  $$

- **切平面方程**：过点 $P_0$ 且与法向量垂直的平面称为切平面，其方程为

  $$
  F_x(x_0,y_0,z_0)(x-x_0)+F_y(x_0,y_0,z_0)(y-y_0)+F_z(x_0,y_0,z_0)(z-z_0)=0
  $$

- **法线方程**：过点 $P_0$ 且与切平面垂直的直线称为法线，其方程为

  $$
  \frac{x-x_0}{F_x(x_0,y_0,z_0)}=\frac{y-y_0}{F_y(x_0,y_0,z_0)}=\frac{z-z_0}{F_z(x_0,y_0,z_0)}
  $$

#### 5.2.2 参数形式的曲面

设曲面 $S$ 的参数方程为

$$
\begin{cases}
x=x(u,v)\\
y=y(u,v)\\
z=z(u,v)
\end{cases},\quad (u,v)\in D
$$

其中 $x(u,v),y(u,v),z(u,v)$ 是 $C^1$ 的，且雅可比矩阵

$$
\begin{pmatrix}
x_u & y_u & z_u\\
x_v & y_v & z_v
\end{pmatrix}
$$

的秩为 $2$。设 $P_0\bigl(x(u_0,v_0),y(u_0,v_0),z(u_0,v_0)\bigr)$ 是曲面上的点，则曲面在 $P_0$ 处的法向量为

$$
\boldsymbol{n}=\left(
\begin{vmatrix}y_u & z_u\\ y_v & z_v\end{vmatrix},\ 
\begin{vmatrix}z_u & x_u\\ z_v & x_v\end{vmatrix},\ 
\begin{vmatrix}x_u & y_u\\ x_v & y_v\end{vmatrix}
\right)_{(u_0,v_0)}
$$

---

## §6 无条件极值

### 6.1 极值点的定义

**定义**：设 $f:D\subset\mathbb{R}^n\to\mathbb{R}$，称 $\boldsymbol{x}_0\in D$ 是 $f$ 的极大（小）值点，如果存在 $\boldsymbol{x}_0$ 的邻域 $U\subset D$，使得对所有 $\boldsymbol{x}\in U$，有

$$
f(\boldsymbol{x})\le(\ge)\, f(\boldsymbol{x}_0)
$$

### 6.2 极值的必要条件（Fermat 引理）

**定理（二元函数 Fermat 引理）**：若 $f$ 在 $(x_0,y_0)$ 处可偏导且 $(x_0,y_0)$ 是 $f$ 的极值点，则

$$
f_x(x_0,y_0)=0,\quad f_y(x_0,y_0)=0
$$

**注**：

1. 偏导数为 $0$ 的点称为驻点，驻点不一定是极值点（反例：$f(x,y)=xy$ 在 $(0,0)$ 处）。
2. 偏导数不存在的点也可能是极值点。

### 6.3 极值的充分条件（Hessian 矩阵判别法）

**定义（Hessian 矩阵）**：设 $f$ 是 $C^2$ 的，称矩阵

$$
H_f(x_0,y_0)=
\begin{pmatrix}
f_{xx}(x_0,y_0) & f_{xy}(x_0,y_0)\\[4pt]
f_{yx}(x_0,y_0) & f_{yy}(x_0,y_0)
\end{pmatrix}
$$

为 $f$ 在 $(x_0,y_0)$ 处的 Hessian 矩阵，也记作 $\nabla^2 f(x_0,y_0)$。

**定理（二元函数极值充分条件）**：设二元函数 $z=f(x,y)$ 在 $(x_0,y_0)$ 附近是 $C^2$ 的，且 $(x_0,y_0)$ 是 $f$ 的驻点，则

1. 若 $H_f(x_0,y_0)$ 是正定的，则 $(x_0,y_0)$ 是极小值点
2. 若 $H_f(x_0,y_0)$ 是负定的，则 $(x_0,y_0)$ 是极大值点
3. 若 $H_f(x_0,y_0)$ 是不定的，则 $(x_0,y_0)$ 不是极值点
4. 若 $H_f(x_0,y_0)$ 是半正定或半负定的，则无法判断，需要进一步分析

**二元函数 Hessian 矩阵的判定方法**：

设 $A=f_{xx}(x_0,y_0)$，$B=f_{xy}(x_0,y_0)$，$C=f_{yy}(x_0,y_0)$，则

- 正定 $\Leftrightarrow A>0$ 且 $AC-B^2>0$
- 负定 $\Leftrightarrow A<0$ 且 $AC-B^2>0$
- 不定 $\Leftrightarrow AC-B^2<0$
- 半正定/半负定 $\Leftrightarrow AC-B^2=0$

### 6.4 $n$ 元函数的极值

**定理（$n$ 元函数极值充分条件）**：设 $n$ 元函数 $y=f(\boldsymbol{x})$ 在 $\boldsymbol{x}_0=(x_1^0,\cdots,x_n^0)$ 附近是 $C^2$ 的，且 $\boldsymbol{x}_0$ 是 $f$ 的驻点（即 $\nabla f(\boldsymbol{x}_0)=\boldsymbol{0}$），则

1. 若 $H_f(\boldsymbol{x}_0)$ 是正定的，则 $\boldsymbol{x}_0$ 是极小值点
2. 若 $H_f(\boldsymbol{x}_0)$ 是负定的，则 $\boldsymbol{x}_0$ 是极大值点
3. 若 $H_f(\boldsymbol{x}_0)$ 是不定的，则 $\boldsymbol{x}_0$ 不是极值点
4. 若 $H_f(\boldsymbol{x}_0)$ 是半正定或半负定的，则无法判断

---

## §7 条件极值问题与 Lagrange 乘数法

### 7.1 问题描述

求目标函数 $f(x,y,z)$ 在约束条件 $F(x,y,z)=0$ 和 $G(x,y,z)=0$ 下的极值。

### 7.2 Lagrange 乘数法

**基本思想**：将条件极值问题转化为无条件极值问题。

构造 Lagrange 函数：

$$
\mathcal{L}(x,y,z,\lambda,\mu)=f(x,y,z)-\lambda F(x,y,z)-\mu G(x,y,z)
$$

其中 $\lambda,\mu$ 称为 Lagrange 乘数。

**定理**：若 $(x_0,y_0,z_0)$ 是条件极值问题的极值点，且雅可比矩阵

$$
\begin{pmatrix}
F_x & F_y & F_z\\
G_x & G_y & G_z
\end{pmatrix}_{(x_0,y_0,z_0)}
$$

的秩为 $2$，则存在 $\lambda_0,\mu_0$，使得 $(x_0,y_0,z_0,\lambda_0,\mu_0)$ 是 $\mathcal{L}$ 的驻点，即满足方程组：

$$
\begin{cases}
\mathcal{L}_x = f_x-\lambda F_x-\mu G_x = 0\\
\mathcal{L}_y = f_y-\lambda F_y-\mu G_y = 0\\
\mathcal{L}_z = f_z-\lambda F_z-\mu G_z = 0\\
\mathcal{L}_\lambda = -F(x,y,z) = 0\\
\mathcal{L}_\mu = -G(x,y,z) = 0
\end{cases}
$$

### 7.3 一般情形的推广

求目标函数 $f(\boldsymbol{x})$（$\boldsymbol{x}\in\mathbb{R}^n$）在约束条件 $g_i(\boldsymbol{x})=0$（$i=1,2,\cdots,m$，$m<n$）下的极值。

构造 Lagrange 函数：

$$
\mathcal{L}(\boldsymbol{x},\lambda_1,\cdots,\lambda_m)=f(\boldsymbol{x})-\sum_{i=1}^{m}\lambda_i g_i(\boldsymbol{x})
$$

**定理**：若 $\boldsymbol{x}_0$ 是条件极值问题的极值点，且雅可比矩阵 $\boldsymbol{g}'(\boldsymbol{x}_0)=\left(\dfrac{\partial g_i}{\partial x_j}(\boldsymbol{x}_0)\right)_{m\times n}$ 的秩为 $m$，则存在 $\boldsymbol{\lambda}_0=(\lambda_1^0,\cdots,\lambda_m^0)\in\mathbb{R}^m$，使得 $(\boldsymbol{x}_0,\boldsymbol{\lambda}_0)$ 是 $\mathcal{L}$ 的驻点。

---

# 第十三章 重积分

## §1 有界闭区域上的重积分

### 1.1 Jordan 测度

**定义（Jordan 测度）**：设 $D\subset\mathbb{R}^2$ 是有界集，用边长为 $\dfrac{1}{2^k}$ 的正方形网格覆盖平面，记

- $\underline{D}_k=\bigcup\{Q\in\mathcal{Q}_k\mid Q\subset D\}$（完全包含在 $D$ 内的正方形集合，内网格）
- $\overline{D}_k=\bigcup\{Q\in\mathcal{Q}_k\mid Q\cap D\neq\varnothing\}$（与 $D$ 相交的正方形集合，外网格）

记 $|\underline{D}_k|$ 为 $\underline{D}_k$ 的面积，$|\overline{D}_k|$ 为 $\overline{D}_k$ 的面积。由单调收敛原理，$\{|\underline{D}_k|\}$ 单调递增有上界，$\{|\overline{D}_k|\}$ 单调递减有下界，故均收敛。定义

- Jordan 内测度：$J_*(D)=\displaystyle\lim_{k\to\infty}|\underline{D}_k|$
- Jordan 外测度：$J^*(D)=\displaystyle\lim_{k\to\infty}|\overline{D}_k|$

若 $J_*(D)=J^*(D)$，则称 $D$ 是 Jordan 可测的，其 Jordan 测度为 $J(D)=J_*(D)=J^*(D)$。

**性质**：

1. 有界集 $D$ 是 Jordan 可测的充要条件是 $J(\partial D)=0$（边界的 Jordan 测度为 $0$）
2. 有限个 Jordan 可测集的并、交、差仍是 Jordan 可测的
3. 若 $A\subset B$，则 $J(A)\le J(B)$

### 1.2 二重积分的定义

**定义（二重积分）**：设 $D\subset\mathbb{R}^2$ 是有界 Jordan 可测区域，$f:D\to\mathbb{R}$ 是有界函数。将 $D$ 任意分割为 $n$ 个小 Jordan 可测区域 $\Delta D_1,\Delta D_2,\cdots,\Delta D_n$，记 $\lambda=\displaystyle\max_{1\le i\le n}\{\operatorname{diam}(\Delta D_i)\}$（小区域直径的最大值）。任取 $(\xi_i,\eta_i)\in\Delta D_i$，作和式

$$
\sum_{i=1}^{n}f(\xi_i,\eta_i)\Delta\sigma_i
$$

其中 $\Delta\sigma_i=J(\Delta D_i)$ 是小区域的面积。若当 $\lambda\to 0$ 时，上述和式的极限存在且与分割方式及点的取法无关，则称 $f$ 在 $D$ 上 Riemann 可积，记作 $f\in R(D)$，该极限称为 $f$ 在 $D$ 上的二重积分，记作

$$
\iint_{D}f(x,y)\,\mathrm{d}\sigma = \lim_{\lambda\to 0}\sum_{i=1}^{n}f(\xi_i,\eta_i)\Delta\sigma_i
$$

**可积的充要条件**：$f$ 在 $D$ 上可积当且仅当

$$
\lim_{\lambda\to 0}(S-s)=0
$$

其中 $S=\displaystyle\sum_{i=1}^{n}M_i\Delta\sigma_i$ 是 Darboux 大和，$s=\displaystyle\sum_{i=1}^{n}m_i\Delta\sigma_i$ 是 Darboux 小和，$M_i=\displaystyle\sup_{(x,y)\in\Delta D_i}f(x,y)$，$m_i=\displaystyle\inf_{(x,y)\in\Delta D_i}f(x,y)$。

**可积函数类**：

1. 有界闭区域上的连续函数必可积
2. 若 $f$ 在 $D$ 上有界，且仅在有限个 Jordan 测度为 $0$ 的集合上不连续，则 $f$ 在 $D$ 上可积

## §2 重积分的性质与计算

### 2.1 重积分的性质

1. **线性性**：若 $f,g\in R(D)$，$\alpha,\beta\in\mathbb{R}$，则 $\alpha f+\beta g\in R(D)$，且

   $$
   \iint_{D}(\alpha f+\beta g)\,\mathrm{d}\sigma = \alpha\iint_{D}f\,\mathrm{d}\sigma + \beta\iint_{D}g\,\mathrm{d}\sigma
   $$

2. **区域可加性**：若 $D=D_1\cup D_2$，且 $D_1\cap D_2$ 的 Jordan 测度为 $0$，则

   $$
   \iint_{D}f\,\mathrm{d}\sigma = \iint_{D_1}f\,\mathrm{d}\sigma + \iint_{D_2}f\,\mathrm{d}\sigma
   $$

3. **保序性**：若 $f,g\in R(D)$ 且 $f(x,y)\le g(x,y)$ 对所有 $(x,y)\in D$ 成立，则

   $$
   \iint_{D}f\,\mathrm{d}\sigma \le \iint_{D}g\,\mathrm{d}\sigma
   $$

4. **绝对可积性**：若 $f\in R(D)$，则 $|f|\in R(D)$，且

   $$
   \left|\iint_{D}f\,\mathrm{d}\sigma\right| \le \iint_{D}|f|\,\mathrm{d}\sigma
   $$

5. **乘积可积性**：若 $f,g\in R(D)$，则 $fg\in R(D)$

6. **积分中值定理**：若 $f\in C(D)$，$g\in R(D)$ 且 $g$ 在 $D$ 上不变号，则存在 $(\xi,\eta)\in D$，使得

   $$
   \iint_{D}f(x,y)g(x,y)\,\mathrm{d}\sigma = f(\xi,\eta)\iint_{D}g(x,y)\,\mathrm{d}\sigma
   $$

   特别地，当 $g\equiv 1$ 时，有

   $$
   \iint_{D}f(x,y)\,\mathrm{d}\sigma = f(\xi,\eta)\cdot J(D)
   $$

### 2.2 直角坐标系下二重积分的计算

**定理（化二重积分为累次积分）**：设 $f(x,y)$ 在矩形区域 $D=[a,b]\times[c,d]$ 上可积，且对每个固定的 $x\in[a,b]$，$f(x,y)$ 关于 $y$ 在 $[c,d]$ 上可积，则

$$
\iint_{D}f(x,y)\,\mathrm{d}\sigma = \int_{a}^{b}\left(\int_{c}^{d}f(x,y)\,\mathrm{d}y\right)\!\mathrm{d}x
$$

同理，若对每个固定的 $y\in[c,d]$，$f(x,y)$ 关于 $x$ 在 $[a,b]$ 上可积，则

$$
\iint_{D}f(x,y)\,\mathrm{d}\sigma = \int_{c}^{d}\left(\int_{a}^{b}f(x,y)\,\mathrm{d}x\right)\!\mathrm{d}y
$$

**一般区域的计算**：

- **X 型区域**：$D=\{(x,y)\mid a\le x\le b,\ y_1(x)\le y\le y_2(x)\}$，其中 $y_1(x),y_2(x)$ 在 $[a,b]$ 上连续，则

  $$
  \iint_{D}f(x,y)\,\mathrm{d}\sigma = \int_{a}^{b}\mathrm{d}x\int_{y_1(x)}^{y_2(x)}f(x,y)\,\mathrm{d}y
  $$

- **Y 型区域**：$D=\{(x,y)\mid c\le y\le d,\ x_1(y)\le x\le x_2(y)\}$，其中 $x_1(y),x_2(y)$ 在 $[c,d]$ 上连续，则

  $$
  \iint_{D}f(x,y)\,\mathrm{d}\sigma = \int_{c}^{d}\mathrm{d}y\int_{x_1(y)}^{x_2(y)}f(x,y)\,\mathrm{d}x
  $$

## §3 重积分的变量代换

### 3.1 二重积分的变量代换公式

**定理**：设 $D\subset\mathbb{R}^2$ 是有界 Jordan 可测区域，变换 $T:(u,v)\mapsto\bigl(x(u,v),y(u,v)\bigr)$ 是从有界闭区域 $D'\subset\mathbb{R}^2$ 到 $D$ 的 $C^1$ 微分同胚（即 $T$ 是双射且 $T,T^{-1}$ 都是 $C^1$ 的），$f$ 在 $D$ 上连续，则

$$
\iint_{D}f(x,y)\,\mathrm{d}x\mathrm{d}y = \iint_{D'}f\bigl(x(u,v),y(u,v)\bigr)\left|\det\frac{\partial(x,y)}{\partial(u,v)}\right|\mathrm{d}u\mathrm{d}v
$$

其中 $\dfrac{\partial(x,y)}{\partial(u,v)}=\begin{pmatrix}x_u & y_u \\ x_v & y_v\end{pmatrix}$ 是雅可比矩阵，$\det\dfrac{\partial(x,y)}{\partial(u,v)}$ 是雅可比行列式。

### 3.2 常用变量代换

1. **极坐标变换**：$x=r\cos\theta$，$y=r\sin\theta$，雅可比行列式为

   $$
   \det\frac{\partial(x,y)}{\partial(r,\theta)}=r
   $$

   因此

   $$
   \iint_{D}f(x,y)\,\mathrm{d}x\mathrm{d}y = \iint_{D'}f(r\cos\theta,r\sin\theta)\,r\,\mathrm{d}r\mathrm{d}\theta
   $$

2. **广义极坐标变换**：$x=ar\cos\theta$，$y=br\sin\theta$，雅可比行列式为 $abr$。

### 3.3 $n$ 重积分的变量代换公式

**定理**：设 $\Omega\subset\mathbb{R}^n$ 是有界 Jordan 可测区域，变换 $T:\boldsymbol{y}\mapsto\boldsymbol{x}(\boldsymbol{y})$ 是从有界闭区域 $\Omega'\subset\mathbb{R}^n$ 到 $\Omega$ 的 $C^1$ 微分同胚，$f$ 在 $\Omega$ 上连续，则

$$
\int_{\Omega}f(\boldsymbol{x})\,\mathrm{d}\boldsymbol{x} = \int_{\Omega'}f\bigl(\boldsymbol{x}(\boldsymbol{y})\bigr)\left|\det\frac{\partial(x_1,\cdots,x_n)}{\partial(y_1,\cdots,y_n)}\right|\mathrm{d}\boldsymbol{y}
$$

**常用 $n$ 维变换**：

- **柱面坐标变换**（三维）：$x=r\cos\theta$，$y=r\sin\theta$，$z=z$，雅可比行列式为 $r$
- **球面坐标变换**（三维）：$x=r\sin\varphi\cos\theta$，$y=r\sin\varphi\sin\theta$，$z=r\cos\varphi$，雅可比行列式为 $r^2\sin\varphi$

## §4 反常重积分

### 4.1 无界区域上的反常重积分

**定义**：设 $D\subset\mathbb{R}^2$ 是无界区域，$f:D\to\mathbb{R}$ 在 $D$ 的任意有界 Jordan 可测子区域上可积。取一列有界 Jordan 可测区域 $\{D_n\}$，满足 $D_1\subset D_2\subset\cdots\subset D$ 且 $\bigcup_{n=1}^{\infty}D_n=D$。若极限

$$
\lim_{n\to\infty}\iint_{D_n}f(x,y)\,\mathrm{d}\sigma
$$

存在且与 $\{D_n\}$ 的选取无关，则称反常重积分 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 收敛，否则称其发散。

**收敛判别法**：

1. **比较判别法**：设 $0\le f(x,y)\le g(x,y)$ 在 $D$ 上成立，若 $\displaystyle\iint_{D}g(x,y)\,\mathrm{d}\sigma$ 收敛，则 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 收敛；若 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 发散，则 $\displaystyle\iint_{D}g(x,y)\,\mathrm{d}\sigma$ 发散。

2. **Cauchy 判别法**：设 $D$ 是无界区域，$f(x,y)$ 在 $D$ 上连续，记 $r=\sqrt{x^2+y^2}$。

   - 若存在 $M>0$ 和 $\alpha>2$，使得当 $r$ 充分大时，$|f(x,y)|\le\dfrac{M}{r^\alpha}$，则 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 收敛
   - 若存在 $M>0$ 和 $\alpha\le 2$，使得当 $r$ 充分大时，$|f(x,y)|\ge\dfrac{M}{r^\alpha}$，且 $D$ 包含任意大的扇形区域，则 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 发散

### 4.2 无界函数的反常重积分

**定义**：设 $D\subset\mathbb{R}^2$ 是有界 Jordan 可测区域，$f:D\setminus\{P_0\}\to\mathbb{R}$ 在 $P_0$ 的任意去心邻域内无界（$P_0$ 是瑕点），且在 $D$ 的任意不包含 $P_0$ 的 Jordan 可测子区域上可积。取一列包含 $P_0$ 的小区域 $\{\sigma_n\}$，满足 $\operatorname{diam}(\sigma_n)\to 0$。若极限

$$
\lim_{n\to\infty}\iint_{D\setminus\sigma_n}f(x,y)\,\mathrm{d}\sigma
$$

存在且与 $\{\sigma_n\}$ 的选取无关，则称反常重积分 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 收敛，否则称其发散。

**Cauchy 判别法**：设 $P_0$ 是 $f$ 的瑕点，记 $r=\sqrt{(x-x_0)^2+(y-y_0)^2}$。

- 若存在 $M>0$ 和 $\alpha<2$，使得当 $r$ 充分小时，$|f(x,y)|\le\dfrac{M}{r^\alpha}$，则 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 收敛
- 若存在 $M>0$ 和 $\alpha\ge 2$，使得当 $r$ 充分小时，$|f(x,y)|\ge\dfrac{M}{r^\alpha}$，则 $\displaystyle\iint_{D}f(x,y)\,\mathrm{d}\sigma$ 发散

### 4.3 Fubini–Tonelli 定理

**定理（Tonelli）**：设 $f(x,y)\ge 0$ 在 $D=[a,+\infty)\times[c,+\infty)$ 上连续，则

$$
\iint_{D}f(x,y)\,\mathrm{d}x\mathrm{d}y = \int_{a}^{+\infty}\mathrm{d}x\int_{c}^{+\infty}f(x,y)\,\mathrm{d}y = \int_{c}^{+\infty}\mathrm{d}y\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x
$$

即三个积分同时收敛或同时发散。

**定理（Fubini）**：设 $f(x,y)$ 在 $D=[a,+\infty)\times[c,+\infty)$ 上连续，且 $\displaystyle\iint_{D}|f(x,y)|\,\mathrm{d}x\mathrm{d}y$ 收敛，则

$$
\iint_{D}f(x,y)\,\mathrm{d}x\mathrm{d}y = \int_{a}^{+\infty}\mathrm{d}x\int_{c}^{+\infty}f(x,y)\,\mathrm{d}y = \int_{c}^{+\infty}\mathrm{d}y\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x
$$

---

# 第十四章 曲线积分、曲面积分与场论

## §1 第一类曲线积分与第一类曲面积分

### 1.1 第一类曲线积分（对弧长的曲线积分）

**定义**：设 $L$ 是 $\mathbb{R}^3$ 中可求长的曲线，$f:L\to\mathbb{R}$ 是有界函数。将 $L$ 任意分割为 $n$ 个小弧段 $\Delta s_1,\Delta s_2,\cdots,\Delta s_n$，记 $\lambda=\displaystyle\max_{1\le i\le n}\{\operatorname{length}(\Delta s_i)\}$。任取 $(\xi_i,\eta_i,\zeta_i)\in\Delta s_i$，作和式

$$
\sum_{i=1}^{n}f(\xi_i,\eta_i,\zeta_i)\Delta s_i
$$

若当 $\lambda\to 0$ 时，上述和式的极限存在且与分割方式及点的取法无关，则称该极限为 $f$ 在 $L$ 上的第一类曲线积分，记作

$$
\int_{L}f(x,y,z)\,\mathrm{d}s = \lim_{\lambda\to 0}\sum_{i=1}^{n}f(\xi_i,\eta_i,\zeta_i)\Delta s_i
$$

**计算方法**：设曲线 $L$ 的参数方程为

$$
\begin{cases}
x=x(t)\\
y=y(t)\\
z=z(t)
\end{cases},\quad t\in[\alpha,\beta]
$$

其中 $x(t),y(t),z(t)$ 是 $C^1$ 的，且 $x'(t)^2+y'(t)^2+z'(t)^2\neq 0$，则

$$
\int_{L}f(x,y,z)\,\mathrm{d}s = \int_{\alpha}^{\beta}f\bigl(x(t),y(t),z(t)\bigr)\sqrt{x'(t)^2+y'(t)^2+z'(t)^2}\,\mathrm{d}t
$$

**注**：积分下限 $\alpha$ 必须小于积分上限 $\beta$。

### 1.2 第一类曲面积分（对面积的曲面积分）

**定义**：设 $\Sigma$ 是 $\mathbb{R}^3$ 中可求面积的曲面，$f:\Sigma\to\mathbb{R}$ 是有界函数。将 $\Sigma$ 任意分割为 $n$ 个小曲面 $\Delta S_1,\Delta S_2,\cdots,\Delta S_n$，记 $\lambda=\displaystyle\max_{1\le i\le n}\{\operatorname{diam}(\Delta S_i)\}$。任取 $(\xi_i,\eta_i,\zeta_i)\in\Delta S_i$，作和式

$$
\sum_{i=1}^{n}f(\xi_i,\eta_i,\zeta_i)\Delta S_i
$$

若当 $\lambda\to 0$ 时，上述和式的极限存在且与分割方式及点的取法无关，则称该极限为 $f$ 在 $\Sigma$ 上的第一类曲面积分，记作

$$
\iint_{\Sigma}f(x,y,z)\,\mathrm{d}S = \lim_{\lambda\to 0}\sum_{i=1}^{n}f(\xi_i,\eta_i,\zeta_i)\Delta S_i
$$

**计算方法**：设曲面 $\Sigma$ 的参数方程为

$$
\begin{cases}
x=x(u,v)\\
y=y(u,v)\\
z=z(u,v)
\end{cases},\quad (u,v)\in D
$$

其中 $x(u,v),y(u,v),z(u,v)$ 是 $C^1$ 的，且雅可比矩阵 $\begin{pmatrix}x_u & y_u & z_u\\ x_v & y_v & z_v\end{pmatrix}$ 的秩为 $2$，则

$$
\iint_{\Sigma}f(x,y,z)\,\mathrm{d}S = \iint_{D}f\bigl(x(u,v),y(u,v),z(u,v)\bigr)\,\|\boldsymbol{r}_u\times\boldsymbol{r}_v\|\,\mathrm{d}u\mathrm{d}v
$$

其中 $\boldsymbol{r}_u=(x_u,y_u,z_u)$，$\boldsymbol{r}_v=(x_v,y_v,z_v)$，$\|\boldsymbol{r}_u\times\boldsymbol{r}_v\|=\sqrt{EG-F^2}$，$E=\boldsymbol{r}_u\cdot\boldsymbol{r}_u$，$F=\boldsymbol{r}_u\cdot\boldsymbol{r}_v$，$G=\boldsymbol{r}_v\cdot\boldsymbol{r}_v$。

**特殊情况**：若曲面 $\Sigma$ 由 $z=z(x,y)$ 给出，$(x,y)\in D$，则

$$
\iint_{\Sigma}f(x,y,z)\,\mathrm{d}S = \iint_{D}f\bigl(x,y,z(x,y)\bigr)\sqrt{1+z_x^2+z_y^2}\,\mathrm{d}x\mathrm{d}y
$$

## §2 第二类曲线积分与第二类曲面积分

### 2.1 第二类曲线积分（对坐标的曲线积分）

**定义**：设 $L$ 是 $\mathbb{R}^3$ 中可求长的有向曲线，$\boldsymbol{F}(x,y,z)=\bigl(P(x,y,z),Q(x,y,z),R(x,y,z)\bigr)$ 是定义在 $L$ 上的向量场。将 $L$ 任意分割为 $n$ 个有向小弧段 $\Delta\boldsymbol{s}_1,\Delta\boldsymbol{s}_2,\cdots,\Delta\boldsymbol{s}_n$，记 $\lambda=\displaystyle\max_{1\le i\le n}\{\operatorname{length}(\Delta\boldsymbol{s}_i)\}$。任取 $(\xi_i,\eta_i,\zeta_i)\in\Delta\boldsymbol{s}_i$，作和式

$$
\sum_{i=1}^{n}\boldsymbol{F}(\xi_i,\eta_i,\zeta_i)\cdot\Delta\boldsymbol{s}_i
$$

若当 $\lambda\to 0$ 时，上述和式的极限存在且与分割方式及点的取法无关，则称该极限为向量场 $\boldsymbol{F}$ 沿有向曲线 $L$ 的第二类曲线积分，记作

$$
\int_{L}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s} = \lim_{\lambda\to 0}\sum_{i=1}^{n}\boldsymbol{F}(\xi_i,\eta_i,\zeta_i)\cdot\Delta\boldsymbol{s}_i
$$

也可写作

$$
\int_{L}P(x,y,z)\,\mathrm{d}x + Q(x,y,z)\,\mathrm{d}y + R(x,y,z)\,\mathrm{d}z
$$

**性质**：

1. **方向性**：$\displaystyle\int_{L^-}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s} = -\int_{L}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s}$，其中 $L^-$ 是 $L$ 的反向曲线
2. **线性性**：$\displaystyle\int_{L}(\alpha\boldsymbol{F}+\beta\boldsymbol{G})\cdot\mathrm{d}\boldsymbol{s} = \alpha\int_{L}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s} + \beta\int_{L}\boldsymbol{G}\cdot\mathrm{d}\boldsymbol{s}$
3. **路径可加性**：若 $L=L_1+L_2$，则 $\displaystyle\int_{L}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s} = \int_{L_1}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s} + \int_{L_2}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s}$

**计算方法**：设有向曲线 $L$ 的参数方程为

$$
\begin{cases}
x=x(t)\\
y=y(t)\\
z=z(t)
\end{cases}
$$

当 $t$ 从 $\alpha$ 变到 $\beta$ 时，点 $(x(t),y(t),z(t))$ 沿 $L$ 的方向从起点运动到终点，且 $x(t),y(t),z(t)$ 是 $C^1$ 的，则

$$
\int_{L}P\,\mathrm{d}x+Q\,\mathrm{d}y+R\,\mathrm{d}z = \int_{\alpha}^{\beta}\Bigl[P\bigl(x(t),y(t),z(t)\bigr)x'(t)+Q\bigl(x(t),y(t),z(t)\bigr)y'(t)+R\bigl(x(t),y(t),z(t)\bigr)z'(t)\Bigr]\mathrm{d}t
$$

**注**：积分下限 $\alpha$ 对应起点，上限 $\beta$ 对应终点，$\alpha$ 不一定小于 $\beta$。

### 2.2 第二类曲面积分（对坐标的曲面积分）

**定义**：设 $\Sigma$ 是 $\mathbb{R}^3$ 中可求面积的有向曲面，$\boldsymbol{F}(x,y,z)=\bigl(P(x,y,z),Q(x,y,z),R(x,y,z)\bigr)$ 是定义在 $\Sigma$ 上的向量场。将 $\Sigma$ 任意分割为 $n$ 个有向小曲面 $\Delta\boldsymbol{S}_1,\Delta\boldsymbol{S}_2,\cdots,\Delta\boldsymbol{S}_n$，记 $\lambda=\displaystyle\max_{1\le i\le n}\{\operatorname{diam}(\Delta\boldsymbol{S}_i)\}$。任取 $(\xi_i,\eta_i,\zeta_i)\in\Delta\boldsymbol{S}_i$，作和式

$$
\sum_{i=1}^{n}\boldsymbol{F}(\xi_i,\eta_i,\zeta_i)\cdot\Delta\boldsymbol{S}_i
$$

若当 $\lambda\to 0$ 时，上述和式的极限存在且与分割方式及点的取法无关，则称该极限为向量场 $\boldsymbol{F}$ 沿有向曲面 $\Sigma$ 的第二类曲面积分，记作

$$
\iint_{\Sigma}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S} = \lim_{\lambda\to 0}\sum_{i=1}^{n}\boldsymbol{F}(\xi_i,\eta_i,\zeta_i)\cdot\Delta\boldsymbol{S}_i
$$

也可写作

$$
\iint_{\Sigma}P\,\mathrm{d}y\mathrm{d}z + Q\,\mathrm{d}z\mathrm{d}x + R\,\mathrm{d}x\mathrm{d}y
$$

**性质**：

1. **方向性**：$\displaystyle\iint_{\Sigma^-}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S} = -\iint_{\Sigma}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S}$，其中 $\Sigma^-$ 是 $\Sigma$ 的反向曲面
2. **线性性**：$\displaystyle\iint_{\Sigma}(\alpha\boldsymbol{F}+\beta\boldsymbol{G})\cdot\mathrm{d}\boldsymbol{S} = \alpha\iint_{\Sigma}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S} + \beta\iint_{\Sigma}\boldsymbol{G}\cdot\mathrm{d}\boldsymbol{S}$
3. **曲面可加性**：若 $\Sigma=\Sigma_1+\Sigma_2$，则 $\displaystyle\iint_{\Sigma}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S} = \iint_{\Sigma_1}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S} + \iint_{\Sigma_2}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S}$

**计算方法**：设有向曲面 $\Sigma$ 的参数方程为

$$
\begin{cases}
x=x(u,v)\\
y=y(u,v)\\
z=z(u,v)
\end{cases},\quad (u,v)\in D
$$

其法向量为 $\boldsymbol{n}=\pm(\boldsymbol{r}_u\times\boldsymbol{r}_v)$（符号由曲面的定向决定），则

$$
\iint_{\Sigma}P\,\mathrm{d}y\mathrm{d}z+Q\,\mathrm{d}z\mathrm{d}x+R\,\mathrm{d}x\mathrm{d}y = \pm\iint_{D}\left[P\frac{\partial(y,z)}{\partial(u,v)}+Q\frac{\partial(z,x)}{\partial(u,v)}+R\frac{\partial(x,y)}{\partial(u,v)}\right]\mathrm{d}u\mathrm{d}v
$$

**特殊情况**：若曲面 $\Sigma$ 由 $z=z(x,y)$ 给出，取上侧，则

$$
\iint_{\Sigma}R(x,y,z)\,\mathrm{d}x\mathrm{d}y = \iint_{D}R\bigl(x,y,z(x,y)\bigr)\,\mathrm{d}x\mathrm{d}y
$$

取下侧则

$$
\iint_{\Sigma}R(x,y,z)\,\mathrm{d}x\mathrm{d}y = -\iint_{D}R\bigl(x,y,z(x,y)\bigr)\,\mathrm{d}x\mathrm{d}y
$$

## §3 Green 公式、Gauss 公式与 Stokes 公式

### 3.1 Green 公式

**定理（Green 公式）**：设 $D\subset\mathbb{R}^2$ 是有界单连通闭区域，其边界 $\partial D$ 是分段光滑的简单闭曲线，取正向（逆时针方向）。若 $P(x,y),Q(x,y)$ 在 $D$ 上具有一阶连续偏导数，则

$$
\oint_{\partial D}P\,\mathrm{d}x+Q\,\mathrm{d}y = \iint_{D}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\!\mathrm{d}x\mathrm{d}y
$$

**曲线积分与路径无关的条件**：设 $D\subset\mathbb{R}^2$ 是单连通区域，$P(x,y),Q(x,y)$ 在 $D$ 上具有一阶连续偏导数，则以下四个命题等价：

1. 对 $D$ 内任意分段光滑闭曲线 $L$，有 $\displaystyle\oint_{L}P\,\mathrm{d}x+Q\,\mathrm{d}y=0$
2. 曲线积分 $\displaystyle\int_{L}P\,\mathrm{d}x+Q\,\mathrm{d}y$ 在 $D$ 内与路径无关，只与起点和终点有关
3. 存在 $D$ 上的可微函数 $U(x,y)$，使得 $\mathrm{d}U=P\,\mathrm{d}x+Q\,\mathrm{d}y$（$U$ 称为原函数）
4. 在 $D$ 内处处有 $\displaystyle\frac{\partial Q}{\partial x}=\frac{\partial P}{\partial y}$

### 3.2 Gauss 公式（散度定理）

**定理（Gauss 公式）**：设 $\Omega\subset\mathbb{R}^3$ 是有界闭区域，其边界 $\partial\Omega$ 是分片光滑的闭曲面，取外侧。若 $P(x,y,z),Q(x,y,z),R(x,y,z)$ 在 $\Omega$ 上具有一阶连续偏导数，则

$$
\oiint_{\partial\Omega}P\,\mathrm{d}y\mathrm{d}z+Q\,\mathrm{d}z\mathrm{d}x+R\,\mathrm{d}x\mathrm{d}y = \iiint_{\Omega}\left(\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}\right)\!\mathrm{d}x\mathrm{d}y\mathrm{d}z
$$

**散度的定义**：向量场 $\boldsymbol{F}=(P,Q,R)$ 的散度为

$$
\operatorname{div}\boldsymbol{F} = \frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}
$$

因此 Gauss 公式可写作

$$
\oiint_{\partial\Omega}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S} = \iiint_{\Omega}\operatorname{div}\boldsymbol{F}\,\mathrm{d}V
$$

### 3.3 Stokes 公式

**定理（Stokes 公式）**：设 $\Sigma\subset\mathbb{R}^3$ 是分片光滑的有向曲面，其边界 $\partial\Sigma$ 是分段光滑的有向闭曲线，且 $\partial\Sigma$ 的定向与 $\Sigma$ 的定向满足右手定则。若 $P(x,y,z),Q(x,y,z),R(x,y,z)$ 在包含 $\Sigma$ 的一个空间区域内具有一阶连续偏导数，则

$$
\oint_{\partial\Sigma}P\,\mathrm{d}x+Q\,\mathrm{d}y+R\,\mathrm{d}z = \iint_{\Sigma}\left(\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}\right)\!\mathrm{d}y\mathrm{d}z + \left(\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}\right)\!\mathrm{d}z\mathrm{d}x + \left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\!\mathrm{d}x\mathrm{d}y
$$

**旋度的定义**：向量场 $\boldsymbol{F}=(P,Q,R)$ 的旋度为

$$
\operatorname{rot}\boldsymbol{F} = \begin{vmatrix}
\boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k}\\[2pt]
\dfrac{\partial}{\partial x} & \dfrac{\partial}{\partial y} & \dfrac{\partial}{\partial z}\\[6pt]
P & Q & R
\end{vmatrix}
$$

因此 Stokes 公式可写作

$$
\oint_{\partial\Sigma}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{s} = \iint_{\Sigma}\operatorname{rot}\boldsymbol{F}\cdot\mathrm{d}\boldsymbol{S}
$$

---

# 第十五章 含参变量积分

## §1 含参变量的常义积分

**定义**：设 $f(x,y)$ 在矩形区域 $D=[a,b]\times[c,d]$ 上有定义，对每个固定的 $y\in[c,d]$，$f(x,y)$ 关于 $x$ 在 $[a,b]$ 上可积，则称

$$
I(y)=\int_{a}^{b}f(x,y)\,\mathrm{d}x
$$

为含参变量 $y$ 的常义积分。

**性质**：

1. **连续性定理**：若 $f(x,y)\in C(D)$，则 $I(y)\in C[c,d]$，即

   $$
   \lim_{y\to y_0}\int_{a}^{b}f(x,y)\,\mathrm{d}x = \int_{a}^{b}\lim_{y\to y_0}f(x,y)\,\mathrm{d}x = \int_{a}^{b}f(x,y_0)\,\mathrm{d}x
   $$

2. **积分次序交换定理**：若 $f(x,y)\in C(D)$，则

   $$
   \int_{c}^{d}\mathrm{d}y\int_{a}^{b}f(x,y)\,\mathrm{d}x = \int_{a}^{b}\mathrm{d}x\int_{c}^{d}f(x,y)\,\mathrm{d}y
   $$

3. **积分号下求导定理**：若 $f(x,y),f_y(x,y)\in C(D)$，则 $I(y)$ 在 $[c,d]$ 上可导，且

   $$
   I'(y)=\frac{\mathrm{d}}{\mathrm{d}y}\int_{a}^{b}f(x,y)\,\mathrm{d}x = \int_{a}^{b}f_y(x,y)\,\mathrm{d}x
   $$

**推广**：若积分限也依赖于参变量，即

$$
I(y)=\int_{a(y)}^{b(y)}f(x,y)\,\mathrm{d}x
$$

其中 $a(y),b(y)$ 在 $[c,d]$ 上可导，且 $a\le a(y),b(y)\le b$，$f(x,y),f_y(x,y)\in C(D)$，则

$$
I'(y)=\int_{a(y)}^{b(y)}f_y(x,y)\,\mathrm{d}x + f\bigl(b(y),y\bigr)b'(y) - f\bigl(a(y),y\bigr)a'(y)
$$

## §2 含参变量的反常积分

### 2.1 一致收敛的定义

**定义（逐点收敛）**：设 $f(x,y)$ 在 $[a,+\infty)\times[c,d]$ 上有定义，若对每个固定的 $y\in[c,d]$，反常积分

$$
\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x
$$

收敛，则称该含参变量反常积分在 $[c,d]$ 上逐点收敛，其和函数为

$$
I(y)=\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x
$$

**定义（一致收敛）**：若对任意 $\varepsilon>0$，存在与 $y$ 无关的 $A_0>a$，使得当 $A>A_0$ 时，对所有 $y\in[c,d]$，有

$$
\left|\int_{A}^{+\infty}f(x,y)\,\mathrm{d}x\right|<\varepsilon
$$

则称含参变量反常积分 $\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛。

### 2.2 一致收敛的判别法

1. **Cauchy 收敛原理**：$\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛的充要条件是：对任意 $\varepsilon>0$，存在与 $y$ 无关的 $A_0>a$，使得当 $A_2>A_1>A_0$ 时，对所有 $y\in[c,d]$，有

   $$
   \left|\int_{A_1}^{A_2}f(x,y)\,\mathrm{d}x\right|<\varepsilon
   $$

2. **Weierstrass 判别法（M 判别法）**：若存在函数 $g(x)$，使得

   - $|f(x,y)|\le g(x)$ 对所有 $x\ge a$ 和 $y\in[c,d]$ 成立
   - 反常积分 $\displaystyle\int_{a}^{+\infty}g(x)\,\mathrm{d}x$ 收敛

   则 $\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛。

3. **Abel 判别法**：若

   - $\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛
   - 对每个固定的 $y\in[c,d]$，$g(x,y)$ 关于 $x$ 单调
   - $g(x,y)$ 在 $[a,+\infty)\times[c,d]$ 上一致有界，即存在 $M>0$，使得 $|g(x,y)|\le M$ 对所有 $x\ge a$ 和 $y\in[c,d]$ 成立

   则 $\displaystyle\int_{a}^{+\infty}f(x,y)g(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛。

4. **Dirichlet 判别法**：若

   - 积分 $\displaystyle\int_{a}^{A}f(x,y)\,\mathrm{d}x$ 关于 $A\ge a$ 和 $y\in[c,d]$ 一致有界，即存在 $M>0$，使得 $\left|\displaystyle\int_{a}^{A}f(x,y)\,\mathrm{d}x\right|\le M$ 对所有 $A\ge a$ 和 $y\in[c,d]$ 成立
   - 对每个固定的 $y\in[c,d]$，$g(x,y)$ 关于 $x$ 单调
   - 当 $x\to+\infty$ 时，$g(x,y)$ 关于 $y\in[c,d]$ 一致趋于 $0$，即对任意 $\varepsilon>0$，存在与 $y$ 无关的 $A_0>a$，使得当 $x>A_0$ 时，对所有 $y\in[c,d]$，有 $|g(x,y)|<\varepsilon$

   则 $\displaystyle\int_{a}^{+\infty}f(x,y)g(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛。

### 2.3 一致收敛积分的分析性质

1. **连续性定理**：若 $f(x,y)\in C\bigl([a,+\infty)\times[c,d]\bigr)$，且 $\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛，则 $I(y)=\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x\in C[c,d]$，即

   $$
   \lim_{y\to y_0}\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x = \int_{a}^{+\infty}\lim_{y\to y_0}f(x,y)\,\mathrm{d}x = \int_{a}^{+\infty}f(x,y_0)\,\mathrm{d}x
   $$

2. **积分次序交换定理**：若 $f(x,y)\in C\bigl([a,+\infty)\times[c,d]\bigr)$，且 $\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛，则

   $$
   \int_{c}^{d}\mathrm{d}y\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x = \int_{a}^{+\infty}\mathrm{d}x\int_{c}^{d}f(x,y)\,\mathrm{d}y
   $$

3. **积分号下求导定理**：若 $f(x,y),f_y(x,y)\in C\bigl([a,+\infty)\times[c,d]\bigr)$，$\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上逐点收敛，且 $\displaystyle\int_{a}^{+\infty}f_y(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上一致收敛，则 $I(y)=\displaystyle\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x$ 在 $[c,d]$ 上可导，且

   $$
   I'(y)=\frac{\mathrm{d}}{\mathrm{d}y}\int_{a}^{+\infty}f(x,y)\,\mathrm{d}x = \int_{a}^{+\infty}f_y(x,y)\,\mathrm{d}x
   $$

---

# 第十六章 Fourier 级数

## §1 函数的 Fourier 级数展开

**定义**：设 $f(x)$ 是以 $2\pi$ 为周期的可积函数，称

$$
\begin{aligned}
a_0 &= \frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\,\mathrm{d}x\\
a_n &= \frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\cos nx\,\mathrm{d}x,\quad n=1,2,3,\cdots\\
b_n &= \frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\sin nx\,\mathrm{d}x,\quad n=1,2,3,\cdots
\end{aligned}
$$

为 $f(x)$ 的 Fourier 系数，称三角级数

$$
\frac{a_0}{2}+\sum_{n=1}^{\infty}\bigl(a_n\cos nx+b_n\sin nx\bigr)
$$

为 $f(x)$ 的 Fourier 级数，记作

$$
f(x)\sim\frac{a_0}{2}+\sum_{n=1}^{\infty}\bigl(a_n\cos nx+b_n\sin nx\bigr)
$$

**周期为 $2l$ 的函数的 Fourier 级数**：设 $f(x)$ 是以 $2l$ 为周期的可积函数，作变量代换 $t=\dfrac{\pi x}{l}$，则 $f(x)=f\!\left(\dfrac{l t}{\pi}\right)$ 是以 $2\pi$ 为周期的函数，其 Fourier 级数为

$$
f(x)\sim\frac{a_0}{2}+\sum_{n=1}^{\infty}\left(a_n\cos\frac{n\pi x}{l}+b_n\sin\frac{n\pi x}{l}\right)
$$

其中

$$
\begin{aligned}
a_0 &= \frac{1}{l}\int_{-l}^{l}f(x)\,\mathrm{d}x\\
a_n &= \frac{1}{l}\int_{-l}^{l}f(x)\cos\frac{n\pi x}{l}\,\mathrm{d}x,\quad n=1,2,3,\cdots\\
b_n &= \frac{1}{l}\int_{-l}^{l}f(x)\sin\frac{n\pi x}{l}\,\mathrm{d}x,\quad n=1,2,3,\cdots
\end{aligned}
$$

## §2 Fourier 级数的收敛性

### 2.1 Riemann–Lebesgue 引理

**定理（Riemann–Lebesgue 引理）**：若 $f(x)$ 在 $[a,b]$ 上可积或绝对可积，则

$$
\lim_{\lambda\to+\infty}\int_{a}^{b}f(x)\sin\lambda x\,\mathrm{d}x = 0,\qquad
\lim_{\lambda\to+\infty}\int_{a}^{b}f(x)\cos\lambda x\,\mathrm{d}x = 0
$$

### 2.2 Fourier 级数的收敛定理

**定理（Dirichlet–Jordan 判别法）**：设 $f(x)$ 是以 $2\pi$ 为周期的函数，且在 $[-\pi,\pi]$ 上分段单调有界（即可以分成有限个单调区间），则 $f(x)$ 的 Fourier 级数在每一点 $x$ 处收敛于

$$
\frac{f(x+0)+f(x-0)}{2}
$$

其中 $f(x+0)$ 和 $f(x-0)$ 分别是 $f(x)$ 在 $x$ 处的右极限和左极限。

**定理（Dini–Lipschitz 判别法）**：设 $f(x)$ 是以 $2\pi$ 为周期的函数，且在 $x_0$ 的某个邻域内满足 Hölder 条件，即存在 $\delta>0$ 和 $L>0$，$\alpha>0$，使得当 $|h|<\delta$ 时，有

$$
|f(x_0+h)-f(x_0)|\le L|h|^\alpha
$$

则 $f(x)$ 的 Fourier 级数在 $x_0$ 处收敛于 $f(x_0)$。

**推论**：若 $f(x)$ 在 $x_0$ 处可导，则其 Fourier 级数在 $x_0$ 处收敛于 $f(x_0)$。

## §3 Fourier 级数的性质

1. **逐项积分定理**：设 $f(x)$ 是以 $2\pi$ 为周期的可积或绝对可积函数，且

   $$
   f(x)\sim\frac{a_0}{2}+\sum_{n=1}^{\infty}\bigl(a_n\cos nx+b_n\sin nx\bigr)
   $$

   则对任意 $c,x\in\mathbb{R}$，有

   $$
   \int_{c}^{x}f(t)\,\mathrm{d}t = \int_{c}^{x}\frac{a_0}{2}\,\mathrm{d}t + \sum_{n=1}^{\infty}\int_{c}^{x}\bigl(a_n\cos nt+b_n\sin nt\bigr)\mathrm{d}t
   $$

   即 Fourier 级数可以逐项积分。

2. **Parseval 等式（最佳平方逼近）**：设 $f(x)$ 是以 $2\pi$ 为周期的平方可积函数，其 Fourier 系数为 $a_n,b_n$，则

   $$
   \frac{1}{\pi}\int_{-\pi}^{\pi}f^2(x)\,\mathrm{d}x = \frac{a_0^2}{2}+\sum_{n=1}^{\infty}\bigl(a_n^2+b_n^2\bigr)
   $$

3. **Weierstrass 逼近定理**：闭区间上的连续函数可以用多项式一致逼近。