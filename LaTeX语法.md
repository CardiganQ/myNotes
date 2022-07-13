# LaTeX语法

## 中文文档

传送门：[*中文教程*](https://www.latexlive.com/help)
网址：`https://www.latexlive.com/help`



## 在线编译器

使用[*在线LaTeX公式编辑器*](https://www.latexlive.com/)，来生成LaTeX公式代码，然后复制到LaTeX编辑器（或Markdown编辑器）中，并在两边加上`$`或`$$`即可。
在线LaTeX公式编辑器网址：`https://www.latexlive.com/`



注意：使用`$`行中公式时，数学公式与`$`连接处不要有空格，否则公式不会显示；使用`$$`居中公式时，`数学公式`与`$$`连接处可以有空格。即`$ 数学公式 $` 不显示公式。

注意事项
使用 $ ，即行中公式时，数学公式与 $连接处不要有空格，否则公式不会显示。即$ 数学公式 $ 不显示公式。
使用$$，即居中公式时，数学公式与$$连接处可以有空格。
使用$$时，上方要空一行。
=不要单独打一行，否则可能会出错。
`+ - * / = ( ) | , . '`等符号直接在$或$$之间输入即可识别

  

## 插入公式

左对齐公式（行中公式）：`$数学公式$`
居中公式（独立公式）：`$$数学公式$$`

例子

```latex
$$
%第一个极限
\lim_{n \to +\infty} \frac{1}{n(n+1)}
\quad %空一格
and %英文单词and
\quad %空一格
%第2个极限
\lim_{x\leftarrow{example} \infty} \frac{1}{n(n+1)}
$$

```


$$
%第一个极限
\lim_{n \to +\infty} \frac{1}{n(n+1)}
\quad %空格
and %英文单词and
\quad
\lim_{x\leftarrow{example} \infty} \frac{1}{n(n+1)}
$$

## 编号

在公式末尾使用`tag{编号}` 来实现公式手动编号,大括号内的内容可以自定义

```latex
$$
x+y = z
\tag{ 1 }
$$
```

$$
x+y = z
\tag{ 1 }
$$

## 反义字符

在公式输入`_`或`^`时，会产生上下标的共嗯，若想输入符号本身则需要转义字符`\`

```latex
$$
home\_name = admin
$$
```

$$
home\_name = admin
$$

## 换与对齐

使用`begin{aligned}` 进行对齐,`&`表示对其位置,**一般在=前面**

```latex
$$
\begin{aligned}
f(x)&=2x+1\\
&=2+1\\
&=3
\end{aligned}
$$
```

$$
\begin{aligned}
f(x)&=2x+1 \\
&=2+1 \\
&=3
\end{aligned}
$$

## 字体

若要对公式的某一部分字符进行转换，可以使用`\字体(需转换字符)`命令

| 输入           | 说明                   | 显示               |
| -------------- | ---------------------- | ------------------ |
| \mathit 或 \it | 斜体（默认，意大利体） | $$\it D$$          |
| \mathrm 或 \rm | 罗马体                 | $$\rm D $$         |
| \mathbf 或 \bf | 粗体                   | $$\bf D$$          |
| \mathbb        | 黑板粗体               | $$\mathbb D$$      |
| \mathsf 或 \sf | 等线体                 | $$ \sf D$$         |
| \mathcal       | 花体                   | $$\mathcal D$$     |
| \mathscr       | 手写体                 | $$ \mathscr D$$    |
| \mathtt        | 打字机体               | $$ \mathtt D$$     |
| \mathfrak      | 哥特体                 | $$\mathfrak{D}$$   |
| \boldsymbol    | 黑体                   | $$\boldsymbol{D}$$ |



## 空格

`\quad`: 空一格
`\qquad`:空两格



## 上下标

`^`表示上标  `_`表示下标，如果上下标内容多余一个字符，需要用`{}` 将内容括成一个整体

```latex
$$
x^{y^z_w} = (1+{\rm e}^e)^{-2xy^w}
$$
```

$$
x^{y^z_w} = (1+{\rm e}^e)^{-2xy^w}
$$

## 括号

`()、[]、|`表示符号本身，使用`\{\}` 表示{}，当要显示大号的括号或分隔符时，要用`left`和`right` 命令，如`$left(表达式\right)$`

| 特殊符号 | 输入                     | 显示                   |
| -------- | ------------------------ | ---------------------- |
| 尖括号   | `$\langle表达式\rangle$` | $\langle表达式\rangle$ |
| 向上取整 | `$\lceil表达式\rceil$`   | $\lceil表达式\rceil$   |
| 向下取整 | `$\lfloor表达式\rfloor$` | $\lfloor表达式\rfloor$ |
| 花括号   | `$\lbrace表达式\rbrace$` | $\lbrace表达式\rbrace$ |

例子：
$$
f(x,y,z) = 3y^3z \left(3+ \frac{7+5}{1+y^2}\right)
$$

## 大括号

- 方法一

​	用 `\left`和 `\right`来创建自动匹配高度的括号，包含 (圆括号)、[方括号]、|绝对值|。

​	

```latex
$$
f\left(
   \left[
     \frac{
       1+\left\{x,y\right\}
     }{
       \left(
          \frac{x}{y}+\frac{y}{x}
       \right)
       \left(u+1\right)
     }+a
   \right]^{3/2}
\right)
$$
```

$$
f\left(
   \left[
     \frac{
       1+\left\{x,y\right\}
     }{
       \left(
          \frac{x}{y}+\frac{y}{x}
       \right)
       \left(u+1\right)
     }+a
   \right]^{3/2}
\right)
$$


​	有时候要用`\left.`或`\right.`进行匹配而不显示本身。

```latex
$$
	\left. \frac{ {\rm d}u}{ {\rm d} x}\right|_{x=0}
$$
```


$$
\left. \frac{ {\rm d}u}{ {\rm d} x}\right|_{x=0}
$$


- 方法二

​	使用`\big`和`\bigg`来创建逐级变大的括号，包含 (圆括号)、[方括号]、|绝对值|。

```latex
$$\bigg( \big( ( ) \big) \bigg)$$
$$\bigg[ \big[ [ ] \big] \bigg]$$
$$\bigg| \big| | | \big| \bigg|$$
```

$$\bigg( \big( ( ) \big) \bigg)$$
$$\bigg[ \big[ [ ] \big] \bigg]$$
$$\bigg| \big| | | \big| \bigg|$$

## 分式

通常使用 ` \frac {分子}{分母}`命令生成一个分式，分式可以嵌套
便捷情况可直接输入` \frac` ab来快速生成一个 $ \frac ab$
如果分式很复杂，亦可使用 分子 \over 分母 命令，此时分式仅有一层。

$$\frac{a-1}{b-1} \quad and \quad {a+1\over b+1}$$



## 根式

`\sqrt [根指数]{被开方数}`
$$
\sqrt[n]{x+y}
$$


## 对数

`\log_{对数底数}{表达式}`

表达式的大括号可以省略
$$
\log_{x+y}{z+1}
$$


## 省略号

`\ldots` 表示与文本底线对齐的横向省略号

`\cdots` 表示与文本中线对齐的横向省略号

`\ddots` 表示斜向省略号



## 最值

`\max_{下标表达式}{最值表达式}`表示最大值，`\min_{下标表达式}{最值表达式}`表达最小值



## 方程组和分段函数

方程组有2种方式，分别是`\begin{aligned}`和`\begin{cases}`方式，`&`表示对齐位置，推荐使用`\begin{cases}`方式，使用方法如下：

`\begin{aligned}`方式：可以使方程组根据`=`对齐
$$
\left\{
\begin{aligned}
a+b&=2 \\
a-b+c&=4 \\
\end{aligned}
\right.
$$
`\begin{cases}`方式（推荐）：简便，但无法根据`=`对齐
$$
\begin{cases}
a+b=2 \\
a-b+c=4 \\
\end{cases}
$$

## 分段函数

分段函数可以通过`\begin{cases}`方式实现，不同的是方程式和条件之间要用`&`符号隔开

```
$$
y =
\begin{cases}
\sin(x)       & x<0 \\
x^2 + 2x +4   & 0 \leq x < 1 \\
x^3           & x \geq 1 \\
\end{cases}
$$
```

$$
y =
\begin{cases}
\sin(x)       & x<0 \\
x^2 + 2x +4   & 0 \leq x < 1 \\
x^3           & x \geq 1 \\
\end{cases}
$$

## 累加和累乘

使用 `\sum_{下标表达式}^{上标表达式}{累加表达式}`来输入一个累加。
与之类似，使用 `\prod \bigcup \bigcap`来分别输入累乘、并集和交集。
此类符号在行内显示时上下标表达式将会移至右上角和右下角。

$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$



## 矢量

使用 `\vec{矢量}`来自动产生一个矢量。
也可以使用 `\overrightarrow`等命令自定义字母上方的符号。



