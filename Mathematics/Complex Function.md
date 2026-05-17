# 复变函数笔记（Markdown 整理版）

> 来源：手写扫描笔记《复变函数.pdf》。右下角水印已忽略。  
> 说明：原文件为手写扫描件，本稿按页码顺序整理为可编辑 Markdown；图形内容用“图示说明”保留。个别字迹较模糊处以“待核对”标注。

---

## 第一章 复数与复变函数

### §1 复数

#### 1. 复数域

实数有序对集合：

$$
\mathbb{R}^2=\mathbb{R}\times \mathbb{R}=\{(x,y)\mid x,y\in\mathbb{R}\}
$$

在 $\mathbb{R}^2$ 上定义运算：

**加法：**

$$
(a,b)+(c,d)=(a+c,b+d)
$$

单位元：

$$
(0,0)
$$

$(a,b)$ 的加法逆元：

$$
-(a,b)=(-a,-b)
$$

**减法：**

$$
(a,b)-(c,d)=(a,b)+(-c,-d)=(a-c,b-d)
$$

**乘法：**

$$
(a,b)(c,d)=(ac-bd,bc+ad)
$$

乘法单位元：

$$
(1,0)
$$

若 $(a,b)\ne(0,0)$，则其乘法逆元为

$$
(a,b)^{-1}=\left(\frac{a}{a^2+b^2},\frac{-b}{a^2+b^2}\right)
$$

**除法：**

$$
\frac{(a,b)}{(c,d)}
=(a,b)\left(\frac{c}{c^2+d^2},\frac{-d}{c^2+d^2}\right)
=\left(\frac{ac+bd}{c^2+d^2},\frac{bc-ad}{c^2+d^2}\right),\quad (c,d)\ne(0,0)
$$

由上述运算可知，$\mathbb{R}^2$ 构成一个域，称为**复数域**，记为 $\mathbb{C}$。

把 $(x,0)$ 与实数 $x$ 等同，则 $\mathbb{R}\subset\mathbb{C}$。令

$$
i=(0,1),\quad i^2=-1
$$

任意复数可写作

$$
z=x+iy,\quad x,y\in\mathbb{R}
$$

其中：

$$
x=\operatorname{Re} z,\qquad y=\operatorname{Im} z
$$

复数相等：

$$
a+ib=c+id\iff a=c,\ b=d
$$

即

$$
(a,b)=(c,d)
$$

#### 2. 复数不能比较大小

在复数域中不能定义与实数一致的全序关系。若假设 $\mathbb{C}$ 中存在大小关系 $<$，并满足对任意 $\alpha,\beta,\gamma\in\mathbb{C}$：

1. $\alpha=\beta$、$\alpha<\beta$、$\beta<\alpha$ 三者有且仅有一个成立；
2. $\alpha<\beta,\ \beta<\gamma\Rightarrow \alpha<\gamma$；
3. $\alpha<\beta\Rightarrow \alpha+\gamma<\beta+\gamma$；
4. $\alpha<\beta,\ 0<\gamma\Rightarrow \alpha\gamma<\beta\gamma$。

则会推出矛盾，故复数不能比较大小。

#### 3. 复平面

复数

$$
z=x+iy
$$

可与平面点 $(x,y)$ 一一对应，复平面中：

- 横轴为实轴；
- 纵轴为虚轴；
- $z$ 也可看作从原点指向 $(x,y)$ 的向量。

共轭复数：

$$
\bar z=x-iy
$$

模：

$$
|z|=\sqrt{x^2+y^2}
$$

辐角：

$$
\arg z=\theta+2k\pi,\\quad k\in\mathbb{Z}
$$

主辐角：

$$
\operatorname{Arg} z\in(-\pi,\pi]
$$

常用关系：

$$
z\bar z=|z|^2,
\qquad |\bar z|=|z|,
\qquad \arg \bar z=-\arg z\pmod{2\pi}
$$

若 $z\ne0$，则

$$
z=r(\cos\theta+i\sin\theta),\quad r=|z|,
$$

也可写为指数形式：

$$
z=re^{i\theta}
$$

