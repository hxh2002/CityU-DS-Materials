# DSC5001: Statistical Machine Learning I

## Assignment 1

---

## Question 1: Gaussian Geometry and Linear Combinations [10 marks]

Let

$$
X=\begin{bmatrix}X_1\\X_2\end{bmatrix}
\sim\mathcal{N}\!\left(
\begin{bmatrix}0\\0\end{bmatrix},
\begin{bmatrix}4&3\\3&4\end{bmatrix}
\right).
$$

Consider the two observations

$$
x_A=\begin{bmatrix}2\\2\end{bmatrix},
\qquad
x_B=\begin{bmatrix}2\\-2\end{bmatrix}.
$$

**(a)** Compute the squared Mahalanobis distance of each observation from the Gaussian mean. **[3 marks]**

**(b)** Determine which observation has the larger Gaussian density and compute

$$
\frac{p(x_A)}{p(x_B)}.
$$

Your argument should use the multivariate Gaussian model rather than Euclidean distance alone. **[3 marks]**

**(c)** Define

$$
U=X_1+X_2,\qquad V=X_1-X_2.
$$

Compute $\operatorname{Var}(U)$, $\operatorname{Var}(V)$, and $\operatorname{Cov}(U,V)$. Are $U$ and $V$ independent? Justify your answer. **[4 marks]**

---

## Question 2: Method of Moments versus Maximum Likelihood [10 marks]

Suppose $X_1,\ldots,X_n$ are independent observations from the model

$$
f(x\mid\theta)=
\begin{cases}
\dfrac{2x}{\theta^2}, & 0\le x\le\theta,\\[4pt]
0, & \text{otherwise},
\end{cases}
\qquad \theta>0.
$$

The observed sample is

$$
1,\qquad 2,\qquad 3,\qquad 4.
$$

**(a)** Using the first population moment, obtain the Method-of-Moments estimate of $\theta$. **[3 marks]**

**(b)** Construct the likelihood as a function of $\theta$ and obtain the maximum-likelihood estimate. Pay particular attention to the support of the model. **[4 marks]**

**(c)** Compare the two estimates. Explain why one of them assigns zero likelihood to the observed dataset, and state what this example shows about mechanically matching moments. **[3 marks]**

---

## Question 3: Bootstrap Uncertainty for a Range Statistic [10 marks]

The observed sample is

$$
D=\{1,3,4,8,10\},
$$

and the statistic of interest is the sample range,

$$
T(D)=\max(D)-\min(D).
$$

Eight bootstrap resamples are shown below:

| Resample | Observations      |
| :------: | :---------------- |
|    1    | $(1,3,3,4,8)$   |
|    2    | $(1,1,4,10,10)$ |
|    3    | $(3,3,4,8,8)$   |
|    4    | $(1,4,4,8,10)$  |
|    5    | $(1,1,3,4,4)$   |
|    6    | $(3,4,8,8,10)$  |
|    7    | $(1,3,8,10,10)$ |
|    8    | $(1,3,4,4,8)$   |

**(a)** Compute the observed statistic and the eight bootstrap replicate values. **[3 marks]**

**(b)** From these replicates, compute the bootstrap bias estimate and bootstrap standard error of the range. **[4 marks]**

**(c)** A second analyst proposes drawing five observations without replacement from $D$ in every repetition. Explain what would happen to the estimated uncertainty of the range and why this is not the ordinary nonparametric bootstrap used in the course. **[3 marks]**

---

## Question 4: Regression Fitting, Leverage, and Influence [20 marks]

Consider the simple linear regression dataset

$$
x=(0,1,2,3,4,9),\qquad y=(1,3,8,7,9,18).
$$

Fit a linear model with an intercept.

**(a)** Obtain the OLS fitted line. Show the quantities needed to obtain the intercept and slope rather than quoting a software output. **[5 marks]**

**(b)** Compute the fitted values, residuals, residual sum of squares, and the usual estimate of the error variance. **[4 marks]**

