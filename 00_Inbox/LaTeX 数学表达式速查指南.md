# LaTeX 数学表达式

> [!INFO] 使用说明
> - **行内公式**：使用 `$...$` 包裹，如 `$x^2$` → $x^2$
> - **块级公式**：使用 `$$...$$` 包裹，独占一行居中显示
> - 所有代码均在 MathJax 环境下测试通过

---

## 一、基础运算符

| 运算       | LaTeX 代码                                        | 渲染效果          | 备注                               |
| ---------- | ------------------------------------------------- | ----------------- | ---------------------------------- |
| 加法       | `a + b`                                           | $a + b$           | 直接输入                           |
| 减法       | `a - b`                                           | $a - b$           | 直接输入                           |
| 乘法(点)   | `a \cdot b`                                       | $a \cdot b$       | 推荐用于向量/标量乘法              |
| 乘法(叉)   | `a \times b`                                      | $a \times b$      | 向量叉乘、单位换算                 |
| 乘法(省略) | `ab` 或 `a\,b`                                    | $ab$              | 变量相邻默认相乘                   |
| 除法(分数) | `\frac{a}{b}`                                     | $\frac{a}{b}$     | 推荐用于复杂表达式                 |
| 除法(斜线) | `a / b`                                           | $a / b$           | 简单表达式可用                     |
| 除法(冒号) | `a : b`                                           | $a : b$           | 比例关系                           |
| 正负号     | `\pm` / `\mp`                                     | $\pm$ / $\mp$     | 误差范围、解的多值性               |
| 绝对值     | `\lvert x \rvert` 或 `\left\lvert x \right\rvert` | $\lvert x \rvert$ | 推荐用 `\left...\right` 自适应高度 |
| 模运算     | `a \bmod b`                                       | $a \bmod b$       | 离散数学、编程相关                 |
| 文本精确正负号| `\textnormal{-}5`          |          $-5$                                       |                   |                                    |

---

## 二、括号与定界符

> [!TIP] 使用 `\left` 和 `\right` 让括号自动适应内容高度

