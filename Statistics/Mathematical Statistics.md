## 第五章 统计量及其分布

### §5.1 总体与样本

#### 一、总体与个体

1. **总体**：研究对象的全体称为总体。
   > 注：总体本质上是一个概率分布，通常用随机变量 $X$ 表示。

2. **个体**：构成总体的每个成员称为个体。

3. **总体分类**：
   - 有限总体：包含有限个个体的总体
   - 无限总体：包含无限个个体的总体

#### 二、样本

1. **样本**：从总体中随机地抽取 $n$ 个个体，记其指标值为 $X_1, X_2, \cdots, X_n$，则 $X_1, X_2, \cdots, X_n$ 称为总体的一个样本，$n$ 称为**样本容量**，样本中的个体称为样品。
   > 注：样本分为完全样本和不完全样本。

2. **简单随机抽样与简单随机样本**：
   - 若抽取样本具有以下两个性质，则称该抽样方法为**简单随机抽样**：
     1. **代表性**：每个 $X_i$ 都与总体 $X$ 同分布
     2. **独立性**：$X_1, X_2, \cdots, X_n$ 相互独立
   - 用简单随机抽样方法得到的样本称为**简单随机样本**，简称样本。

---

### §5.2 样本数据的整理与呈现

#### 一、经验分布函数

1. **有序样本**：设 $X_1, X_2, \cdots, X_n$ 是取自总体分布函数为 $F(x)$ 的样本，将样本观测值由小到大排列，记为
   $$
   x_{(1)} \leq x_{(2)} \leq \cdots \leq x_{(n)}
   $$
   则 $x_{(1)}, x_{(2)}, \cdots, x_{(n)}$ 称为有序样本。

2. **经验分布函数**：定义如下函数
   $$
   F_n(x) = 
   \begin{cases}
   0, & x < x_{(1)} \\
   \dfrac{k}{n}, & x_{(k)} \leq x < x_{(k+1)}, \quad k = 1, 2, \cdots, n-1 \\
   1, & x \geq x_{(n)}
   \end{cases}
   $$
   $F_n(x)$ 满足分布函数的单调性、有界性和右连续性，称为该样本的**经验分布函数**。

3. **格利文科定理**：设 $X_1, X_2, \cdots, X_n$ 是取自总体分布函数为 $F(x)$ 的样本，$F_n(x)$ 是其经验分布函数，则当 $n \to \infty$ 时，有
   $$
   P\left( \sup_{-\infty < x < +\infty} |F_n(x) - F(x)| \xrightarrow{n \to \infty} 0 \right) = 1
   $$
   > 注：该定理表明，当样本容量很大时，经验分布函数 $F_n(x)$ 是总体分布函数 $F(x)$ 的一个很好的近似。

#### 二、频数频率表

通过对样本数据进行分组，计算每组的频数和频率，以展示数据的分布特征。

#### 三、样本数据的图形显示

1. **直方图**：用矩形的面积表示各组频数或频率的图形
2. **茎叶图**：同时展示数据的数值大小和分布形状的图形

---

### §5.3 统计量及其分布

#### 一、统计量与抽样分布

1. **统计量**：设 $X_1, X_2, \cdots, X_n$ 为来自某总体的样本，若样本函数 $T = T(X_1, X_2, \cdots, X_n)$ 中不含有任何未知参数，则称 $T$ 为**统计量**。
2. **抽样分布**：统计量的分布称为抽样分布。

#### 二、样本均值及其抽样分布

1. **样本均值**：设 $X_1, X_2, \cdots, X_n$ 为来自某总体的样本，其算术平均值称为样本均值，记为
   $$
   \bar{X} = \frac{1}{n} \sum_{i=1}^{n} X_i
   $$

2. **样本均值的性质**：

   (1) 样本所有偏差之和为 $0$：
   $$
   \sum_{i=1}^{n} (X_i - \bar{X}) = 0
   $$

   (2) 数据观测值与样本均值的偏差平方和最小：
   $$
   \sum_{i=1}^{n} (X_i - \bar{X})^2 \leq \sum_{i=1}^{n} (X_i - c)^2
   $$
   对任意常数 $c$ 成立。

3. **样本均值的抽样分布**：

   (1) 若总体分布为 $N(\mu, \sigma^2)$，则 $\bar{X}$ 的精确分布为
   $$
   \bar{X} \sim N\left(\mu, \frac{\sigma^2}{n}\right)
   $$

   (2) 若总体分布未知或不是正态分布，但 $E(X) = \mu$，$\mathrm{Var}(X) = \sigma^2$ 存在，则当 $n$ 较大时，$\bar{X}$ 的渐近分布为
   $$
   \bar{X} \dot{\sim} N\left(\mu, \frac{\sigma^2}{n}\right)
   $$

#### 三、样本方差与样本标准差

1. **样本方差**：

   (1) 有偏样本方差：
   $$
   S_n^2 = \frac{1}{n} \sum_{i=1}^{n} (X_i - \bar{X})^2
   $$

   (2) 无偏样本方差（常用）：
   $$
   S^2 = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \bar{X})^2
   $$

2. **样本标准差**：
   $$
   S = \sqrt{S^2}
   $$

3. **样本均值与样本方差的期望**：
   设总体 $X$ 具有二阶矩，即 $E(X) = \mu$，$\mathrm{Var}(X) = \sigma^2 < \infty$，$X_1, X_2, \cdots, X_n$ 为从该总体得到的样本，则
   $$
   E(\bar{X}) = \mu, \quad \mathrm{Var}(\bar{X}) = \frac{\sigma^2}{n}, \quad E(S^2) = \sigma^2
   $$

#### 四、样本矩及其函数

