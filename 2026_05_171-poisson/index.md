# 人是一根会思考的芦苇



青之芦苇中一直在强调踢球要不断地思考，以及衍生出的观点是球场上可以做到不需要语言进行沟通，沟通是可以通过足球本身传递的。然后关于思考与沟通本质上是，赛场上一大类问题，队友突然给你传球，但因为担心战术暴露，他无法和你进行语言沟通（时间也来不及），很多时候打手势或者眼神也来不及。然后书中就有这样的时刻，接到球的人，一开始对于传球人的动机完全不清楚，也不知道后续自己应该怎么配合。然后通过思考，比如这个传来的球的力度，落点，旋转，球的轨迹对视野的引导……最终推断出传球人的意图，想要自己做的事。
这种过程在数学上其实蛮多，在经过多层逻辑链之后得出结论的过程也是比较爽的。不过我始终有点怀疑在足球比赛过程中根本不到1秒的时间内，真的有办法走过多层的逻辑链吗？关于思考这个话题，我感觉几乎人人都觉得自己特会思考，但实际上这其中有一个巨大差异就在于逻辑链一层一层有价值地持续推进。
想说明这个问题或许还是得举个例子，但我也不确定这样的例子是否号。
***
假设我们未学过任何相关知识，看书的时候突然冒出一个泊松括号的定义
$$
\lbrace f,g\rbrace:=\frac{\partial {f}}{\partial {q}}\frac{\partial {g}}{\partial {p}}-\frac{\partial {f}}{\partial {p}}\frac{\partial {g}}{\partial {q}}
$$
其中$f,g:M\to \mathbb{R}$ 是光滑函数。
并且未加说明地在之后突然大量使用。（这种情形在数学上是大量存在的。如果学过，后面的思考过程可能会显得trivial。数学大体就是如此，但作为例子，还是需要假设没学过才有意义）
这个定义第一眼看是有点懵的，和青之芦苇中的情节类似，我们会自然地想问为什么要定义这样一个结构？这东西有什么用？我们唯一有的信息就是定义本身。
通过观察可以知道基本都是两个偏导数相乘再做加减法这样的形式。首先想到的这可能是某种二次型。
令$\nabla f=\left( \frac{\partial {f}}{\partial {q}},\frac{\partial {f}}{\partial {p}} \right)^{T}$，表为列向量形式。同理有$\nabla g=\left( \frac{\partial {g}}{\partial {q}},\frac{\partial {g}}{\partial {p}} \right)^{T}$
以此为基础要得到$\frac{\partial {f}}{\partial {q}}\frac{\partial {g}}{\partial {p}}-\frac{\partial {f}}{\partial {p}}\frac{\partial {g}}{\partial {q}}$这样的交错形式。想到两种可行的思路：
***
思路1：
这很像两个列向量并在一起形成的矩阵的行列式
简单尝试可以发现这个思路在只有两个变量的情况下没有问题。最终结果如果是行列式，那么为了便于理解可以暂时认为结果属于R，是一个数。
$\lbrace f,g \rbrace$可以理解为以向量$\nabla f,\nabla g$为边围成的平行四边形的有向面积。
***
思路 2： 
先做些变换后再做内积
我们如今有的是$\nabla g=\left( \frac{\partial {g}}{\partial {q}},\frac{\partial {g}}{\partial {p}} \right)^{T}$，但如果要做内积，我们需要的是$\left( \frac{\partial {g}}{\partial {p}},-\frac{\partial {g}}{\partial {q}} \right)^{T}$
这是一个顺时针的90度旋转，可以用一个线性变换J表示。
于是泊松括号变为
$$
\lbrace f,g \rbrace=(\nabla f)^{T}J\nabla g
$$
或者表示为
$$
\lbrace f,g \rbrace=\omega(\nabla f,\nabla g)
$$
这是一个辛内积。
***
<!--more-->
从第一种思路得到的面积的解释，暂时没看出有什么特别的用法。我们顺着第二种思路继续，先考虑$J\nabla g$的意义。g的梯度可以理解为g增加最快的方向。乘以J之后得到的是一个垂直与梯度的方向。可以理解为g不变的方向，因此$J\nabla g$也形成了一个向量场，通过积分可以得到路径称为相流。$\nabla f$再与$J\nabla g$做内积，得到的结果可以理解成**f在g不变方向上的方向导数**，也就是f在g不变方向上的变化强度。

到此，我们对泊松括号算是有了一个直观认识。接着取特殊值，看看是否有些特别的意义。

假设$\lbrace f,g \rbrace= 0$，我们可以知道f在沿着g生成的相流移动的过程中f的值不会发生改变。反之，也可认为g在沿着f生成的相流移动的过程中g不变，这是对称的。所以f是g所生成系统的某种守恒量（还需要一些其他条件，但这里只是讲思考过程，就暂时无视掉了。比如对于2维辛流形，满足$\lbrace f,g \rbrace= 0$的守恒量实际只有一个。对于2n维的辛流形，最多有n个）