其中

$$
e^{i\theta}=\cos\theta+i\sin\theta
$$

#### 4. 复数和复平面点的关系

若

$$
z_1=r_1e^{i\theta_1},\qquad z_2=r_2e^{i\theta_2}
$$

则：

$$
z_1z_2=r_1r_2e^{i(\theta_1+\theta_2)}
$$

$$
\frac{z_1}{z_2}=\frac{r_1}{r_2}e^{i(\theta_1-\theta_2)},\quad z_2\ne0
$$

因此：

$$
|z_1z_2|=|z_1||z_2|,
\quad \arg(z_1z_2)=\arg z_1+\arg z_2
$$

$$
\left|\frac{z_1}{z_2}\right|=\frac{|z_1|}{|z_2|},
\quad \arg\frac{z_1}{z_2}=\arg z_1-\arg z_2
$$

三点 $A,B,C,D$ 共圆的一个复数判别式：若四点对应复数为 $a,b,c,d$，则可用交比

$$
\frac{(a-c)(b-d)}{(b-c)(a-d)}
$$

为实数来判定其共线或共圆。

#### 5. 复数的乘方与方根

De Moivre 公式：

$$
(\cos\theta+i\sin\theta)^n=\cos n\theta+i\sin n\theta
$$

若

$$
z=r(\cos\theta+i\sin\theta)=re^{i\theta}
$$

则

$$
z^n=r^ne^{in\theta}=r^n(\cos n\theta+i\sin n\theta)
$$

求 $n$ 次方根：设 $w^n=z$。若 $z=re^{i\theta}\ne0$，则

$$
w_k=\sqrt[n]{r}\exp\left(i\frac{\theta+2k\pi}{n}\right),\quad k=0,1,\ldots,n-1
$$

即

$$
w_k=\sqrt[n]{r}\left[\cos\frac{\theta+2k\pi}{n}+i\sin\frac{\theta+2k\pi}{n}\right]
$$

这些根在复平面上位于同一圆周上，且相邻根辐角相差 $2\pi/n$。

#### 6. 复数方程

复数方程通常可转化为实变量方程。设

$$
z=x+iy
$$

将复方程

$$
F(z,\bar z)=0
$$

化为关于 $x,y$ 的方程，可得到其对应的几何图形。

常见例子：

**直线：**

$$
ax+by+c=0
$$

可写成复数形式：

$$
\bar\alpha z+\alpha\bar z+c=0
$$

其中 $\alpha$ 与 $a,b$ 有关。

**圆：**

$$
|z-z_0|=R
$$

或

$$
(z-z_0)(\bar z-\bar z_0)=R^2
$$

一般圆方程可写成

$$
z\bar z+\bar a z+a\bar z+c=0
$$

其中 $a\in\mathbb{C}$，$c\in\mathbb{R}$。

#### 7. 无穷远点与复球面

在复平面 $\mathbb{C}$ 中加入一个无穷远点 $\infty$，得扩充复平面：

$$
\mathbb{C}_\infty=\mathbb{C}\cup\{\infty\}
$$

通过球极投影可将扩充复平面与 Riemann 球面对应。

图示说明：笔记中画出复平面与球面相切，球面北极对应无穷远点，平面点通过北极连线投影到球面上。

---

### §2 复平面上的点集

#### 1. 平面点集的基本概念

设 $E\subset\mathbb{C}$。

邻域：

$$
N(z_0,\varepsilon)=\{z\mid |z-z_0|<\varepsilon\}
$$

去心邻域：

$$
0<|z-z_0|<\varepsilon
$$

内点：若存在 $\varepsilon>0$，使

$$
N(z_0,\varepsilon)\subset E
$$

则称 $z_0$ 为 $E$ 的内点。

外点：若存在 $\varepsilon>0$，使

$$
N(z_0,\varepsilon)\cap E=\varnothing
$$

则称 $z_0$ 为 $E$ 的外点。

边界点：任意邻域既含有 $E$ 中的点，又含有不属于 $E$ 的点。