1. **样本 $k$ 阶原点矩**：$a_k = \dfrac{1}{n} \displaystyle\sum_{i=1}^{n} X_i^k,\quad k = 1, 2, \cdots$
2. **样本 $k$ 阶中心矩**：$b_k = \dfrac{1}{n} \displaystyle\sum_{i=1}^{n} (X_i - \bar{X})^k,\quad k = 1, 2, \cdots$
3. **样本偏度系数**：$\hat{\beta}_s = \dfrac{b_3}{b_2^{3/2}}$
4. **样本峰度系数**：$\hat{\beta}_k = \dfrac{b_4}{b_2^2} - 3$

#### 五、次序统计量及其分布

1. **次序统计量**：设 $X_1, X_2, \cdots, X_n$ 是来自总体 $X$ 的样本，将样本观测值由小到大排列后得到的第 $k$ 个值 $X_{(k)}$ 称为该样本的第 $k$ 个次序统计量。
   - 最小次序统计量：$X_{(1)} = \min\{X_1, X_2, \cdots, X_n\}$
   - 最大次序统计量：$X_{(n)} = \max\{X_1, X_2, \cdots, X_n\}$

2. **单个次序统计量的分布**：
   设总体 $X$ 的密度函数为 $p(x)$，分布函数为 $F(x)$，则第 $k$ 个次序统计量 $X_{(k)}$ 的密度函数为
   $$
   p_k(x) = \frac{n!}{(k-1)!(n-k)!} [F(x)]^{k-1} [1 - F(x)]^{n-k} p(x)
   $$

3. **两个次序统计量的联合分布**：
   次序统计量 $(X_{(i)}, X_{(j)})$（$i < j$）的联合密度函数为
   $$
   p_{ij}(y,z) = \frac{n!}{(i-1)!(j-i-1)!(n-j)!} [F(y)]^{i-1} [F(z) - F(y)]^{j-i-1} [1 - F(z)]^{n-j} p(y) p(z)
   $$
   其中 $y < z$。

4. **样本极差**：
   $$
   R_n = X_{(n)} - X_{(1)}
   $$

#### 六、样本分位数与样本中位数

1. **样本中位数**：
   $$
   m_{0.5} = 
   \begin{cases}
   X_{\left(\frac{n+1}{2}\right)}, & n \text{ 为奇数} \\[6pt]
   \dfrac{1}{2} \left( X_{\left(\frac{n}{2}\right)} + X_{\left(\frac{n}{2}+1\right)} \right), & n \text{ 为偶数}
   \end{cases}
   $$

2. **样本 $p$ 分位数**：
   $$
   m_p = 
   \begin{cases}
   X_{([np]+1)}, & np \text{ 不是整数} \\[6pt]
   \dfrac{1}{2} \left( X_{(np)} + X_{(np+1)} \right), & np \text{ 是整数}
   \end{cases}
   $$

#### 七、五数概括与箱线图

1. **五数概括**：
   $$
   x_{\min} = X_{(1)},\quad Q_1 = m_{0.25},\quad m_{0.5},\quad Q_3 = m_{0.75},\quad x_{\max} = X_{(n)}
   $$
   即最小值、下四分位数、中位数、上四分位数、最大值。

2. **箱线图**：用五数概括绘制的图形，用于展示数据的分布特征。

---

### §5.4 三大抽样分布

#### 一、$\chi^2$ 分布（卡方分布）

1. **定义**：设 $X_1, X_2, \cdots, X_n$ 独立同分布于 $N(0,1)$，则
   $$
   \chi^2 = X_1^2 + X_2^2 + \cdots + X_n^2
   $$
   的分布称为自由度为 $n$ 的 $\chi^2$ 分布，记为 $\chi^2 \sim \chi^2(n)$。
   > 注：$\chi^2(n) \sim \mathrm{Ga}\left( \dfrac{n}{2}, \dfrac{1}{2} \right)$，即自由度为 $n$ 的卡方分布是形状参数为 $\dfrac{n}{2}$、尺度参数为 $\dfrac{1}{2}$ 的伽马分布。

2. **密度函数**：
   $$
   p(y) = \frac{1}{\Gamma\left(\frac{n}{2}\right) \left(\frac{1}{2}\right)^{\frac{n}{2}}} y^{\frac{n}{2} - 1} e^{-\frac{y}{2}},\quad y > 0
   $$

3. **期望与方差**：
   $$
   E(\chi^2) = n,\quad \mathrm{Var}(\chi^2) = 2n
   $$

4. **正态总体样本方差的分布**：
   设 $X_1, X_2, \cdots, X_n$ 是来自正态总体 $N(\mu, \sigma^2)$ 的样本，$\bar{X}$ 和 $S^2$ 分别是样本均值和样本方差，则
   
   (1) $\bar{X}$ 与 $S^2$ 相互独立
   
   (2) $\dfrac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$

#### 二、$F$ 分布

1. **定义**：设随机变量 $X_1 \sim \chi^2(m)$，$X_2 \sim \chi^2(n)$，且 $X_1$ 与 $X_2$ 独立，则
   $$
   F = \frac{X_1 / m}{X_2 / n}
   $$
   的分布是自由度为 $m$ 和 $n$ 的 $F$ 分布，记为 $F \sim F(m, n)$，其中 $m$ 称为分子自由度，$n$ 称为分母自由度。

2. **分位数性质**：
   $$
   F_{1-\alpha}(m, n) = \frac{1}{F_\alpha(n, m)}
   $$

