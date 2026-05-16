# 第1章 随机过程的基本概念

# 1.1 随机过程的定义

*Def (随机过程)

> 随机过程是概率空间$(Ω, F, P)$上的一族随机变量 $\{x(t),t∈T\}$ ，其中 $T$ 称为指标集式参数集

注：随机过程是从$(Ω×T)$到$R$上的映射： $(\omega,t)↦X(\omega,t)$

(1) 固定 $t$ , $X(\omega, t)$是一个随机变量

(2) 固定 $\omega$, $X(\omega,t)$ 是关于 $t$ 的函数,称为 $\omega$ 的样本函数或样本轨道

# 1.2 随机过程的分布

*Def (一维分布函数)

> 设 $\{X(t),t∈T\}$ 为随机过程，对任意固定的 $t∈T$ ，称$$F_1​(x;t)=P(X(t)≤x) ，x∈\mathbb{R}$$ 为随机过程 $\{x(t),t∈T\}$ 的一维分布函数。

*Def (离散型: 一位概率分布)

>设 $\{X(t),t \in T\}$ 为随机过程，对任意固定的 $t∈T$ ，若 $P_k​(t)=P\{X(t)=x_k​\}, k = 1, 2...$
>满足：(1) 非负性： $P_k​(t)≥0,k=1,2⋯$ 
>       (2) 规范性： $\sum_{k=1}^{\infty}p_k(t)=1$
>则称 $P_k​(t)$ 为随机过程 $X(t)$ 的一维概率分布。

*Def(连续型:一位概率密度函数)

>设 $\{X(t),t∈T\}$ 为随机过程，对任意固定的 $t∈T$ ，若存在非负可积函数 $f_1​(x,t)$ ，满足 $F_1​(x,t)=\int_{-\infty}^{x}​f_1​(y,t)dy, ∀x∈\mathbb{R}$，则称 $f_1(x;t)$ 为 $X(t)$ 的一维概率密度函数。

*Def (二维分布函数)

>设$\{X(t),t \in T\}$ 为随机过程,对任意两个时刻 $t_1,t_2\in T$ ,称$$F_2​(x_1​,x_2​;t_1,t_2​)=P\{X(t_1​)≤x_1​,X(t_2​)≤x_2​\} (x_1​,x_2​)\in \mathbb{R}^2$$ 为随机过程$\{X(t),t \in T\}$的二维分布函数。

*Def (n维分布函数)

>设 $\{X(t),t \in T\}$ 为随机过程, $n∈\mathbb{N}^∗$,$t_1​,t_2​,⋯,t_n​∈T$ , 称$$F_n​(x_1​,x_2​,⋯,x_n​;t_1,t_2​,t_n​) = P \{X(t_1​)≤x_1​,⋯,X(t_n​)≤x_n \},(x_1​,x_2​ \cdots x_n​)∈\mathbb{R}^n$$为随机过程$\{X(t),t\in T\}$的n维分布函数。

*Def (有限维分布函数族)

>随机过程 $\{X(t),t \in T\}$ 的所有有限维分布函数的全体：$$\{F_n​(x_1​,x_2​,⋯,x_n​;t_1,t_2,⋯t_n​),x_i∈\mathbb{R},t_i∈T,1≤i≤n∈\mathbb{N}^*\}$$称为此随机过程的有限维分布函数。

*Prop. (有限维分布函数族的性质)

>(1) 对称性
>(2) 相容性

注：(柯尔莫哥洛夫存在定理)
>函数族 $\{F_n​(x_1,⋯,x_n;t_1,⋯,t_n​), x_i∈\mathbb{R},t_i∈T,1≤i≤n∈\mathbb{R}^∗\}$ 能为某随机过程的有限维分布函数族当且仅当它满足对称性和相容性。

# 1.3 随机过程的数学特征

*Def (均值函数)

>$∀t∈T.E[X(t)]$ 存在， $m_x​(t)=E[X(t)]$

*Def (均方值函数)

>$∀x∈T,E[x^2(t)]$ 存在， $\psi_x^2​(t)=E[X^2(t)]$

*Def (自相关函数)

>$∀s.t\in T,E[X(s)X(t)]$ 存在,$R_x​(s,t)=E[X(s)X(t)]$

*Def (方差函数)

>$∀t\in T,E[X(t)−m_x​(t)]^2$ 存在,$D_x​(t)=E[X(t)−m_x​(t)]^2=\psi_x^2​(t)−m_x^2​(t)$

*Def (自协方差函数)

>$∀s.t∈T,E\{[X(s)−m_x​(s)][X(t)−m_x​(t)]\}$ 存在，$C_x​(s.t)=E\{[X(s)−m_x​(s)][X(t)−m_x​(t)]\}=R_x(s,t)-m_x(s)m_x(t)$

# 随机过程的特征函数

*Def(一维特征函数)

>随机过程 $\{X(t),t \in T\}$ 的一维特征函数定义为$$φ_X​(v;t)=φ_X(t)​(v)=E[e^ivX(t)],v∈\mathbb{R},t∈T$$

注：
$$
\varphi_x(v;t)=
\begin{cases}
\displaystyle\sum_{k=1}^{\infty} e^{ivx_k}p_k(t), & X(t)\text{为离散型随机变量} \\
\displaystyle\int_{-\infty}^{\infty} e^{ivx}f(x;t)dx, & X(t)\text{为连续型随机变量}
\end{cases}
$$