| 类型 | LaTeX 代码 | 渲染效果 | 说明 |
|------|-----------|---------|------|
| 小括号 | `(x)` 或 `\left( \frac{a}{b} \right)` | $(x)$ / $\left( \frac{a}{b} \right)$ | 基础括号 |
| 中括号 | `[x]` 或 `\left[ \frac{a}{b} \right]` | $[x]$ / $\left[ \frac{a}{b} \right]$ | 区间、矩阵 |
| 大括号 | `\{ x \}` 或 `\left\{ \frac{a}{b} \right\}` | $\{ x \}$ / $\left\{ \frac{a}{b} \right\}$ | **注意**：`{` 和 `}` 需转义 |
| 尖括号 | `\langle x \rangle` 或 `\left\langle \frac{a}{b} \right\rangle` | $\langle x \rangle$ | 量子力学、平均量 |
| 绝对值 | `\lvert x \rvert` | $\lvert x \rvert$ | 标量模长 |
| 范数 | `\lVert \mathbf{v} \rVert` | $\lVert \mathbf{v} \rVert$ | 向量/矩阵范数 |
| 向上取整 | `\lceil x \rceil` | $\lceil x \rceil$ | 离散化、网格划分 |
| 向下取整 | `\lfloor x \rfloor` | $\lfloor x \rfloor$ | 索引计算 |
| 单侧括号 | `\left\{ \begin{array}{l} x>0 \\ x<0 \end{array} \right.` | $\left\{ \begin{array}{l} x>0 \\ x<0 \end{array} \right.$ | 分段函数，右侧用 `.` 表示空 |

---

## 三、指数、对数与根式

| 表达 | LaTeX 代码 | 渲染效果 | 备注 |
|------|-----------|---------|------|
| 上标(指数) | `x^2` / `x^{n+1}` | $x^2$ / $x^{n+1}$ | 多字符指数**必须**用 `{}` 包裹 |
| 下标 | `x_0` / `T_{total}` | $x_0$ / $T_{total}$ | 多字符下标**必须**用 `{}` 包裹 |
| 上下标组合 | `x_i^2` / `T_{ij}^{k+1}` | $x_i^2$ / $T_{ij}^{k+1}$ | 顺序可互换 |
| 平方根 | `\sqrt{x}` | $\sqrt{x}$ | |
| n次根 | `\sqrt[n]{x}` | $\sqrt[n]{x}$ | |
| 自然对数 | `\ln(x)` | $\ln(x)$ | **推荐**：用 `\ln` 而非 `ln` |
| 常用对数 | `\log_{10}(x)` | $\log_{10}(x)$ | |
| 任意底对数 | `\log_a(x)` | $\log_a(x)$ | |
| 指数函数 | `e^x` / `\exp(x)` | $e^x$ / $\exp(x)$ | 复杂指数推荐用 `\exp` |
| 三角函数 | `\sin(x)`, `\cos(x)`, `\tan(x)` | $\sin(x)$, $\cos(x)$, $\tan(x)$ | 同理 `\arcsin`, `\sinh` 等 |

> [!WARNING] 函数名必须用反斜杠转义，否则会变成斜体变量乘积：
> - ❌ `sin(x)` → $sin(x)$ (错误：被解析为 $s \cdot i \cdot n \cdot x$)
> - ✅ `\sin(x)` → $\sin(x)$ (正确)

---

## 四、微积分核心符号

### 4.1 微分与偏微分

| 表达 | LaTeX 代码 | 渲染效果 | 应用场景 |
|------|-----------|---------|---------|
| 微分符号 | `\mathrm{d}x` | $\mathrm{d}x$ | **推荐**：用罗马体区分变量 |
| 一阶导数 | `\frac{\mathrm{d}f}{\mathrm{d}x}` | $\frac{\mathrm{d}f}{\mathrm{d}x}$ | 常微分 |
| 高阶导数 | `\frac{\mathrm{d}^2 f}{\mathrm{d}x^2}` | $\frac{\mathrm{d}^2 f}{\mathrm{d}x^2}$ | 二阶导 |
| 偏导数 | `\frac{\partial f}{\partial x}` | $\frac{\partial f}{\partial x}$ | 多变量函数、CFD控制方程 |
| 梯度 | `\nabla f` | $\nabla f$ | 标量场梯度 |
| 散度 | `\nabla \cdot \mathbf{u}` | $\nabla \cdot \mathbf{u}$ | 向量场散度 |
| 旋度 | `\nabla \times \mathbf{u}` | $\nabla \times \mathbf{u}$ | 向量场旋度 |
| 拉普拉斯算子 | `\nabla^2 f` 或 `\Delta f` | $\nabla^2 f$ / $\Delta f$ | 扩散项、泊松方程 |

### 4.2 积分

| 表达 | LaTeX 代码 | 渲染效果 | 说明 |
|------|-----------|---------|------|
| 不定积分 | `\int f(x) \, \mathrm{d}x` | $\int f(x) \, \mathrm{d}x$ | `\,` 添加小间距 |
| 定积分 | `\int_{a}^{b} f(x) \, \mathrm{d}x` | $\int_{a}^{b} f(x) \, \mathrm{d}x$ | 上下限用 `_` `^` |
| 二重积分 | `\iint_{D} f \, \mathrm{d}A` | $\iint_{D} f \, \mathrm{d}A$ | 面积分 |
| 三重积分 | `\iiint_{V} \rho \, \mathrm{d}V` | $\iiint_{V} \rho \, \mathrm{d}V$ | 体积分、守恒律积分形式 |
| 闭合曲线积分 | `\oint_{C} \mathbf{F} \cdot \mathrm{d}\mathbf{r}` | $\oint_{C} \mathbf{F} \cdot \mathrm{d}\mathbf{r}$ | 环量、斯托克斯定理 |
| 闭合曲面积分 | `\oiint_{S} \mathbf{u} \cdot \mathrm{d}\mathbf{S}` | $\oiint_{S} \mathbf{u} \cdot \mathrm{d}\mathbf{S}$ | 通量、高斯定理 |

---

## 五、求和、乘积、极限与集合

| 表达 | LaTeX 代码 | 渲染效果 |
|------|-----------|---------|
| 求和 | `\sum_{i=1}^{N} x_i` | $\sum_{i=1}^{N} x_i$ |
| 双重求和 | `\sum_{i=1}^{M} \sum_{j=1}^{N} a_{ij}` | $\sum_{i=1}^{M} \sum_{j=1}^{N} a_{ij}$ |
| 乘积 | `\prod_{k=1}^{n} x_k` | $\prod_{k=1}^{n} x_k$ |
| 极限 | `\lim_{x \to \infty} f(x)` | $\lim_{x \to \infty} f(x)$ |
| 趋近符号 | `x \to a` / `x \rightarrow a` | $x \to a$ / $x \rightarrow a$ |
| 属于 | `x \in \mathbb{R}` | $x \in \mathbb{R}$ |
| 集合 | `\{ x \mid x > 0 \}` | $\{ x \mid x > 0 \}$ |
| 实数集/复数集 | `\mathbb{R}` / `\mathbb{C}` | $\mathbb{R}$ / $\mathbb{C}$ | 需 AMS 数学包（Obsidian 默认支持） |

---

## 六、希腊字母速查 (气动/CFD 高频)

```latex
% 小写
\alpha  \beta  \gamma  \delta  \epsilon  \varepsilon  \zeta  \eta  \theta
\iota  \kappa  \lambda  \mu  \nu  \xi  \pi  \rho  \sigma  \tau  \upsilon
\phi  \varphi  \chi  \psi  \omega

% 大写
\Gamma  \Delta  \Theta  \Lambda  \Xi  \Pi  \Sigma  \Upsilon  \Phi  \Psi  \Omega
```

| 字母 | 代码 | 典型物理含义 |
|------|------|-------------|
| $\alpha$ | `\alpha` | 攻角、热扩散率 |
| $\beta$ | `\beta` | 侧滑角、体积膨胀系数 |
| $\gamma$ | `\gamma` | 比热比、涡量 |
| $\delta$ | `\delta` | 边界层厚度、变分符号 |
| $\epsilon$ | `\epsilon` | 湍流耗散率、小量 |
| $\eta$ | `\eta` | 效率、坐标变换系数 |
| $\theta$ | `\theta` | 温度、角度 |
| $\lambda$ | `\lambda` | 特征值、分子平均自由程 |
| $\mu$ | `\mu` | 动力粘度、摩擦系数 |
| $\nu$ | `\nu` | 运动粘度、频率 |
| $\rho$ | `\rho` | 密度 |
| $\sigma$ | `\sigma` | 应力、表面张力、标准差 |
| $\phi$ | `\phi` | 势函数、体积分数 |
| $\omega$ | `\omega` | 角速度、湍流比耗散率 |
| $\Omega$ | `\Omega` | 计算域、涡量向量 |

---

## 七、关系符号与逻辑符号

| 类型 | LaTeX 代码 | 渲染效果 |
|------|-----------|---------|
| 等于 | `=` | $=$ |
| 恒等于 | `\equiv` | $\equiv$ |
| 约等于 | `\approx` | $\approx$ |
| 不等于 | `\neq` | $\neq$ |
| 小于/大于 | `<` `>` 或 `\lt` `\gt` | $<$ $>$ |
| 小于等于 | `\leq` 或 `\le` | $\leq$ |
| 大于等于 | `\geq` 或 `\ge` | $\geq$ |
| 远小于/远大于 | `\ll` / `\gg` | $\ll$ / $\gg$ |
| 正比于 | `\propto` | $\propto$ |
| 等价/定义 | `\Leftrightarrow` / `:=` | $\Leftrightarrow$ / $:=$ |
| 蕴含 | `\Rightarrow` | $\Rightarrow$ |
| 且/或 | `\land` / `\lor` | $\land$ / $\lor$ |
| 非 | `\neg` | $\neg$ |
| 存在/任意 | `\exists` / `\forall` | $\exists$ / $\forall$ |

---

## 八、向量、矩阵与张量

### 8.1 向量表示

```latex
% 推荐：粗体表示向量/张量
\mathbf{u}      % 向量 u
\boldsymbol{\omega}  % 粗体希腊字母(涡量)

% 箭头表示(手写风格)
\vec{v}         % 带箭头向量

% 单位向量
\hat{i}, \hat{j}, \hat{k}  % 笛卡尔基向量
\mathbf{e}_x, \mathbf{e}_r, \mathbf{e}_\theta  % 曲线坐标基向量
```

| 表达 | LaTeX 代码 | 渲染效果 |
|------|-----------|---------|
| 向量 | `\mathbf{u}` | $\mathbf{u}$ |
| 向量点积 | `\mathbf{a} \cdot \mathbf{b}` | $\mathbf{a} \cdot \mathbf{b}$ |
| 向量叉积 | `\mathbf{a} \times \mathbf{b}` | $\mathbf{a} \times \mathbf{b}$ |
| 向量模长 | `\lVert \mathbf{v} \rVert` | $\lVert \mathbf{v} \rVert$ |
| 单位向量 | `\hat{\mathbf{n}}` | $\hat{\mathbf{n}}$ |

### 8.2 矩阵与张量

```latex
% 小矩阵 (行内)
$\begin{pmatrix} a & b \\ c & d \end{pmatrix}$

% 大矩阵 (块级)
$$
\mathbf{A} = \begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$

% 应力张量示例
$$
\boldsymbol{\sigma} = \begin{bmatrix}
\sigma_{xx} & \tau_{xy} & \tau_{xz} \\
\tau_{yx} & \sigma_{yy} & \tau_{yz} \\
\tau_{zx} & \tau_{zy} & \sigma_{zz}
\end{bmatrix}
$$
```

| 环境 | 括号样式 | 适用场景 |
|------|---------|---------|
| `pmatrix` | $(\cdots)$ | 一般矩阵、变换矩阵 |
| `bmatrix` | $[\cdots]$ | **推荐**：刚度矩阵、系数矩阵 |
| `vmatrix` | $\|\cdots\|$ | 行列式 |
| `Bmatrix` | $\{\cdots\}$ | 集合、分段定义 |

---

## 九、常用函数与特殊符号

```latex
% 三角/反三角
\sin  \cos  \tan  \cot  \sec  \csc
\arcsin  \arccos  \arctan

% 双曲函数
\sinh  \cosh  \tanh

% 极限相关
\max  \min  \sup  \inf  \arg\max

% 微分方程常用
\text{Re}  % 雷诺数 (用 \text 保持正体)
\text{Ma}  % 马赫数
\text{Pr}  % 普朗特数

% 其他
\infty  % 无穷大
\nabla  % 梯度算子
\partial  % 偏微分符号
\in  \ni  % 属于/包含
\subset  \subseteq  \supset  % 集合关系
```

> [!TIP] 无量纲数/缩写**必须用正体**：
> - ❌ `$Re = \frac{\rho U L}{\mu}$` → $Re = \frac{\rho U L}{\mu}$ (错误：像变量乘积)
> - ✅ `$\text{Re} = \frac{\rho U L}{\mu}$` → $\text{Re} = \frac{\rho U L}{\mu}$ (正确)
> - 或定义命令：`\newcommand{\Rey}{\text{Re}}` 后使用 `\Rey`

---

## 十、排版技巧与间距控制

| 需求 | LaTeX 代码 | 效果对比 |
|------|-----------|---------|
| 小间距 | `a \, b` | $a \, b$ (比 `ab` 略宽) |
| 中间距 | `a \: b` | $a \: b$ |
| 大间距 | `a \; b` | $a \; b$ |
|  quad 间距 | `a \quad b` | $a \quad b$ (≈1em) |
| 双 quad | `a \qquad b` | $a \qquad b$ (≈2em) |
| 强制换行(块级公式内) | `\\` | 在 `align` 等环境中使用 |
| 公式编号 | 块级公式末尾加 `\tag{1}` | 右侧显示 (1) |
| 多行对齐 | 使用 `align` 环境 (见下方示例) | |

### 多行公式对齐示例 (推导过程)

```latex
$$
\begin{align}
\frac{\partial (\rho \mathbf{u})}{\partial t} 
&= -\nabla \cdot (\rho \mathbf{u} \otimes \mathbf{u}) - \nabla p + \nabla \cdot \boldsymbol{\tau} + \rho \mathbf{f} \tag{动量方程} \\
\boldsymbol{\tau} 
&= \mu \left[ \nabla \mathbf{u} + (\nabla \mathbf{u})^T - \frac{2}{3} (\nabla \cdot \mathbf{u}) \mathbf{I} \right] \tag{牛顿流体本构}
\end{align}
$$
```

渲染效果：
$$
\begin{align}
\frac{\partial (\rho \mathbf{u})}{\partial t} 
&= -\nabla \cdot (\rho \mathbf{u} \otimes \mathbf{u}) - \nabla p + \nabla \cdot \boldsymbol{\tau} + \rho \mathbf{f} \tag{动量方程} \\
\boldsymbol{\tau} 
&= \mu \left[ \nabla \mathbf{u} + (\nabla \mathbf{u})^T - \frac{2}{3} (\nabla \cdot \mathbf{u}) \mathbf{I} \right] \tag{牛顿流体本构}
\end{align}
$$

> [!NOTE] `&` 指定对齐位置（通常在等号前），`\\` 换行，`\tag{}` 添加自定义标签

---

## 十一、综合实战模板 (可直接复用)

```markdown
## 公式推导：一维非定常可压缩欧拉方程

### 守恒形式

$$
\frac{\partial \mathbf{U}}{\partial t} + \frac{\partial \mathbf{F}}{\partial x} = 0
$$

其中守恒变量与通量向量定义为：

$$
\mathbf{U} = \begin{bmatrix} \rho \\ \rho u \\ \rho E \end{bmatrix}, \quad
\mathbf{F} = \begin{bmatrix} \rho u \\ \rho u^2 + p \\ u(\rho E + p) \end{bmatrix}
$$

### 状态方程

$$
p = (\gamma - 1) \left( \rho E - \frac{1}{2} \rho u^2 \right), \quad \gamma = \frac{c_p}{c_v}
$$

### 特征速度 (特征值)

$$
\lambda_1 = u - a, \quad \lambda_2 = u, \quad \lambda_3 = u + a
$$

其中声速 $a = \sqrt{\gamma p / \rho}$，马赫数定义为 $\text{Ma} = u / a$。

### 数值通量 (示例：Roe 平均)

$$
\mathbf{F}_{i+1/2} = \frac{1}{2} \left[ \mathbf{F}(\mathbf{U}_L) + \mathbf{F}(\mathbf{U}_R) - \lvert \mathbf{A}_{\text{Roe}} \rvert (\mathbf{U}_R - \mathbf{U}_L) \right]
$$
```

---

## 十二、快速复制区：常用代码片段

> [!COPY] 点击右侧复制按钮，粘贴到 Obsidian 即可使用

```latex
% ===== 基础模板 =====
$ $          % 行内公式占位
$$ $$        % 块级公式占位

% ===== 微积分 =====
\frac{\partial}{\partial t}     % 偏时间导
\frac{\mathrm{d}}{\mathrm{d}x}  % 全导数(正体 d)
\int_{\Omega} \cdot \, \mathrm{d}V  % 体积分
\oint_{\partial \Omega}         % 闭合积分

% ===== 向量运算 =====
\mathbf{u}                      % 粗体向量
\boldsymbol{\nabla}             % 粗体梯度算子
\mathbf{u} \cdot \mathbf{v}     % 点积
\mathbf{u} \times \mathbf{v}    % 叉积
\nabla \cdot \mathbf{u}         % 散度
\nabla \times \mathbf{u}        % 旋度

% ===== 矩阵/张量 =====
\begin{bmatrix} a & b \\ c & d \end{bmatrix}  % 2x2 矩阵
\otimes                         % 张量积/外积
\mathbf{I}                      % 单位张量

% ===== 无量纲数 =====
\text{Re} = \frac{\rho U L}{\mu}
\text{Ma} = \frac{U}{a}
\text{Pr} = \frac{\mu c_p}{k}

% ===== 多行对齐推导 =====
$$
\begin{align}
\text{第一行} &= \text{表达式 1} \\
             &= \text{表达式 2} \tag{标签}
\end{align}
$$
```

---

> [!SUCCESS] 使用建议
> 1. 将本文保存为 `LaTeX 速查.md`，放入 Obsidian 模板文件夹
> 2. 配合 **Templater** 或 **Quick Add** 插件，设置快捷键快速插入常用公式
> 3. 遇到新符号时，先查 [Detexify](https://detexify.kirelabs.org) (手绘识别 LaTeX)
> 4. 复杂公式建议先在 [Overleaf](https://www.overleaf.com) 测试，再复制到 Obsidian

如需针对特定领域（如湍流模型、气动弹性、轨道力学）的专用公式模板，可随时告诉我，我可为你定制。