3. **两正态总体方差比的分布**：
   设 $X_1, X_2, \cdots, X_m$ 是来自 $N(\mu_1, \sigma_1^2)$ 的样本，$Y_1, Y_2, \cdots, Y_n$ 是来自 $N(\mu_2, \sigma_2^2)$ 的样本，且两样本相互独立，则
   $$
   F = \frac{S_x^2 / \sigma_1^2}{S_y^2 / \sigma_2^2} \sim F(m-1, n-1)
   $$
   特别地，若 $\sigma_1^2 = \sigma_2^2$，则
   $$
   F = \frac{S_x^2}{S_y^2} \sim F(m-1, n-1)
   $$

#### 三、$t$ 分布

1. **定义**：设随机变量 $X_1$ 与 $X_2$ 独立，且 $X_1 \sim N(0,1)$，$X_2 \sim \chi^2(n)$，则
   $$
   t = \frac{X_1}{\sqrt{X_2 / n}}
   $$
   的分布为自由度为 $n$ 的 $t$ 分布，记为 $t \sim t(n)$。

2. **性质**：
   (1) 自由度为 $1$ 的 $t$ 分布为标准柯西分布，它的均值不存在
   (2) 当 $n > 1$ 时，$t$ 分布的数学期望存在且为 $0$
   (3) 当 $n > 2$ 时，$t$ 分布的方差存在且为 $\dfrac{n}{n-2}$
   (4) 当 $n$ 较大（$n \geq 30$）时，$t$ 分布可以用 $N(0,1)$ 分布近似

3. **单正态总体的 $t$ 统计量**：
   设 $X_1, X_2, \cdots, X_n$ 是来自正态总体 $N(\mu, \sigma^2)$ 的一个样本，$\bar{X}$ 与 $S^2$ 分别是该样本的样本均值与样本方差，则
   $$
   t = \frac{\bar{X} - \mu}{S / \sqrt{n}} \sim t(n-1)
   $$

4. **两正态总体的 $t$ 统计量**：
   设 $X_1, X_2, \cdots, X_m$ 是来自 $N(\mu_1, \sigma^2)$ 的样本，$Y_1, Y_2, \cdots, Y_n$ 是来自 $N(\mu_2, \sigma^2)$ 的样本，且两样本相互独立。记
   $$
   S_W^2 = \frac{(m-1)S_x^2 + (n-1)S_y^2}{m+n-2}
   $$
   则
   $$
   \frac{(\bar{X} - \bar{Y}) - (\mu_1 - \mu_2)}{S_W \sqrt{\dfrac{1}{m} + \dfrac{1}{n}}} \sim t(m+n-2)
   $$

---

### §5.5 充分统计量

#### 一、充分统计量

**定义**：设 $X_1, X_2, \cdots, X_n$ 是来自某个总体的样本，总体分布函数为 $F(x; \theta)$，统计量 $T = T(X_1, X_2, \cdots, X_n)$ 称为 $\theta$ 的**充分统计量**，如果在给定 $T$ 的取值后，$X_1, X_2, \cdots, X_n$ 的条件分布与 $\theta$ 无关。

> 注：充分统计量包含了样本中关于未知参数 $\theta$ 的全部信息。

#### 二、因子分解定理

**定理**：设总体概率函数为 $f(x; \theta)$，$X_1, X_2, \cdots, X_n$ 为样本，则 $T = T(X_1, X_2, \cdots, X_n)$ 为充分统计量的充要条件是：存在两个函数 $g(t, \theta)$ 和 $h(x_1, x_2, \cdots, x_n)$，使得对任意的 $\theta$ 和任意一组观测值 $x_1, x_2, \cdots, x_n$，有
$$
f(x_1, x_2, \cdots, x_n; \theta) = g(T(x_1, x_2, \cdots, x_n), \theta) \cdot h(x_1, x_2, \cdots, x_n)
$$
其中 $g(t, \theta)$ 通过统计量 $T$ 的数值依赖于样本，$h(x_1, x_2, \cdots, x_n)$ 不依赖于 $\theta$。

**推论（充分性的不变性）**：若统计量 $T$ 是充分统计量，且存在某个函数 $h(\cdot)$，使得 $S = h(T)$ 是一一映射，则统计量 $S$ 也是充分统计量。

---

## 第六章 参数估计

### §6.1 点估计的概念与无偏性

#### 一、点估计

**定义**：设 $X_1, X_2, \cdots, X_n$ 是来自总体的一个样本，用于估计未知参数 $\theta$ 的统计量 $\hat{\theta} = \hat{\theta}(X_1, X_2, \cdots, X_n)$ 称为 $\theta$ 的**估计量**，或称为 $\theta$ 的**点估计**（简称估计）。

#### 二、无偏性

**定义**：设 $\hat{\theta} = \hat{\theta}(X_1, X_2, \cdots, X_n)$ 是 $\theta$ 的一个估计，$\theta$ 的参数空间为 $\Theta$。若对任意 $\theta \in \Theta$，有

$$
E_\theta(\hat{\theta}) = \theta
$$

则称 $\hat{\theta}$ 是 $\theta$ 的**无偏估计**，否则称为**有偏估计**。

> 注：若 $\hat{\theta}$ 是 $\theta$ 的无偏估计，一般而言，其函数 $g(\hat{\theta})$ 不是 $g(\theta)$ 的无偏估计。

**定义（渐近无偏估计）**：若当样本容量 $n \to \infty$ 时，有

$$
\lim_{n \to \infty} E(\hat{\theta}_n) = \theta
$$

则称 $\hat{\theta}_n$ 是 $\theta$ 的**渐近无偏估计**。

**定义（可估性）**：当参数存在无偏估计时，我们称该参数是**可估的**，否则称它是**不可估的**。

#### 三、有效性