聚点：若 $z_0$ 的任意去心邻域都含有 $E$ 中的点，则 $z_0$ 是 $E$ 的聚点。

孤立点：若 $z_0\in E$，且存在去心邻域不含 $E$ 中点，则 $z_0$ 是孤立点。

开集：每一点都是内点的集合。

闭集：包含其所有聚点的集合。

有界集：存在 $R>0$，使

$$
E\subset\{z:|z|<R\}
$$

#### 2. Jordan 曲线

设连续曲线

$$
z=z(t)=x(t)+iy(t),\quad \alpha\le t\le\beta
$$

若 $z(\alpha)=z(\beta)$，且除端点外没有自交，则称为简单闭曲线，亦称 Jordan 曲线。

Jordan 曲线将平面分成两个部分：

- 内部；
- 外部。

图示说明：笔记中以圆形闭曲线说明内部与外部，以自交曲线说明非 Jordan 曲线。

---

### §3 复变函数

#### 1. 概念

设 $E\subset\mathbb{C}$。若对每个 $z\in E$，按某一规则对应唯一复数 $w$，则称

$$
w=f(z)
$$

为定义在 $E$ 上的复变函数。

写作

$$
z=x+iy,
\quad w=u+iv
$$

其中

$$
u=u(x,y),\qquad v=v(x,y)
$$

故

$$
f(z)=u(x,y)+iv(x,y)
$$

复变函数可看作平面到平面的映射。

#### 2. 极限与连续

设 $f(z)$ 在 $z_0$ 的去心邻域内有定义。若存在复数 $A$，对任意 $\varepsilon>0$，存在 $\delta>0$，当

$$
0<|z-z_0|<\delta
$$

时，有

$$
|f(z)-A|<\varepsilon
$$

则称

$$
\lim_{z\to z_0}f(z)=A
$$

若

$$
f(z)=u(x,y)+iv(x,y),\quad A=a+ib,
$$

则

$$
\lim_{z\to z_0}f(z)=A
\iff
\begin{cases}
\lim_{(x,y)\to(x_0,y_0)}u(x,y)=a,\\
\lim_{(x,y)\to(x_0,y_0)}v(x,y)=b.
\end{cases}
$$

连续性：若 $f$ 在 $z_0$ 有定义，且

$$
\lim_{z\to z_0}f(z)=f(z_0)
$$

则称 $f$ 在 $z_0$ 连续。

若 $f$ 在区域 $D$ 内每一点连续，则称 $f$ 在 $D$ 内连续。

---

## 第二章 解析函数

### §1 解析函数的概念及 Cauchy-Riemann 方程

#### 1. 导数与微分

设 $f(z)$ 在 $z_0$ 的邻域内有定义。若极限

$$
\lim_{\Delta z\to0}\frac{f(z_0+\Delta z)-f(z_0)}{\Delta z}
$$

存在，则称 $f$ 在 $z_0$ 处可导，其值记为

$$
f'(z_0)
$$

若 $f$ 在区域 $D$ 内处处可导，则称 $f$ 在 $D$ 内解析；若在 $z_0$ 的某邻域内解析，则称 $f$ 在 $z_0$ 解析。

微分：

$$
dw=f'(z)\,dz
$$

#### 2. Cauchy-Riemann 方程

设

$$
f(z)=u(x,y)+iv(x,y),\quad z=x+iy
$$

若 $f$ 在 $z_0=x_0+iy_0$ 可导，则有 Cauchy-Riemann 方程：

$$
\frac{\partial u}{\partial x}=\frac{\partial v}{\partial y},
\qquad
\frac{\partial u}{\partial y}=-\frac{\partial v}{\partial x}
$$

且导数可写为

$$
f'(z)=u_x+iv_x=v_y-iu_y
$$

或

$$
f'(z)=u_x-iu_y=v_y+iv_x
$$

充分条件：若 $u,v$ 在 $z_0$ 的邻域内一阶偏导连续，并满足 Cauchy-Riemann 方程，则 $f$ 在 $z_0$ 可导；若在区域 $D$ 内满足，则 $f$ 在 $D$ 内解析。