**(c)** Compute the leverage of every observation and identify the highest-leverage point. **[4 marks]**

**(d)** Using the Cook’s-distance expression developed in Week 4, compute an influence score for every observation, up to the common positive scaling factor used in the lecture. Identify the most influential observation. Is it also the observation with the largest absolute residual? **[4 marks]**

**(e)** Remove the most influential observation, refit the regression line, and compare the new slope with the original slope. Explain what this calculation shows about influence. **[3 marks]**

---

## Question 5: Mean and Covariance under a Linear Transformation [10 marks]

Let $X\in\mathbb{R}^d$ be a random vector with finite second moments, mean $\mu$, and covariance matrix $\Sigma$. Let

$$
Y=AX+b,
$$

where $A\in\mathbb{R}^{m\times d}$ and $b\in\mathbb{R}^m$ are fixed.

**(a)** Starting from the definition of expectation, derive the mean vector of $Y$. **[3 marks]**

**(b)** Starting from the definition of a covariance matrix, derive the covariance matrix of $Y$. Do not quote the transformation rule without proof. **[5 marks]**

**(c)** Specialize your result to the scalar random variable

$$
Z=a^{\top}X.
$$

Explain from your expression why $\operatorname{Var}(Z)$ cannot be negative. **[2 marks]**

---

## Question 6: Bias–Variance Trade-off between Two Bernoulli Estimators [10 marks]

Let

$$
X_1,\ldots,X_n\overset{\mathrm{iid}}{\sim}\operatorname{Bernoulli}(p),
\qquad
S=\sum_{i=1}^{n}X_i.
$$

Consider the two estimators

$$
\hat{p}_1=\frac{S}{n},
\qquad
\hat{p}_2=\frac{S+1}{n+2}.
$$

**(a)** Derive the bias and variance of both estimators. **[4 marks]**

**(b)** Derive the mean-squared error of both estimators. **[3 marks]**

**(c)** Determine, as an inequality involving $p$ and $n$, when $\hat{p}_2$ has smaller MSE than $\hat{p}_1$. Briefly explain why an estimator with nonzero bias can nevertheless have smaller MSE. **[3 marks]**

---

## Question 7: Sampling Distribution Induced by the Bootstrap [10 marks]

Let the observed dataset be

$$
D=\{x_1,\ldots,x_n\},
\qquad
\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i.
$$

In the ordinary nonparametric bootstrap, each bootstrap observation is drawn independently from the empirical distribution that places equal probability on the observed values. Let

$$
\bar{X}^{*}=\frac{1}{n}\sum_{j=1}^{n}X_j^{*}
$$

denote the mean of one bootstrap resample.

**(a)** Conditioning on the observed dataset $D$, derive the mean and variance of one bootstrap draw $X_j^{*}$. **[4 marks]**

**(b)** Use your result to derive the conditional mean and variance of $\bar{X}^{*}$. Hence obtain the bootstrap bias estimate and bootstrap standard error for the sample mean. **[4 marks]**

**(c)** Rewrite the bootstrap variance of $\bar{X}^{*}$ in terms of the usual unbiased sample variance. Identify the finite-sample multiplicative factor that appears. **[2 marks]**

---

## Question 8: Projection Geometry and OLS Variability [20 marks]

Consider the linear regression model

$$
y=X\beta+\varepsilon,
$$

where $X\in\mathbb{R}^{n\times p}$ has full column rank and

$$
E[\varepsilon\mid X]=0,
\qquad
\operatorname{Var}(\varepsilon\mid X)=\sigma^2 I.
$$

Let $\hat{y}$ be the OLS fitted vector, $e=y-\hat{y}$ the residual vector, and $H$ the OLS hat matrix.

**(a)** Write $H$ in terms of $X$ and prove that it is both symmetric and idempotent. **[5 marks]**

**(b)** Prove that the residual vector is orthogonal to every column of $X$. Then derive

$$
\sum_{i=1}^{n}h_{ii}=p,
$$

