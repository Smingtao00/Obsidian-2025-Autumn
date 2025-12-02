
#齐次函数

# 齐次函数的性质

一个函数 $f: \mathbb{R}^n \to \mathbb{R}$ 为 **m 次齐次函数**，如果对于所有  $t > 0$ 和所有 $\mathbf{x} = (x_1, \dots, x_n)$ 在其定义域内，满足以下基本性质：

## 1. 核心定义

$$
f(t\mathbf{x}) = f(tx_1, tx_2, \dots, tx_n) = t^m f(\mathbf{x})
$$



## 2. 重要性质与定理

#欧拉齐次函数定理

### 2.1. 欧拉齐次函数定理

如果一个 $m$ 次齐次函数 $f$ 是可微的，那么它的所有一阶偏导数满足以下关系：

$$
x_1 \frac{\partial f}{\partial x_1} + x_2 \frac{\partial f}{\partial x_2} + \dots + x_n \frac{\partial f}{\partial x_n} = m f(x_1, x_2, \dots, x_n)
$$

（$f(tx_1, tx_2, \dots, tx_n) = t^m f(\mathbf{x})$ 两边同时对t求导即可。）

用更简洁的向量记号（梯度 $\nabla f$）表示为：

$$
\mathbf{x} \cdot \nabla f(\mathbf{x}) = m f(\mathbf{x})
$$



### 2.2. 偏导数的齐次性

如果 $f(\mathbf{x})$ 是 $m$ 次齐次的，那么它的一阶偏导数 $\frac{\partial f}{\partial x_i}$ 是 $(m-1)$ 次齐次的。

$$
\frac{\partial f}{\partial x_i}(t\mathbf{x}) = t^{m-1} \frac{\partial f}{\partial x_i}(\mathbf{x})
$$

更一般地，$k$ 阶偏导数是 $(m-k)$ 次齐次的。



---

# 拉格朗日方程

#Lagrange方程

$y=xf(y^{'})+\phi(y^{'})$

[[虚功原理，达朗贝尔原理和拉格朗日方程]]



---

# 一致收敛

#Weierstrass判别法

### 定理 10.2.2（Weierstrass 判别法）

设函数项级数 $\sum_{n = 1}^{\infty}u_{n}(x)(x \in D)$ 的每一项 $u_{n}(x)$ 满足 

$$|u_{n}(x) \leq a_{n}|, x \in D$$
并且数项级数 $\sum_{n = 1}^{\infty} a_{n}$ 收敛，则 $\sum_{n=1}^{\infty}u_{n}(x)$ 在 $D$ 一致收敛。



---

# 边值问题和周期解

###  定理 5.1

齐次方程组（LH）只有平凡解 $x = 0$ 满足两点边值条件 $Lx(a) + Nx(b) = 0$ 当且仅当 $L\Phi(a) + N\Phi(b)$ 是非奇异矩阵，其中 $\Phi(t)$ 是方程组（LH）的基本解矩阵。



### 定理 5.2

若齐次方程组（LH）只有零解 $x=0$ 满足两点边值条件，则对任何 $f(t)$，方程组（NH）恒有解满足两点边值条件。



### 定理 5.3 （马赛拉（Massera）准则）

若 $A(t)$ 和 $f(t)$ 是 $R$ 上连续的 $\omega$-周期函数，则方程组（NH）存在 $\omega$-周期解的充要条件是方程组（NH）有一个 $R$ 上的有界解。 



---

# 一般理论

## 引言