#### 3. 调和函数与解析函数

若实函数 $u(x,y)$ 二阶连续可偏导，并满足 Laplace 方程

$$
\Delta u=u_{xx}+u_{yy}=0
$$

则称 $u$ 为调和函数。

若

$$
f(z)=u(x,y)+iv(x,y)
$$

在区域 $D$ 内解析，则 $u$ 与 $v$ 均为调和函数。

若 $u,v$ 满足 Cauchy-Riemann 方程，则称 $v$ 为 $u$ 的共轭调和函数。

---

### §2 初等解析函数

#### 1. 指数函数

复指数函数定义为

$$
e^z=e^{x+iy}=e^x(\cos y+i\sin y)
$$

性质：

$$
e^{z_1+z_2}=e^{z_1}e^{z_2}
$$

$$
(e^z)'=e^z
$$

$$
e^{z+2\pi i}=e^z
$$

故 $e^z$ 以 $2\pi i$ 为周期。

#### 2. 三角函数

复三角函数定义：

$$
\sin z=\frac{e^{iz}-e^{-iz}}{2i},
\qquad
\cos z=\frac{e^{iz}+e^{-iz}}{2}
$$

性质：

$$
(\sin z)'=\cos z,
\qquad
(\cos z)'=-\sin z
$$

$$
\sin^2 z+\cos^2 z=1
$$

展开为实、虚部：

$$
\sin(x+iy)=\sin x\cosh y+i\cos x\sinh y
$$

$$
\cos(x+iy)=\cos x\cosh y-i\sin x\sinh y
$$

双曲函数：

$$
\sinh z=\frac{e^z-e^{-z}}{2},\qquad
\cosh z=\frac{e^z+e^{-z}}{2}
$$

#### 3. 初等多值函数

对数函数：若

$$
w=\log z
$$

表示 $e^w=z$，则

$$
\log z=\ln|z|+i\arg z
$$

即

$$
\log z=\ln r+i(\theta+2k\pi),\quad k\in\mathbb{Z}
$$

主值：

$$
\operatorname{Log}z=\ln|z|+i\operatorname{Arg}z
$$

在割去负实轴或适当割线的区域上，可选取单值解析分支。

幂函数：

$$
z^\alpha=e^{\alpha\log z}
$$

当 $\alpha$ 非整数时，一般为多值函数。

根式函数：

$$
w=\sqrt[n]{z}=z^{1/n}
$$

有 $n$ 个值：

$$
w_k=\sqrt[n]{r}\exp\left(i\frac{\theta+2k\pi}{n}\right),\quad k=0,1,\ldots,n-1
$$

---

## 第三章 复变函数积分

### §1 复变函数的积分概念、性质和计算

#### 1. 定义

设曲线 $C$ 由参数方程给出：

$$
z=z(t),\quad a\le t\le b
$$

且 $f$ 在 $C$ 上连续。将 $[a,b]$ 分割为

$$
a=t_0<t_1<\cdots<t_n=b
$$

对应曲线上点

$$
z_k=z(t_k)
$$

取 $\xi_k$ 为弧段 $z_{k-1}z_k$ 上任一点。若极限存在，则定义

$$
\int_C f(z)\,dz
=\lim_{\lambda\to0}\sum_{k=1}^{n}f(\xi_k)\Delta z_k
$$

其中

$$
\Delta z_k=z_k-z_{k-1}
$$

若 $z(t)=x(t)+iy(t)$，$f(z)=u(x,y)+iv(x,y)$，则

$$
\int_C f(z)\,dz
=\int_a^b f(z(t))z'(t)\,dt
$$

并可转化为实线积分：

$$
\int_C f(z)\,dz
=\int_C (u+iv)(dx+i\,dy)
$$

$$
=\int_C (u\,dx-v\,dy)+i\int_C (v\,dx+u\,dy)
$$

#### 2. 基本性质

线性：

$$
\int_C[\alpha f(z)+\beta g(z)]\,dz
=\alpha\int_C f(z)\,dz+
\beta\int_C g(z)\,dz
$$

路径反向：

