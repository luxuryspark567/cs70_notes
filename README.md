---
description: https://ericzong.github.io/posts/markdown-formula.html
---

# GitBook公式

### 插入公式

插入的数学公式有两种：行内公式和独立公式。

```
$$行内公式$$
新增一行选项中选择新增一行公式
```

### 特殊符号

### 注释

行注释使用 `%` 开头，直到行结束都是注释内容，不会渲染显示。

换行（`\\`）应置于注释（`%`）之前。

$$
\begin{align}
line1 \\ % 这是注释，不会显示
line2
\end{align}
$$

```
$$
\begin{align}
line1 \\ % 这是注释，不会显示
line2
\end
```

### 括号

`()`、`[]`、`|` 都可以表示符号本身，但是 `{}` 有特殊含义，即将其内容当成一个整体看待。如果要表示花括号需要要转义，即使用 `\{\}` 表示。

更多括号符号详见【附录·括号】章节。

### 空格

公式中键入的普通空格会被忽略，如果真的需要显示间隔，可以使用 `\,`、`\;`、`\quad`、`\qquad`，它们将显示为从小到大的间隔。甚至可以使用 `\text{n个空格}` 实现任意空格间隔。

另外，`\!` 是一种负向间隔，它可以缩减字符间距（常用于物理单位中），重复使用可以叠加不同的字符。

符号汇总：`\!`、`\,`、`\;`、`\quad`、`\qquad`、`\text{n个空格}`

