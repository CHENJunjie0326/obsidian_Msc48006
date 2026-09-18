---

### 一、 基础公式语法

在 Obsidian 中，必须先在 `设置 -> 编辑器` 中开启 **“数学公式渲染”**。

|类型|Markdown 语法|说明|
|:--|:--|:--|
|**行内公式**|`$E = mc^2$`|嵌入在文字段落中，不独占一行。|
|**块级公式**|`$$ \int_a^b f(x)dx $$`|独占一行，居中显示，适合复杂公式。|
|**带编号公式**|`$$ F = ma \tag{1} $$`|使用 `\tag{}` 手动给公式添加右侧编号。|

---

### 二、 核心推导环境（必会）

数学和物理笔记的核心是**推导过程**。千万不要用多个 `$$` 换行写推导，一定要用 `aligned` 环境。

#### 1. 多行等号对齐推导

使用 `&` 作为对齐锚点（通常放在 `=` 前面），`\\` 用于换行。

```latex
$$
\begin{aligned}
\mathcal{L} &= T - V \\
            &= \frac{1}{2}m\dot{x}^2 - \frac{1}{2}kx^2 \\
            &= \frac{1}{2}m\left(\frac{dx}{dt}\right)^2 - \frac{1}{2}kx^2
\end{aligned}
$$
```

#### 2. 带文字说明的推导

在推导中插入物理意义或假设条件。

```latex
$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\epsilon_0} & \text{(高斯定律)} \\
\oint \mathbf{E} \cdot d\mathbf{A} &= \frac{Q_{\text{enc}}}{\epsilon_0} & \text{(积分形式)}
\end{aligned}
$$
```

#### 3. 分段函数 / 条件方程

使用 `cases` 环境（默认左大括号）。

```latex
$$
V(x) = \begin{cases}
0 & |x| < a \\
\infty & |x| \ge a
\end{cases}
$$
```

---

### 三、 数学 & 物理高频符号速查表

#### 1. 微积分与算子

|符号|LaTeX 代码|物理/数学场景|
|:--|:--|:--|
||`\partial`||
||`\nabla`|梯度/散度/旋度 (Nabla算子)|
||`\square` 或 `\Box`|达朗贝尔算子 (相对论/波动)|
||`\oint`|环路积分|
||`\iint`|二重积分 (三重 `\iiint`)|
||`\lim_{x \to 0}`|极限 (加 `limits` 强制下标在正下方)|

#### 2. 矢量、张量与矩阵

|符号|LaTeX 代码|说明|
|:--|:--|:--|
||`\vec{v}`|简单矢量箭头|
||`\boldsymbol{\sigma}`|**粗体希腊字母** (如泡利矩阵)|
||`\mathbf{F}`|粗体英文字母 (表示矢量/张量)|
||`\hat{n}`|单位矢量 / 量子力学算符|
||`\dot{x}`, `\ddot{x}`|时间一阶/二阶导数|

**矩阵排版：**

```latex
$$
\sigma_z = \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
$$
```

_(注：`pmatrix` 圆括号, `bmatrix` 方括号, `vmatrix` 行列式竖线)_

#### 3. 量子力学专用 (Dirac 符号)

MathJax 原生不支持 `\bra` 和 `\ket`，请使用以下标准写法：

|符号|LaTeX 代码|说明|
|:--|:--|:--|
|$|\psi \rangle$|`\| \psi \rangle`|
|$\langle \phi|$|`\langle \phi \|`|
|$\langle \phi|\psi \rangle$|`\langle \phi \| \psi \rangle`|
||`\langle \hat{A} \rangle`|期望值|

#### 4. 常用数学集合与特殊字体

|符号|LaTeX 代码|用途|
|:--|:--|:--|
||`\mathbb{R}`|实数集 (Q, C, Z 同理)|
||`\mathcal{H}`|哈密顿量 / 希尔伯特空间|
||`\mathcal{L}`|拉格朗日量|
||`\mathfrak{g}`|李代数 (哥特字体)|

---

### 四、 排版美化与 Obsidian 特色技巧

#### 1. 结合 Obsidian Callouts 写“定理/定义”

Obsidian 原生支持 Callouts（警示框），结合 LaTeX 非常适合写定理和推论。

```markdown
> [!theorem] 薛定谔方程
> 量子系统的态矢量随时间演化满足：
> $$ i\hbar \frac{\partial}{\partial t} |\psi(t)\rangle = \hat{H} |\psi(t)\rangle $$
```

#### 2. 公式着色与高亮

使用 `\color{颜色}{公式}` 或 `\textcolor{颜色}{公式}` 标记重点。

```latex
$$
F = \color{red}{G} \frac{m_1 m_2}{r^2}
$$
```

#### 3. 调整间距（防拥挤）

LaTeX 默认公式间距有时太紧凑，物理公式中微分符号 `d` 前通常需要加小空格 `\,`。

```latex
% 推荐写法（微分号前有小空格，且 d 是正体）
$$ \int f(x) \, \mathrm{d}x $$
```

_空格指令：`\,` (小), `\:` (中), `\;` (大), `\quad` (超大)_

---

### 五、 🚀 终极效率：自定义宏 (Macros)

每次输入 `\mathbb{R}` 或 `\mathrm{d}` 太繁琐。你可以在单篇笔记的**最顶部**定义宏，或者在 Obsidian 设置中全局配置。

**在笔记开头添加以下代码（在阅读模式下不可见，但全局生效）：**

```latex
$$
\newcommand{\dd}{\mathrm{d}}       % 正体微分号
\newcommand{\R}{\mathbb{R}}        % 实数集
\newcommand{\C}{\mathbb{C}}        % 复数集
\newcommand{\bra}[1]{\langle #1 |} % 左矢
\newcommand{\ket}[1]{| #1 \rangle} % 右矢
\newcommand{\braket}[2]{\langle #1 | #2 \rangle} % 内积
\newcommand{\avg}[1]{\langle #1 \rangle}         % 期望值
$$
```

**配置后，你的输入将极其简洁：**

---