where $h_{ii}$ denotes the $i$th leverage value. **[5 marks]**

**(c)** Derive the conditional covariance matrices of the fitted vector $\hat{y}$ and the residual vector $e$. **[6 marks]**

**(d)** Use the diagonal entries of your results from part (c) to describe how leverage affects the variability of a fitted value and the variability of its residual. Explain why this matters when interpreting unusually large residuals. **[4 marks]**

---

---

# Worked Solutions

## Question 1 解答：Gaussian Geometry and Linear Combinations

### (a) Squared Mahalanobis distance 马氏距离平方

**步骤**

1. 求协方差矩阵的逆。$\det\Sigma=4\cdot4-3\cdot3=7$，用 $2\times2$ 求逆公式：
   $$
   \Sigma^{-1}=\frac{1}{7}\begin{bmatrix}4&-3\\-3&4\end{bmatrix}.
   $$
2. 套定义 $d^2(x)=(x-\mu)^\top\Sigma^{-1}(x-\mu)$，此处 $\mu=0$：
   - $\Sigma^{-1}x_A=\frac17\begin{bmatrix}4\cdot2-3\cdot2\\-3\cdot2+4\cdot2\end{bmatrix}=\frac17\begin{bmatrix}2\\2\end{bmatrix}$，故
     $$
     d^2(x_A)=x_A^\top\Sigma^{-1}x_A=\frac17(2\cdot2+2\cdot2)=\frac{8}{7}.
     $$
   - $\Sigma^{-1}x_B=\frac17\begin{bmatrix}4\cdot2+3\cdot2\\-3\cdot2-4\cdot2\end{bmatrix}=\frac17\begin{bmatrix}14\\-14\end{bmatrix}$，故
     $$
     d^2(x_B)=\frac17(2\cdot14+(-2)(-14))=\frac{56}{7}=8.
     $$

**中文讲解**：马氏距离用 $\Sigma^{-1}$ 把坐标轴"按方差缩放、按相关旋转"后再量距离；$x_A$ 沿相关方向（方差大的方向），同样欧氏距离下显得离中心更近。

### (b) 密度比

**步骤**

1. 写多元高斯密度：$p(x)=(2\pi)^{-1}|\Sigma|^{-1/2}\exp(-\tfrac12 d^2(x))$，归一化常数两点相同。
2. 比较指数：$d^2(x_A)=8/7<8=d^2(x_B)$，故 $p(x_A)>p(x_B)$。
3. 计算比值：
   $$
   \frac{p(x_A)}{p(x_B)}=\exp\left[-\frac12\left(\frac87-8\right)\right]=e^{24/7}\approx30.8.
   $$

**中文讲解**：两点欧氏距离相同（都是 $2\sqrt2$），但高斯密度只由马氏距离决定——这就是题目要求"不能只用欧氏距离"的原因。

### (c) 线性组合的方差与独立性

**步骤**

1. $\operatorname{Var}(U)=\operatorname{Var}(X_1)+\operatorname{Var}(X_2)+2\operatorname{Cov}(X_1,X_2)=4+4+6=14$。
2. $\operatorname{Var}(V)=4+4-6=2$。
3. $\operatorname{Cov}(U,V)=\operatorname{Cov}(X_1+X_2,X_1-X_2)=\operatorname{Var}(X_1)-\operatorname{Var}(X_2)=4-4=0$。
4. 独立性：$(U,V)=AX$ 是联合高斯的线性变换，仍是联合高斯；**联合高斯 + 零协方差 $\Rightarrow$ 独立**。所以 $U,V$ 独立。

**变式应对**：换 $\Sigma$ 或观察点——只改第 1 步求逆和第 2 步乘法，流程不变；若均值非零，先算 $x-\mu$；若问非高斯变量的两个线性组合，零协方差**不能**推出独立（只能用"不相关"）。判断独立前必须先确认联合高斯。

---

## Question 2 解答：MoM versus MLE

### (a) Method-of-Moments 矩估计

**步骤**