**定义**：设 $\hat{\theta}_1$ 和 $\hat{\theta}_2$ 是 $\theta$ 的两个无偏估计，如果对任意的 $\theta \in \Theta$，有

$$
\mathrm{Var}_\theta(\hat{\theta}_1) \leq \mathrm{Var}_\theta(\hat{\theta}_2)
$$

且至少有一个 $\theta \in \Theta$ 使得上述不等号严格成立，则称 $\hat{\theta}_1$ 比 $\hat{\theta}_2$ **有效**。

---

### §6.2 矩估计及相合性

#### 一、替换原理和矩法估计

**矩法估计的基本思想（替换原理）**：

1. 用样本矩去替换总体矩（可以是原点矩，也可以是中心矩）
2. 用样本矩的函数去替换相应总体矩的函数

> 注：矩法估计的实质是用经验分布函数去替换总体分布，其理论基础是格利文科定理。

**矩法估计的步骤**：

1. 计算总体的前 $k$ 阶矩（$k$ 为未知参数的个数）
2. 建立未知参数与总体矩的关系式
3. 用样本矩替换总体矩，得到未知参数的矩估计

#### 二、相合性

**定义**：设 $\theta \in \Theta$ 为未知参数，$\hat{\theta}_n = \hat{\theta}_n(X_1, X_2, \cdots, X_n)$ 是 $\theta$ 的一个估计量。若对任意 $\varepsilon > 0$，有

$$
\lim_{n \to \infty} P(|\hat{\theta}_n - \theta| \geq \varepsilon) = 0
$$

则称 $\hat{\theta}_n$ 为参数 $\theta$ 的**相合估计**（或一致估计）。

**相合性的判别方法**：

1. 若 $\hat{\theta}_n$ 满足

   $$
   \lim_{n \to \infty} E(\hat{\theta}_n) = \theta,\quad \lim_{n \to \infty} \mathrm{Var}(\hat{\theta}_n) = 0
   $$

   则 $\hat{\theta}_n$ 是 $\theta$ 的相合估计。

2. 若 $\hat{\theta}_{n1}, \hat{\theta}_{n2}, \cdots, \hat{\theta}_{nk}$ 分别是 $\theta_1, \theta_2, \cdots, \theta_k$ 的相合估计，$g(\theta_1, \theta_2, \cdots, \theta_k)$ 是 $\theta_1, \theta_2, \cdots, \theta_k$ 的连续函数，则

   $$
   \hat{g}_n = g(\hat{\theta}_{n1}, \hat{\theta}_{n2}, \cdots, \hat{\theta}_{nk})
   $$

   是 $g(\theta_1, \theta_2, \cdots, \theta_k)$ 的相合估计（相合性具有不变性）。

---

### §6.3 最大似然估计与 EM 算法

#### 一、最大似然估计

**定义（似然函数）**：设总体的概率函数为 $p(x;\theta)$，$\theta \in \Theta$，其中 $\theta$ 是一个未知参数或几个未知参数组成的参数向量，$\Theta$ 是参数空间。$X_1, X_2, \cdots, X_n$ 是来自该总体的样本，将样本的联合概率函数看作 $\theta$ 的函数，用 $L(\theta; x_1, x_2, \cdots, x_n)$ 表示，简记为 $L(\theta)$：

$$
L(\theta) = \prod_{i=1}^{n} p(x_i; \theta)
$$

$L(\theta)$ 称为样本的**似然函数**。

**定义（最大似然估计）**：如果某统计量 $\hat{\theta} = \hat{\theta}(X_1, X_2, \cdots, X_n)$ 满足

$$
L(\hat{\theta}) = \max_{\theta \in \Theta} L(\theta)
$$

则称 $\hat{\theta}$ 是 $\theta$ 的**最大似然估计**（MLE）。

> 注：最大似然估计具有不变性：若 $\hat{\theta}$ 是 $\theta$ 的最大似然估计，则对任一函数 $g(\theta)$，$g(\hat{\theta})$ 是 $g(\theta)$ 的最大似然估计。

**求最大似然估计的步骤**：

1. 写出似然函数 $L(\theta)$
2. 取对数，得到对数似然函数 $\ln L(\theta)$
3. 对 $\theta$ 求导，令导数为 $0$，得到似然方程
4. 解似然方程，得到最大似然估计

#### 二、EM 算法

EM 算法是一种用于求解含有缺失数据的最大似然估计的迭代算法，分为 E 步（期望步）和 M 步（极大步）。

#### 三、渐近正态性

**定义**：参数 $\theta$ 的相合估计 $\hat{\theta}_n$ 称为**渐近正态的**，若存在趋于 $0$ 的非负常数序列 $\sigma_n(\theta)$，使得

$$
\frac{\hat{\theta}_n - \theta}{\sigma_n(\theta)} \xrightarrow{L} N(0,1)
$$

这时也称 $\hat{\theta}_n$ 服从渐近正态分布 $N(\theta, \sigma_n^2(\theta))$，记为

$$
\hat{\theta}_n \sim AN(\theta, \sigma_n^2(\theta))
$$

$\sigma_n^2(\theta)$ 称为 $\hat{\theta}_n$ 的**渐近方差**。

**定义（费希尔信息量）**：设总体 $X$ 有密度函数 $p(x;\theta)$，$\theta \in \Theta$，则

$$
I(\theta) = E\left[ \left( \frac{\partial}{\partial \theta} \ln p(X;\theta) \right)^2 \right]
$$

称为总体分布的**费希尔信息量**。

> 注：若二阶偏导数 $\frac{\partial^2}{\partial \theta^2} p(x;\theta)$ 对所有 $\theta \in \Theta$ 存在，则
> $$
> I(\theta) = -E\left[ \frac{\partial^2}{\partial \theta^2} \ln p(X;\theta) \right]
> $$