$$
\int_{-C} f(z)\,dz=-\int_C f(z)\,dz
$$

路径可加：若 $C=C_1+C_2$，则

$$
\int_C f(z)\,dz=\int_{C_1}f(z)\,dz+\int_{C_2}f(z)\,dz
$$

估值不等式：若 $|f(z)|\le M$，$C$ 的长度为 $L$，则

$$
\left|\int_C f(z)\,dz\right|\le ML
$$

#### 3. 原函数与积分

若 $F'(z)=f(z)$，则

$$
\int_C f(z)\,dz=F(b)-F(a)
$$

其中 $a,b$ 为路径端点。因此若 $C$ 为闭曲线，则

$$
\int_C f(z)\,dz=0
$$

---

### §2 两个积分定理

#### 1. Cauchy 积分定理

若 $f(z)$ 在单连通区域 $D$ 内解析，$C$ 是 $D$ 内任一闭曲线，则

$$
\int_C f(z)\,dz=0
$$

常用特例：若 $f$ 在闭圆盘及其内部解析，则沿圆周积分为零。

#### 2. 不定积分

若 $f$ 在单连通区域 $D$ 内解析，则存在原函数 $F$，使得

$$
F'(z)=f(z)
$$

此时积分与路径无关。

#### 3. 复合闭路定理

设 $C,C_1,\ldots,C_n$ 为若干互不相交的简单闭曲线，$C$ 包含所有 $C_k$，且 $f$ 在这些曲线围成的区域内解析，则

$$
\int_C f(z)\,dz=
\sum_{k=1}^{n}\int_{C_k} f(z)\,dz
$$

内边界方向通常取负向，需与外边界方向相配合。

---

### §3 Cauchy 积分公式及其推广

#### 1. Cauchy 积分公式

若 $f$ 在闭曲线 $C$ 及其内部解析，$C$ 为正向简单闭曲线，$z_0$ 在 $C$ 内，则

$$
f(z_0)=\frac{1}{2\pi i}\int_C\frac{f(z)}{z-z_0}\,dz
$$

等价地，

$$
\int_C\frac{f(z)}{z-z_0}\,dz=2\pi i f(z_0)
$$

特别地：

$$
\int_C\frac{1}{z-z_0}\,dz=2\pi i
$$

若 $z_0$ 在 $C$ 外部，则

$$
\int_C\frac{f(z)}{z-z_0}\,dz=0
$$

#### 2. 高阶导数公式

若 $f$ 在 $C$ 及其内部解析，$z_0$ 在 $C$ 内，则

$$
f^{(n)}(z_0)=\frac{n!}{2\pi i}
\int_C\frac{f(z)}{(z-z_0)^{n+1}}\,dz,
\quad n=0,1,2,\ldots
$$

即

$$
\int_C\frac{f(z)}{(z-z_0)^{n+1}}\,dz
=\frac{2\pi i}{n!}f^{(n)}(z_0)
$$

#### 3. Cauchy 不等式与 Liouville 定理

若 $f$ 在 $|z-z_0|\le R$ 内解析，且

$$
|f(z)|\le M_R
$$

则

$$
|f^{(n)}(z_0)|\le\frac{n!M_R}{R^n}
$$

Liouville 定理：若 $f$ 在整个复平面解析且有界，则 $f$ 为常数。

推论：非零多项式必有复根，即代数基本定理可由 Liouville 定理推出。

#### 4. Morera 定理

若 $f$ 在区域 $D$ 内连续，且对 $D$ 内任意闭曲线 $C$ 都有

$$
\int_C f(z)\,dz=0
$$

则 $f$ 在 $D$ 内解析。

---

### §4 解析函数与调和函数的关系

#### 1. 调和函数

若实函数 $H(x,y)$ 二阶连续可偏导，并满足

$$
\frac{\partial^2 H}{\partial x^2}+\frac{\partial^2 H}{\partial y^2}=0
$$

则称 $H$ 为调和函数。

#### 2. 解析函数与调和函数

若

$$
f(z)=u(x,y)+iv(x,y)
$$

在区域 $D$ 内解析，则