特别一点，可以令g=H 是一个哈密顿量。
***
将相空间扩展到一般的广义坐标,泊松括号的定义变为
$$
\lbrace f,g \rbrace:=\sum \left( \frac{\partial {f}}{\partial {q_{i}}}\frac{\partial {g}}{\partial {p_{i}}}-\frac{\partial {f}}{\partial {p_{i}}}\frac{\partial {g}}{\partial {q_{i}}} \right)
$$

第一种思路变得不再可行，但第二种思路则完全没问题。
只要令
$$
\nabla f=\left( \frac{\partial {f}}{\partial {q_{1}}},\frac{\partial {f}}{\partial {q_{2}}},\dots,\frac{\partial {f}}{\partial {q_{n}}},\frac{\partial {f}}{\partial {p_{1}}},\dots,\frac{\partial {f}}{\partial {p_{n}}} \right)^{T}
$$

$$
J=
\begin{pmatrix}
0 & I \\
-I & 0
\end{pmatrix}
$$
依旧有$\lbrace f,g \rbrace=(\nabla f)^{T}J\nabla g$

将空间扩展到2n维之后，延续上面的思考，用$I_{i}$表示守恒量，我们首先想问的是**在2n维的辛流形上，最多允许有多少个 满足相互对易$\lbrace I_{i},I_{j} \rbrace=0$且$\nabla I_{i}$彼此线性独立的守恒量**?

这似乎是一个和辛结构$\omega$以及线性切空间相关的问题。假设允许的守恒量个数用k表示，在2n维辛流形上随意选取点x，我们先考虑x点处的切空间$T_{x}M$. 为了书写简便，令 $v_{i}=\nabla I_{i}\vert _{x}$  s.t. $v_{i}\in T_{x}M$.
这k个向量$v_{i}$张成的子空间用V表示，$V=\text{span}\lbracev_{1},\dots,v_{k}\rbrace$, 子空间的任意两个元素$v,u$都满足$\omega(v,u)=0$
为了求得V的维度k需要满足的约束，一个思路是考察V的某种补子集所具有的性质和关系。例如最常见的正交补，或者直和补W s.t. $W\oplus V=T_{x}M$. 但V本身是由辛结构$\omega$定义出的子集，它的补子集，要想和V相关，或许也应该从辛内积$\omega$入手。
***
于是现在的首要问题变为了解$\omega$的性质。
1. 因为$J^{T}=-J$
   有$\omega(u,v)=u^{T}Jv=(Jv)^{T}u=v^{T}J^{T}u=-v^{T}Ju=-\omega(v,u)$
2. for $\forall v\in T_{x}M$, 有$\omega(v,v)=0$。
按照原本内积中的说法，向量变成总是自正交的。但因此我们没有了模长，也没有了长度的概念。但从前面$\omega(v,u)=v^{T}Ju$可以看出，$\omega(v,u)$给出了$v,u$为边的平行四边形的有向面积。并且对于任意的$v\in T_{x}M$，总能找到一个u  s.t. $\omega(v,u)=v^{T}Ju=1$。由此我们可以推出存在u  s.t. ${\color{red}v=Ju}$
由于J可逆，u是唯一的。u无法用$av$， $a\in \mathbb{R}$表示。于是假如我们选v作为$T_{x}M$ 的一个基，u可以很自然地称为一组基的一份子。

这样的两个基我们用$e_{1},f_{1}$表示。$e_{1}$本身的长度我们无从得知也无要求，反而通过$\omega(e_{1},f_{1})=1$将二者关联起来。$e_{1},f_{1}$共同决定了一个2维子空间，或者说平面。换个角度上说。这个平面是由$e_{1}$和J完全决定的。$e_{1}=Jf_{1},Je_{1}=-f_{1}$.
对任意的u，若满足$\omega(u,a_{1}e_{1}+b_{1}f_{1})=1$, 可以推出 $u=\lambda J(a_{1}e_{1}+b_{1}f_{1})$是这个二维子空间的一个向量。

然后我们在剩余的2n-2维子空间中寻找新的基，显然新基$e_{2}$ 需满足$\omega(e_{2},e_{1})=0,\omega(e_{2},f_{1})=0$
有了$e_{2}$, 自然有对应的$f_{2}$ ，$f_{2}$应满足$\omega(e_{2},f_{2})=1,\omega(f_{2},e_{1})=0,\omega(f_{2},f_{1})=0$

