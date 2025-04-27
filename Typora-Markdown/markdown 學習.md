why markdown:

-> 导出格式+支持html-Latex
-> 插入图片代码和公式
->支持基本排版

**I.标题**

<a id="entrance"></a>

# 一级标题

## 二级标题

### 三级标题

111111111111111111111111111111111111111111111111111111111111111
qq   
asdfasdf
<p> this is a new paragraph </p>
sdaf<br> this is a new line

A sequence to translate C program: first preprocess it ,then compile it.

a preprocessor :

1223134 this is a new line

The这是新一行，但不是新的一段

#### 四级标题

###### 六级标题 (不要忘了有空格)

**两个这是粗体的**

*斜体*

***粗斜体***

`加阴影`

数据~下表小写123~

平方^上标^

**crtl+B自动加粗**

<u>crtl+U自动下划线</u>

<a id="<entrance>"></a>

**II.分割线**

----

+++++

III.引用和注释

加上一个>

换行   
阿斯蒂芬




>   “the size of the entrance”

>   这是引用
>
>   >   多级引用

<!--一段话,这纯纯是注释了-->

VI.列表

-   无序列表中的一项（要空格）
-   *也可以   
-   1.  什么鬼
    2.  c
    3.  

1.   
2.  sequential array

V. 链接 注意格式！

传送门输入口：有id用于标识

[跳转名称](#entrance)

脚注跳转[^<test1>]

tag for jumping[^<jump>]

[^]:here

鏈接文件

[你想顯示的内容,it's also ok to drag it here]()

图片：

![photo](resources/chatgpt使用.jpg)

图片：[link for a photo](./resources/chatgpt使用.jpg)

注：“./” is ok to be omitted

-   wenjianlujin

```C++
int main(){
    printf("hello markdown!\n")
}
```

表格：

| 标题一                        | 标题二 | category3        |
| ----------------------------- | ------ | ---------------- |
| asdf<br>haojiahuo, a linefeed | ?      | *123*            |
| `shadow`                      |        | <u>important</u> |
| br 可以在表格中间换行         |        |                  |
|                               |        |                  |
|                               |        |                  |

嵌入html代码

----

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=1600641662&bvid=BV172421w7Ba&cid=1587688641&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>



integrate Latex

$x_{1,2}= \frac{a0}{bo}$
$$
f(x)=a^2 + 2*a +1
$$


```latex
the most common latex signs and characters:
1. operators:
 + ,-, *, \frac, = ,\times, \equiv(equivalent) \approx
 \le \ge \supset \subset
 \sum \prod \int 
 
 
2.characters:
\alpha \beta \gamma \theta \epsilon \eta \mu \iota \lambda
\kappa \pi \rho \sigma \tau \varphi \phi \psi \omega
\Gamma \Lambda \Sigma \Delta \Theta \Pi \Phi \Omega

3.arrows
\Leftrightarrow \Rightarrow \iff \uparrow \Downarrow

4.brace brack 
[] okey \{ \} \lgroup (l for left) \rgroup

5.\dots ... \vdots 

6.上标
\hat{a} \dot{a} \vet{a} \bar{a} \widetilde{a} (复数求导)
\overrihgtarrow{AB} (geometric vector)
7.例子：
\frac{d}{dx}\left(x^2\right) = 2x 求导格式
\int 2x,dx = x^2+C 积分格式
\int^5_1 2x,dx = 24 积分表明上下界
\frac{\partial^2U}{\partial x^2} (二阶偏导)
\max \argmax \det \dim \sin \arctan \infty (infinity)
\lim \ln e \log_e
double integration \iint_{D}f(x,y)dxdy \iiint_{\Omega}f(x,y,z)dxdydz (trible) (其实环路积分就加个o)

8.矩阵（Matrices and Arrays）
We can typeset a matrix with the matrix, bmatrix, pmatrix, or vmatrix environments. The letters b, p, and v refer to the delimiters around the matrix (brackets[], parentheses{}, and vertical bars||, respectively). For example, the following code
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
\end {bmatrix}

9.Text Styles in Math Mode
$$n^2 + 5 = 30\text{ so we have }n=\pm5$$
{\displaystyle} vs. \textstyle
```

（如果想要全文的行内公式都显示行间公式效果，在文章头部添加\everymath{\displaystyle}命令。这个命令同时也会让分式变大。）相反地，\textstyle 把行间换成行内。

　　$\displaystyle\oiint_{\sigma}f(x, y)dxdy$ (把积分符号放大)

![a photo](https://img.picui.cn/free/2025/04/24/680a26f0f055b.png)

[a photo](https://img.picui.cn/free/2025/04/24/680a26f0f055b.png)(他本来就是全黑的)

//from the 

[^]: 这里是test1




<p> this is a new paragraph </p>

something<br>1223134 this is a new line
The这是新一行，但不是新的一段
新的一行；

这有好多段文字；每一段必须要空出一整行来。
**asdf**
something<br>1223134 this is a new line
The这是新一行，但不是新的一段
新的一行；

新的一行；

这有好多段文字；每一段必须要空出一整行来.   
这就是换行

-   *斜体* `jiahei` **bold** <u>*underline*</u>

    ***mixed***

    very nice

    It’s ok now

    

```
这个newprint 主要用来做数学物理工作
github做计算机类工作
其他格式基本没有什么用。

```

>   **这也还行**
>
>   `everything will be alright`
>
>   
>
>   
>
>   

111111111111111111111111111111111111111111111111111111111

<p> this is a new paragraph </p>

`something<br>`1223134 this is a new line

asdf

正常情况一个enter换两行 等于 <p> content </p>

已经足以见得typora之方便

relative(这是假的换行；打字舒服而已)

`ahsdf`The这是新一行，但不是新的一段<br>
新的一行；（这是真换行；几个空格+shift+enter或者<br>)他会自动帮你换行

例子：这有好多段文字；每一段必须要空出一整行来.   
这就是换行

```text

```

~~世界是平坦的。~~ 我们现在知道世界是圆的。

```text
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```

- [ ] Write the press release
- [ ] Update the website
- [ ] Contact the media

​	

```text
这是可见的段落。

[这是一个隐藏的注释]: # (#is unneccessary)
<!--这也是注释 -->

这是另一个可见的段落。

没用的就是text格式
```

效果：

one p

[comment]: fsadsdf

<!--这也是注释 -->

two p

```text
> :warning: **警告：** 不要按下大红色按钮！
emoji is supported!
> :memo: **注意：** 日出很美。

> :bulb: **提示：** 记得珍惜生活中的小事。
```

> :warning: **警告：** 不要按下大红色按钮！

> :memo: **注意：** 日出很美。

> :bulb: **提示：** 记得珍惜生活中的小事。

:blush:

:relaxed:

:exclamation:

:question:

:+1: `:+1:`

:zap: `:zap:`

:penguin:

:rose:

:apple: `:apple:`

 `:coffee:`

:tea: `:tea:`

 `:file_folder:`

:rocket: `:rocket:`

:round_pushpin: `:round_pushpin:`

:arrow_lower_right:

:x: `:x:` :o: `:o:`:heavy_check_mark: `:heavy_check_mark:`:white_check_mark: `:white_check_mark:`

:large_blue_diamond: `:large_blue_diamond:`  :large_orange_diamond:

|                `:small_red_triangle:`                 |
| :---------------------------------------------------: |  |  |
| :small_red_triangle_down: `:small_red_triangle_down:` |  |  |