更多空格命令可参考 [MathJax 相关说明](https://docs.mathjax.org/en/latest/input/tex/extensions/textmacros.html#spacing-commands)。

### 省略号

普通公式中常见有两种省略号：与文本底线对齐的省略号用 `\ldots`，与文本中线对齐的省略号用 `\cdots`。

在矩阵中，省略号样式更为丰富，有水平（`\cdots`）、垂直（`\vdots`）甚至倾斜（`\ddots`）显示的。

### 位置相关

### 上下标

| 符号  | 作用 | 示例代码     | 示例显示    |
| --- | -- | -------- | ------- |
| `^` | 上标 | `$2^n$$` | $$2^n$$ |
| `_` | 下标 | `$A_0$`  | $$A_0$$ |

* 上下标不止一个字符

使用花括号将上下标整体括起来，如：$$T_n = 2T_{n-1} + 1 = 2(2^{n-1} - 1) + 1 = 2^n - 1$$

```
$$T_n = 2T_{n-1} + 1 = 2(2^{n-1} - 1) + 1 = 2^n - 1$$
```

* 左右都有上下标

使用 `\sideset` 命令，如：$$\sideset{^1_2}{^3_4}\bigotimes$$

```
$\sideset{^1_2}{^3_4}\bigotimes$
```

### 顶底部字符

想把一串字符放在另一串字符上方或下方，需要使用：`\overset{顶部内容}{常规内容}` 和 `\underset{底部内容}{常规内容}`。

### 分数

| 命令      | 格式                | 示例代码                      | 示例显示                      |
| ------- | ----------------- | ------------------------- | ------------------------- |
| `\frac` | `\frac {分子} {分母}` | `$\frac {a + 1} {b + 1}$` | $$\frac {a + 1} {b + 1}$$ |
| `\over` | `{分子} \over {分母}` | `$\frac {a - 1} {b - 1}$` | $$\frac {a - 1} {b - 1}$$ |

* 连分数

使用 `\cfrac` 命令：

$$
x = a_0 + \cfrac{1^2}{a_1 
		+ \cfrac{2^2}{a_2 
		+ \cfrac{3^2}{a_3 
		+ \cfrac{4^4}{a_4 
		+ \cdots}}}}
$$

```
$$
x = a_0 + \cfrac{1^2}{a_1 
		+ \cfrac{2^2}{a_2 
		+ \cfrac{3^2}{a_3 
		+ \cfrac{4^4}{a_4 
		+ \cdots}}}}
$$
```

注意：不要使用 `\frac` 或 `\over` 来创建连分数，否则会逐级缩小显示。

### 开方

开方语法为：`\sqrt [根指数，默认为2] {被开方数}`。

$$\sqrt {2} \quad and \quad \sqrt[n]{5}$$

```
$$ \sqrt {2} \quad and \quad \sqrt[n]{5}$$
```

### 累加/乘

| 命令    | 作用 | 格式                       |
| ----- | -- | ------------------------ |
| \sum  | 累加 | \sum\_{下标}^{上标} {累加表达式}  |
| \prod | 累乘 | \prod\_{下标}^{上标} {累乘表达式} |

$$S = \sum_{k = 0}^n {p^k} = 1 + p + p^2 + ... + p^n$$

```
$$S = \sum_{k = 0}^n {p^k} = 1 + p + p^2 + ... + p^n$$
```

$$S = \prod_{k=0}^{m} \frac {1 - p_k^{a_{k+1}}} {1-p_k}$$

```
$$S = \prod_{k=0}^{m} \frac {1 - p_k^{a_{k+1}}} {1-p_k}$$
```

### 极限

语法为：`\lim_{变量 \to 表达式} 表达式`。`\to` 可改为其他任意符号。

$$\lim_{n \to \infty} \frac{1}{n(n+1)}$$

```
$$\lim_{n \to \infty} \frac{1}{n(n+1)}$$
```

### 积分

语法为：`\int_积分下限^积分上限 {被积表达式}`。

更多积分符号见附录。

### 矢量

语法为：`\vec{矢量}`。也可以使用位于字符上方的箭头命令：`\overleftarrow` 和 `\overrightarrow`。

更多详见【附录·环绕符号】章节。

### 对齐

**默认居中对齐**

默认情况下，公式是居中对齐的。在多行公式中，居中对齐会显得参差不齐。

常见的场景是，期望“连等式”每行开头的等号对齐。这时需要使用 `\begin{align}` 和 `\end{align}` 包裹公式，并用 `&` 标识要对齐的位置。

$$
\begin{align}
L_n & = L_{n-1} + n  \\
    & = L_{n-2} + (n - 1) + n \\
    & = \cdots \\
    & = L_0 + 1 + 2 + \cdots + (n-1) + n \\
    & = 1 + { {n(n+1)} \over {2} } \\ 
    & = 1 + S_n
\end{align}
$$

```
$$
\begin{align}
L_n & = L_{n-1} + n  \\
    & = L_{n-2} + (n - 1) + n \\
    & = \cdots \\
    & = L_0 + 1 + 2 + \cdots + (n-1) + n \\
    & = 1 + { {n(n+1)} \over {2} } \\ 
    & = 1 + S_n
\end{align}
$$
```

> **禁止自动编号**\
> `{align}` 会自动编号，不需要可使用 `{align*}` 禁用。

**左对齐与右对齐**

要想公式左对齐或右对齐，就要用到 `{flalign}` 或 `{flalign*}` 了。它的效果是：首列左对齐，末列右对齐。

因此，要左对齐效果就把公式放在首列，要右对齐效果就把公式放在末列。

$$
\begin{flalign*}
& 多行左对齐文本1 & \\
& 多行左对齐文本2 & \\
& 多行左对齐文本3 &
\end{flalign*}
$$

```
$$
\begin{flalign*}
& 多行左对齐文本1 & \\
& 多行左对齐文本2 & \\
& 多行左对齐文本3 &
\end{flalign*}
$$
```

$$
\begin{flalign*}
& & 多行右对齐文本1 \\ % 注意首列是空的
& & 多行右对齐文本2 \\
& & 多行右对齐文本3
\end{flalign*}
$$

```
$$
\begin{flalign*}
& & 多行右对齐文本1 \\ % 注意首列是空的
& & 多行右对齐文本2 \\
& & 多行右对齐文本3
\end{flalign*}
$$
```

### 变换相关

### 大小

可以通过命令来调整字符的大小，MathJax 提供了从小到大共十种命令：

`\tiny`、`Tiny`、`\scriptsize`、`\small`、`\normalsize`、`\large`、`\Large`、`\LARGE`、`\huge`、`\Huge`。

更多说明详见 [MathJax 文档相关章节](https://docs.mathjax.org/en/latest/input/tex/extensions/textmacros.html#size-control)。

### 字体

更改字体语法为：`\字体 {被转换字符}`。（更多详见【附录·字体转换】章节）

公式中“不可识别”的运算符号或普通文本均是以斜体显示的，如果想让其转换为常规字体显示，需要分别使用 `\operatorname` 和 `\text` 命令。

`\operatorname` 用以定义一个新的运算符号，其语法为：`\operatorname{运算符}{表达式}` 或 `\operatorname*{运算符}_{下标}^{上标}{表达式}`。

`\text` 用以定义普通文本，通常是注释，其语法为：`\text {文本}`。

### 颜色

更改字符颜色语法为：`\color{颜色}{字符}`。

注意：文字颜色需要浏览器支持，否则将显示为黑色。对于较老的浏览器可能只支持有限的颜色名称，较新的浏览器支持 RGB 颜色。

### 高亮

语法：`\bbox[背景色,边距*,border:width* type color`。

* 背景色：可以使用上节所述的颜色。
* 边距：可使用绝对像素 px 或相对大小 em。
* 边框宽度：同“边距”类似。
* 边框类型：可用 solid、dotted、dashed 等。（与 CSS 中 border-style 值对应）
* 边框颜色：与“背景色”类似。

$$
\bbox[yellow, 5px, border:2px solid #ff0000]{
    e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)
}
$$

```
$$
\bbox[yellow, 5px, border:2px solid #ff0000]{
    e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)
}
$$
```

### 删除线

可使用 `\cancel`、`\bcancel`、`\xcancel`、`\cancelto` 等命令添加删除效果。（更多详见【附录·删除线】章节）

### 括号

普通的各种括号通常只显示为一行的大小，如果要显示为多行的括号，需要使用 `\left` 和 `\right` 命令——这使得括号会随内部公式大小调整大小高度。

`\left` 和 `\right` 必须配对使用，如果只想显示一半的括号，可以使用 `\left.` 或 `\right.` 来配对，但不显示。

需要注意的是，配对范围被限制在“公式行”中，如果一对括号被换行（`\\`）分隔在不同的行，那括号所在行需要使用 `\left.` 或 `\right.` 来“虚假配对”。

$$
\begin{align*} 
S = & \left[ 1 + 2 + 3 + \cdots \right. \\ 
	& \cdots + \left. (n-2) + (n-1) + n \right]
\end{align*}
$$

```
$$
\begin{align*} 
S = & \left[ 1 + 2 + 3 + \cdots \right. \\ 
	& \cdots + \left. (n-2) + (n-1) + n \right]
\end{align*}
$$
```

更多括号符号详见【附录·括号】章节。

### 行标

公式末尾前使用 `\tag {行标}` 注明行标。

> 注：不要尝试给连分数“每行”标注行标，因为整体上看，连分数只有一行。

使用如下语法可以实现自动编号：

```
\begin{equation}
    表达式
    \label{eq:公式名}
\end{equation}
```

自动编号的公式，可以在全文任意位置使用 `\eqref{eq:公式名}` 引用自动编号的公式。

> 注意：
>
> 1. 仍可以使用 `\tag` 手动编号；
> 2. 自动编号是个带圆括号的数字，引用显示的也是该“带圆括号的数字”。通常显示为超链接，指向引用的公式标注行；
> 3. 从经验看，一些 Markdown 编辑器不完全支持自动编号，可能会存在一些显示问题。但在 hexo 中通过 MathJax 渲染的公式通常是支持自动编号语法的。

如果想不自动编号可以：

```
\begin{equation*}
    表达式
\end{equation*}
```

如果对公式的对齐方式有要求，则需要使用：

```
\begin{align}
    表达式
\end{align}
```

该语句是自动编号的，不想自动编号类似地可使用：

```
\begin{align*}
    表达式
\end{align*}
```

如果只是有些行不需要编号，可以使用 `\nonumber` 或 `\notag` 移除当前行的行标。

另注意，自动编号是“全局”的，针对页面所有公式而言的。

### 复杂公式

### 矩阵

矩阵以 `\begin{matrix}` 开始 `\end{matrix}` 结束，以 `\\` 分行，以 `&` 分隔元素。

$$
\begin{matrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{matrix}
$$

```
$$
\begin{matrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{matrix}
$$
```

**矩阵边框**

默认矩阵没有边框，要显示不同的边框，可以为 `matrix` 添加不同的前缀：

| matrix                                          | pmatrix                                           | bmatrix                                           | Bmatrix                                           | vmatrix                                           | Vmatrix                                           |
| ----------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| $$\begin{matrix} 1 & 2 \ 3 & 4 \ \end{matrix}$$ | $$\begin{pmatrix} 1 & 2 \ 3 & 4 \ \end{pmatrix}$$ | $$\begin{bmatrix} 1 & 2 \ 3 & 4 \ \end{bmatrix}$$ | $$\begin{Bmatrix} 1 & 2 \ 3 & 4 \ \end{Bmatrix}$$ | $$\begin{vmatrix} 1 & 2 \ 3 & 4 \ \end{vmatrix}$$ | $$\begin{Vmatrix} 1 & 2 \ 3 & 4 \ \end{Vmatrix}$$ |

**省略号**

矩阵中常用的省略号有水平（`\cdots`）、垂直（`\vdots`）以及倾斜（`\ddots`）等几种。

**行内矩阵**

如果矩阵行列足够少，就有可能显示在行中，此时使用 `\begin{smallmatrix}` 和 `\end{smallmatrix}` 界定。

### 条件表达式

条件表达式以 `\begin{cases}` 开始 `\end{cases}` 结束，插入 `&` 来对齐内容，每行以 `\\` 结束换行。

$$
L_n = 
  \begin{cases}
    1 & (n = 0) \\[2ex]
    L_{n-1} + n & ( n > 0 )
  \end{cases}
$$

```
$$
L_n = 
  \begin{cases}
    1 & (n = 0) \\[2ex]
    L_{n-1} + n & ( n > 0 )
  \end{cases}
$$
```

**行高配置**

默认情况下，条件表达式每行均显示为单倍行高，通常会显得比较紧凑，甚至有些较高的公式显示会存在问题。

此时，可以在换行符（`\\`）后指定行高。如上例中指定了 `[2ex]`，当然可以视需要指定任意数量的 `[ex]`。

> **关于单位 `ex`**\
> `ex` 是一个相对的尺寸单位，指“x-height”，即字母 x 的高度。\
> 注：在 CSS 中，字母 x 的下边缘即基线（baseline）所在的位置。

**数组表示条件表达式**

条件表达式除了使用 `{cases}` 外，也可以使用左对齐数组（`{array}`）来表示：

$$
L_n = 
\left\{
  \begin{array}{l}
    1 & (n = 0)\\[2ex]
    L_{n-1} + n & ( n > 0 )
  \end{array}
\right.
$$

```
$$
L_n = 
\left\{
  \begin{array}{l}
    1 & (n = 0)\\[2ex]
    L_{n-1} + n & ( n > 0 )
  \end{array}
\right.
$$
```

> **数组表示条件表达式的优点**\
> 概念上说，条件表达式对应的应该是 `{cases}`，但 `{array}` 可以实现相同的效果，并且更为灵活，可以实现“右括号”显示的条件表达式效果。

### 数组与表格

数组以表格形式展示，使用 `\begin{array}` 开始 `\end{array}` 结束。

`\begin{array}` 后紧跟花括号定义列及其文本对齐方式，可选对齐方式有居中（`c`）、左对齐（`l`）、右对齐（`r`）。一个有四列的表格可能这样开头：`\begin{array}{lcrc}`。

默认表格没有分割线。垂直分割线，在定义式中插入 `|`，如：`{l|crc}`。水平分割线在行间插入 `\hline`。

行以 `\\` 结尾换行，列以 `&` 分隔。

$$
\begin{array}{c|lcr}
	\hline
	 No. & \text{左对齐} & \text{居中对齐} & \text{右对齐} \\
    \hline
	 1 & \text{test one} & 121 & 100 \\
	 2 & \text{test two} & 12321 & 2 \\
	 3 & \text{test three} & 1 & 42 \\
\end{array}
$$

```
$$
\begin{array}{c|lcr}
	\hline
	 No. & \text{左对齐} & \text{居中对齐} & \text{右对齐} \\
    \hline
	 1 & \text{test one} & 121 & 100 \\
	 2 & \text{test two} & 12321 & 2 \\
	 3 & \text{test three} & 1 & 42 \\
\end{array}
$$
```

> **补充说明**\
> 数组也可以用于展示条件表达式或者方程组，这可以参考上一章节【条件表达式】。\
> 以数组展示表格，比“普通”的 Markdown 表格更灵活，可以实现嵌套和单元格合并效果。

### 交换图表

开头使用 `\require{AMScd}` 来启用交换图表。

> 部分 Markdown 编辑器不需要，但为了兼容性，建议加上。

以 `\begin{CD}` 开头 `\end{CD}` 结束。

每行以 `\\` 结尾换行，元素以 `&` 分隔。

连线箭头如下显示：

| 符号     | 说明      | 符号     | 说明    |
| ------ | ------- | ------ | ----- |
| `@<<<` | 左箭头     | `@>>>` | 右箭头   |
| `@AAA` | 上箭头     | `@VVV` | 下箭头   |
| `@=`   | 水平双实线   | `@\|`  | 垂直双实线 |
| `@.`   | 无箭头（占位） |        |       |

箭头符号可以添加注释文字。上表可以看到，代表箭头的符号都有 3 个相同的字符，在这些字符间插入的文字会作为箭头上的注释显示。注意，在第一、二个或第二、三个相同字符间插入文字，其显示的方位不同。

$$
\require{AMScd}
\begin{CD}
    A @. B \\
    @VbVV \# @VVcV \\
    C @>>d> D \\
\end{CD}
$$

```
$$
\require{AMScd}
\begin{CD}
    A @. B \\
    @VbVV \# @VVcV \\
    C @>>d> D \\
\end{CD}
$$
```

### 附录

### 希腊字母

| 命令         | 显示           | 命令        | 显示          | 命令         | 显示           | 命令         | 显示           |
| ---------- | ------------ | --------- | ----------- | ---------- | ------------ | ---------- | ------------ |
| `\alpha`   | $$\alpha$$   | A         | $$A$$       | `\beta`    | $$\beta$$    | B          | $$B$$        |
| `\gamma`   | $$\gamma$$   | `\Gamma`  | $$\Gamma$$  | `\delta`   | $$\delta$$   | `\Delta`   | $$\Delta$$   |
| `\epsilon` | $$\epsilon$$ | E         | $$E$$       | `\zeta`    | $$\zeta$$    | Z          | $$Z$$        |
| `\eta`     | $$\eta$$     | H         | $$H$$       | `\theta`   | $$\theta$$   | `\Theta`   | $$\Theta$$   |
| `\iota`    | $\iota$      | I         | $I$         | `\kappa`   | $$\kappa$$   | K          | $$K$$        |
| `\lambda`  | $$\lambda$$  | `\Lambda` | $$\Lambda$$ | `\mu`      | $$\mu$$      | M          | $$M$$        |
| `\nu`      | $$\nu$$      | N         | $$N$$       | `\xi`      | $$\xi$$      | `\Xi`      | $$\Xi$$      |
| o          | $$o$$        | O         | $$O$$       | `\pi`      | $$\pi$$      | `\Pi`      | $$\Pi$$      |
| `\rho`     | $$\rho$$     | P         | $$P$$       | `\sigma`   | $$\sigma$$   | `\Sigma`   | $$\Sigma$$   |
| `\tau`     | $$\tau$$     | T         | $$T$$       | `\upsilon` | $$\upsilon$$ | `\Upsilon` | $$\Upsilon$$ |
| `\phi`     | $$\phi$$     | `\Phi`    | $$\Phi$$    | `\chi`     | $$\chi$$     | X          | $$X$$        |
| `\psi`     | $$\psi$$     | `\Psi`    | $$\Psi$$    | `\omega`   | $$\omega$$   | `\Omega`   | $$\Omega$$   |

部分字母加 `var` 前缀转变为变量专用形式：

| 小写         | 大写       | 变量            | 显示                                |
| ---------- | -------- | ------------- | --------------------------------- |
| `\epsilon` | `E`      | `\varepsilon` | $$\epsilon \; E \; \varepsilon$$  |
| `\theta`   | `\Theta` | `\vartheta`   | $$\theta \; \Theta \; \vartheta$$ |
| `\rho`     | `P`      | `\varrho`     | $$\rho \; P \; \varrho$$          |
| `\sigma`   | `\Sigma` | `\varsigma`   | $$\sigma \; \Sigma \; \varsigma$$ |
| `\phi`     | `\Phi`   | `\varphi`     | $$\phi \; \Phi \; \varphi$$       |

### 关系运算符

| 命令      | 显示        | 命令       | 显示         | 命令        | 显示          | 命令       | 显示         |
| ------- | --------- | -------- | ---------- | --------- | ----------- | -------- | ---------- |
| `\pm`   | $$\pm$$   | `\times` | $$\times$$ | `\div`    | $$\div$$    | `\mid`   | $$\mid$$   |
| `\cdot` | $$\cdot$$ | `\ast`   | $$\ast$$   | `\oplus`  | $$\oplus$$  | `\leq`   | $$\leq$$   |
| `\geq`  | $$\geq$$  | `\neq`   | $$\neq$$   | `\approx` | $$\approx$$ | `\equiv` | $$\equiv$$ |

### 集合运算符

| 命令          | 显示            | 命令          | 显示            | 命令          | 显示            | 命令        | 显示          |
| ----------- | ------------- | ----------- | ------------- | ----------- | ------------- | --------- | ----------- |
| `\emptyset` | $$\emptyset$$ | `\in`       | $$\in$$       | `\notin`    | $$\notin$$    | `\subset` | $$\subset$$ |
| `\supset`   | $$\supset$$   | `\subseteq` | $$\subseteq$$ | `\supseteq` | $$\supseteq$$ | `\cap`    | $$\cap$$    |
| `\cup`      | $$\cup$$      |             |               |             |               |           |             |

### 对数运算符

| 命令     | 显示       | 命令    | 显示      | 命令    | 显示      |
| ------ | -------- | ----- | ------- | ----- | ------- |
| `\log` | $$\log$$ | `\lg` | $$\lg$$ | `\ln` | $$\ln$$ |

### 三角运算符

| 命令         | 显示           | 命令     | 显示       | 命令     | 显示       |   |   |
| ---------- | ------------ | ------ | -------- | ------ | -------- | - | - |
| `\angle A` | $$\angle A$$ | `\sin` | $$\sin$$ | `\cos` | $$\cos$$ |   |   |
| `\tan`     | $$\tan$$     | `\cot` | $$\cot$$ |        |          |   |   |

### 逻辑运算符

<table><thead><tr><th width="119.83984375">命令</th><th width="54.6796875">显示</th><th width="135.046875">命令</th><th width="57.42578125">显示</th><th width="105.234375">命令</th><th width="69.28125">显示</th><th width="106.3359375">命令</th><th width="58.16796875">显示</th></tr></thead><tbody><tr><td><code>\because</code></td><td><span class="math">\because</span></td><td><code>\therefore</code></td><td><span class="math">\therefore</span></td><td><code>\forall</code></td><td><span class="math">\forall</span></td><td><code>\exists</code></td><td><span class="math">\exists</span></td></tr><tr><td><code>\lnot</code> 或 <code>\neg</code></td><td><span class="math">\neg</span></td><td><code>\land</code></td><td><span class="math">\land</span></td><td><code>\lor</code></td><td><span class="math">\lor</span></td><td></td><td></td></tr></tbody></table>

### 箭头符号

| 命令                    | 显示                      | 命令                    | 显示                      |
| --------------------- | ----------------------- | --------------------- | ----------------------- |
| `\to`                 | $$\to$$                 | `\implies`            | $$\implies$$            |
| `\iff`                | $$\iff$$                | `\impliedby`          | $$\impliedby$$          |
| `\uparrow`            | $$\uparrow$$            | `\Uparrow`            | $$\Uparrow$$            |
| `\downarrow`          | $$\downarrow$$          | `\Downarrow`          | $$\Downarrow$$          |
| `\leftarrow`          | $$\leftarrow$$          | `\Leftarrow`          | $$\Leftarrow$$          |
| `\rightarrow`         | $$\rightarrow$$         | `\Rightarrow`         | $$\Rightarrow$$         |
| `\leftrightarrow`     | $$\leftrightarrow$$     | `\Leftrightarrow`     | $$\Leftrightarrow$$     |
| `\longleftarrow`      | $$\longleftarrow$$      | `\Longleftarrow`      | $$\Longleftarrow$$      |
| `\longrightarrow`     | $$\longrightarrow$$     | `\Longrightarrow`     | $$\Longrightarrow$$     |
| `\longleftrightarrow` | $$\longleftrightarrow$$ | `\Longleftrightarrow` | $$\Longleftrightarrow$$ |

### 括号

| 命令        | 显示          | 命令        | 显示          |
| --------- | ----------- | --------- | ----------- |
| `\langle` | $$\langle$$ | `\rangle` | $$\rangle$$ |
| `\lceil`  | $$\lceil$$  | `\rceil`  | $$\rceil$$  |
| `\lfloor` | $$\lfloor$$ | `\rfloor` | $$\rfloor$$ |
| `\lbrace` | $$\lbrace$$ | `\rbrace` | $$\rbrace$$ |
| `\lvert`  | $$\lvert$$  | `\rvert`  | $$\rvert$$  |
| `\lVert`  | $$\lVert$$  | `\rVert`  | $$\rVert$$  |

### 微积分运算符

| 命令       | 显示         | 命令       | 显示         | 命令       | 显示         |
| -------- | ---------- | -------- | ---------- | -------- | ---------- |
| `\int`   | $$\int$$   | `\iint`  | $$\iint$$  | `\prime` | $$\prime$$ |
| `\infty` | $$\infty$$ | `\nabla` | $$\nabla$$ |          |            |

### 环绕符号

| 命令                     | 示例代码                        | 示例显示                          |
| ---------------------- | --------------------------- | ----------------------------- |
| `\overleftarrow`       | `\overleftarrow{a+b}`       | $$\overleftarrow{a+b}$$       |
| `\overrightarrow`      | `\overrightarrow{a+b}`      | $$\overrightarrow{a+b}$$      |
| `\overleftrightarrow`  | `\overleftrightarrow{a+b}`  | $$\overleftrightarrow{a+b}$$  |
| `\underleftarrow`      | `\underleftarrow{a+b}`      | $$\underleftarrow{a+b}$$      |
| `\underrightarrow`     | `\underrightarrow{a+b}`     | $$\underrightarrow{a+b}$$     |
| `\underleftrightarrow` | `\underleftrightarrow{a+b}` | $$\underleftrightarrow{a+b}$$ |
| `\overline`            | `\overline{a+b}`            | $$\overline{a+b}$$            |
| `\underline`           | `\underline{a+b}`           | $$\underline{a+b}$$           |
| `\overbrace`           | `\overbrace{a+b}^{sample}`  | $$\overbrace{a+b}^{sample}$$  |
| `\underbrace`          | `\underbrace{a+b}_{sample}` | $$\underbrace{a+b}_{sample}$$ |
| `\fbox`                | `\fbox{a+b}`                | $$\fbox{a+b}$$                |
| `\bar`                 | `\bar{a}`                   | $$\bar{a}$$                   |
| `\acute`               | `\acute{a}`                 | $$\acute{a}$$                 |
| `\breve`               | `\breve{a}`                 | $$\breve{a}$$                 |
| `\check`               | `\check{a}`                 | $$\check{a}$$                 |
| `\grave`               | `\grave{a}`                 | $$\grave{a}$$                 |
| `\dot`                 | `0.\dot{9}`                 | $$0.\dot{9}$$                 |

### 字体转换

| 输入   | 说明   | 显示               |
| ---- | ---- | ---------------- |
| \rm  | 罗马体  | $$\rm{SAMPLE}$$  |
| \it  | 意大利体 | $$\it{SAMPLE}$$  |
| \mit | 数学斜体 | \$$\mit{SAMPLE}$ |
| \bf  | 粗体   | $$\bf{SAMPLE}$$  |
| \sf  | 等线体  | $$\sf{SAMPLE}$$  |
| \tt  | 打字机体 | $$\tt{SAMPLE}$$  |

### 浏览器支持的颜色名

| 颜色名    | 显示                       | 颜色名     | 显示                        |
| ------ | ------------------------ | ------- | ------------------------- |
| black  | $$\color{black}{text}$$  | grey    | $$\color{grey}{text}$$    |
| silver | $$\color{sliver}{text}$$ | white   | $$\color{white}{text}$$   |
| maroon | $$\color{maroon}{text}$$ | red     | $$\color{red}{text}$$     |
| yellow | $$\color{yellow}{text}$$ | lime    | $$\color{lime}{text}$$    |
| olive  | $$\color{olive}{text}$$  | green   | $$\color{green}{text}$$   |
| teal   | $$\color{teal}{text}$$   | auqa    | $$\color{auqa}{text}$$    |
| blue   | $$\color{blue}{text}$$   | navy    | $$\color{navy}{text}$$    |
| purple | $$\color{purple}{text}$$ | fuchsia | $$\color{fuchsia}{text}$$ |

### 删除线

| 命令                             | 示例代码                                 | 示例显示                                   |
| ------------------------------ | ------------------------------------ | -------------------------------------- |
| `\cancel`                      | `\cancel{a+b}`                       | $$\cancel{a+b}$$                       |
| `\bcancel`                     | `\bcancel{a+b}`                      | $$\bcancel{a+b}$$                      |
| `\xcancel`                     | `a+\xcancel{b}`                      | $$a+\xcancel{b}$$                      |
| `\cancelto`                    | `a+\cancelto{c}{b}`                  | \$$a+\cancelto{c}{b}$                  |
| `\enclose{horizontalstrike}`   | `\enclose{horizontalstrike}{a+b}`    | \$$\enclose{horizontalstrike}{a+b}$    |
| `\enclose{verticalstrike}`     | `\enclose{verticalstrike}{\frac ab}` | \$$\enclose{verticalstrike}{\frac ab}$ |
| `\enclose{updiagonalstrike}`   | `\enclose{updiagonalstrike}{a+b}`    | \$$\enclose{updiagonalstrike}{a+b}$    |
| `\enclose{downdiagonalstrike}` | `\enclose{downdiagonalstrike}{a+b}`  | \$$\enclose{downdiagonalstrike}{a+b}$  |

注意：对于 `\enclose` 命令，可以组合使用删除线，比如：`\enclose{horizontalstrike,updiagonalstrike}`。

### 参考

[MathJax basic tutorial and quick reference](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)：基础教程（英文版），绝大部分命令都有介绍。

[LaTeX/Advanced Mathematics](https://en.wikibooks.org/wiki/LaTeX/Advanced_Mathematics#align_and_align*)：维基百科（英文版）关于 LaTex 高等数学公式的说明。

[Detexify](http://detexify.kirelabs.org/classify.html)：一个搜索查询 LaTeX 符号的在线工具。可以通过鼠标书写来检索符号（使用 AI 识别，当然也可以浏览所有符号）。

[完整 LaTeX 可用符号列表](https://mirror.its.dal.ca/ctan/info/symbols/comprehensive/symbols-a4.pdf)：超多，不便于查询。

[精简 LaTeX 可用符号列表](https://pic.plover.com/MISC/symbols.pdf)：大部分常用符号可查询。

[MathJax 文档·TeX/LaTeX扩展列表](https://docs.mathjax.org/en/latest/input/tex/extensions/index.html)：所有支持的命令列表。