1. 算总体一阶矩：
   $$
   E[X]=\int_0^\theta x\cdot\frac{2x}{\theta^2}\,dx=\frac{2}{\theta^2}\cdot\frac{\theta^3}{3}=\frac{2\theta}{3}.
   $$
2. 样本均值 $\bar x=(1+2+3+4)/4=2.5$。
3. 匹配 $E[X]=\bar x$：$2\theta/3=2.5\Rightarrow\hat\theta_{MM}=3.75$。

### (b) MLE（注意支持集）

**步骤**

1. 写联合似然，**必须带上支持集约束**：每个观测都要满足 $x_i\le\theta$，即 $\theta\ge\max_i x_i$：
   $$
   L(\theta)=\prod_{i=1}^4\frac{2x_i}{\theta^2}\cdot I(\theta\ge x_{(4)})=\frac{2^4\prod x_i}{\theta^8}\cdot I(\theta\ge4).
   $$
2. 在允许区域 $\theta\ge4$ 内，$L(\theta)=C\theta^{-8}$ 关于 $\theta$ **单调递减**。
3. 因此最大值取在最小允许值：$\hat\theta_{MLE}=\max_i x_i=4$。

### (c) 比较与教训

- MoM 给出 $3.75<4$，观测值 4 落在支持集外，该数据集 likelihood $=0$；MLE 自带支持集约束，不会犯此错。
- 教训：机械地匹配矩可能产生**不在参数允许区域内**的估计；矩匹配不保证与模型支持集兼容，而 MLE 的似然函数自动编码了支持集。

**变式应对**：换成 $Uniform(0,\theta)$——同样套路：$E[X]=\theta/2\Rightarrow\hat\theta_{MM}=2\bar x$，$L(\theta)=\theta^{-n}I(\theta\ge x_{(n)})$ 递减 $\Rightarrow\hat\theta_{MLE}=x_{(n)}$。识别信号：密度形如"常数/$\theta$ 的幂 + 区间支持"，MLE 几乎总在边界（最大或最小次序统计量），不用求导，改用单调性论证。若模型有两个未知参数，MoM 需再匹配二阶矩 $E[X^2]$。

---

## Question 3 解答：Bootstrap Uncertainty for a Range

### (a) 观测统计量与复制值

$T(D)=\max-\min=10-1=9$。逐行取 max−min：

| Resample |  Range  |
| -------- | :-----: |
| 1        | 8−1=7 |
| 2        | 10−1=9 |
| 3        | 8−3=5 |
| 4        | 10−1=9 |
| 5        | 4−1=3 |
| 6        | 10−3=7 |
| 7        | 10−1=9 |
| 8        | 8−1=7 |

### (b) Bootstrap bias 与 SE

**步骤**

1. 复制值均值：$\bar T^*=(7+9+5+9+3+7+9+7)/8=56/8=7$。
2. 偏差估计：$\widehat{Bias}_{boot}=\bar T^*-T(D)=7-9=-2$。
3. 平方离差和：$(7-7)^2+(9-7)^2+(5-7)^2+(9-7)^2+(3-7)^2+(7-7)^2+(9-7)^2+(7-7)^2=0+4+4+4+16+0+4+0=32$。
4. 用 $B-1$：
   $$
   SE_{boot}=\sqrt{\frac{32}{8-1}}=\sqrt{\frac{32}{7}}\approx2.138.
   $$

**中文讲解**：偏差为负说明 range 在小样本重抽中系统性偏小（重抽常丢掉端点 1 或 10）——这正是"极值类统计量"的典型行为。

### (c) 无放回抽 5 个会怎样

无放回抽满 $n=5$ 个，每次只是原集合的重新排列，max、min 不变，range 恒等于 9：复制值零波动，$SE_{boot}=0$、bias 估计为 0，**严重低估**真实不确定性。普通非参数 bootstrap 必须有放回：正是"有的点重复、有的点缺席"才模拟出重新抽样的波动。