$$
u_{xx}+u_{yy}=0,
\qquad
v_{xx}+v_{yy}=0
$$

因此实部 $u$ 与虚部 $v$ 均为调和函数。

反之，若 $u$ 是单连通区域 $D$ 内的调和函数，则存在调和共轭函数 $v$，使

$$
f(z)=u+iv
$$

在 $D$ 内解析。

由 Cauchy-Riemann 方程：

$$
u_x=v_y,
\qquad
u_y=-v_x
$$

求共轭调和函数时可由

$$
dv=v_xdx+v_y dy=-u_y dx+u_x dy
$$

积分得到 $v$。

---

## 第四章 解析函数表示为级数的方法

### §1 复级数的基本性质

#### 1. 复数列与级数

设

$$
z_n=x_n+iy_n
$$

若

$$
\lim_{n\to\infty}z_n=z
$$

则等价于

$$
\lim_{n\to\infty}x_n=x,
\qquad
\lim_{n\to\infty}y_n=y
$$

复级数：

$$
\sum_{n=1}^{\infty}a_n
$$

部分和：

$$
S_n=\sum_{k=1}^{n}a_k
$$

若 $S_n\to S$，则称级数收敛，$S$ 为和。

若 $a_n=\alpha_n+i\beta_n$，则

$$
\sum a_n\text{ 收敛}
\iff
\sum\alpha_n\text{ 与 }\sum\beta_n\text{ 均收敛}
$$

#### 2. 绝对收敛

若

$$
\sum_{n=1}^{\infty}|a_n|
$$

收敛，则称

$$
\sum_{n=1}^{\infty}a_n
$$

绝对收敛。

绝对收敛必收敛。

Cauchy 收敛准则：级数 $\sum a_n$ 收敛当且仅当对任意 $\varepsilon>0$，存在 $N$，当 $n>N$、$p>0$ 时，

$$
\left|\sum_{k=n+1}^{n+p}a_k\right|<\varepsilon
$$

#### 3. 函数项级数

函数项级数：

$$
\sum_{n=1}^{\infty}f_n(z)
$$

若对 $D$ 内每个 $z$ 都收敛，则其和函数为

$$
f(z)=\sum_{n=1}^{\infty}f_n(z)
$$

一致收敛：对任意 $\varepsilon>0$，存在 $N$，使 $n>N$ 时对所有 $z\in D$ 都有

$$
\left|\sum_{k=n+1}^{n+p}f_k(z)\right|<\varepsilon
$$

Weierstrass 判别法：若

$$
|f_n(z)|\le M_n,
\qquad z\in D
$$

且

$$
\sum M_n
$$

收敛，则

$$
\sum f_n(z)
$$

在 $D$ 内一致收敛。

一致收敛级数若各项连续，则和函数连续。

若各项解析且在区域内一致收敛，则和函数解析，并可逐项积分；在一定条件下可逐项求导。

---

### §2 幂级数

幂级数形式：

$$
\sum_{n=0}^{\infty}c_n(z-a)^n
$$

其中 $a$ 为中心，$c_n$ 为复系数。

#### 1. Abel 定理

若幂级数在某点 $z_1$ 收敛，则在圆

$$
|z-a|<|z_1-a|
$$

内绝对收敛，且在任意闭圆

$$
|z-a|\le r<|z_1-a|
$$

上一致收敛。

若幂级数在某点 $z_2$ 发散，则在

$$
|z-a|>|z_2-a|
$$

处发散。

因此存在收敛半径 $R$：

- $|z-a|<R$ 时绝对收敛；
- $|z-a|>R$ 时发散；
- $|z-a|=R$ 上需逐点判断。

#### 2. 收敛半径

Cauchy-Hadamard 公式：

$$
\frac{1}{R}=\limsup_{n\to\infty}\sqrt[n]{|c_n|}
$$

若极限存在，也可用比值法：

$$
R=\lim_{n\to\infty}\left|\frac{c_n}{c_{n+1}}\right|
$$

或根值法。

#### 3. 幂级数的性质