**定理（最大似然估计的渐近正态性）**：在一定正则条件下，未知参数 $\theta$ 的最大似然估计 $\hat{\theta}_n$ 具有相合性和渐近正态性：

$$
\hat{\theta}_n \sim AN\left( \theta, \frac{1}{n I(\theta)} \right)
$$

---

### §6.4 最小方差无偏估计

#### 一、均方误差

**定义**：设 $\hat{\theta}$ 是 $\theta$ 的一个估计，则

$$
\mathrm{MSE}(\hat{\theta}) = E(\hat{\theta} - \theta)^2 = \mathrm{Var}(\hat{\theta}) + [E(\hat{\theta}) - \theta]^2
$$

称为 $\hat{\theta}$ 的**均方误差**。

> 注：均方误差由点估计的方差和偏差 $|E(\hat{\theta}) - \theta|$ 的平方两部分组成。

**定义（一致最小均方误差估计）**：设有样本 $X_1, X_2, \cdots, X_n$，对待估参数 $\theta$，设有一个估计类。称 $\hat{\theta}(X_1, X_2, \cdots, X_n)$ 是该估计类中 $\theta$ 的**一致最小均方误差估计**，如果对该估计类中另外任意一个 $\theta$ 的估计 $\tilde{\theta}$，在参数空间 $\Theta$ 上都有

$$
\mathrm{MSE}_\theta(\hat{\theta}) \leq \mathrm{MSE}_\theta(\tilde{\theta})
$$

#### 二、一致最小方差无偏估计

**定义**：对参数估计问题，设 $\hat{\theta}$ 是 $\theta$ 的一个无偏估计。如果对另外任意一个 $\theta$ 的无偏估计 $\tilde{\theta}$，在参数空间 $\Theta$ 上都有

$$
\mathrm{Var}_\theta(\hat{\theta}) \leq \mathrm{Var}_\theta(\tilde{\theta})
$$

则称 $\hat{\theta}$ 是 $\theta$ 的**一致最小方差无偏估计**，简记为 UMVUE。

**定理（UMVUE 的判别法）**：设 $X = (X_1, X_2, \cdots, X_n)$ 是来自某总体的一个样本，$\hat{\theta} = \hat{\theta}(X)$ 是 $\theta$ 的一个无偏估计，$\mathrm{Var}(\hat{\theta}) < \infty$。则 $\hat{\theta}$ 是 $\theta$ 的 UMVUE 的充要条件是：对任意一个满足 $E(\varphi(X)) = 0$ 和 $\mathrm{Var}(\varphi(X)) < \infty$ 的 $\varphi(X)$，都有

$$
\mathrm{Cov}_\theta(\hat{\theta}, \varphi) = 0, \quad \forall \theta \in \Theta
$$

#### 三、充分性原则

**定理（Rao-Blackwell 定理）**：设总体概率函数是 $p(x;\theta)$，$X_1, X_2, \cdots, X_n$ 是其样本，$T = T(X_1, X_2, \cdots, X_n)$ 是 $\theta$ 的充分统计量。则对 $\theta$ 的任一无偏估计 $\hat{\theta}$，令

$$
\tilde{\theta} = E(\hat{\theta} \mid T)
$$

则 $\tilde{\theta}$ 也是 $\theta$ 的无偏估计，且

$$
\mathrm{Var}(\tilde{\theta}) \leq \mathrm{Var}(\hat{\theta})
$$

> 注：较好的无偏估计一定是充分统计量的函数。若充分统计量和 UMVUE 存在，则 UMVUE 一定可以表示为充分统计量的函数。

#### 四、克拉默 - 拉奥不等式

**定理（克拉默 - 拉奥不等式）**：设总体分布 $p(x;\theta)$ 满足一定正则条件，$X_1, X_2, \cdots, X_n$ 是来自该总体的样本，$T = T(X_1, X_2, \cdots, X_n)$ 是 $g(\theta)$ 的任一个无偏估计，$g'(\theta) = \frac{\partial g(\theta)}{\partial \theta}$ 存在，则