**变式应对**：换统计量（median、SD、IQR）——流程完全一样：先算原样本统计量，再逐行算复制值，$\bar\theta^*-\hat\theta$ 得偏差、$B-1$ 公式得 SE；若题目要求 percentile interval，就把复制值排序取 2.5%/97.5% 分位数。若问"为什么 $B-1$ 而不是 $B$"：因为是从有限 $B$ 个复制值估计总体方差，同 $n-1$ 样本方差同理。

---

## Question 4 解答：Regression Fitting, Leverage, and Influence

### (a) OLS 拟合线

**步骤**（先备齐五个汇总量）

1. $\bar x=19/6\approx3.167$，$\bar y=46/6=23/3\approx7.667$。
2. $S_{xx}=\sum(x_i-\bar x)^2=\sum x_i^2-n\bar x^2=111-6(19/6)^2=305/6$。
3. $S_{xy}=\sum(x_i-\bar x)(y_i-\bar y)=\sum x_iy_i-n\bar x\bar y=238-6\cdot(19/6)(23/3)=277/3$。
4. 斜率与截距：
   $$
   \hat\beta_1=\frac{S_{xy}}{S_{xx}}=\frac{277/3}{305/6}=\frac{554}{305}\approx1.816,\qquad
   \hat\beta_0=\bar y-\hat\beta_1\bar x=\frac{584}{305}\approx1.915.
   $$
5. 拟合线：$\hat y=1.915+1.816x$。

### (b) 拟合值、残差、RSS、误差方差

逐点 $\hat y_i=\hat\beta_0+\hat\beta_1x_i$，$e_i=y_i-\hat y_i$：

| $i$ | $x_i$ | $y_i$ | $\hat y_i$ | $e_i$ |
| ----: | ------: | ------: | -----------: | ------: |
|     1 |       0 |       1 |        1.915 | −0.915 |
|     2 |       1 |       3 |        3.731 | −0.731 |
|     3 |       2 |       8 |        5.548 |   2.452 |
|     4 |       3 |       7 |        7.364 | −0.364 |
|     5 |       4 |       9 |        9.180 | −0.180 |
|     6 |       9 |      18 |       18.262 | −0.262 |

$$
RSS=\sum e_i^2=\frac{2324}{305}\approx7.620,\qquad
\hat\sigma^2=\frac{RSS}{n-2}=\frac{2324/305}{4}=\frac{581}{305}\approx1.905.
$$

### (c) Leverage

一元含截距回归用心算公式 $h_{ii}=\frac1n+\frac{(x_i-\bar x)^2}{S_{xx}}$：

| $i$      | 1     | 2     | 3     | 4     | 5     | 6               |
| ---------- | ----- | ----- | ----- | ----- | ----- | --------------- |
| $h_{ii}$ | 0.364 | 0.259 | 0.193 | 0.167 | 0.164 | **0.853** |

最高杠杆：**第 6 点**（$x=9$ 远离 $\bar x$）。检查：$\sum h_{ii}=2=p$。

### (d) Cook's-distance 影响分数

按课件形式，忽略共同正因子 $1/(p\hat\sigma^2)$，计算 $I_i=e_i^2\cdot\frac{h_{ii}}{(1-h_{ii})^2}$：

| $i$   | 1     | 2     | 3     | 4     | 5     | 6               |
| ------- | ----- | ----- | ----- | ----- | ----- | --------------- |
| $I_i$ | 0.753 | 0.252 | 1.788 | 0.032 | 0.009 | **2.140** |

最有影响：**第 6 点**。但绝对残差最大的是第 3 点（$|e_3|=2.452$）——二者不是同一点：influence = 残差 × 杠杆的联合作用，高杠杆点即使残差小也可能最影响拟合。

### (e) 删除后重拟合

删除第 6 点：$\bar x'=2$，$\bar y'=5.6$，$S'_{xx}=10$，$S'_{xy}=20$，得

$$
\hat y'=1.6+2x.
$$