*Def (n 维特征函数)

>随机过程 (x(t),t(t)) 的n值特征函数定义为$$φ_x​(v_1​,\dots,v_n​;t_1​,\dots,t_n​)=E[exp(i\displaystyle\sum_{k=1}^{n} v_k​X(t_k​))]$$其中, $V_k​∈\mathbb{R},t_k​∈T,1≤k≤n$.

*Def (有限维特殊函数族)

>随机过程 $\{X(t),t \in T\}$ 的所有有限维特征函数的全体$$\{\varphi_x​(v_1​,v_2,\dots,v_n​;t_1,…,t_n​),\forall v_k \in \mathbb{R},​t_k \in T,1\le k≤n\}$$称为此随机过程的有限维特征函数族。

# 复随机过程与二维随机过程

*Def（复随机过程）

>设 $X(t)$ 与 $Y(t)$ 为两个实随机过程, 则称$\{ Z(t)=X(t)+iY(t), t \in T\}$  为复随机过程, 其中$i =\sqrt{−1}​$ .

*Def (复随机过程的有限维分布函数族)

>对复随机过程 $\{Z(t)=X(t)+iY(t)​,t \in T\}$ ，称 $(X(t),Y(t))$ 的联合分布函数为$Z(t)$的分布函数： $F(x_1,⋯,x_n​,y_1​,⋯,y_n;t_1,\dots,t_n​)=P\{X(t_k)\le x_k,Y(t_k) \le y_k, 1 \le k \le n\}$
>并称$\{F(x_1​,\dots, x_n,y_1​,\dots,y_n​;t_1,\dots,t_n)\,\bigg|\,\forall t_k \in T,x_k​ \in \mathbb{R},y_k​ \in \mathbb{R},1 \le k \le n \in \mathbb{R}\}$ 为已知的有限维分布函数族。

*Def($Z(t)=X(t)+iY(t)​)$ 的均值函数,均方值函数,方差函数,自相关函数.

>$m_z​(t)=E[Z(t)]=E[X(t)]+iE[Y(t)]$
>$\psi^2_Z(t)=E[|Z(x)|^2]=E[Z(t)\overline{Z(t)}​]$
>     注:$\psi^2_Z(t)=\psi^2_X(t)+\psi^2_Y(t)$
>$D_Z​(t)=D[Z(t)]=E\{[Z(t)−m_Z​(t)]\overline{[Z(t)−m_Z​(t)]}\}$​
>     注:$D_Z​(t)=D_X(t)+D_Y​(t)$
>$R_z​(s,t)=E[Z(s)Z(t)​]$
>     注: $R_Z​(s,t)=R_X​(s,t)−iR_{XY}​(s,t)+iR_{YX}​(s,t)+​R_Y​(s,t)$
>$C_Z​(s,t)=E\{[Z(s)−m_Z​(s)]\overline{[Z(t)−m_Z​(t)]​}\}$
>     注:$C_Z​(s,t)=R_Z​(s,t)−m_Z​(s)m_Z​(t)$​

*Def (二维随机过程)

>若 $∀s∈S,t∈T,(X(s),Y(t))$ 是概率空间 (Ω,π,p) 上的二维随机变量，则称 $\{(X(s),Y(t)),s\in S,t \in T\}$ 为二维随机过程，简记为 $(X(s),Y(t))$

注：