在收敛圆内，幂级数和函数解析，并且可逐项求导与逐项积分：

$$
\left(\sum_{n=0}^{\infty}c_n(z-a)^n\right)'
=\sum_{n=1}^{\infty}n c_n(z-a)^{n-1}
$$

$$
\int \sum_{n=0}^{\infty}c_n(z-a)^n\,dz
=\sum_{n=0}^{\infty}\frac{c_n}{n+1}(z-a)^{n+1}+C
$$

求导和积分后的收敛半径不变。

---

### §3 解析函数的 Taylor 展开

#### 1. Taylor 定理

若 $f$ 在圆盘

$$
|z-a|<R
$$

内解析，则 $f$ 可在该圆盘内展开为 Taylor 级数：

$$
f(z)=\sum_{n=0}^{\infty}c_n(z-a)^n
$$

其中

$$
c_n=\frac{f^{(n)}(a)}{n!}
$$

故

$$
f(z)=\sum_{n=0}^{\infty}\frac{f^{(n)}(a)}{n!}(z-a)^n
$$

系数也可由 Cauchy 积分公式给出：

$$
c_n=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-a)^{n+1}}\,d\zeta
$$

其中 $C$ 为圆盘内绕 $a$ 的正向闭曲线。

#### 2. 常用展开式

指数函数：

$$
e^z=\sum_{n=0}^{\infty}\frac{z^n}{n!},\quad z\in\mathbb{C}
$$

正弦函数：

$$
\sin z=\sum_{n=0}^{\infty}(-1)^n\frac{z^{2n+1}}{(2n+1)!}
$$

余弦函数：

$$
\cos z=\sum_{n=0}^{\infty}(-1)^n\frac{z^{2n}}{(2n)!}
$$

几何级数：

$$
\frac{1}{1-z}=\sum_{n=0}^{\infty}z^n,
\quad |z|<1
$$

对数函数：

$$
\log(1+z)=\sum_{n=1}^{\infty}(-1)^{n-1}\frac{z^n}{n},
\quad |z|<1
$$

一般二项式：

$$
(1+z)^\alpha=1+\alpha z+\frac{\alpha(\alpha-1)}{2!}z^2+\
\cdots
$$

即

$$
(1+z)^\alpha=\sum_{n=0}^{\infty}\binom{\alpha}{n}z^n,
\quad |z|<1
$$

#### 3. 展开举例

将函数化为已知展开形式，再通过代换、求导、积分等方式展开。

例：

$$
\frac{1}{z-a}
$$

在不同圆环内展开时，应根据 $|z|$ 与 $|a|$ 的关系选择形式。

---

### §4 解析函数零点和孤立奇点的第一类定理

#### 1. 解析函数零点的孤立性

若 $f$ 在 $z_0$ 的邻域内解析，且

$$
f(z_0)=0
$$

若存在正整数 $m$，使

$$
f(z_0)=f'(z_0)=\cdots=f^{(m-1)}(z_0)=0,
\qquad
f^{(m)}(z_0)\ne0
$$

则称 $z_0$ 是 $f$ 的 $m$ 阶零点。

此时

$$
f(z)=(z-z_0)^m\varphi(z)
$$

其中 $\varphi$ 在 $z_0$ 邻域解析，且

$$
\varphi(z_0)\ne0
$$

若 $f$ 不恒为零，则其零点是孤立的。

#### 2. 唯一性定理

若 $f,g$ 在区域 $D$ 内解析，且存在 $D$ 内具有聚点的点列 $\{z_n\}$，满足

$$
f(z_n)=g(z_n)
$$

则

$$
f(z)\equiv g(z),\quad z\in D
$$

特别地，若解析函数 $f$ 在区域 $D$ 内有具有聚点的零点集，则

$$
f\equiv0
$$

#### 3. 最大模原理

若 $f$ 在有界区域 $D$ 内解析，在闭区域 $\bar D$ 上连续，且 $f$ 非常数，则 $|f(z)|$ 的最大值只能在边界上取得。

若 $|f|$ 在区域内部取得最大值，则 $f$ 为常数。

---