斜率从 $1.816$ 变为 $2.0$（约 +10%）。说明单个高杠杆点就能明显拉动整条直线；influential ≠ 错误数据，但必须在报告中识别并核查。

**变式应对**：换数据——完全按同一管线走（$\bar x,\bar y,S_{xx},S_{xy}\to\hat\beta\to e_i\to h_{ii}\to I_i$）；$h_{ii}$ 心算公式只对"含截距的一元回归"成立，多元情形用 $h_{ii}=x_i^\top(X^\top X)^{-1}x_i$；若题目给 $\hat y$ 和 $h$ 的现成表格，直接从残差和 Cook 比例式入手，先检查残差和是否为 0（不为 0 说明给的不是含截距 OLS 的拟合值，需在答案中注明）。

---

## Question 5 解答：Mean and Covariance under Linear Transformation

### (a) 均值

**步骤**（从期望定义/线性性出发）

$$
E[Y]=E[AX+b]=E[AX]+E[b]=AE[X]+b=A\mu+b.
$$

依据：期望对每个分量是线性算子，常数矩阵 $A$ 和常数向量 $b$ 可提出（$E[b]=b$）。

### (b) 协方差矩阵（从定义推导）

**步骤**

1. 写定义：$\operatorname{Cov}(Y)=E[(Y-E[Y])(Y-E[Y])^\top]$。
2. 代入并消去 $b$：$Y-E[Y]=AX+b-(A\mu+b)=A(X-\mu)$。
3. 转置规则 $(Mv)^\top=v^\top M^\top$：
   $$
   \operatorname{Cov}(Y)=E[A(X-\mu)(X-\mu)^\top A^\top]=A\,E[(X-\mu)(X-\mu)^\top]\,A^\top=A\Sigma A^\top.
   $$
4. 注意常数 $b$ 不出现在结果中：平移不改变协方差。

### (c) 为什么 $\operatorname{Var}(Z)$ 非负

$Z=a^\top X$ 即 $A=a^\top$、$b=0$ 的特例，由 (b) 得

$$
\operatorname{Var}(Z)=a^\top\Sigma a.
$$

从定义看 $\operatorname{Var}(Z)=E[(Z-EZ)^2]$ 是平方量的期望，必 $\ge0$；因此对任意 $a$ 都有 $a^\top\Sigma a\ge0$。

**变式应对**：若改成 $Y=AX+b$ 给具体数字矩阵——先算 $A\mu+b$ 再算 $A\Sigma A^\top$，注意矩阵乘法顺序不可换；若问 $Z=a^\top X+b$（多一个常数），方差不变；若要求"证明 $\Sigma$ 半正定"，就是用本题 (c) 的结论。

---

## Question 6 解答：Bias–Variance Trade-off

### (a) Bias 与 Variance

预备：$E[S]=np$，$\operatorname{Var}(S)=np(1-p)$。

**$\hat p_1=S/n$：**

$$
E[\hat p_1]=\frac{np}{n}=p\Rightarrow Bias=0,\qquad
\operatorname{Var}(\hat p_1)=\frac{np(1-p)}{n^2}=\frac{p(1-p)}{n}.
$$

**$\hat p_2=(S+1)/(n+2)$：**

$$
E[\hat p_2]=\frac{np+1}{n+2}\Rightarrow
Bias=\frac{np+1}{n+2}-p=\frac{1-2p}{n+2},
$$

$$
\operatorname{Var}(\hat p_2)=\frac{\operatorname{Var}(S+1)}{(n+2)^2}=\frac{np(1-p)}{(n+2)^2}.
$$

### (b) MSE

用 $\operatorname{MSE}=Bias^2+\operatorname{Var}$：

$$
\operatorname{MSE}(\hat p_1)=\frac{p(1-p)}{n},\qquad
\operatorname{MSE}(\hat p_2)=\frac{np(1-p)+(1-2p)^2}{(n+2)^2}.
$$

### (c) 何时 $\hat p_2$ 的 MSE 更小

列不等式并化简：

