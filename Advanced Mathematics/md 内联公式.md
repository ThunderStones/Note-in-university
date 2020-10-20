# 1. 偏好设置

首先设置选项：文件 > 偏好设置 > 将下面的选项打钩

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191113124032761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2l0aGFubWFuZw==,size_16,color_FFFFFF,t_70)

# 2. 添加公式

## 1. 行内公式

```shell
$ (需要输入的公式) $
1
```

**语法**：`$ x_2 $`

**效果**：$ x_2$

## 2. 单行公式

```shell
$$
(需要输入的公式)
$$
```

**语法**：

```shell
$$
x_2
$$
```

**效果**：
$x_2$

# 3. 常用算式

## 1. 分式

语法：`$\frac{a}{b}$`，效果：$\frac{a}{b}$

## 2. 根式

语法：`$\sqrt[n]{x}$`，效果：$\sqrt[n]{x}$

## 3. 上角标

语法：`$x^2$`，效果：x 2 x^2*x*2
**多个上角标**
语法：`$x^{2n}$`，效果：x 2 n x^{2n}*x*2*n*

## 4. 下角标

语法：`$x_2$`，效果：$x_2$
**多个下角标**
语法：`$x_{2n}$`，效果：$x_{2n}$

## 5. 向量

语法：`$\vec{A}\cdot\vec{B} = 0$`，效果：$\vec{A}\cdot\vec{B} = 0$

## 6. 均值

语法：`$\overline{x}$`，效果： $\overline{X}$

语法：`$\over{x}$`，效果：$\over{x}$

## 7. 极限

语法：`$ \lim_{n\to + \infty}$ n$`，效果：
$$
\lim_{n\to + \infty}
$$


## 8. 积分

语法：`$ \int_0^n f(x)dx $`，效果：$ \int_0^n f(x)dx$

## 9. 累加

语法：`$ \sum_{i=1}^n a_i $`，效果：$\sum_{i=1}^n a_i$

## 10. 累乘

语法：`$ \prod_{i=1}^n x_i $`，效果：$\prod_{i=1}^n x_i$

# 4. 矩阵

## 1. 简单矩阵

语法：

```shell
$$
\begin{matrix}
1 & 2 & 3\\
4 & 5 & 6\\
7 & 8 & 9\\
\end{matrix}
$$
```

效果：
$$
\begin{matrix}
1 & 2 & 3\\
4 & 5 & 6\\
7 & 8 & 9\\
\end{matrix}
$$


## 2. 带大括号

语法：

```shell
$$
 \left\{
 \begin{matrix}
   1 & 2 & 3 \\
   4 & 5 & 6 \\
   7 & 8 & 9
  \end{matrix}
  \right\} \tag{1}
$$

```

效果：
$$
\left\{
 \begin{matrix}
   1 & 2 & 3 \\
   4 & 5 & 6 \\
   7 & 8 & 9
  \end{matrix}
  \right\} \tag{1}
$$

## 3. 带中括号

语法：

```shell
$$
\left[
 \begin{matrix}
   1 & 2 & 3 \\
   4 & 5 & 6 \\
   7 & 8 & 9
  \end{matrix}
  \right] \tag{2}
$$

```

$$
\left[
 \begin{matrix}
   1 & 2 & 3 \\
   4 & 5 & 6 \\
   7 & 8 & 9
  \end{matrix}
  \right] \tag{2}
$$

## 4. 带参数

比如写增广矩阵，可能需要最右边一列单独考虑。可以用`array`命令来处理：

```shell
$$ 
\left[
    \begin{array}{cc|c}
      1 & 2 & 3 \\
      4 & 5 & 6 \\
      7 & 8 & 9
    \end{array}
\right] \tag{3}
$$
```

效果：
$$
\left[
    \begin{array}{cc|c}
      1 & 2 & 3 \\
      4 & 5 & 6 \\
      7 & 8 & 9
    \end{array}
\right] \tag{3}
$$

## 5. 行间矩阵

使用`\bigl(\begin{smallmatrix} ... \end{smallmatrix}\bigr)`，

语法：`使用矩阵 $\bigl( \begin{smallmatrix} a & b \\ c & d \end{smallmatrix} \bigr)$ 作为因子矩阵`

效果： $\bigl( \begin{smallmatrix} a & b \\ c & d \end{smallmatrix} \bigr)$

# 5. 运算符

| 运算符             | 语法              |
| ------------------ | ----------------- |
| $\pm$              | `\pm`             |
| $\times$           | `\times`          |
| $\div$             | `\div`            |
| $\leq$             | `\leq`            |
| $\ge$              | `\ge`             |
| $\neq$             | `\neq`            |
| $\Rightarrow$      | `\Rightarrow`     |
| $ \Leftrightarrow$ | `\Leftrightarrow` |
| $ \subset$         | `\subset`         |
| $ \subseteq$       | `\subseteq`       |
| $ \in$             | `\in`             |
| $ \notin$          | `\notin`          |
| $ \cup$            | `\cup`            |
| $ \cap$            | `\cap`            |
| $ \mathbb{R}$      | `\mathbb{R}`      |

# 6. 函数

## 1. 三角函数与对数函数

| 函数        | 语法       |
| ----------- | ---------- |
| $ \sin(x)$  | `\sin(x)`  |
| $ \cos(x)$  | `\cons(x)` |
| $\tan(x)$   | `\tan(x)`  |
| $ \log_2 x$ | `\log_2 x` |
| $ ⁡ \ln x$   | `\ln x`    |
| $ \lg x$    | `\lg x`    |

## 2. 分段函数

语法：

```markdown
$$
f(x)=
\begin{cases}
1 & x\geq 0\\
0 & x<0
\end{cases}
$$
```

效果：
$$
f(x)=
\begin{cases}
1 & x\geq 0\\
0 & x<0
\end{cases}
$$


# 7. 古希腊字母

| 大写 | 语法          | 小写 | 语法        |
| ---- | ------------- | ---- | ----------- |
| A    | A or \Alpha   | α    | \alpha      |
| B    | B or \Beta    | β    | \beta       |
| Γ    | \Gamma        | γ    | \gamma      |
| Δ    | \Delta        | δ    | \delta      |
| E    | E or \Epsilon | ϵ    | \epsilon    |
|      |               | ε    | \varepsilon |
| Z    | Z or \Zeta    | ζ    | \zeta       |
| H    | H or \Eta     | η    | \eta        |
| Θ    | \Theta        | θ    | \theta      |
| I    | I or \Iota    | ι    | \iota       |
| K    | K or \Kappa   | κ    | \kappa      |
| Λ    | \Lambda       | λ    | \lambda     |
| M    | M or \Mu      | μ    | \mu         |
| N    | N or \Nu      | ν    | \nu         |
| Ξ    | \Xi           | ξ    | \xi         |
| O    | O or \Omicron | ο    | \omicron    |
| Π    | \Pi           | π    | \pi         |
| P    | P or \Rho     | ρ    | \rho        |
| Σ    | \Sigma        | σ    | \sigma      |
| T    | T or \Tau     | τ    | \tau        |
| Υ    | Y or \Upsilon | υ    | \upsilon    |
| Φ    | \Phi          | ϕ    | \phi        |
| X    | X or \Chi     | χ    | \chi        |
| Ψ    | \Psi          | ψ    | \psi        |
| Ω    | \Omega        | ω    | \omega      |