![](file:///C:/Users/Alice/MinerU/%E9%9A%8F%E6%9C%BA%E8%BF%87%E7%A8%8B.pdf-a0b2711a-4aeb-480c-82ce-642d983a25db/images/7cf4c424be7b2604a5b4b4a3970aad8ef65368f936a75151cc9aaa0b06e69eaa.jpg)

![](file:///C:/Users/Alice/MinerU/%E9%9A%8F%E6%9C%BA%E8%BF%87%E7%A8%8B.pdf-a0b2711a-4aeb-480c-82ce-642d983a25db/images/c3ddee670251eabc6f53963bd8d35b1af6a2be9e05f5d77acb10ec3ca3845f6f.jpg)

*Def (二维随机过程的分布函数)

>对 $∀m,n \in \mathbb{N}^∗ ,s_1,s_2,\dots,s_m​ \in S , t_1​,t_2​,\dots,t_n​\in T$ ,称$$F_{m+n​}(x_1​,x_2​,\dots,x_m​,y_1​,y_2,​\dots,y_n​;s_1​,s_2,\dots,​s_m​,t_1​,t_2,\dots,t_n​)=P\{X(s_i​)≤x_i,Y(t_j​)≤y_j​,1≤i≤m,1≤j≤n\}$$ 为 $\{(X(s),Y(t),s∈S,t∈T\}$ 的m+n维分布函数.

*Def(相互独立的随机过程)

>若 $\forall m,n​ \in \mathbb{N}^∗ , s_i​∈S , t_j​∈T , x_i​,y_j​∈\mathbb{R},1≤i≤m , 1≤j≤n$$F_{m+n​}(x_1​,x_2​,⋯,x_n​,y_1​,⋯,y_n​;s_1​,⋯,s_m​,t_1​,⋯t_n​)=F^*_m​(x_1​,⋯,x_m​;s_1​,⋯,s_m​)F^*_n​(y_1​,⋯,y_n​;t_1​,⋯,t_n​)$ 恒成立，则称随机过程 $\{X(s),s \in S\}$ 与 $\{Y(t),t \in T\}$ 相交独立。

*Def (二维随机过程的数字特征)

>若$(X(s),Y(t))$ 为二维随机过程, 则称 $R_{XY}​(s,t)=E[X(s),Y(t)]$为随机过程 $X(s)$ 与 $Y(t)$ 的互相关函数。
>称 $C_{XY}​(s,t)=E[X(s)−m_X​(s)][Y(t)−m_Y(t)]$ 为随机过程 $X(s)$ 与 $Y(t)$ 的互协方差方差函数。
>	注：称随机过程 $X(s)$ 与 $Y(t)$ 不相关，若 $C_{XY}​(s,t)=0 ,\forall s\in S,t\in T$ 。

# 随机过程的分类

按参数集与状态空间分类

|     | 离散      | 连续   |
| --- | ------- | ---- |
| 离散  | 离散参数链   | 随机序列 |
| 连续  | (连续参数)链 | 随机过程 |

*Def(实二阶矩过程)

>设 $X(t)$ 为实随机过程, 若其均方值函数 $\psi^2_x​(t)=E[X^2(t)]$ ，对于 $∀t∈T$ 都存在. 则称此 $X(t)$ 为实二阶矩过程。

*Def (复二阶矩过程).

>设 $Z(t)$ 为复随机过程, 若其均方值函数 $\psi^2_x​(t)=E[|Z(t)|^2]$  , 对于 $∀t∈T$ 都存在. 则称此 $Z(t)$ 为复二阶矩过程。

>Prop. 二阶矩过程的均值函数和自相关函数必然存在.
>	注：二阶矩有限 则一阶矩有限.(由Cauchy-Schwarz不等式)$$[E(XY)]^2≤E(X^2)E(Y^2)⇒[E(X)]^2≤E(X^2)<∞$$.

>Prop 自相关函数 $R_Z​(s,t)$ 具有 Hermite 性
$$\overline{R_Z(s,t)}​=R_Z(t,s),s∈S,t∈T$$

>Prop. (自相关函数 $R_Z​(s,t)$ 具有非负极性).
>$$\displaystyle\sum_{i=1}^{n}\displaystyle\sum_{j=1}^{n}R_Z(t_i,t_j)a_i\overline{a_j}\ge0,\forall n\in \mathbb{N}^*,t_i \in T,a_i \in \mathbb{C},1\le i\le n$$
	注： $R_Z​(t_i​,t_j​)$ 不一定 $≥0,t_i​,t_j​∈T$ .

>Prop . (自协方差函数$C_z​(s,t)$ 具有非负定性)
>$$\displaystyle\sum_{i=1}^{n}\displaystyle\sum_{j=1}^{n}C_Z(t_i,t_j)a_i\overline{a_j}\ge0,\forall n\in \mathbb{N}^*,t_i \in T,a_i \in \mathbb{C},1\le i\le n$$
	注：自协方差函数 $C_Z(s,t) 具有Hermite性。

**Thm (二阶矩过程的存在性定理)

>设定义在参数集$T \in \mathbb{R}$上的二元函数 $R(s,t)$ 成为某二阶矩过程 $X(t)$ 的自相关函数的充要条件是它满足非负定性。
	注：当 R(s,t) 是实值二元非负函数,而 X(t) 是一个实二阶矩过程

*Def(独立过程)

>称 $\{X(t),t∈T\}$ 为独立过程,若对 $∀n \in \mathbb{N}^*,t_1,…,t_n∈T,X(t_1),X(t_2),\dots X(t_n)$ 相互为独立.

*Def (独立增益过程).

>若 $∀n⩾3,\text{及}t_1,t_2<⋯<t_n \in T, X(t_2​)−X(t_1​), X(t_3​)−X(t_2​),⋯,X(t_n​)−X(t_{n−1}​)$ 相互为独立，则称 $\{X(t),t \in T\}$ 为独立增量过程（可加过程）.
	注：独立过程累加和为独立增量过程。

>Prop. 设 $\{X(t) | a≤t≤b\}$ 是独立增量过程，则 $\{Y(t)=X(t)−X(a)|a≤t≤b\}$ 仍为独立增量过程
	注：独立增量过程强调增量，而不强调从哪点开始。独立增量过程的初值不影响其独立增量性，故通常假设初值为0。

>Prop. 设 $\{X(t),t \in T\}$ 是独立增量过程，则增量 $X(s,t)=X(t)−X(s)$ 的分布函数 F(x;s,t) 满足 $F(x;t_1​,t_3​)=F(x;t_1​,t_2​) \star F(x;t_2​,t_3​) ∀t_1​<t_2​<t_3​ \in T$
	注：$\star$ 表示卷积。

*Def (平稳增量过程)

>称随机过程 $X(t)$ 为平稳(齐次)增量过程. 若 $∀s,t,h∈T,X(t+h)−X(s+h) \text{与} X(t)−X(s)$ 同分布。
	注：若它是独立增量过程，也称之为平稳(齐次)独立增量过程。

**Example (平稳独立增量过程的方差函数与自协方差函数)

>设二阶矩过程 $\{X(t),t≥0\}$ 具有平稳独立增量且 $X(0)=0 , \forall s,t≥0$
(1)$D[X(t)−X(s)]=σ^2∣t−s∣$(绝对齐性)        
​(2)$C_X​(s,t)=σ^2(s \wedge t)$
其中 $\sigma^2 = D[X[1]],s \wedge t=min\{s,t\}$

*Def(不相关增量过程)

>设 $\{X(t),t∈T\}$ 为二阶矩过程，若对 $∀t_1​<t_2​≤t_3​<t_4​∈T,X(t_2​)−X(t_1​) \text{与} X(t_4​)−X(t_3​)$不相关，即 $Cov(X(t_2​)−X(t_1​),X(t_4​)−X(t_3​))=0$ 则称此 $X(t)$ 为不相关增量过程。

*Def(正交增量过程)

>设 $\{X(t),t \in T\}$ 为二阶矩过程,若对 $$∀t_1​<t_2​<t_3​<t_4​∈T,​ E\{[X(t_2​)−X(t_1​)]\overline{[X(t_4​)−X(t_3​)]}\}=0$$ 则称此 $X(t)$ 为正交增量过程。

注：

![](file:///C:/Users/Alice/MinerU/%E9%9A%8F%E6%9C%BA%E8%BF%87%E7%A8%8B.pdf-a0b2711a-4aeb-480c-82ce-642d983a25db/images/5f0b827e4f486cfadbb7fdd3e20cc860878813b1ccd8675c035f8859b092bb59.jpg)

![](file:///C:/Users/Alice/MinerU/%E9%9A%8F%E6%9C%BA%E8%BF%87%E7%A8%8B.pdf-a0b2711a-4aeb-480c-82ce-642d983a25db/images/3451215cad1cdb26a77fad53e59e785b8378bb992fe19d2598b6f4adc48687bf.jpg)


**Example 设 $\{X(t),t \in T \}$为正交增量过程, $X(a)=0$,
(1) $R_X(s,t)=R_X​(s∧t,s∧t)$
(2) $R_X​(t,t)$ 是 $[a,b]$ 上的单调不减函数

*Def (正态过程/高斯过程)

>若随机过程 $\{X(t),t \in T\}$ 的任意有限维分布为正态分布,则称之为正态过程。即 
>$$∀n∈\mathbb{N}^∗,t_1,t_2,⋯,t_n∈T,(X(t_1),X(t_2),⋯,X(t_n))∼N(\mu,Σ)$$其中 $\mu=(m_X​(t_1​),…m_X​(t_n​))^T,∑=(∑_{ij})_{n×n​},∑_{ij}​=Cov[X(t_i​),X(t_j​)],1 \le i,j \le n$

**Thm n维随机变量 $(X_1​,X_2​,\dots,X_n​)$ 服从 n 维正态分布 ⇔ n 个随机变量 $X_1​,X_2​,\dots X_n$。的任意非零线性组合均服从一维正态分布。

*Def (复正态过程)

>设 $\{X(t),t \in T\}$，$\{Y(t),t \in T\}$ 均为实正态过程，则称$\{Z(t)=X(t)+iY(t),t \in T\}$ 为复正态过程。

*Def(布朗运动)

>若随机过程 $\{B(t),t \ge 0\}$ 满足：
>(1) $B(0)=0,a.s.$；
>(2) $\{B(t),t≥0\}$ 具有独立增量；
>(3) 对 $∀s<t,B(t)−B(s)∼N(0,\sigma^2(t−s))$ (平稳增量)
>则称 $B(t)$ 为参数是 $\sigma^2$ 的布朗运动或维纳过程。
	注：当 $σ=1$ 时,称为标准布朗运动。当 $\sigma \ne 1$ 时, $\frac{B(t)}{\sigma}$​ 是标准布朗运动。

*Prop. 布朗运动是具有平稳独立增量的正态过程.

*Prop. 标准布朗运动$B(t)$的自协方差矩阵为 $C_B​(s,t)=s∧t=min(s,t)$ ，且则 $$∀n∈\mathbb{N},t_1​<t_2​⋯<t_n​,B=(B(t_1​),B(t_2​)…B(t_n​))∼N(0,∑_n​)$$其中，求协方差矩阵为$$∑_n​=
\begin{pmatrix}
t_{1} & t_{1} & \dots & t_{1}\\
t_{1} & t_{2} & \dots & t_{2}\\
\vdots & \vdots & \ddots & \vdots\\
t_{1} & t_{2} & \dots & t_{n}
\end{pmatrix}
$$​

# 第2章 均方微积分

# 均方极限

*Def (二阶矩变量空间)

>称二阶矩存在的随机变量的全体组成的集合$H=\{X∣E(X^2)<+∞\}$ 为二阶矩变量空间

**Thm. H是一个赋范线性空间，其中范数为 $$||X||=\sqrt{ E(X^2) }$$​ ，且对 $∀x,y∈H$ 有 $$E(|XY|​)≤||X||||Y||  (Cauchy-Schwarz不等式)$$$$∣E(X)∣≤E(|X|)≤||X|| (Jessen 不等式)$$
	注： $||X||=E(X^2)$​ 满足范数的三条性质
	    1.非负性： $||X||≥0 , 且 ||X||=0⇔X=0,a.s.$
		2.绝对奇性 $∀a∈C,∥aX∥=∣a∣ ||X||$
		3.三角不等式 $∣∣X∣∣+∣∣Y∣∣≥∣∣X+Y∣∣$

*Def (均方极限)

>设随机变量序列 $\{X_n​,n≥1\}$ ，若存在随机变量X满足$$\lim_{n\to\infty}​E(∣X_{n}​−X∣^2)=0⟺∥X_{n}​−X∥\to 0(n \to +\infty)$$则称序列 $\{X_n​\}$ 均方收敛于$X$，或称$X$是 $\{X_n​\}$ 的均方极限。记作： $\operatorname*{l.i.m.}\limits_{n \to +\infty} X_n​=X \text{或} X_n \xrightarrow{​m.s.} X$

*Prop. (均方极限以概率1唯一)

>若 $X_n​\xrightarrow{m.s.}X$ 且 $X_n\xrightarrow{​m.s.}​ Y$ . 则 $P(X=Y)=1$ 。

*Prop. (均方收敛, 依概率收敛)

>$X_n \xrightarrow{​m.s.}X⇒X_n \xrightarrow{​p.}X$

*Prop.(均方极限与期望可换序)

>若 $X_n\xrightarrow{​m.s.}​X$ 且 $Y_n\xrightarrow{​m.s.}​Y$ , 则
$(1) \lim\limits_{n \to \infty}​E(X_n​)=E(\operatorname*{l.i.m.}\limits_{n \to \infty} X_n​)=E(X)$  $(2) \lim\limits_{n→∞​}E(X_n^2​)=E(\operatorname*{l.i.m.}\limits_{n→∞​}X_n^2​)=E(X^2)$  $(3) \lim\limits_{n→∞​}D(X_n​)=D(\operatorname*{l.i.m.}\limits_{n→∞​}X_n​)=D(X)$  $(4) \lim\limits_{\substack{m \to \infty​ \\ n \to \infty}}E(X_m​Y_n​)=E(\operatorname*{l.i.m.}\limits_{m \to \infty}X_m\cdot\operatorname*{l.i.m}\limits_{n \to \infty}Y_n​)=E(XY​)​$

*Prop. 若 $X_n \xrightarrow{​m.s.} ​X$ 且 $Y_n \xrightarrow{m.s.} X$ ，则 $aX_n​+bY_n \xrightarrow{​m.s.}​aX+bY,∀a,b∈G$ .

*Prop. 若$\lim\limits_{n→∞​}a_n​=0$ , 则 $a_n​X \xrightarrow{m.s.} 0$​

*Prop. 若 $X_n$​ 和 $X$ 为实随机变量, 且 $X_n \xrightarrow{​m.s.}X$ 则
$$\lim_{n \to \infty}​E[e^{ivX_n}​]=E[e^{ivX}]⟺\varphi_{X_n}​​(v)\xrightarrow{n \to \infty}φ_{X}​(v)$$

***注： 均有收敛 → 依概率收敛 → 依分布收敛 以概率，收敛***

*Prop. (Cauchy收敛法则).

>$\{X_n​,n≥1\}$ 均方收敛的充要条件是 $X_n$​ 是 H 中的 Cauchy 列. 即
>$$\lim​_{n \to \infty}∥X_{m}−X_{n}​∥^2=\lim_{\substack{m \to \infty \\ n \to \infty}}​E∣X_m​−X_n​∣^2=0$$

*Cor. H是完备的赋范线性空间.即H为Banach空间.

*Prop. (Loève 准则或均方收敛准则)

>$\{X_n​,n≥1\}$ 均方收敛的充要条件为 $$\lim_{\substack{m \to \infty \\ n \to \infty}} E \left( {X}_{m} - \overline{X_{n}}\right) = Const\left( \text{常数}\right)$$ .

*Prop(均方大数定律)

>设 $\{X_n​,n≥1\}$ 是独立同分布的随机变量序列, 则 $E(X_1​)=\mu$ . 则 $\frac{1}{n}\displaystyle\sum_{k=1}^{k} X_{k} \xrightarrow{m.s.} \mu$

# 均方连续

*Def (均方连续)

>对于二阶矩过程 $\{X(t),t∈T\}$ 和某个固定的 $t_0​∈T$ , 若$$\lim_{t \to t_{0}}​​∣∣X(t)−X(t_0​)∣∣=0,\text{即},∀ε>0,∃δ>0,\text{使得}E\{[X(t)−X(t_{0})]^2\}​<ε,∀|t−t_{0}|≤ε$$则称， $X(t)$ 在 $t_{0}$ 处均方连续。
>若 $∀t∈T,X(t)$ 在 t 处都均方连续，则称 $X(t)$ 在 T 上均方连续。

*Prop. (均方连续性则).

>二阶矩过程 $X(t)$ 在 $t_{0}$​ 处均为连续 ⇔ 自相关函数 $R_{X}(s,t)$ 在点 $(t_{0},t_{0})$ 处连续。
	Cor.二阶矩过程 $X(t)$ 在 T 上均方连续 ⇔ 其自相关函数 $R_{X}(s,t)$ 在对角线上连续。
	Cor.二阶矩过程 $X(t)$ 在 T 上均方连续 ⇔ 自相关函数在整个 $T^2$ 上连续
	Cor. 若二阶矩过程 $X(t)$ 在 T 上均方连续，则其均值函数及方差函数也在 T 上连续
		注：(1) 以上性质中可以将自相关函数换成自协方差函数，结论依然成立
		(2) 均方连续并不意味着每个样本函数或某个样本函数连续。

# 均方导数

*Def(均方导数)

>设 $\{X(t),t∈T\}$ 是二阶矩过程， $t_{0}\in T$ ，若均方极限 $\operatorname*{l.i.m}\limits_{\Delta t \to 0}\frac{{X(t_{0}+\Delta t)-X(t_{0})}}{\Delta t}$ 存在，则称， $X(t)$ 在 $t_{0}$​ 处均方可导，并将该极限称为 $X(t)$ 的均方导数，记作 $X'(t_{0})$ 。
>若对于 $\forall t \in T, X'(t)$ 都存在，则称 $X'(t)$ 在 T 上均方可导，并称 $X'(t)$ 为 $X(t)$ 的导数过程。
	注:$$X''(t)=\operatorname*{l.i.m}\limits_{\Delta t \to 0}\frac{{X'(t_{0}+\Delta t)-X'(t_{0})}}{\Delta t}$$$$X^{(n)}(t)=\operatorname*{l.i.m}\limits_{\Delta t \to 0}\frac{{X^{(n-1)}(t_{0}+\Delta t)-X^{(n-1)}((t_{0})}}{\Delta t}$$

*Def(广义二阶可导)

设 +(s,7) 为普顶二元函数. 若极限 h→0lim​h⋅h′7(s+h,7+h)−7(s+h,7)−7(s,7+h)+7(s,7)​ 在右. 则称 +(s,7) 在(s,7)处广义二阶可导式可微,此极限称为 +(s,7) 在(s,7) 处的广义二阶导数.

注：设 f(s,7) 关于 s,t 的一阶偏导数存在.

(1) 若 f(s,7) 的二阶混合偏导表存在且反续,则 f(s,7) 一定是大义可导的. 且广义二阶导数为 fsn​(s,7)=f7s​(s,7) .

(2)若 +(s,7) 的二阶混合偏导数存在但不连续,即使 +s7​(s,7)+t5​(s,7) 均存在. 广义二阶导数不一定存在.

Thm. (均方可导准则)

x(7)左正处 均方可写 ⇔ 其自相关边表 Rn(s,7) 在(7,7)处 +义二阶矛盾.

C0v​ , x(+) 在 T 上均可导 x⇔ 其何相关函数 Rx​(s,?) 在 D 为代上广义二阶可写.

C01. 若 Rx​(s,t) 在对角线上广义二阶可导，则在 T 上也广义二阶元

∂S∂T∂2RX(S,7)​​=E[X′(S)X′(1)]∀(S,7)(−7)2

C01. 若二阶矩过程 x(+) 均为可导, 其自相关函数为 Rλ​(s,?) , 则

∂s∂​Rλ​(s,7),∂t∂​Rλ​(s,7),∂s∂t∂2​Rλ​(s,7),∂t∂s∂2​Rλ​(s,7) 都存在，且有

(1) Rλ⋅λ​(S,7)=E[x′(s)×(7)]=∂S∂​Rλ​(S,7).  
(2) Rλλ​⋅(S.1)=E[X(s)×(1−1)]=∂t∂​Rλ​(S.1)  
(3) kx​⋅(s,−)=E[x′(s)×(−1)]=dsd​d2​kx​(s,−)=dtd​sd2​kx​(s,−)=kx​⋅(s,−)

Prop. (1) 若 x(−) 在一处均方可导, 则 x(+) 在一处均方连续.

(2) 若 x(7) ， y(7) 在 T 均方可导 ∀a,b∈R6 ，有 [a×(7)+b×(7)]=a×(7)+b×(7)  
(3) x(−1) 的均方导数的均值函数为 mx′​(−t)=E[x′(t)]=dtd​E[x(t)]=mx′​(t)  
(4)若两随机过程的均方导数相等,则它们只相差一个随机变量.  
(5) 设 {x(−1),(−1)} 均为可导， f(−1) 是 T 上的普适可导函数，则 f(−1)×(−1) 也均可导，且有 [f(−1)×(−1)]′=f(−1)×(−1)→f(−1)×(−1) .

# 均古积名

det (均点积分)

设 x(7),x−7=2a . b7 是二阶矩函数.

(1) 分割 T:a=t0​<t1​<⋯<tn​=b ，令 Δ=max1≤k≤n​(tk​−tk−1​) ;  
(2)作和式： Yn​=∑k=1n​×(sk​)Δtk​ sk​=[tk−1​,tk​] 1≤k≤n  
(s) 取极限：若 limn→∞​∣nn−1∣=0 ，则称 (7) 在 T=[a,b] 上均为可积，并称 (7) 的极限 (7) 在 [c,b] 上的均为积分。记作 y=∫0b​xlndt 。

Prop. (唯一性)

设二阶矩过程 x(7) 在 [a,b] 上均才可推, 若 y1​=∫ab​x(7)d7 , y2​=∫ab​x(7)d7 . 则 P(y1​=y2​)=1 ?

Thm. (均方可积准则)

二阶矩过程 {x(−1),(−1c,b)} 在 [a,b] 上均方可积 ⇔∫ab​∫ab​Rx​(s,t)dsdt 存在.

当 x(−1) 均方可积则， E[I∫ab​x(−1)d1]2=∫ab​∫ab​Rx​(s,t)dsdt .

注：一般而古 [∫ab​x(2)d7]2=∫ab​x2(2)d7

所以 E[∫ab​x(7)d7]2=∫ab​E[x2(7)]d7 D[∫ab​x(7)d7]=∫ab​D[x(7)]d7

Prop. 均有积分具有线性化,可加性

Prop. 设二阶知过程 λ(n) 在 [a,b] 上均为可解. 则 [∫a1​x(s)ds]′=x(−n)a.s ∀n∈[a,b]

P.0P (牛顿一莱布尼茨公式)

设 x(t) 在 [a,b] 上均方可导, 则 x(t) 在 [a,b] 上均方连续, 且 ∫ab​x(t)dt=x(b)−x(a)

Prop. (换方)

设二阶矩过程 x(7) 在 [a,b] 上均才可积, 则 E[∫ab​x(7)d7]=∫ab​E[2x(7)]d7

Prop. (均为连续 ⇒ 均求可积)

设 x(+) 在 [a,b] 上均方连续，则 x(−) 在 [a,b] 上，必均为可积，且

EI∫ab​x(x)dxI2≤m(b−a)2, 其中 m=a≤x≤bmax​E[x2(x)].

注：均为连续的二阶矩过程的积分过程也为二阶矩过程

Prop. 设 x (π) 在 [a,b] 上均有可积,则

Cov(∫as​x(u)du,∫a−1​x(v)dv)=∫as​∫a−1​Cx​(u,v)dudv.s=7.51a.b2

补： x(7) 均方连续 ⇔Rx​(s,7) 在 T 上连续

x(2) 均方可得 ⇔kx​(s,7)π 在 T 上 f 义二阶可得.

λ(n) 均为可积 ⇔Rn​ 是 n 左 T 上可积

# 正态过程的均方微积分

76m.正态随机变量序列的均态极限仍为正态随机变量

7hm.（正态分布序列的均方极限仍为正态分布）

若 {x(n)=(x1(n)​,x2(n)​⋯xk(n)​)n≥1} 是k值正态随机序列，且

x(m)m.s.​x 即 x(n)m.s.​x;1≤i≤k. 则 x=(x1​,⋯,xn​) 仍是r化正态限制

7hm.正态随机过程的均方导数过程称为正态随机过程.

正态随机过程的均才积分过程为正态随机过程

注： xn​m.s.​x(xn​) 正态序列 ⇒x 正态.

x1​m.s.​x {x1​} 正态过程 ⇒x 正态,

布朗运动处处连续，但处处不可导

# 下随机微分方程

Def (n阶随机得分方程)

设 {x(1),x(−1)} 和 {y(1),y(−1)} 为随机过程， y(1) 的 n 阶均方导数 y(n)(1) 存在， xk​(1≤k≤n) 为随机变量式常数，则称

an​Y(n)(7)+an−1​Y(n−1)(7)+⋯+a1​Y(n)(7)+a0​Y(7)=x(7) 为 n 阶随机线性微分方程

Thm. 设 x(7) 为二阶矩过程, y0​ 二阶矩有限, 则一阶随机微分方程

{y′(7)=x(7)−7y(−7)=y0​​ 为唯一行为 y(7)=∫0t​x(s)ds+y0​

设 a(n) 为普顶函数 则一阶随机微分方程 ⎩⎨⎧​y(n)=a(n)y(n)+x(n)−1y(n+1)=1​

的唯一解为 γ(7)=γ0​exp(∫707​a(u)du)+∫707​χ(s)exp(∫s7​a)

共用齐次方程： r(r)=ar(−r) ，再用常数变易法求所 r 的一

# 第三章 泊松过程

# 泊松过程

# Def (什数过程)

称 {N(+),t≥0} 是一个计数过程. 如果

(1) A>0 , N(τ)∈W

(2) ∀s<t,N(δ)≤N(τ)

(5) ∀s<t,N(+)−N(s) 代表在时间段(S. 7门内事件发生的次数

# Def(泊松过程)

如果计数过程 {N(t),t≥0} 满足

(1) N(0)=0 a.s.

(2) N(−t) 具有独立增量.

(2) ∀t≥0,dt>0,N(t+dt)−N(t)∼P(dt) (平稳增益)

其中, λ>0 . 则称 N(1) 为参数 (强友) 为 λ 的 (齐次) 泊松过程

注： E[ΔtN(t+Δt)−N(7)​]=λ 强及

# Def (泊松过程)

如果计数过程 {N(t),t≥0} 满足

(1)N(0)=0,G,S.

(2) N(t) 具有独立增盈

(3) N(+)具有平稳增量, 且当 a>0 时.

P(N(Δ7)=0)=1−λΔ7​+O(Δ7)P(N(Δ7)=1)=λΔ7​+O(Δ7)

P(N(Δτ)≥2)=0(Δτ)

其中, λ>0 . 则称 N(t) 方参数(强友)为 λ 的(齐次)泊松过程

# 泊松过程的数字特征

Prop. (泊松过程的数字特征)

设 (N(+),−z=0) 是参数为分的泊松过程,则其

mN​(τ)=λτψN2​(τ)=(λτ)2+λτDN​(τ)=λτ

RN​(t,t2​)=λ2t1​t2​+λ(t,Δt2​)

CN​(z1​,z2​)=λ(z1​∧z2​)

φN​(t,v)=exp[λτ(eiv−1)]

注：用泊松分布描述次数时，可以说均值与差一样，因为无量纲，费血纲从0开始。

# 复合泊松过程

Def (复吉泊松过程)

设泊松过程 {N(t),t≥0} 与独立同分布随机变量列 {xn​,n∈N∗} 相互独立

称， Y(t)=∑n=1N(n)​xn​t≥0 ，为复合泊松过程

注：为书写简洁，约定 ∑i=10​xi​=0

② 泊松过程是复合泊松过程的特例. N(x)=∑i=1N(x)​1

P10P. (复合泊松过程的性质)

设 {r(n)=∑n=1N(r)​xn​,t≥0} 是一个复台泊松过程. 则

(1) 广州具有平稳独立增量.

(2) Y(−1) 的特征函数为 φY​(x,v)=exp{λ+[φX​(x)−1]} .

(5) 若 E[I(x)]<+∞ ，则 mr​(x)=λr[E(x)] .

② 若 E[1λ12​] < +∞，则 Or​(−1)=λ1​×E[x2]

# 泊松过程的叠加

Thm. (泊松过程的叠加)

设 {N1​(−t),t≥0} 与 {N2​(−t),t≥0} 是相互独立且强度分别为 A, 与 A 的泊松过程，则 {N(t)=N1​(t)+N2​(t),t≥0} ，仍为泊松过程。

即两个相互独立的泊松过程的叠加均为泊松过程，且其强度为二泊松过程的强度之和 λ=λ1​+λ

Thm. (泊松过程叠加的推广)

若 {Nk​(t),t≥0} ， k=1,2,⋯,n 是 n 个相互独立且强友分别为 λ,λ0​,⋯,λn​ 的泊松过程。则 {N(t)=∑k=1n​Nk​(t),t≥0} 是强友为 ∑k=1n​λk​ 的泊松过程。

注：① N1​(t) , N2​(t) 相互为独立的泊松过程. N1​(t)+1 从 N2​(t) 不足泊松过程 (3).

② N1​(7) . N2​(7) 仅为泊松过程. 不独立 N1​(7)+N2​(7) 不一定是泊松过程 (s).

③ N1​(7) , N2​(7) 相互独立的泊松过程, N1​(7)−N2​(7) 不是泊松过程 (s).

Example 设 N1​(r) 与 N2​(r) 是两个相互独立的泊松过程 参数分别为 λ1​ 和 λ2​ ，对任意不全为 0 的实数 α,α2​

(1) α1​N1​(r)+α2​N2​(r) 是复合泊松过程

(2) 2,N1​(7)+d2​N0​(7) 是泊松及程 ⇔ α=α1​=1 或 α1​=1,α2​=0 时 α1​=0,α2​=1 .

# 泊松过程的分析

Thm(泊松过程的分析)

设 N(τ),τ≥0 是强反为 A 的泊松过程， N1​(τ) 为进入子系统 A 的质点数， N2​(τ) 为进入子系统 B 的质点数，则 N(τ) 的分析过程 N1​(t) 与 N2​(t) 相互独立，分别服从强反为 λP​ 和 λ9​ 的泊松过程

# 随机质点的到达时间与时间间隔

记 Tn​ 为第 n 次事件发生的时间， Tn​ 为第 n−1 次事件到第 n 次事件时间间隔，则 N(x)=sup{n:Tn​≤x} Tn​=in+(x∣N(x))≤n}=∑k=1n​Tk​

Thm. 设 {N(+),t≥0} 是参数为 A 的泊松过程，则

Ftn​(t)={1−k=0∑n−1​k!(λt)k​e−λtt>0

tan(7)=∫00​(n−2!)λ(λτ)n−1​e−λτ=τ(n)λnτn−1​e−λτ,τ>0

此分布是 T(n,λ) 分布.

质点

P10P​ . 设 N(7) 服从参数为 A 的泊松过程, T0​ 为第 n 个随机变量而到达时间, 则

(1) Tn​ 的期望和方差为 E(Tn​)=λn​,L(Tn​)=λ2n​  
(2) T0​ 的特征函数为 φT0​​(v)=(λ−ivλ​)n

到达

Thm​ 。令 Ti​=ti​−ti−1​ ，表示第：一个质点与第 i 个质点之间的时间间隔，计数过程： N(t)=sup{h∣Tn​≤t} 同反从参数为 n 的泊松过程 ⇔ 其质点到达时间；间隔独立同参数为 n 的指数分布。

![](file:///C:/Users/Alice/MinerU/%E9%9A%8F%E6%9C%BA%E8%BF%87%E7%A8%8B.pdf-a0b2711a-4aeb-480c-82ce-642d983a25db/images/22f8d08385278b5f1855b75a7b17ce1084d95d88af23bb1ea377ecb19899b0b7.jpg)

N(−1)=sup{n:Tn​≤τ}τn​=in+{τ:N(n)≥n}=∑k=0∞​Tk​​