$$
\frac{np(1-p)+(1-2p)^2}{(n+2)^2}<\frac{p(1-p)}{n}
\Longleftrightarrow
n^2p(1-p)+n(1-2p)^2<(n^2+4n+4)p(1-p)
$$

$$
\Longleftrightarrow n(1-2p)^2<4(n+1)p(1-p).
$$

**结论**：$p$ 接近 $1/2$ 时 $\hat p_2$ 胜出；$p$ 靠近 0/1 时 $\hat p_1$ 胜出。$\hat p_2$ 把估计向 $1/2$ 收缩，引入 $O(1/n)$ 的小偏差却换来更小的方差，平方损失下总误差可降低——**有偏 ≠ 更差，MSE 才是完整标准**。

**变式应对**：换成一般收缩估计 $(S+a)/(n+b)$——同一管线：先 $E$、$Var$（常数平移不影响方差），再 $Bias^2+Var$，最后解关于 $p$ 的不等式；若题目给具体 $n,p$ 问谁更好，直接代入两个 MSE 比较数值即可。

---

## Question 7 解答：Bootstrap 诱导的抽样分布

### (a) 单次抽取的条件均值与方差

条件于 $D$，$X_j^*$ 是离散均匀：$P^*(X_j^*=x_i)=1/n$。

$$
E^*[X_j^*]=\sum_i x_i\cdot\frac1n=\bar x,
$$

$$
\operatorname{Var}^*(X_j^*)=E^*[(X_j^*)^2]-(E^*X_j^*)^2=\frac1n\sum_i x_i^2-\bar x^2=\frac1n\sum_i(x_i-\bar x)^2.
$$

### (b) $\bar X^*$ 的条件分布特征

各次抽取相互独立，方差可加：

$$
E^*[\bar X^*]=\frac1n\sum_j E^*[X_j^*]=\bar x,
$$

$$
\operatorname{Var}^*(\bar X^*)=\frac{1}{n^2}\cdot n\operatorname{Var}^*(X_j^*)=\frac{1}{n^2}\sum_i(x_i-\bar x)^2.
$$

因此

$$
\widehat{Bias}_{boot}=E^*[\bar X^*]-\bar x=0,\qquad
SE_{boot}=\frac1n\sqrt{\sum_i(x_i-\bar x)^2}.
$$

### (c) 用无偏样本方差改写

由 $s^2=\frac{1}{n-1}\sum_i(x_i-\bar x)^2$ 得 $\sum_i(x_i-\bar x)^2=(n-1)s^2$，故

$$
\operatorname{Var}^*(\bar X^*)=\frac{(n-1)s^2}{n^2}=\frac{n-1}{n}\cdot\frac{s^2}{n},
\qquad
SE_{boot}=\sqrt{\frac{n-1}{n}}\cdot\frac{s}{\sqrt n}.
$$

有限样本乘性因子：$\sqrt{(n-1)/n}$。精确 bootstrap 的 SE 比 plug-in 公式 $s/\sqrt n$ 略小，$n$ 大时因子趋近 1。

**变式应对**：若改为中位数等无解析形式的统计量——(a)(b) 的推导只适用于均值，答案应写"需要 Monte Carlo 枚举/模拟"；若问"为什么这里偏差恰为 0"：因为 bootstrap 世界里的"真参数"就是 $\bar x$，而均值是无偏的；若题目给 $n=2$ 的小样本让枚举全部 $n^n$ 种重抽，列表算概率即可（如讲义 $D=[2,4]$ 例）。

---

## Question 8 解答：Projection Geometry and OLS Variability

### (a) $H$ 的定义、对称性与幂等性

$$
H=X(X^\top X)^{-1}X^\top\quad(\text{要求 } X \text{ 满列秩，使 } X^\top X \text{ 可逆}).
$$

**对称**：$(X^\top X)^{-1}$ 对称（因为 $(X^\top X)^\top=X^\top X$），故