$$
\mathrm{Var}(T) \geq \frac{[g'(\theta)]^2}{n I(\theta)}
$$

上式右端称为 $g(\theta)$ 的无偏估计的方差的**C-R 下界**。

---

### §6.5 贝叶斯估计

#### 一、贝叶斯公式的密度函数形式

在贝叶斯统计中，我们将未知参数 $\theta$ 看作一个随机变量，其分布称为**先验分布**，记为 $\pi(\theta)$。

**贝叶斯公式（密度函数形式）**：

$$
\pi(\theta \mid x) = \frac{p(x \mid \theta) \pi(\theta)}{\int_\Theta p(x \mid \theta) \pi(\theta) \, d\theta}
$$

其中：

- $p(x \mid \theta)$ 是总体的条件密度函数
- $\pi(\theta)$ 是先验分布
- $\pi(\theta \mid x)$ 是在得到样本 $x$ 后 $\theta$ 的**后验分布**

> 注：后验分布综合了总体信息、样本信息和先验信息，是贝叶斯统计推断的基础。

#### 二、贝叶斯估计

常用的贝叶斯估计有三种：

1. **最大后验估计**：使用后验分布的密度函数最大值点作为 $\theta$ 的点估计
2. **后验中位数估计**：使用后验分布的中位数作为 $\theta$ 的点估计
3. **后验期望估计**：使用后验分布的均值作为 $\theta$ 的点估计（通常称为贝叶斯估计）

---

### §6.6 区间估计

#### 一、区间估计的概念

**定义（置信区间）**：设 $\theta$ 是总体的一个参数，其参数空间为 $\Theta$，$X_1, X_2, \cdots, X_n$ 是来自该总体的样本。对给定的一个 $\alpha$（$0 < \alpha < 1$），假设有两个统计量

$$
\hat{\theta}_L = \hat{\theta}_L(X_1, X_2, \cdots, X_n), \quad \hat{\theta}_U = \hat{\theta}_U(X_1, X_2, \cdots, X_n)
$$

若对 $\forall \theta \in \Theta$，有

$$
P_\theta(\hat{\theta}_L \leq \theta \leq \hat{\theta}_U) \geq 1 - \alpha
$$

则称随机区间 $[\hat{\theta}_L, \hat{\theta}_U]$ 为 $\theta$ 的置信水平为 $1 - \alpha$ 的**置信区间**，$\hat{\theta}_L$ 和 $\hat{\theta}_U$ 分别称为 $\theta$ 的（双侧）置信下限和置信上限。

> 注：置信水平 $1 - \alpha$ 表示在大量重复抽样中，大约有 $100(1 - \alpha)\%$ 的置信区间包含未知参数的真值。

**定义（单侧置信限）**：

1. **单侧置信下限**：若对 $\forall \theta \in \Theta$，有

   $$
   P_\theta(\hat{\theta}_L \leq \theta) \geq 1 - \alpha
   $$

   则称 $\hat{\theta}_L$ 为 $\theta$ 的置信水平为 $1 - \alpha$ 的单侧置信下限。

2. **单侧置信上限**：若对 $\forall \theta \in \Theta$，有

   $$
   P_\theta(\hat{\theta}_U \geq \theta) \geq 1 - \alpha
   $$

   则称 $\hat{\theta}_U$ 为 $\theta$ 的置信水平为 $1 - \alpha$ 的单侧置信上限。

#### 二、枢轴量法

**枢轴量法**是构造置信区间的常用方法，步骤如下：

1. 构造一个样本和未知参数的函数 $G = G(X_1, X_2, \cdots, X_n; \theta)$，使得 $G$ 的分布已知且不依赖于任何未知参数（这样的 $G$ 称为**枢轴量**）
2. 对于给定的置信水平 $1 - \alpha$，选择两个常数 $c$ 和 $d$，使得

   $$
   P(c \leq G \leq d) = 1 - \alpha
   $$
3. 将不等式 $c \leq G \leq d$ 变形为 $\hat{\theta}_L \leq \theta \leq \hat{\theta}_U$，则 $[\hat{\theta}_L, \hat{\theta}_U]$ 就是 $\theta$ 的一个置信水平为 $1 - \alpha$ 的置信区间。

#### 三、单个正态总体的置信区间

设 $X_1, X_2, \cdots, X_n$ 是来自正态总体 $N(\mu, \sigma^2)$ 的样本，$\bar{X}$ 和 $S^2$ 分别是样本均值和样本方差。

1. **$\sigma^2$ 已知时，$\mu$ 的置信区间**

   枢轴量：

   $$
   Z = \frac{\bar{X} - \mu}{\sigma / \sqrt{n}} \sim N(0,1)
   $$

   置信区间：

   $$
   \left[ \bar{X} - z_{\alpha/2} \frac{\sigma}{\sqrt{n}},\ \bar{X} + z_{\alpha/2} \frac{\sigma}{\sqrt{n}} \right]
   $$

2. **$\sigma^2$ 未知时，$\mu$ 的置信区间**

   枢轴量：

   $$
   t = \frac{\bar{X} - \mu}{S / \sqrt{n}} \sim t(n-1)
   $$

   置信区间：

   $$
   \left[ \bar{X} - t_{\alpha/2}(n-1) \frac{S}{\sqrt{n}},\ \bar{X} + t_{\alpha/2}(n-1) \frac{S}{\sqrt{n}} \right]
   $$

3. **$\sigma^2$ 的置信区间**

   枢轴量：

   $$
   \chi^2 = \frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)
   $$

   置信区间：

   $$
   \left[ \frac{(n-1)S^2}{\chi_{\alpha/2}^2(n-1)},\ \frac{(n-1)S^2}{\chi_{1-\alpha/2}^2(n-1)} \right]
   $$

#### 四、两个正态总体的置信区间

设 $X_1, X_2, \cdots, X_m$ 是来自 $N(\mu_1, \sigma_1^2)$ 的样本，$Y_1, Y_2, \cdots, Y_n$ 是来自 $N(\mu_2, \sigma_2^2)$ 的样本，且两样本相互独立。$\bar{X}, \bar{Y}$ 和 $S_x^2, S_y^2$ 分别是两个样本的均值和方差。

1. **$\mu_1 - \mu_2$ 的置信区间**

   (1) $\sigma_1^2$ 和 $\sigma_2^2$ 已知

   枢轴量：

   $$
   Z = \frac{(\bar{X} - \bar{Y}) - (\mu_1 - \mu_2)}{\sqrt{\dfrac{\sigma_1^2}{m} + \dfrac{\sigma_2^2}{n}}} \sim N(0,1)
   $$

   置信区间：

   $$
   \left[ (\bar{X} - \bar{Y}) - z_{\alpha/2} \sqrt{\frac{\sigma_1^2}{m} + \frac{\sigma_2^2}{n}},\ (\bar{X} - \bar{Y}) + z_{\alpha/2} \sqrt{\frac{\sigma_1^2}{m} + \frac{\sigma_2^2}{n}} \right]
   $$

   (2) $\sigma_1^2 = \sigma_2^2 = \sigma^2$ 未知

   记

   $$
   S_W^2 = \frac{(m-1)S_x^2 + (n-1)S_y^2}{m+n-2}
   $$

   枢轴量：

   $$
   t = \frac{(\bar{X} - \bar{Y}) - (\mu_1 - \mu_2)}{S_W \sqrt{\dfrac{1}{m} + \dfrac{1}{n}}} \sim t(m+n-2)
   $$

   置信区间：

   $$
   \left[ (\bar{X} - \bar{Y}) - t_{\alpha/2}(m+n-2) S_W \sqrt{\frac{1}{m} + \frac{1}{n}},\ (\bar{X} - \bar{Y}) + t_{\alpha/2}(m+n-2) S_W \sqrt{\frac{1}{m} + \frac{1}{n}} \right]
   $$

2. **$\dfrac{\sigma_1^2}{\sigma_2^2}$ 的置信区间**

   枢轴量：

   $$
   F = \frac{S_x^2 / \sigma_1^2}{S_y^2 / \sigma_2^2} \sim F(m-1, n-1)
   $$

   置信区间：

   $$
   \left[ \frac{S_x^2}{S_y^2} \cdot \frac{1}{F_{\alpha/2}(m-1, n-1)},\ \frac{S_x^2}{S_y^2} \cdot \frac{1}{F_{1-\alpha/2}(m-1, n-1)} \right]
   $$

#### 五、大样本置信区间

在有些场合，寻找枢轴量及其分布比较困难。在样本容量充分大时，可用渐近分布来构造近似的置信区间。

#### 六、样本量的确定

在实际应用中，我们常常需要确定合适的样本量，使得置信区间的长度不超过预先给定的精度。

---

## 第七章 假设检验

### §7.1 假设检验的基本思想与概念

#### 一、假设检验的基本步骤

1. **建立假设**

   设有来自某一个参数分布族 $\{F(x;\theta) \mid \theta \in \Theta\}$ 的样本 $X_1, X_2, \cdots, X_n$，其中 $\Theta$ 为参数空间。设 $\Theta_0 \subset \Theta$，且 $\Theta_0 \neq \varnothing$，则命题

   $$
   H_0: \theta \in \Theta_0
   $$

   称为**原假设**（或零假设）。

   若有另一个集合 $\Theta_1 \subset \Theta$，且 $\Theta_0 \cap \Theta_1 = \varnothing$（通常 $\Theta_1 = \Theta - \Theta_0$），则命题

   $$
   H_1: \theta \in \Theta_1
   $$

   称为 $H_0$ 的**对立假设**（或备择假设）。

   - 若 $\Theta_0$ 只包含一个点，则称 $H_0$ 为**简单原假设**，否则称为**复杂原假设**
   - 若备择假设分散在原假设两侧，则称 $H_0$ vs $H_1$ 为**双侧假设**；否则称为**单侧假设**

2. **选择检验统计量，给出拒绝域形式**

   由样本对原假设进行检验总是通过一个统计量来实现，这个统计量称为**检验统计量**。

   当样本观测值落在某个区域 $W$ 时，我们拒绝原假设 $H_0$；否则接受 $H_0$。称 $W$ 为该检验的**拒绝域**，而 $\overline{W}$ 称为**接受域**。

3. **选择显著性水平**

   假设检验可能犯两类错误：

   - **第一类错误（拒真错误）**：原假设 $H_0$ 为真，但样本观测值落在拒绝域 $W$ 中，从而拒绝 $H_0$
   - **第二类错误（取伪错误）**：原假设 $H_0$ 为假，但样本观测值落在接受域 $\overline{W}$ 中，从而接受 $H_0$

   | 观测数据情况 | $H_0$ 为真 | $H_1$ 为真 |
   |---|---|---|
   | $(X_1, \cdots, X_n) \in W$ | 第一类错误 | 正确 |
   | $(X_1, \cdots, X_n) \in \overline{W}$ | 正确 | 第二类错误 |

   > 注：在样本容量固定时，减小一类错误的概率会增大另一类错误的概率。

   **定义（势函数）**：设检验问题 $H_0: \theta \in \Theta_0$ vs $H_1: \theta \in \Theta_1$ 的拒绝域为 $W$，则样本观测值 $X$ 落在拒绝域 $W$ 内的概率称为该检验的**势函数**，记为

   $$
   g(\theta) = P_\theta(X \in W), \quad \theta \in \Theta = \Theta_0 \cup \Theta_1
   $$

   **定义（显著性水平）**：对检验问题 $H_0: \theta \in \Theta_0$ vs $H_1: \theta \in \Theta_1$，如果一个检验满足对 $\forall \theta \in \Theta_0$，都有

   $$
   g(\theta) \leq \alpha
   $$

   则称该检验是**显著性水平为 $\alpha$ 的显著性检验**，简称水平为 $\alpha$ 的检验。

   > 注：显著性水平 $\alpha$ 是控制犯第一类错误的概率不超过 $\alpha$，通常取 $\alpha = 0.05, 0.01$ 等。

4. **给出拒绝域**

   根据显著性水平 $\alpha$ 和检验统计量的分布，确定拒绝域 $W$ 的临界值。

5. **做出判断**

   根据样本观测值计算检验统计量的值，若该值落在拒绝域 $W$ 内，则拒绝原假设 $H_0$；否则接受原假设 $H_0$。

#### 二、检验的 P 值

**定义（P 值）**：在一个假设检验问题中，利用样本观测值能够作出拒绝原假设的最小显著性水平称为检验的**P 值**。

> 注：
> - 若 $P \leq \alpha$，则在显著性水平 $\alpha$ 下拒绝 $H_0$
> - 若 $P > \alpha$，则在显著性水平 $\alpha$ 下接受 $H_0$
> - P 值越小，拒绝原假设的理由越充分

---

### §7.2 正态总体参数的假设检验

#### 一、单个正态总体均值的检验

设 $X_1, X_2, \cdots, X_n$ 是来自正态总体 $N(\mu, \sigma^2)$ 的样本，$\bar{X}$ 和 $S^2$ 分别是样本均值和样本方差。

1. **$\sigma^2$ 已知时的 $u$ 检验**

   检验问题：

   - 双侧检验：$H_0: \mu = \mu_0$ vs $H_1: \mu \neq \mu_0$
   - 左侧检验：$H_0: \mu \geq \mu_0$ vs $H_1: \mu < \mu_0$
   - 右侧检验：$H_0: \mu \leq \mu_0$ vs $H_1: \mu > \mu_0$

   检验统计量：

   $$
   Z = \frac{\bar{X} - \mu_0}{\sigma / \sqrt{n}} \sim N(0,1)
   $$

   拒绝域：

   - 双侧检验：$W = \{ |Z| \geq z_{\alpha/2} \}$
   - 左侧检验：$W = \{ Z \leq -z_\alpha \}$
   - 右侧检验：$W = \{ Z \geq z_\alpha \}$

2. **$\sigma^2$ 未知时的 $t$ 检验**

   检验问题同上。

   检验统计量：

   $$
   t = \frac{\bar{X} - \mu_0}{S / \sqrt{n}} \sim t(n-1)
   $$

   拒绝域：

   - 双侧检验：$W = \{ |t| \geq t_{\alpha/2}(n-1) \}$
   - 左侧检验：$W = \{ t \leq -t_\alpha(n-1) \}$
   - 右侧检验：$W = \{ t \geq t_\alpha(n-1) \}$

#### 二、单个正态总体方差的检验

检验问题：

- 双侧检验：$H_0: \sigma^2 = \sigma_0^2$ vs $H_1: \sigma^2 \neq \sigma_0^2$
- 左侧检验：$H_0: \sigma^2 \geq \sigma_0^2$ vs $H_1: \sigma^2 < \sigma_0^2$
- 右侧检验：$H_0: \sigma^2 \leq \sigma_0^2$ vs $H_1: \sigma^2 > \sigma_0^2$

检验统计量：

$$
\chi^2 = \frac{(n-1)S^2}{\sigma_0^2} \sim \chi^2(n-1)
$$

拒绝域：

- 双侧检验：$W = \{ \chi^2 \leq \chi_{1-\alpha/2}^2(n-1) \text{ 或 } \chi^2 \geq \chi_{\alpha/2}^2(n-1) \}$
- 左侧检验：$W = \{ \chi^2 \leq \chi_{1-\alpha}^2(n-1) \}$
- 右侧检验：$W = \{ \chi^2 \geq \chi_\alpha^2(n-1) \}$

#### 三、两个正态总体均值差的检验

设 $X_1, X_2, \cdots, X_m$ 是来自 $N(\mu_1, \sigma_1^2)$ 的样本，$Y_1, Y_2, \cdots, Y_n$ 是来自 $N(\mu_2, \sigma_2^2)$ 的样本，且两样本相互独立。$\bar{X}, \bar{Y}$ 和 $S_x^2, S_y^2$ 分别是两个样本的均值和方差。

1. **$\sigma_1^2$ 和 $\sigma_2^2$ 已知时的 $u$ 检验**

   检验问题：

   - 双侧检验：$H_0: \mu_1 = \mu_2$ vs $H_1: \mu_1 \neq \mu_2$
   - 左侧检验：$H_0: \mu_1 \geq \mu_2$ vs $H_1: \mu_1 < \mu_2$
   - 右侧检验：$H_0: \mu_1 \leq \mu_2$ vs $H_1: \mu_1 > \mu_2$

   检验统计量：

   $$
   Z = \frac{(\bar{X} - \bar{Y}) - (\mu_1 - \mu_2)}{\sqrt{\dfrac{\sigma_1^2}{m} + \dfrac{\sigma_2^2}{n}}} \sim N(0,1)
   $$

   拒绝域与单个正态总体的 $u$ 检验相同。

2. **$\sigma_1^2 = \sigma_2^2 = \sigma^2$ 未知时的 $t$ 检验**

   检验问题同上。

   记

   $$
   S_W^2 = \frac{(m-1)S_x^2 + (n-1)S_y^2}{m+n-2}
   $$

   检验统计量：

   $$
   t = \frac{(\bar{X} - \bar{Y}) - (\mu_1 - \mu_2)}{S_W \sqrt{\dfrac{1}{m} + \dfrac{1}{n}}} \sim t(m+n-2)
   $$

   拒绝域与单个正态总体的 $t$ 检验相同。

#### 四、两个正态总体方差比的检验

检验问题：

- 双侧检验：$H_0: \sigma_1^2 = \sigma_2^2$ vs $H_1: \sigma_1^2 \neq \sigma_2^2$
- 左侧检验：$H_0: \sigma_1^2 \geq \sigma_2^2$ vs $H_1: \sigma_1^2 < \sigma_2^2$
- 右侧检验：$H_0: \sigma_1^2 \leq \sigma_2^2$ vs $H_1: \sigma_1^2 > \sigma_2^2$

检验统计量：

$$
F = \frac{S_x^2}{S_y^2} \sim F(m-1, n-1)
$$

拒绝域：

- 双侧检验：$W = \{ F \leq F_{1-\alpha/2}(m-1, n-1) \text{ 或 } F \geq F_{\alpha/2}(m-1, n-1) \}$
- 左侧检验：$W = \{ F \leq F_{1-\alpha}(m-1, n-1) \}$
- 右侧检验：$W = \{ F \geq F_\alpha(m-1, n-1) \}$