一阶正规形非线性方程组
$$
\begin{cases} 
\frac{dx_1}{dt} = f_1(t,x_1,x_2,\dots,x_n), \\
\frac{dx_2}{dt}=f_2(t,x_1,x_2,\dots,x_n), \\
\dots\dots\dots \\
\frac{dx_n}{dt}=f_n(t,x_1,x_2,\dots,x_n).
\end{cases}
(E)
$$
任意正规形高阶方程
$$x^{(n)} = f(t,x,x^{'},\dots,x^{(n - 1)})(E_n)$$
都可以变为等价的一阶正规形方程组，因此关于一阶正规形方程组 $(E)$ 的所有结论都可以转移到正规形高阶方程 $E_n$ 上。

方程组 $(E)$ 可简记为 $$\frac{dx}{dt} = f(t,x)$$，其中 $$\frac{dx}{dt} = \begin{pmatrix} \frac{dx_1}{dt} \\ \frac{dx_2}{dt} \\ \vdots \\ \frac{dx_n}{dt}\end{pmatrix},x = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n\end{pmatrix},f(t,x) = \begin{pmatrix} f_1(t,x_1,x_2, \dots, x_n) \\ f_2(t, x_1, x_2, \dots, x_n) \\ \vdots \\ f_n(t,x_1,x_2,\dots,x_n)\end{pmatrix}.$$
方程组 $(E)$ 的最基本的定解问题是初值问题，也称为 **柯西问题**。设处置条件为 $$x(\tau) = \xi$$，其中 $\xi$ 是 $n$ 维列向量。



## 皮卡存在与唯一性定理


### Lipschitz 条件
函数 $f(t,x)$ 在闭域 
$$R = \{(t,x)| |t - \tau| \leq a,|x - \xi| \leq b\}$$
上满足利氏条件，如果 $\exists N > 0$，使得对任意点 $(t, x_1), (t, x_2) \in R$，都有 
$$|f(t,x_1) - f(t,x_2)|\leq N|x_1 - x_2|$$
，其中 $N$ 称为**利氏常数**。

> [!tip]
>
> 由中值定理知，若 $f(t,x)$ 在 $R$ 上关于 $x$ 的各个分量的偏微商都存在且有界，则 $f(t,x)$ 在 $R$ 上满足利氏条件。 



### 皮卡定理

若 $f(t,x)$ 在闭域 $R$ 上连续，且满足利氏条件，则初值问题于区间 $I_0 = \{t||t - \tau| \leq h\}$ 上存在唯一解，其中 $h = min\{a, \frac{b}{M}\}$，$M$ 是 $|f(t,x)|$ 于 $R$ 的一个上界。

> [!tip]
>
> 区间 $I_0$ 和 $h$ 的构造是为了使得构造的皮卡迭代序列 $\{\varphi_k(t)\}$ 不超出 $I_0$，从而 $f(t,\varphi_k(t))$ 不超出 $R$，从而能使用 Lipschitz 条件。


> [!tip] 证明
>
> 1. 归结为证明等价的积分方程组 $$x(t) = \xi + \int_{\tau}^t f(s, x(s))ds$$ 于 $I_0$ 上存在唯一连续解
> 2. 在 $I_0$ 上构造皮卡迭代序列 $\{\varphi_k(t)\}$ 并证明其一致收敛。令$$\varphi_0(t) = \xi$$ $$\varphi_k(t) = \xi + \int_{\tau}^t f(s,\varphi_{k - 1}(s))ds, k = 1,2, \dots.$$
> 3. 证明唯一性。

> [!tip]
>
> 皮卡序列的构造过程实质上是一边在证明[[压缩映像原理]]，一边在用它解决常微分方程问题。


设 $G$ 是 $(t,x)$ 空间的域，若对任意 $(\tau,\xi) \in G$，都存在闭域 $R \subset G$，使得 $f(t,x)$ 在 $R$ 上满足利氏条件（对 $G$ 上不同的点 $(\tau,\xi)$，常数 $a,b$ 和利氏常数 $N$ 可能不同），则称 $f(t,x)$ 于域 $G$ 上**局部地满足利氏条件**。

> [!tip]
>
> 若 $f(t,x)$ 在域 $G$ 上关于 $x$ 的各个分量的偏微商均存在且连续，则 $f(t,x)$ 于 $G$ 上局部地满足利氏条件。



### 推论

若 $f(t,x)$ 在域 $G$ 内连续，且局部地满足利氏条件，则对任意 $(\tau,\xi) \in G$，初值问题的解在含 $\tau$ 的某一区间上的存在且唯一。



### 定理（解的整体唯一性）

若对任意 $(t_0,\xi_0) \in G$，初值问题 $(E),x(t_0) = \xi_0$ 的解在含 $t_0$ 的某区间上唯一，则对任意 $(\tau, \xi) \in G$，初值问题的任意两个解在其共同存在区间上恒等。

保证 $(E)$ 的局部解唯一的任何条件，也能保证 $(E)$ 的整体解唯一。



### 解不唯一的情况，奇解

若 $f(t,x)$ 在 $(t,x)$ 空间的域 $G$ 内连续，且局部地满足利氏条件或其他更一般的条件，则对任何 $(\tau,\xi) \in G$，初值问题的解不仅存在，而且是唯一的。

然而，如果只假设 $f(t,x)$ 连续，那么初值问题的解依然存在，但不一定唯一。例如初值问题 $$\frac{dx}{dt} = 2|x|^{\frac{1}{2}},x(0) = 0$$，就有无穷多个解。

从几何上看，初值问题的解唯一，就是只有一条积分曲线经过点 $(\tau,\xi)$，初值问题有无穷多个解，就是有无穷多条积分曲线经过点 $(\tau,\xi)$，所有这些积分曲线都在点 $(\tau,\xi)$ 相切。

考虑一阶隐方程 $$F(t,x,x^{'}) = 0,(2.13)$$
设 $x = \varphi(t)$ 是方程 $(2.13)$ 在区间 $I$ 上的解，若在它相应的积分曲线上任何一点都有方程 $(2.13)$ 的另一条积分曲线经过并在该点与之相切，则称 $x = \varphi(t)$ 为方程 $(2.13)$ 在 $I$ 上的**奇解**。

设 $F(t,x,p)$ 是 $(t,x,p)$ 的连续可微函数，则 $x = \varphi(t)$ 是方程 $(2.13)$ 在 $I$ 上的奇解的必要条件是 $$F(t,\varphi(t),\varphi^{'}(t)) = 0, F_p(t,\varphi(t),\varphi^{'}(t))= 0 , t \in I$$
必要条件表明，方程 $(2.13)$ 的奇解包含在由方程组
$$F(t,x,p) = 0, F_p(t,x,p) = 0$$
消去 $p$ 而得到的曲线中，该曲线称为方程 $(2.13)$ 的 **$p$-判别曲线**。$p$-判别曲线是不是奇解，需要进一步验证。



### 定理

**克莱罗(Clairaut,1713-1765)方程**
$$x = tx^{'} + g(x^{'})$$
恒有奇解，这里函数 $g(p)$ 两次连续可微，且 $g^{''}(p) \neq 0$。



## 佩亚诺存在定理

### 定理
设 $f(t,x)$ 于闭域 $R = \{(t,x) | |t - \tau| \leq a, |x -\xi| \leq b\}$ 上连续，则初值问题有定义于区间 $I_0 = \{t | |t - \tau| \leq h\}$ 上的解，其中 $h = min\{a, \frac{b}{M}\}$，$M$ 是 $|f(t,x)|$ 在 $R$ 上的一个上界。




### 阿尔泽拉(Arzela)-阿斯科利(Ascoli)引理
意义与证明方法类似数学分析中的聚点原理。



#### 定义
若存在常数 $M_0 > 0$，使得对任意 $f(t) \in F$，都有
$$|f(t)| \leq M_0, t \in I,$$
则称函数族 $F$ 在区间 $I$ 上是 **一致有界** 的。



#### 定义

若对任意 $\epsilon > 0$，都存在只与 $\epsilon$ 相关的常数 $\delta > 0$，使得对任意 $f(t) \in F$，只要 $t_1,t_2 \in I, |t_1 - t_2| \leq \delta$，就有 $$|f(t_1) - f(t_2)| \leq \epsilon$$，则称函数族 $F$ 在区间 $I$ 上是 **等度连续** 的。



#### 引理

假设 $F = \{f(t)\}$ 是有限区间 $I = [c, d]$ 上一致有界，等度连续的函数族，则 $F$ 必有于区间 $I$ 上一致收敛的子序列。



#### 推论 3.1

若函数 $f(t,x)$ 于 $(t,x)$ 空间的域 $G$ 内连续，则对任意 $(\tau, \xi) \in G$，初值问题有定义于含 $\tau$ 的某区间（其长度一般与 $(\tau, \xi)$ 有关）上的解。



#### 推论 3.2

若函数 $f(t,x)$ 于 $(t,x)$ 空间的域 $G$ 内连续，$D$ 是 $(t, x)$ 空间的有界域，且 $\overline{D} \subset G$，则存在 $h > 0$，使得对任意 $(\tau, \xi) \in D$，初值问题有定义在区间 $[\tau - h, \tau + h]$ 上的解。 

> [!tip] 闭包
> [[数学分析]]



## 解的延展与解的整体存在性

### 定理 5.1
设 $f(t,x)$ 于 $(t,x)$ 空间域 $G$ 内连续。若对任意 $(\tau, \xi) \in G$，初值问题的解在含 $\tau$ 的某一区间上是唯一的（可以使用解的整体唯一性），则 $\dot{x} = f(t,x)$ 的任何非饱和解都可以延展成为饱和解。



### 定理 5.2

设 $f(t,x)$ 于 $(t,x)$ 空间域 $G$ 内连续，$D$ 是 $(t,x)$ 空间中一有界域，且 $\overline{D} \subset G$。则方程组 $\dot{x} = f(t,x)$ 经过 $D$ 中任一点的解曲线，经向左和向右延展，都可以达到 $D$ 的边界。

> [!tip]
>
> 使用 引理 3.2 证明（对每个 $(\tau, \xi) \in D$, 有 **固定的 $h$** 使得方程组有定义在 $[\tau - h, \tau + h]$ 上的解。）



### 比较定理

解的存在定理告诉我们，微分方程的解的初值问题可以延拓到边界，但是解的存在区间的大小对于具体问题来说还是费解的，有了比较定理之后，我们会收获一个计算解的存在区间的强有力的工具。



#### 第一比较定理

设函数 $f(x, y)$ 和 $F(x, y)$ 均在区域 $G$ 内连续，且 $$f(x,y) < F(x, y), (x,y) \in G,$$
又设函数 $y = \phi(x)$ 和 $y = \Phi(x)$ 在区间 $(a,b)$ 上分别是初值问题 $$y^{'}=f(x,y),y(x_0)=y_0$$
和 $$y^{'}=F(x,y),y(x_0) = y_0$$
的解，其中 $(x_0,y_0) \in G$，则 
$$
\begin{cases} 
\phi(x) < \Phi(x), x_0 < x < b, \\
\phi(x) > \Phi(x), a < x < x_0.
\end{cases}
$$

> [!tip]
> 第一比较定理要求 $F(x,y)$ 严格地大于 $f(x,y)$，要是不严格的话我们可以取 $f(x,y) = F(x,y)$ 为反例，它们的解是无法比较大小的。



---

假设 $f(t,x)$ 在域 $G = \{(t,x) | T_0 < t < T_1, |x| < +\infty\}$ 内连续。根据延展定理容易证明，若方程组的任意饱和解 $x = \varphi(t)$ 是有界的，即存在常数 $C$ 使得 $|\varphi(t)| \leq C$，则 $x = \varphi(t)$ 的存在区间是 $(T_0, T_1)$。事实上，对充分小的 $\delta > 0$，记 $D = \{(t,x) | T_0 + \delta < t < T_1 - \delta, |x| < 2C\}$，由定理 5.2 知解曲线 $x = \varphi(t)$ 向左、右延展都可以达到 $D$ 的边界。但是 $|\varphi(t)| \leq C$，所以它不可能达到 $|x| = 2C$，于是它一定可以达到 $t = T_0 + \delta$ 和 $t = T_1 - \delta$，即 $x = \varphi(t)$ 至少在 $[T_0+ \delta,T_1 - \delta]$ 上有定义，此时我们称方程组 $(E)$ 存在整体解。



### 定理 5.6

若 $f(t,x)$ 在域 $G$ 内连续，且 $$|f(t,x)| \leq A|x| + B$$，其中 $A,B$ 是常数，则方程组 $(E)$ 的任何饱和解 $x = \varphi(t)$ 都在区间 $(T_0, T_1)$ 上存在。

> [!tip]
>
> **证明：**
>
> 
>
> 设 $\varphi(t) = (\varphi_1(t), \varphi_2(t),\dots,\varphi_n(t))$ 的存在区间为 $(a, b)$，其中 $T_0 < a < b < T_1$。存在 $\delta > 0$，使得 $T_0 + \delta < a < b < T_1 - \delta$，也即 $(a, b) \subseteq [T_0 + \delta, T_1 - \delta]$，若 $\varphi(t)$ 在其存在区间内有界，也即 $\exists C > 0, |\varphi(t)| \leq C$，考虑域 $G$ 内有界域 $D = \{(t,x) | t \in [T_0 + \delta, T_1 - \delta], |x| \leq 2C\}$，则 $\varphi(t)$ 是 $D$ 内的解曲线 $\Rightarrow \varphi(t)$ 可以拓展到 $D$ 的边界，又 $|\varphi(t)| \leq C \Rightarrow \varphi(t)$ 不可能达到 $|x| = 2C \Rightarrow \varphi(t)$ 可拓展到 $[T_0 + \delta, T_1 - \delta]$。由 $\delta \rightarrow 0$ 得到 $\varphi(t)$ 存在区间为 $(T_0, T_1)$。故只需证明 $\varphi(t)$ 在其存在区间 $(a,b)$ 内有界。
> 假设 $x = \varphi(t)$ 在 $[t_0, b)$ 无界（这里 $t_0 \in (a,b)$。令 $$r(t) = (\sum\limits_{i = 1}^n {\varphi_i^2(t)})^{\frac{1}{2}}$$，则 $r(t)$ 在 $[t_0,b)$ 上连续，且在其不为零得点处连续可微。因为 $\varphi(t)$ 在 $[t_0,b)$ 上无界，所以对任意 $K > r(t_0) + 1$，都有 $t_k \in (t_0, b)$，使得 $r(t_k) \geq K$。根据 $r(t)$ 的连续性，存在 $\tau_k \in (t_0, t_k)$，使得 $r(\tau_k) = r(t_0) + 1$，且当 $t \in [\tau_k, t_k]$ 时，$r(t) > 0$。又由 Cauchy 不等式知 $|\varphi(t)| \leq \sqrt{n}r(t)$，$$\frac{dr(t)}{dt} = \frac{1}{r(t)}\sum\limits_{i = 1}^n {\varphi_i(t) f_i(t,\varphi(t))} \leq \frac{1}{r(t)} \sum\limits_{i = 1}^n {|\varphi_i(t)||f(t,\varphi(t)|} \leq \sqrt{n}|f(t,\varphi(t)| \leq \sqrt{n}(A|\varphi(t)| + B) \leq \sqrt{n}(A\sqrt{n}r(t) + B)$$，上式两端从 $\tau_k$ 到 $t_k$ 积分得 $$ln(A\sqrt{n}r(t_k)+B) - ln(A\sqrt{n}r(\tau_k)+B)) \leq An(t_k - \tau_k) \leq An(b - t_0)$$，上式右端是有限的，而由 $t(\tau_k) \geq K$ 知，当 $K$ 充分大时，上式左端可以任意大，矛盾！这说明 $x = \varphi(t)$ 在 $[t_0, b)$ 有界。


定理 5.6 中的条件可以推广为
$$|f(t,x)| \leq G(||x||),(t,x) \in G,$$
其中 $G(s)$ 在 $s \geq 0$ 上连续，当 $s > 0$ 时，$G(s) > 0$，且
$$\int_{s_0}^{+\infty} \frac{ds}{G(s)} = +\infty,s_0 > 0$$



### 定理 5.7

若 $f(t,x)$ 在 $G$ 内连续且满足上述条件，则 $\dot{x} = f(t,x)$ 的任何饱和解 $x = \varphi(t)$ 都在区间 $(T_0, T_1)$ 上存在。

![image-20251128130927795](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130927795.png)

> [!tip]
> 若不存在 $t_0$ 使得 $\lim\limits_{t \rightarrow t_0}|x(t)| \rightarrow + \infty$，则可以构造有界域 $D = \{(t,x)| -h < t < h,|x| \leq 2 \cdot sup\{x(t)|-h < t < h\}\},t_0 \in (-h,h)$，$x(t)$ 可以拓展到 $D$ 的边界，而 $x(t)$ 达不到 $|x| = 2 \cdot sup\{x(t)|t \in (-h,h)\}$，故 $x(t)$ 可以拓展到 $(-h, h)$，由 $h$ 的任意性知 $x(t)$ 可以拓展到 $(-\infty,+\infty)$。
> 由 $p \rightarrow q \Leftrightarrow \neg q \rightarrow \neg p$ 知不能拓展到 $(-\infty,+\infty)\Rightarrow$ 存在 $t_0 > 0$，使 $\lim\limits_{t \rightarrow t_0} |x(t)| \rightarrow + \infty$。 

![image-20251128130934942](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130934942.png)

![image-20251128130940762](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130940762.png)






## 解对初值和与参数的连续性

以下我们假设 $f(t,x)$ 在 $(t,x)$ 空间的域 $G$ 内连续，且局部地满足利氏条件。

根据推论 2.1 和 定理 5.1，对任意 $(\tau,\xi) \in G$，方程组 $(E) : \dot{x} = f(t,x)$ 地满足初值条件 $x(\tau) = \xi$ 的饱和解存在且唯一，记为 $$x = \varphi(t, \tau, \xi)$$，设其存在区间为 $(a(\tau,\xi),b(\tau,\xi))$，则 $\varphi(t,\tau,\xi)$ 是集合 $$S = \{(t,\tau,\xi)|t\in(a(\tau,\xi),b(\tau,\xi)),(\tau,\xi) \in G\},(6.1)$$ 上的 $n + 2$ 元向量函数。（$t, \tau$ 一元，$\xi$ $n$ 元）



### 定理 6.1

若 $x = \psi(t)$ 是方程组 $(E)$ 的解，$[\alpha,\beta]$ 是其存在区间的任一有限子区间，则存在 $\delta > 0$，使得当 $$\tau \in [\alpha, \beta]，|\xi - \psi(\tau)| \leq \delta$$ 时，方程组 $(E)$ 的解 $x = \varphi(t, \tau, \xi)$ 至少在 $[\alpha, \beta]$ 上有定义，并且对 $(t, \tau, \xi)$ 是闭域 $$V = \{(t, \tau, \xi)| t\in [\alpha, \beta], \tau \in [\alpha,\beta], |\xi - \psi(\tau)| \leq \delta\}$$ 上的连续函数。

定理 6.1 在理论和应用上都有重要意义。我们知道，在实际应用中，微分方程往往描述某种物理过程。将一个物理过程化为微分方程的初值问题时，初值条件是通过测量确定的，而测量一般不能保证绝对准确。如果初值的微笑误差引起对应的解有很大变动，那么所求得得初值问题得解的使用价值就会很小。有了定理 6.1，这种情形就不会发生。

![image-20251128130815600](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130815600.png)

![image-20251128130827395](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130827395.png)

![image-20251128130836559](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130836559.png)

![image-20251128130845993](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130845993.png)



### 推论 6.1

若方程组 $(E)$ 的解 $x = \varphi(t,\tau_0,\xi_0)$ 在有限闭区间 $[\alpha,\beta]$ 上有定义，$\tau_0 \in (\alpha, \beta)$，则当 $(\tau,\xi)$ 与 $(\tau_0, \xi_0)$ 充分靠近时，解 $x = \varphi(t, \tau, \xi)$ 在 $[\alpha,\beta]$ 上有定义，且对 $t \in [\alpha,\beta]$ 一致地有 $$\lim_\limits{(\tau,\xi)\rightarrow(\tau_0, \xi_0)} \varphi(t,\tau,\xi) = \varphi(t, \tau_0, \xi_0)$$

> [!tip]
>
> 由 $\varphi(t,\tau,\xi)$ 是 $V$ 上的关于 $(t,\tau,\xi)$ 的连续函数，显然。



### 推论 6.2

方程组 $(E)$ 的解 $x = \varphi(t, \tau, \xi)$ 在由 $(6.1)$ 式表示的集合 $S$ 上连续。此外，$S$ 是 $(t,\tau,\xi)$ 空间上的开集。



---

下面考虑含参量 $\lambda$ 的方程组 $$\frac{dx}{dt} = f(t,x,\lambda),(E)_\lambda$$
设 $G$ 为 $(t,x)$ 空间的域，$D$ 为 $\lambda$ 空间的域，假设 $f(t,x,\lambda)$ 在 $$G \times D = \{(t,x,\lambda)|(t,x) \in G, \lambda \in D\}$$ 内连续，且对 $(x,\lambda)$ 局部地满足利氏条件，则根据存在与唯一性定理，对任意 $\lambda \in D$ 和 $(\tau,\xi) \in G$，初值问题 $(E)_\lambda,x(\tau) = \xi$ 的饱和解存在且唯一，记为 $x = \varphi(t,\tau,\xi,\lambda)$。



### 定理 6.2
设 $f(t,x,\lambda)$ 于域 $G\times D$ 内连续，且对 $(x, \lambda)$ 局部地满足利氏条件。若 $x = \psi(t)$ 是方程组 $(E)_{\lambda_0},\lambda_0 \in D$ 的一个解，$[\alpha,\beta]$ 是其存在区间的任一有限闭子区间，则存在 $\delta > 0$，使得 $x = \varphi(t,\tau,\xi,\lambda)$ 于闭域 $$V = \{(t,\tau,\xi,\lambda)| t,\tau \in [\alpha,\beta],|\xi - \psi(\tau)| + |\lambda - \lambda_0| \leq \delta\}$$ 上有定义且连续。

![image-20251128130801307](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130801307.png)

类似地有推论 6.3 和 推论 6.4


![image-20251128130736872](C:\Users\浪涛依旧铭记\AppData\Roaming\Typora\typora-user-images\image-20251128130736872.png)