$$
H^\top=\bigl(X(X^\top X)^{-1}X^\top\bigr)^\top=X\bigl((X^\top X)^{-1}\bigr)^\top X^\top=X(X^\top X)^{-1}X^\top=H.
$$

**幂等**：

$$
H^2=X(X^\top X)^{-1}\underbrace{X^\top X(X^\top X)^{-1}}_{I}X^\top=X(X^\top X)^{-1}X^\top=H.
$$

### (b) 残差正交性与 $\sum h_{ii}=p$

1. 残差：$e=y-\hat y=y-Hy=(I-H)y$。
2. 正交性：

   $$
   X^\top e=X^\top(I-H)y=\bigl(X^\top-X^\top X(X^\top X)^{-1}X^\top\bigr)y=(X^\top-X^\top)y=0,
   $$

   即 $e$ 与 $X$ 的每一列正交。
3. 迹的轮换性 $\operatorname{tr}(AB)=\operatorname{tr}(BA)$：

   $$
   \sum_{i=1}^n h_{ii}=\operatorname{tr}(H)=\operatorname{tr}\!\bigl(X(X^\top X)^{-1}X^\top\bigr)=\operatorname{tr}\!\bigl((X^\top X)^{-1}X^\top X\bigr)=\operatorname{tr}(I_p)=p.
   $$

### (c) $\hat y$ 与 $e$ 的条件协方差

由 $\hat y=Hy=H(X\beta+\varepsilon)=X\beta+H\varepsilon$（用了 $HX=X$），且 $\operatorname{Var}(\varepsilon|X)=\sigma^2I$：

$$
\operatorname{Var}(\hat y\mid X)=H(\sigma^2I)H^\top=\sigma^2HH=\sigma^2H.
$$

同理 $e=(I-H)y=(I-H)\varepsilon$（因 $(I-H)X\beta=0$）：

$$
\operatorname{Var}(e\mid X)=(I-H)(\sigma^2I)(I-H)^\top=\sigma^2(I-H).
$$

（两处都用了 $H$、$I-H$ 对称幂等。）

### (d) 杠杆值如何影响波动

对角线元素给出

$$
\operatorname{Var}(\hat y_i\mid X)=\sigma^2h_{ii},\qquad
\operatorname{Var}(e_i\mid X)=\sigma^2(1-h_{ii}).
$$

- $h_{ii}$ 越大，该点拟合值越受自身 $y_i$ 支配，fitted value 的抽样波动越大；
- 同时残差方差 $\sigma^2(1-h_{ii})$ 越小——**高杠杆点的残差被"压小"了**，因为直线已被拉向该点。
- 解读启示：判断异常点时不能直接比较原始残差大小；高杠杆点的真实异常可能被小残差掩盖，应结合杠杆（或用标准化残差 $e_i/(\hat\sigma\sqrt{1-h_{ii}})$）和 Cook's distance 一起判断。

**变式应对**：若题目改问 $I-H$ 的性质——同样对称幂等（$(I-H)^2=I-2H+H^2=I-H$）；若改问 $\operatorname{Cov}(\hat y,e|X)$——等于 $\sigma^2H(I-H)=0$，即拟合值与残差不相关（高斯假设下还独立）；若 $X$ 只有截距列，$H=\frac1n J$（全 $1/n$ 矩阵），$h_{ii}=1/n$，此时 $\sum h_{ii}=1=p$ 仍然成立。

---

1. **计算题**：数字会变，管线不变。先把"汇总量"（$\bar x$、$S_{xx}$、$\Sigma^{-1}$、复制值表）列清，再代公式；支持集、自由度、分母（$n$ vs $n-1$ vs $B-1$）是最常见的改题点。
2. **推导题**：结论会换（如把 $H$ 换成 $I-H$、把均值换成加权组合），但评分点始终是"从定义出发 + 每步给出依据（线性性/对称幂等/独立性）"。
3. **概念问句**：凡涉及"是否独立"先想分布假设；凡涉及"区间/不确定性"先分清 SE 与 SD、置信区间与预测区间。