## 第五章 解析函数的 Laurent 展开与孤立奇点

### §1 解析函数的 Laurent 展开

#### 1. 双边幂级数

Laurent 级数形式：

$$
\sum_{n=-\infty}^{\infty}c_n(z-a)^n
$$

可写作

$$
\sum_{n=0}^{\infty}c_n(z-a)^n+
\sum_{n=1}^{\infty}c_{-n}(z-a)^{-n}
$$

前者称为正幂部分，后者称为主要部分。

若正幂部分收敛半径为 $R$，负幂部分在 $0<|z-a|<r$ 外侧满足收敛条件，则 Laurent 级数在某圆环

$$
r<|z-a|<R
$$

内收敛。

#### 2. Laurent 定理

若 $f$ 在圆环

$$
r<|z-a|<R
$$

内解析，则 $f$ 在该圆环内可唯一展开为 Laurent 级数：

$$
f(z)=\sum_{n=-\infty}^{\infty}c_n(z-a)^n
$$

其中

$$
c_n=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-a)^{n+1}}\,d\zeta,
\quad n\in\mathbb{Z}
$$

$C$ 为圆环内绕 $a$ 的任一正向简单闭曲线。

#### 3. Laurent 级数与 Taylor 级数关系

当主要部分为零，即

$$
c_{-1}=c_{-2}=\cdots=0
$$

时，Laurent 级数退化为 Taylor 级数。

Taylor 级数可视为 Laurent 级数的一种特殊情形。

---

## 附：按页码的主题索引

| 页码 | 主题 |
|---:|---|
| 1 | 复数域、复数运算、复平面初步 |
| 2 | 模、辐角、主辐角、共轭复数 |
| 3 | 复数几何意义、共圆判别、乘方与方根 |
| 4 | De Moivre 公式、复数方程与几何图形 |
| 5 | 直线/圆的复数方程、无穷远点与复球面 |
| 6 | 点集概念、Jordan 曲线、单连通/多连通区域 |
| 7 | 复变函数定义、映射、极限与连续 |
| 8 | 极限、连续、有界性相关性质 |
| 9 | 解析函数、导数定义、Cauchy-Riemann 方程 |
| 10 | Cauchy-Riemann 方程推论与充分条件 |
| 11 | 指数函数、三角函数、双曲函数 |
| 12 | 多值函数、对数函数、割线与单值分支 |
| 13 | 根式函数、多值性图示 |
| 14 | 对数函数分支、复幂函数 |
| 15 | 对数函数分支与导数、一般幂函数 |
| 16 | 幂函数分支、单值分支条件 |
| 17 | 反三角/反双曲函数相关条目（字迹较少） |
| 18 | 复积分定义、性质、计算公式 |
| 19 | Cauchy 积分定理、不定积分 |
| 20 | Cauchy 积分定理推广、复合闭路定理 |
| 21 | Cauchy 积分公式、高阶导数公式 |
| 22 | Cauchy 不等式、Liouville 定理、Morera 定理 |
| 23 | 调和函数与解析函数关系 |
| 24 | 复数列、复级数、收敛准则 |
| 25 | 绝对收敛、条件收敛、判别法 |
| 26 | 函数项级数、一致收敛、Weierstrass 判别法 |
| 27 | 解析函数项级数的性质 |
| 28 | 幂级数、Abel 定理、收敛圆 |
| 29 | 幂级数性质、Cauchy-Hadamard 定理、Taylor 展开 |
| 30 | Taylor 级数展开与常用例题 |
| 31 | 常用 Taylor 展开、零点与唯一性定理 |
| 32 | 解析函数零点、唯一性定理 |
| 33 | 最大模原理 |
| 34 | Laurent 级数与 Laurent 展开 |

---

## 待核对项

1. 第 17 页部分内容较少且字迹偏浅，反三角/反双曲函数公式需对照原稿二次核对。  
2. 少数图示仅保留文字说明，若后续需要，可单独从原 PDF 裁图嵌入 Markdown。  
3. 个别例题的中间推导在扫描图中较密集，本稿优先保留核心公式与结论。