由此我们得到了辛线性空间的标准基$\lbrace e_{1},\dots,e_{n},f_{1},\dots,f_{n} \rbrace$应该满足的关系
$$
\begin{align}
\omega(e_{i},e_{j})&=0 \\
\omega(f_{i},f_{j})&=0 \\
\omega(e_{i},f_{j})&=\delta _{ij}
\end{align}
$$
我们可以说$e_{i}$是和任意$e_{j},f_{j}$，$i\neq j$, 辛正交的.
到这里我们可以看出辛线性空间的一些性质:对于任意其上的一个向量v，由J完全决定了一个2维平面W. 在这一平面W内部，**任意的$v,u\in W$, 如果有$\omega(v,u)= 0$，那么可以推出$v=\lambda u$**
从这里可以看出2维的情形下，最多只允许一个守恒量。
***
回到2n维，最多允许多少个守恒量的问题

我们希望了解V的正交补，这里应该使用辛正交补$V^{\omega}$
$$
V^{\omega} = \lbrace u \in T_xM \mid \omega(u,v) = 0, \forall v \in V \rbrace
$$
容易知道$V\subseteq V^{\omega}$
这样是否还能有$dim\ V+dim\ V^{\omega}=dim\ T_{x}M$ 这样的结论?
定义
$$
V^{\circ }=\lbrace \alpha \in T_{x}^{*}M|\alpha(v)=0,\forall v\in V \rbrace
$$
我们从V的基底$\lbrace v_{1},\dots,v_{k} \rbrace$出发，延拓出整个$T_{x}M$的一组基$\lbrace e_{1},\dots,e_{k},e_{k+1},\dots,e_{2n} \rbrace$. 其中$e_{i}=v_{i}$ , for $i\leq k$, and $e_{n+i}=f_{i}$. 我们从V中元素满足的性质$\omega(v_{i},v_{j})=0$可知$f_{i}=Jv_{i}\not\in V$, 因为$\omega(v_{i},f_{i})=1$.
与$\lbrace e_{1},\dots,e_{k},e_{k+1},\dots,e_{2n} \rbrace$相对应的对偶基底表示为$\lbrace \alpha^{1},\dots,\alpha^{2n} \rbrace$
满足$\alpha^{i}(e_{j})=\delta _{ij}$
由$V^{\circ }$的定义可知，对任意的$\beta \in V^{\circ}$ ,可唯一表示为$\beta=a_{k+1}\alpha^{k+1}+\dots+a_{2n}\alpha^{2n}$
由此可知$dim\ V^{\circ}=2n-k$
***
如果可能我们希望在$V^{\omega}$和$V^{\circ}$之间建立映射关系。
定义$\Phi:T_{x}M\to T_{x}^{*}M$,  $\Phi(v)=\omega(v,\cdot)$
由于$\omega$是非退化的，只有$\omega(0,T_{x}M)=0$
所以 $Ker\ \Phi=0$，$\Phi$是一个单射。
对任意的$\beta=\sum a_{i}\alpha^{i}\in T_{x}^{*}M$
$\alpha^{i}(e_{j})=\delta _{ij}$
由$\omega(-Je_{i},e_{j})=\delta _{ij}$， 可以得到$\alpha^{i}=\omega(-Je_{i},\cdot)=\Phi(-Je_{i})$
所以$\beta=\sum a_{i}\Phi(-Je_{i})=\Phi\left( \sum -a_{i}Je_{i} \right)$
$\Phi$是个满射。
所以$\Phi$是一个同构映射
***
由$V^{\omega},V^{\circ}$的定义可以知道$\Phi(V^{\omega})=V^{\circ}$， 由$dim\ V^{\omega}=dim\ V^{\circ}=2n-k$

所以有$\boxed{dim\ V+dim\ V^{\omega}=dim\ T_{x}M}$
$V\subseteq V^{\omega}$ ,于是有$k\leq 2n-k$， $\implies k\leq n$。
k的最大值为n。
所以**在2n维的辛流形上，最多允许有n个 满足相互对易$\lbrace I_{i},I_{j} \rbrace=0$且$\nabla I_{i}$彼此线性独立的守恒量**
***
假设我们找到了$I_{1},\dots,I_{k}$作为守恒量, $k\leq n$，彼此满足$\lbrace I_{i},I_{j} \rbrace=0$,并且$\nabla I_{i}$彼此线性无关。
每个守恒量对应着一个约束方程，或者说一个2n维辛流形上的2n-1维的子流形。k个子流形的交最终得到一个2n-k维的子流形。并且满足$\omega(\nabla I_{i},\nabla I_{j})=0$. 当k=n的时候，2n-n=n维的子流形正好是一个拉格朗日子流形，也称为完全可积系统。当 $k<n$ 时，2n-k维子流形的内部也可能包含了一个拉格朗日子流形（这需要能找到n个守恒量，这并不总是必然的）。并且这个2n-k维子流形是一个部分可积系统。
我们完全还可以凭着自己的兴趣继续提出各种问题往下探索，但作为一个说明的举例，到此或许足够了。

这样的情况每天的数学学习过程中都在发生。主要的问题在于我发现本来以为只是3句话的内容，想把思考过程中的细节尽量写出来的话，一下子就老长。


