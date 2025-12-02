# 一阶隐式方程——多元法显性表示

例：$(y')^2 - xy' + \frac{1}{2}x^2 - y = 0$。

一般形式 $f(x, y, y') = 0$。

四种特殊形式：

-   I) $y = f(x, y')$
-   II) $x = f(y, y')$
-   III) $f(x, y') = 0$
-   IV) $f(y, y') = 0$

## 类别 I) $y = f(x, y')$

例：$(y')^2 - xy' + \frac{1}{2}x^2 - y = 0$。

令 $p = y'$，$y = p^2 - xp + \frac{1}{2}x^2$。两边同时对 $x$ 求导

$$
p = 2p\frac{dp}{dx} - p - x\frac{dp}{dx} + x
$$

$$
\Rightarrow (2p - x)\frac{dp}{dx} = 2p - x
$$

1.  若 $2p = x$，$p = \frac{x}{2}$，代入可得 $y = \frac{x^2}{4}$ (不加 $C$)。
2.  若 $2p \neq x$，$\frac{dp}{dx} = 1$，$p = x + C$，$\Rightarrow y = \frac{1}{2}x^2 + Cx + C^2$。

---

## 类型 II：$x = f(y, y')$

令 $p = y'$，$x = f(y, p)$。

对 $y$ 求导 $\frac{dx}{dy} = f_y(y, p) + \frac{dp}{dy} f_p(y, p)$。

即

$$
\frac{1}{p} = f_y(y, p) + f_p(y, p) \frac{dp}{dy}
$$

解为 $p = w(y, C)$。

原方程解为 $x = f(y, p)$。

例：$(y^3 - 4xyy' + 8y^2) = 0$。

$$
x = \frac{1}{4} \left( \frac{y^3}{y'} \right) + 2 \frac{y}{y'}
$$

令 $p = y'$，两边对 $y$ 求导得

$$
\frac{1}{p} = \frac{1}{4} \left( \frac{y^3}{y} \right) + 2 \frac{y}{y^2}
$$

$$
\left( \frac{p}{2y} - \frac{2y}{p^2} \right) \frac{dp}{dy} = \frac{1}{4y^2} p^2 - \frac{1}{p}
$$

求：$x = \frac{1}{4} \frac{p^2}{y} + 2 \frac{y}{p}$。

---

1.  若 $\frac{p}{2y} = \frac{2y}{p^2}$，即 $p^3 = 4y^2$，得 $y = \frac{4}{27}x^3$（代入式）。
2.  若 $p^3 \neq 4y^2$，$\frac{1}{p} \cdot \frac{dp}{dy} = \frac{1}{2y}$，得 $p = C\sqrt{y}$。

代入求得。

---

## 类型 III：$F(x, y') = 0$

找到 $x, y$ 的参数表示（以 $t$ 为新的自变量）。

$$
\begin{cases}
x = \varphi(t), \\
y' = \psi(t).
\end{cases}
$$

能否直接积分？

$$
\frac{dy}{dt} = \frac{dy}{dx} \cdot \frac{dx}{dt} = y' \cdot \frac{dx}{dt} = \psi(t) \cdot \varphi'(t)
$$

然后对 $t$ 积分。

$$
y = \int \psi(t) \cdot \varphi'(t)  dt + C
$$

$$
x = \varphi(t)
$$

参数解。

例：解 $x^3 + y'^3 - xy' = 0$。

(设 $y' = tx$ )：

$$
x^3 + t^3x^3 - tx^2 = 0 \Rightarrow (t^3+1)x^3 = t x^2 \Rightarrow x = \frac{t}{t^3+1}
$$

$$
y' = tx = \frac{t^2}{t^3+1}
$$

$$
\frac{dy}{dt} = \frac{dy}{dx} \cdot \frac{dx}{dt} = y' \cdot \frac{dx}{dt} = \frac{t^2}{1+t^3} \cdot \frac{(t^3+1)-3t^3}{(1+t^3)^2} = \frac{t^2(1-2t^3)}{(1+t^3)^3}
$$

$$
y = \int \frac{t^2(1-2t^3)}{(1+t^3)^3} dt + C = \frac{1+4t^3}{6(1+t^3)^2} + C
$$

$$
x = \frac{t}{1+t^3}
$$

---

## 类型 IV：$f(y, y') = 0$

参数表示：

$$
\begin{cases}
y = \varphi(t) \\
y' = \psi(t)
\end{cases}
$$

$$
\frac{dx}{dt} = \frac{dx}{dy} \cdot \frac{dy}{dt} = \frac{1}{y'} \cdot \frac{dy}{dt} = \frac{1}{\psi(t)} \varphi'(t)
$$

$$
x = \int \frac{\varphi'(t)}{\psi(t)} dt + C
$$

$$
y = \varphi(t)
$$

例：

$$
y^2 (y - 1) = (2 - y')^2
$$

令 $2 - y' = y t$，

$y = 1 + t^2$？ $\Rightarrow y = \frac{1 - t^2}{t}$？ 我们重新推导：

令 $2 - y' = y t$，则 $y' = 2 - y t$。

由原方程 $y^2 (y - 1) = (yt)^2 \Rightarrow y^2(y-1) = y^2 t^2 \Rightarrow y-1 = t^2 \Rightarrow y = 1 + t^2$。

则 $y' = 2 - (1+t^2)t = 2 - t - t^3$。

又 $y' = \frac{dy}{dx} = 2t \frac{dt}{dx}$。

所以 $2t \frac{dt}{dx} = 2 - t - t^3$。

$$
\frac{dx}{dt} = \frac{2t}{2 - t - t^3}
$$

$$
x = \int \frac{2t}{2 - t - t^3} dt + C
$$

或另一种参数化（参考原文）：

原文取 $y = \frac{1 - t^2}{t}$，$y' = 1 + t^2$。

$$
\frac{dx}{dt} = \frac{dx}{dy} \cdot \frac{dy}{dt} = \frac{1}{y'} \cdot \frac{dy}{dt} = \frac{1}{1 + t^2} \cdot (-\frac{1}{t^2} - 1) = -\frac{1}{t^2}
$$

$$
x = \frac{1}{t} + C
$$

$$
y = \frac{1}{t} - t
$$

消去 $t$ $\rightarrow$ $y = (x - C) - \frac{1}{x - C}$。

---

例：$y = e^{\frac{xy'}{y}}$？ ($my = \frac{xy}{y}$ 原文不清)

1.  按 $y$ 解出 $y = x y' (m y')^{-1}$？
2.  按 $x$ 解出 $x = (m y')^{-1} y (y')^{-1}$？

($x$) $y = x y' (m y')^{-1}$？ 令 $p = y'$，$y = x p (m p)^{-1}$？ 对 $x$ 求导

$p = \frac{(m p)(p + x\frac{dp}{dx}) - x p m \frac{dp}{dx}}{(m p)^{2}}$

$p (m p)^{2} = m p (p + x\frac{dp}{dx}) - x p m \frac{dp}{dx}$

$\Rightarrow (m p - 1) x \frac{dp}{dx} = p m p (m p - 1)$

1.  $m p - 1 = 0 \Rightarrow p = \frac{1}{m} \Rightarrow y = \frac{x}{m}$？
2.  $m p - 1 \neq 0 \Rightarrow \frac{dp}{p m p} = \frac{dx}{x} \Rightarrow \frac{1}{m p} d(m p) = \frac{1}{x} dx$

$\Rightarrow \ln(m p) = \ln x + C$

$\Rightarrow p = \frac{1}{m} e^{C x} (c \neq 0)$。(带回原式)

$\Rightarrow y = \frac{x}{m} e^{C x} (c \neq 0)$？

(此页原文公式混乱，建议结合上下文理解或参考其他资料)

---

# 高阶方程的几种可积类型

## 类型 1

$F(x, y^{(n)}) = 0$

**若能解出**

$y^{(n)} = f(x)$

**积分 $n$ 次**

**若有参数形式**

$x = \varphi(t)$, $y^{(n)} = \psi(t)$

$\frac{dy^{(n-1)}}{dx} = y^{(n)} \rightarrow dy^{(n-1)} = y^{(n)} dx = \psi(t) d\varphi(t)$

$y^{(n)} = \frac{dy^{(n-1)}}{dx} = \frac{dy^{(n-1)}}{dt} \cdot \frac{dt}{dx} \Rightarrow dy^{(n-1)} = \frac{dx}{dt} \cdot y^{(n)} dt = \varphi'(t) \psi(t) dt$

$\Rightarrow x = \varphi(t)$, $y^{(n-1)} = \int \varphi'(t) \psi(t) dt + C_1$

**以此类推**

$y = \psi_{n}(t, C_{1}, C_{2}, \cdots, C_{n})$

**参数解**

$x = \varphi(t)$

---

## 类型 II

$F(x, y^{(k)}, y^{(k+1)}, y^{(k+2)})=0$, ($n>2$, 例如 $k=n-2$)。

**降阶法**：令 $z = y^{(k)}$。则 $F(x, z, z', z'')=0$ 为二阶隐方程。

1.  若不显含 $x$，$F(z, z', z'')=0$。

    令 $u = z'$。$F(z, u, u')=0$ (含 $z, u$)。

    $z'' = \frac{dz'}{dx} = \frac{du}{dx} = \frac{du}{dz} \cdot \frac{dz}{dx} = \frac{du}{dz} \cdot u$。

    $F(z, u, u \frac{du}{dz})=0$ 一阶隐方程。

2.  若不显含 $z$，$F(x, z', z'')=0$。

    令 $u = z'$，$F(x, u, u')=0$ (只含 $u, x$, 一阶隐方程)。

3.  若 $F$ 关于 $z, z', z''$ 是 $m$ 次齐次函数，即

    $F(x, t z, t z', t z'') = t^m F(x, z, z', z'')$

    令 $u = \frac{z'}{z}$，则 $z' = u z$。

    $z'' = u' z + u z' = (u' + u^2) z$

    $F(x, z, u z, (u' + u^2) z) = z^m F(x, 1, u, u' + u^2) = 0$。

---

例：$2y \cdot y'' = 1$。

令 $u = y'$

$y'' = \frac{dy'}{dx} = \frac{du}{dy} \cdot \frac{dy}{dx} = \frac{du}{dy} \cdot u$。

$\Rightarrow 2y \cdot \frac{du}{dy} \cdot u = 1$

$\Rightarrow 2u  du = \frac{1}{y} dy$

$\Rightarrow u^2 = \ln y + C_1$

$\Rightarrow u = \frac{dy}{dx} = \sqrt{\ln y + C_1}$

$\Rightarrow \frac{dy}{\sqrt{\ln y + C_1}} = dx$

或另一种思路（参数解）：由 $u^2 = \ln y + C_1 \Rightarrow y = e^{u^2 - C_1}$。

$\frac{dy}{dx} = u = 2u \frac{du}{dx} e^{u^2 - C_1}$，$\frac{dx}{du} = 2 e^{u^2 - C_1}$。

$\Rightarrow x = 2 e^{-C_1} \int e^{u^2} du + C_2$。参数解

$$
\begin{cases}
x = 2C \int e^{u^2} du + C_2 \\
y = C e^{u^2}
\end{cases}
$$ ($C = e^{-C_1}$)

---

例：$y''(1+y'^2)^{-3/2} = a > 0$。（曲率处处为常数 $a$ 的曲线方程）。

令 $u = y'$，$y'' = \frac{du}{dx} = \frac{du}{dy} \cdot \frac{dy}{dx} = u \frac{du}{dy}$。

$u \frac{du}{dy} (1+u^2)^{-3/2} = a$。

$u du = a (1+u^2)^{3/2} dy$？ 应重新推导：

$y'' = a (1+y'^2)^{3/2}$。

令 $u = y'$，则 $y'' = u \frac{du}{dy}$。

$u \frac{du}{dy} = a (1+u^2)^{3/2}$

$\frac{u du}{(1+u^2)^{3/2}} = a  dy$

积分得 $-\frac{1}{\sqrt{1+u^2}} = a y + C_1$，即 $(y + \frac{C_1}{a})^2 (1+u^2) = \frac{1}{a^2}$？ 更直接的是：

$-\frac{1}{\sqrt{1+u^2}} = a y + C_1$ $\Rightarrow$ $1+u^2 = \frac{1}{(a y + C_1)^2}$。

又 $u = \frac{dy}{dx}$，所以 $\frac{dy}{dx} = \pm \sqrt{ \frac{1}{(a y + C_1)^2} - 1 }$。

两边对 $x$ 求导？或由 $u = \frac{dy}{dx}$，且 $x = \int \frac{1}{u} dy$。

利用关系 $u = \frac{dy}{dx}$，且从 $-\frac{1}{\sqrt{1+u^2}} = a y + C_1$ 解出 $u$。

$1+u^2 = \frac{1}{(a y + C_1)^2}$ $\Rightarrow$ $u^2 = \frac{1 - (a y + C_1)^2}{(a y + C_1)^2}$。

$u = \frac{dy}{dx} = \frac{\sqrt{1 - (a y + C_1)^2}}{a y + C_1}$ ($\pm$ 号隐含在根号，决定单调性)

$\frac{dx}{dy} = \frac{a y + C_1}{\sqrt{1 - (a y + C_1)^2}}$

令 $z = a y + C_1$，则 $dz = a dy$，$dy = dz / a$。

$\frac{dx}{dz} = \frac{1}{a} \cdot \frac{z}{\sqrt{1-z^2}}$

$x = \frac{1}{a} \int \frac{z}{\sqrt{1-z^2}} dz + C_2 = -\frac{1}{a} \sqrt{1-z^2} + C_2 = -\frac{1}{a} \sqrt{1 - (a y + C_1)^2} + C_2$。

整理得 $(x - C_2)^2 + (y + \frac{C_1}{a})^2 = \frac{1}{a^2}$。即圆的方程。

---

# 解题的灵活性

## 方法 1：变量替换

例：

$\frac{dy}{dx} + \frac{y}{x} + 4x^2 y^2 + 1 = 0$

令 $u = xy$，

$du = x dy + y dx$

$\frac{du}{dx} = x \frac{dy}{dx} + y = x\left(-\frac{y}{x} - 4x^2 y^2 - 1\right) + y = -y - 4x^3 y^2 - x + y = -4x^3 y^2 - x = -4x u^2 / x^2 - x = -\frac{4u^2}{x} - x$

$\frac{du}{dx} = -x - \frac{4u^2}{x}$

这是伯努利方程吗？令 $v = u^{-1}$，$\frac{dv}{dx} = -u^{-2} \frac{du}{dx} = -u^{-2}(-x - \frac{4u^2}{x}) = \frac{x}{u^2} + \frac{4}{x} = x v^2 + \frac{4}{x}$。

$\frac{dv}{dx} - x v^2 = \frac{4}{x}$ (里卡蒂方程)。

(此例计算复杂，原文过程似有跳跃)

原文后续：

$\frac{du}{dx} = -x(4u+1)$？ (这与前面推导不符，可能原例有误或简化)

若 $\frac{du}{dx} = -x(4u+1)$，则 $\frac{du}{4u+1} = -x dx$。

$\frac{1}{4} \ln|4u+1| = -\frac{1}{2}x^2 + C$

$4u+1 = e^{-2x^2 + 4C}$

$u = \frac{1}{4}(K e^{-2x^2} - 1)$ ($K = e^{4C}$)

$y = \frac{u}{x} = \frac{1}{4x}(K e^{-2x^2} - 1)$。

---

**一般形式**：

$\frac{dy}{dx} = -\frac{y}{x} + f(xy)$

令 $u = xy$，

---

例：

$\frac{dy}{dx} = \frac{1}{x}(x e^y - 1) = e^y - \frac{1}{x}$

令 $u = e^y$

$\frac{du}{dx} = e^y \frac{dy}{dx} = u (e^y - \frac{1}{x}) = u (u - \frac{1}{x}) = u^2 - \frac{u}{x}$

$\frac{du}{dx} + \frac{u}{x} = u^2$

伯努利方程

令 $v = u^{-1}$，$\frac{dv}{dx} = -u^{-2} \frac{du}{dx} = -u^{-2}(u^2 - \frac{u}{x}) = -1 + \frac{1}{x u} = -1 + \frac{v}{x}$

$\frac{dv}{dx} - \frac{v}{x} = -1$

一阶线性方程。

积分因子 $\mu = e^{\int -\frac{1}{x} dx} = e^{-\ln x} = \frac{1}{x}$。

$\frac{d}{dx}(v \cdot \frac{1}{x}) = -1 \cdot \frac{1}{x} = -\frac{1}{x}$

$v \cdot \frac{1}{x} = -\ln x + C$

$v = -x \ln x + C x$

$u = \frac{1}{v} = \frac{1}{C x - x \ln x}$

$y = \ln u = -\ln(C x - x \ln x) = - \ln x - \ln(C - \ln x)$

---

**一般形式**：

$\frac{dy}{dx} = p(x) + q(x) e^{a y}$

令 $u = e^{a y}$

---

例：

$\frac{dy}{dx} = (x^2 + y^2) / y$？ 原文为 $\frac{dy}{dx} = (x^2 + y^2) + y$？ 假设为 $\frac{dy}{dx} = \frac{x^2 + y^2}{y}$

$= \frac{x^2}{y} + y$

令 $u = \frac{y}{x}$，$y = u x$，$dy = u dx + x du$

$\frac{dy}{dx} = u + x \frac{du}{dx} = \frac{x^2}{u x} + u x = \frac{x}{u} + u x$

$\Rightarrow x \frac{du}{dx} = \frac{x}{u} + u x - u = \frac{x}{u} + u(x - 1)$

$\frac{du}{dx} = \frac{1}{u} + u(1 - \frac{1}{x})$

(非标准形式)

原文另一例：$\frac{dy}{dx} = x (x + \frac{y}{x})^2 + \frac{y}{x}$

令 $u = \frac{y}{x}$，$y = u x$，$\frac{dy}{dx} = u + x \frac{du}{dx}$

$u + x \frac{du}{dx} = x (x+u)^2 + u$

$\Rightarrow x \frac{du}{dx} = x (x+u)^2$

$\Rightarrow \frac{du}{dx} = (x+u)^2$

令 $z = x+u$，则 $\frac{dz}{dx} = 1 + \frac{du}{dx} = 1 + z^2$

$\frac{dz}{1+z^2} = dx$

$\arctan z = x + C$

$z = \tan(x + C)$

$u = z - x = \tan(x + C) - x$

$y = x u = x \tan(x + C) - x^2$

---

**一般形式**

$\frac{dy}{dx} = x f(a x + b \frac{y}{x}) + \frac{y}{x}$

---

例：

$\frac{dy}{dx} = 6x \sqrt{x^4 + y}$

$\frac{dy}{dx^2} = 3 \sqrt{x^4 + y}$？ 令 $t = x^2$，则 $\frac{dy}{dt} = \frac{dy}{dx} \cdot \frac{dx}{dt} = \frac{dy}{dx} \cdot \frac{1}{2x}$。

由原式 $\frac{dy}{dx} = 6x \sqrt{x^4 + y}$，所以 $\frac{dy}{dt} = \frac{1}{2x} \cdot 6x \sqrt{x^4 + y} = 3 \sqrt{t^2 + y}$。

$\frac{dy}{dt} = 3 \sqrt{t^2 + y}$

令 $u = \sqrt{t^2 + y}$，则 $y = u^2 - t^2$，$\frac{dy}{dt} = 2u \frac{du}{dt} - 2t$。

代入：$2u \frac{du}{dt} - 2t = 3u$

$2u \frac{du}{dt} = 3u + 2t$

$\frac{du}{dt} = \frac{3}{2} + \frac{t}{u}$

齐次方程。令 $z = \frac{u}{t}$，则 $u = z t$，$\frac{du}{dt} = z + t \frac{dz}{dt}$。

$z + t \frac{dz}{dt} = \frac{3}{2} + \frac{1}{z}$

$t \frac{dz}{dt} = \frac{3}{2} + \frac{1}{z} - z = \frac{3z + 2 - 2z^2}{2z}$

$\frac{2z dz}{3z + 2 - 2z^2} = \frac{dt}{t}$

积分求解。

结果（原文）：$(\sqrt{x^4 + y} - 2x^2)(2\sqrt{x^4 + y} + x^2) = C$

---

例：

$\frac{dy}{dx} = y^2 - \frac{2}{x^2}$ (令 $u = \frac{1}{y}$)

$du = -\frac{1}{y^2} dy$

$\frac{du}{dx} = -\frac{1}{y^2} \left( y^2 - \frac{2}{x^2} \right) = -1 + \frac{2}{x^2 y^2} = -1 + \frac{2u^2}{x^2}$

$\frac{du}{dx} - \frac{2}{x^2} u^2 = -1$ (里卡蒂方程)。

解：$y = \frac{1 - 2C x^3}{x + C x^4}$？ 验证：

$y' = \frac{ (-6C x^2)(x+C x^4) - (1-2C x^3)(1+4C x^3) }{(x+C x^4)^2}$

$y^2 = \frac{(1-2C x^3)^2}{(x+C x^4)^2}$

$y^2 - \frac{2}{x^2} = \frac{(1-2C x^3)^2 - 2(x+C x^4)^2 / x^2}{(x+C x^4)^2} = \frac{(1-2C x^3)^2 - 2(1+C x^3)^2}{(x+C x^4)^2}$

计算分子：$(1 - 4C x^3 + 4C^2 x^6) - 2(1 + 2C x^3 + C^2 x^6) = 1 - 4C x^3 + 4C^2 x^6 - 2 - 4C x^3 - 2C^2 x^6 = -1 - 8C x^3 + 2C^2 x^6$

与 $y'$ 的分子比较：$(-6C x^2)(x+C x^4) = -6C x^3 - 6C^2 x^6$；$(1-2C x^3)(1+4C x^3) = 1 + 4C x^3 - 2C x^3 - 8C^2 x^6 = 1 + 2C x^3 - 8C^2 x^6$。

$y'$ 分子：$(-6C x^3 - 6C^2 x^6) - (1 + 2C x^3 - 8C^2 x^6) = -6C x^3 - 6C^2 x^6 -1 -2C x^3 + 8C^2 x^6 = -1 -8C x^3 + 2C^2 x^6$。匹配。

---

## 方法 2：交换 $x$ 和 $y$ 的位置

例：

$\frac{dy}{dx} = \frac{y}{x + y + y e^y}$

$\frac{dx}{dy} = \frac{x + y + y e^y}{y} = \frac{x}{y} + 1 + e^y$

$\Rightarrow \frac{dx}{dy} - \frac{x}{y} = 1 + e^y$

一阶线性方程。

积分因子 $\mu = e^{\int -\frac{1}{y} dy} = e^{-\ln y} = \frac{1}{y}$。

$\frac{d}{dx}(x \cdot \frac{1}{y}) = (1 + e^y) \cdot \frac{1}{y} = \frac{1}{y} + \frac{e^y}{y}$

$x \cdot \frac{1}{y} = \int \left( \frac{1}{y} + \frac{e^y}{y} \right) dy = \ln |y| + \int \frac{e^y}{y} dy$ (指数积分)

$x = y (\ln |y| + \text{Ei}(y) + C)$

另解 $y = 0$。

---

## 方法 3：改变方程的形式

例：

$\frac{dy}{dx} = \frac{x - y + 2}{x + y - 4}$？ 原文为 $x + y^2 + 4$，疑误。按常见类型。

$(x + y - 4) dy = (x - y + 2) dx$

$(x + y - 4) dy - (x - y + 2) dx = 0$

$M = -(x - y + 2)$, $N = x + y - 4$

$M_y = 1$, $N_x = 1$，$M_y = N_x$，恰当微分方程。

---

例：

$(\ln x + x y) dx + 2x y dy = 0$？ 原文为 $C \ln x + xy^2 dx + 2xy^2 dy = 0$，不清。

$\frac{dy}{dx} = -\frac{\ln x + x y}{2x y}$ $\Rightarrow$ $\frac{d(y^2)}{dx} = 2y \frac{dy}{dx} = 2y \left( -\frac{\ln x + x y}{2x y} \right) = -\frac{\ln x + x y}{x}$

令 $u = y^2$，则 $\frac{du}{dx} = -\frac{\ln x}{x} - u$。

$\frac{du}{dx} + u = -\frac{\ln x}{x}$

一阶线性方程。

---

例：$y' = 2\sqrt{y} - \frac{x}{2}$？ 原文 $P_{3} = 8 \cdot \frac{dy}{dx} = 2\sqrt{y} - \frac{x}{2}$ 不清。

令 $u = \sqrt{y}$

$\frac{du}{dx} = \frac{1}{2\sqrt{y}} \frac{dy}{dx} = \frac{1}{2u} (2u - \frac{x}{2}) = 1 - \frac{x}{4u}$

注意特解 $y = \frac{x^2}{16}$？ ($\sqrt{y} = \frac{x}{4}$，代入 $y' = \frac{x}{8}$，右边 $2(\frac{x}{4}) - \frac{x}{2} = \frac{x}{2} - \frac{x}{2} = 0$，不匹配)。可能原方程是 $y' = 2\sqrt{y} - x$？

若 $y' = 2\sqrt{y} - x$，令 $u=\sqrt{y}$，$\frac{du}{dx} = \frac{1}{2u}(2u - x) = 1 - \frac{x}{2u}$。

$\frac{du}{dx} = 1 - \frac{x}{2u}$

---

# 第三章 线性微分方程组

## 记号

$$
\begin{aligned}
\frac{dx_1}{dt} &= a_{11}(t)x_1 + \cdots + a_{1n}(t)x_n + f_1(t) \\
&\vdots \\
\frac{dx_n}{dt} &= a_{n1}(t)x_1 + \cdots + a_{nn}(t)x_n + f_n(t)
\end{aligned}
$$

$a_{ij}(t), f_i(t)$ 为区间 $I$ 上的连续函数。

$$
X(t) =
\begin{bmatrix}
x_1(t) \\
\vdots \\
x_n(t)
\end{bmatrix}, \quad \frac{dX}{dt} =
\begin{bmatrix}
\frac{dx_1}{dt} \\
\vdots \\
\frac{dx_n}{dt}
\end{bmatrix}
$$

$$
A(t) =
\begin{bmatrix}
a_{11}(t) & \cdots & a_{1n}(t) \\
\vdots & \ddots & \vdots \\
a_{n1}(t) & \cdots & a_{nn}(t)
\end{bmatrix}, \quad f(t) =
\begin{bmatrix}
f_1(t) \\
\vdots \\
f_n(t)
\end{bmatrix}
$$

$$
\frac{dX}{dt} = A(t) X + f(t)
$$

- 当 $f(t) \equiv 0$， $\frac{dX}{dt} = A(t) X$，**齐次线性微分方程组**，记作 $LH$。
- 当 $f(t) \not\equiv 0$， $\frac{dX}{dt} = A(t) X + f(t)$ **非齐次线性微分方程组**，记作 $NH$。

**初值问题**：

$$
X_i(t_0) = \xi_i, \quad i = 1, 2, \cdots, n
$$

$$
X(t_0) = \xi =
\begin{bmatrix}
\xi_1 \\
\xi_2 \\
\vdots \\
\xi_n
\end{bmatrix}
$$

- 矩阵（向量）函数是连续（可微），指每个分量连续（可微）。
- 导数、积分定义为对各分量求导、积分。

**范数**：

记 $|x| = \sum_{i=1}^n |x_i|$。 ($l_1$ 范数)

$|A| = \sum_{i=1}^n \sum_{j=1}^n |a_{ij}|$。 (矩阵的 $l_1$ 范数)

**性质**：

- $|A x| \le |A| \cdot |x|$
- $|x + y| \le |x| + |y|$, $|A + B| \le |A| + |B|$
- $|A B| \le |A| \cdot |B|$
- 若 $x(t)$ 是向量函数，在 $[a,b]$ 上连续
    $\left| \int_{a}^{b} x(t) dt \right| \le \int_{a}^{b} |x(t)| dt$

---

- 向量函数序列 $\{x_k(t)\}$ 收敛，如果每个分量函数序列收敛。
- 向量函数级数 $\sum_{k=1}^{\infty} x_k(t)$ 在 $I$ 上收敛，如果部分和 $S(K,t) = \sum_{m=1}^{K} x_m(t)$ 构成的向量函数序列在 $I$ 上收敛。

**★ Weierstrass 判别法** (判断向量函数级数一致收敛)：
如果 $|x_k(t)| \le M_k$, $\forall t \in I$, 而且正项级数 $\sum_{k=1}^{\infty} M_k$ 收敛，
则函数级数 $\sum_{k=1}^{\infty} x_k(t)$ 在 $I$ 上一致收敛。

---

**定理 2.1** 设 $\frac{dX}{dt} = A(t) X + f(t)$。 $A(t)$, $f(t)$ 都在区间 $I$ 上连续，则对任意 $t_0 \in I$, 任意的 $n$ 维常向量 $\xi$, 方程 $NH$ 恒有定义在 $I$ 上的满足初值条件 $X(t_0) = \xi$ 的解，且这样的解唯一。

**思路**：

1.  构造皮卡序列 $\{\varphi_0(t), \varphi_1(t), \cdots, \varphi_k(t), \cdots\}$。

    $$
    \begin{aligned}
    \varphi_0(t) &= \xi \\
    \varphi_k(t) &= \xi + \int_{t_0}^t \left( A(s) \varphi_{k-1}(s) + f(s) \right) ds \quad (k \ge 1)
    \end{aligned}
    $$

    (等价于积分方程 $X(t) = \xi + \int_{t_0}^t (A(s) X(s) + f(s)) ds$)

2.  证明函数列 $\{\varphi_k(t)\}$ 一致收敛（通过将其写为级数形式 $\varphi_k(t) = \varphi_0(t) + \sum_{m=1}^k (\varphi_m(t) - \varphi_{m-1}(t))$，并估计差项）。

    利用 Weierstrass 判别法，可得 $|\varphi_m(t) - \varphi_{m-1}(t)| \le \frac{(K |t-t_0|)^m}{m!}$ ($K$ 为 $A(t)$ 在区间上的界)。

    $\sum_{m=1}^{\infty} \frac{(K |t-t_0|)^m}{m!}$ 收敛 $\Rightarrow$ $\sum_{m=1}^{\infty} |\varphi_m(t) - \varphi_{m-1}(t)|$ 一致收敛 $\Rightarrow$ $\{\varphi_k(t)\}$ 一致收敛。

3.  极限函数 $\varphi(t) = \lim_{k \to \infty} \varphi_k(t)$ 是原方程的解。

4.  唯一性：设 $\varphi(t)$, $\psi(t)$ 是同一初值问题的两个解。

    $\varphi(t) - \psi(t) = \int_{t_0}^t A(s) (\varphi(s) - \psi(s)) ds$

    $|\varphi(t) - \psi(t)| \le \int_{t_0}^t |A(s)| \cdot |\varphi(s) - \psi(s)| ds$

    设 $N = \sup |A(s)|$ (在 $t$, $t_0$ 附近)，则

    $|\varphi(t) - \psi(t)| \le N \int_{t_0}^t |\varphi(s) - \psi(s)| ds$

    反复代入，可得 $|\varphi(t) - \psi(t)| \le \frac{N^m (t-t_0)^m}{m!} \sup |\varphi(s)-\psi(s)| \to 0$ ($m \to \infty$)。

    故 $\varphi(t) \equiv \psi(t)$。

---

**推论 2.1** $LH$ ($\frac{dX}{dt} = A(t) X$) 的解若在区间 $I$ 上某点为 $0$，则在 $I$ 上恒为零。

**推论 2.2** 若 $\varphi(t,t_0,\xi)$ 是 $LH$ 上定义的解，则 $\varphi(t,t_0,\xi_1+\xi_2) = \varphi(t,t_0,\xi_1) + \varphi(t,t_0,\xi_2)$？ (线性性)

实际上，对于 $LH$，解满足线性性质：若 $X_1(t)$, $X_2(t)$ 是解，则 $C_1 X_1(t) + C_2 X_2(t)$ 也是解。

构建 $\varphi(t) = \varphi(t,t_0,\xi_1+\xi_2) - \varphi(t,t_0,\xi_1) - \varphi(t,t_0,\xi_2)$，则 $\varphi(t_0)=0$，由推论 2.1，$\varphi(t) \equiv 0$。

---

设 $A(t)$, $f(t)$ 是周期为 $\omega$ 的周期函数，$X = \varphi(t)$ 是 $NH$ 的解。
那么 $\varphi(t)$ 是以 $\omega$ 为周期的周期解的充要条件是 $\varphi(\omega) = \varphi(0)$。

---

## 齐次方程 ($LH$) 解的结构

**引理**：设 $t \in I$，$\varphi_1(t),\varphi_2(t),\cdots,\varphi_m(t)$ 是 $(LH)$ 在区间 $I$ 上的 $m$ 个解。
则 $\varphi_1(t),\varphi_2(t),\cdots,\varphi_m(t)$ 在 $I$ 上线性相关当且仅当向量组 $\varphi_1(t_0),\varphi_2(t_0),\cdots,\varphi_m(t_0)$ 线性相关 ($t_0 \in I$ 任意)。

**定理 3.1** $(LH)$ 于区间 $I$ 上存在 $n$ 个线性无关的解。如果 $\varphi_1(t),\varphi_2(t),\cdots,\varphi_n(t)$ 是 $(LH)$ 在 $I$ 上的 $n$ 个线性无关的解（称为**基本解组**），则

$$
X = \sum_{i=1}^{n} C_i \varphi_i(t)
$$

是 $(LH)$ 的全部解（**通解**）。

$(LH)$ 的解的集合构成一个 $n$ 维线性空间。

以 $(LH)$ 的 $n$ 个线性无关解作为列向量，得到 $(LH)$ 的**基本解矩阵** $\Phi(t) = [\varphi_1(t), \varphi_2(t), \cdots, \varphi_n(t)]$。

通解可写为

$$
X = \Phi(t) C, \quad C = (C_1, C_2, \cdots, C_n)^T
$$

---

$$
\frac{d\Phi(t)}{dt} = A(t) \Phi(t), \quad t \in I
$$

$$
\det \Phi(t) \neq 0, \quad t \in I
$$

**证明**：若 $\exists t_0 \in I$, $\det \Phi(t_0)=0$，则列向量 $\varphi_1(t_0), \cdots, \varphi_n(t_0)$ 线性相关。由引理，$\varphi_1(t), \cdots, \varphi_n(t)$ 在 $I$ 上线性相关，矛盾。

---

**朗斯基行列式**:

$$
W(t) = \det \Phi(t) =
\begin{vmatrix}
\varphi_{11}(t) & \varphi_{12}(t) & \cdots & \varphi_{1n}(t) \\
\varphi_{21}(t) & \varphi_{22}(t) & \cdots & \varphi_{2n}(t) \\
\vdots & \vdots & \ddots & \vdots \\
\varphi_{n1}(t) & \varphi_{n2}(t) & \cdots & \varphi_{nn}(t)
\end{vmatrix}
$$

**引理 3.3 刘维尔公式**：$\varphi_{1}(t), \varphi_{2}(t), \cdots, \varphi_{n}(t)$ 是 $(LH)$ 的解。

$$
W(t) = W(t_0) \exp\left\{ \int_{t_0}^{t} \operatorname{tr} A(s)  ds \right\}, \quad t \in I
$$

$t_0 \in I$ 任意取定，$\operatorname{tr} A(s) = a_{11}(s) + a_{22}(s) + \cdots + a_{nn}(s)$。

**证明**:

行列式求导公式：

$$
\frac{dW(t)}{dt} = \sum_{i=1}^{n}
\begin{vmatrix}
\varphi_{11}(t) & \cdots & \varphi_{1n}(t) \\
\vdots & \ddots & \vdots \\
\varphi_{i1}'(t) & \cdots & \varphi_{in}'(t) \\
\vdots & \ddots & \vdots \\
\varphi_{n1}(t) & \cdots & \varphi_{nn}(t)
\end{vmatrix}
= \sum_{i=1}^{n} W_i(t)
$$

$(\varphi_j(t))$ 为解，$\varphi_j'(t) = A(t) \varphi_j(t)$，即 $\varphi_{ij}'(t) = \sum_{k=1}^{n} a_{ik}(t) \varphi_{kj}(t)$。

$$\Rightarrow W_i(t) = \sum_{k=1}^{n} a_{ik}(t) \cdot
\begin{vmatrix}
\varphi_{11}(t) & \cdots & \varphi_{1n}(t) \\
\vdots & \ddots & \vdots \\
\varphi_{k1}(t) & \cdots & \varphi_{kn}(t) \\
\vdots & \ddots & \vdots \\
\varphi_{n1}(t) & \cdots & \varphi_{nn}(t)
\end{vmatrix}
$$ (将第 $i$ 行用第 $k$ 行替换？ 注意行列式性质)

实际上，将 $\varphi_{ij}'(t) = \sum_{k} a_{ik} \varphi_{kj}$ 代入 $W_i(t)$ 的行列式中，由于行列式是线性的，可以拆开。但只有 $k=i$ 的那一项对应的行列式等于 $W(t)$ (因为替换的是同一行)，其他项 $k \neq i$ 对应的行列式有两行成比例，值为 $0$。

所以 $W_i(t) = a_{ii}(t) W(t)$。

因此

$$
\frac{dW(t)}{dt} = \sum_{i=1}^{n} a_{ii}(t) W(t) = [\operatorname{tr} A(t)] W(t)
$$

这是一个一阶线性方程，解为 $W(t) = W(t_0) \exp\left\{ \int_{t_0}^{t} \operatorname{tr} A(s) ds \right\}$。

---

**推论**：

1.  若 $\exists t_0 \in I, W(t_0) = 0$，则 $W(t) \equiv 0$。
2.  判断 $n$ 个解是否线性无关，只需验证 $W(t)$ 在某一点不为 $0$。

---

设 $\Phi(t)$, $\Psi(t)$ 都为基本解矩阵，则存在非奇异常数矩阵 $C$，使得

$\Psi(t) \equiv \Phi(t) \cdot C \quad \forall t \in I$。

**证明**：$\Psi(t) = [\psi_1(t) \cdots \psi_n(t)]$，每个 $\psi_j(t)$ 可表示为 $\Phi(t) c_j$，$c_j$ 为常数列向量。

则 $\Psi(t) = \Phi(t) [c_1 \cdots c_n] = \Phi(t) C$。且 $\det C \neq 0$ (因为 $\det \Psi(t) = \det \Phi(t) \cdot \det C \neq 0$)。

---

设 $\tau \in I$，若 $(LH)$ 的基本解矩阵 $\Phi(t)$ 满足 $\Phi(\tau) = E$ (单位矩阵)，则称 $\Phi(t)$ 为**状态转移矩阵**，记为 $\Phi(t, \tau)$。

对任意基本解矩阵 $\Phi(t)$，$\Phi(t, \tau) = \Phi(t) \cdot \Phi^{-1}(\tau)$。

**性质**：

1.  $\Phi(t, \tau)$ 是基本解矩阵，且 $\Phi(\tau, \tau) = E$。
2.  $\Phi(t, \tau)$ 与基本解矩阵的选取无关。
3.  $\Phi(t, s) \Phi(s, \tau) = \Phi(t, \tau)$。
4.  $[\Phi(t, \tau)]^{-1} = \Phi(\tau, t)$。

---

## 非齐次方程 ($NH$) 解的结构

**定理**：任意 $NH$ 的解都可表示为一个特解与 $LH$ 通解之和。

$NH$ 的解集合中最多有 $n+1$ 个线性无关的解？ (实际上，$NH$ 的解集是一个 $n$ 维仿射空间，不存在 $n+1$ 个线性无关的解)

设 $\Phi(t)$ 是 $LH$ 的基本解矩阵，则 $NH$ 的全部解可以表示为

$$
X = \Phi(t) \left( C + \int_{t_0}^{t} \Phi^{-1}(s) f(s)  ds \right)
$$

其中 $C$ 为 $n$ 维常向量，$t_0 \in I$ 任意。

**证明**：常数变易法。

$LH$ 通解为 $X = \Phi(t) C$。考虑 $NH$ 解为 $X = \Phi(t) C(t)$。

$$
\frac{d}{dt} (\Phi(t) C(t)) = \frac{d\Phi(t)}{dt} C(t) + \Phi(t) \frac{dC(t)}{dt} = A(t) \Phi(t) C(t) + \Phi(t) \frac{dC(t)}{dt}
$$

这应等于 $A(t) X + f(t) = A(t) \Phi(t) C(t) + f(t)$。

所以 $\Phi(t) \frac{dC(t)}{dt} = f(t)$ $\Rightarrow$ $\frac{dC(t)}{dt} = \Phi^{-1}(t) f(t)$。

$\Rightarrow C(t) = C + \int_{t_0}^{t} \Phi^{-1}(s) f(s)  ds$。

---

## 线性方程的复数解

- 实变量复值函数

$f(t) = U(t) + i V(t)$

- 复指数函数定义：

$e^{\lambda t} = 1 + \lambda t + \frac{(\lambda t)^2}{2!} + \frac{(\lambda t)^3}{3!} + \cdots$ ($\lambda$ 可为复数)

性质：$e^{\lambda_1 t + \lambda_2 t} = e^{\lambda_1 t} e^{\lambda_2 t}$，$\frac{d}{dt} e^{\lambda t} = \lambda e^{\lambda t}$。

---

例：

$\frac{d}{dt} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ -1 & 0 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$

复值解：$X = \begin{bmatrix} \cos t + i \sin t \\ -\sin t + i \cos t \end{bmatrix} = \begin{bmatrix} e^{i t} \\ i e^{i t} \end{bmatrix}$

---

- 复系数线性方程

$\frac{dX}{dt} = A(t) X + f(t)$

$A(t) = A_1(t) + i A_2(t)$, $f(t) = f_1(t) + i f_2(t)$

有复值解 $X(t) = U(t) + i V(t)$，代入原方程。

**定理** (实部虚部分解原理)：

1.  若 $X(t) = U(t) + i V(t)$ 是复系数 $NH$ 的解，则 $U(t)$ 是实部方程 $\frac{dX}{dt} = A_1(t) X + f_1(t)$ 的解？ (不完全正确)

    实际上，将实部虚部分开：

    $\frac{dU}{dt} + i \frac{dV}{dt} = (A_1 + i A_2)(U + i V) + (f_1 + i f_2) = (A_1 U - A_2 V + f_1) + i (A_2 U + A_1 V + f_2)$

    所以
    $$
    \begin{cases}
    \frac{dU}{dt} = A_1 U - A_2 V + f_1 \\
    \frac{dV}{dt} = A_2 U + A_1 V + f_2
    \end{cases}
    $$

    这是一个实变量的实系数方程组。

2.  若 $LH$ 有 $n$ 个线性无关的复解，则它们的实部和虚部可以组合出 $2n$ 个实函数，但其中只有 $n$ 个是线性无关的实解。

---

## 边值问题

$$
\frac{dX}{dt} = A(t) X + f(t)
$$

两点边值条件，例如：

- 周期边值条件：$X(a) = X(b)$
- 一般线性边值条件：$M X(a) + N X(b) = 0$

边值问题不一定有解，解也不一定唯一。

---

### 周期边值问题

$X(a) = X(b)$

通解 $X(t) = \Phi(t) \left[ C + \int_{a}^{t} \Phi^{-1}(s) f(s) ds \right]$。

$X(a) = \Phi(a) C$
$X(b) = \Phi(b) \left[ C + \int_{a}^{b} \Phi^{-1}(s) f(s) ds \right]$

周期条件 $X(a)=X(b)$ $\Rightarrow$ $\Phi(a) C = \Phi(b) \left[ C + \int_{a}^{b} \Phi^{-1}(s) f(s) ds \right]$

$\Rightarrow (\Phi(a) - \Phi(b)) C = \Phi(b) \int_{a}^{b} \Phi^{-1}(s) f(s) ds$

若 $(\Phi(a) - \Phi(b))$ 可逆，则 $C$ 可被唯一确定，边值问题有唯一解。

---

**定理 5.1** 方程 $LH$ 的周期边值问题仅有平凡解 $X=0$，则对任意 $f(t)$，方程 $NH$ 的周期边值问题有唯一解。

(即齐次问题只有零解 $\Rightarrow$ 非齐次问题有唯一解)

---

### 两点边值条件

$M X(a) + N X(b) = 0$

类似地，若 $M \Phi(a) + N \Phi(b)$ 可逆，则可唯一确定 $C$。

---

## 周期解

**问题**：$A(t)$，$f(t)$ 周期为 $\omega > 0$，问 $NH$ 是否存在周期为 $\omega$ 的周期解？

**引理**：$A(t)$，$f(t)$ $\omega$-周期，$X(t)$ 是 $NH$ 的解，则 $X(t+\omega)$ 也是 $NH$ 的解。

**引理**：$A(t)$，$f(t)$ $\omega$-周期，$X(t)$ 是 $NH$ 的解，则 $X(t)$ 是 $\omega$ 周期解 $\Leftrightarrow$ $X(\omega) = X(0)$。

---

**定理 5.2** $A(t)$，$f(t)$ 为 $\mathbb{R}$ 上 $\omega$-周期，则 $NH$ 存在 $\omega$-周期解 $\Leftrightarrow$ $NH$ 在 $\mathbb{R}$ 上有一个有界解。

**证明思路**：设 $X_0(t)$ 是一个有界解，则 $X_0(t+k\omega)$ 也为解。

由解的表达形式及周期条件，可推导出周期解存在的条件。

若 $X_0(t)$ 不是周期解，假设 $NH$ 存在有界非周期解，通过考虑序列 $X_0(k\omega)$ 并利用状态转移矩阵的性质，可推出矛盾（无界）。

---

# 高阶线性方程

形式：

$$
\frac{d^n x}{dt^n} + a_1(t) \frac{d^{n-1} x}{dt^{n-1}} + \cdots + a_{n-1}(t) \frac{dx}{dt} + a_n(t) x = f(t)
$$

可化为一阶方程组。

---

## 求解方法

### 变量替换

例：二阶方程 $\frac{d^2 x}{dt^2} + a(t) \frac{dx}{dt} + b(t) x = f(t)$

令 $x = \varphi(t) y$

$$
\begin{aligned}
\frac{dx}{dt} &= \varphi'(t) y + \varphi(t) \frac{dy}{dt} \\
\frac{d^2 x}{dt^2} &= \varphi''(t) y + 2 \varphi'(t) \frac{dy}{dt} + \varphi(t) \frac{d^2 y}{dt^2}
\end{aligned}
$$

代入原方程：

$$
\varphi(t) \frac{d^2 y}{dt^2} + [2 \varphi'(t) + a(t) \varphi(t)] \frac{dy}{dt} + [\varphi''(t) + a(t) \varphi'(t) + b(t) \varphi(t)] y = f(t)
$$

1.  若 $\varphi(t)$ 为 $LH$ ($f=0$) 的解，则 $\varphi''(t) + a(t) \varphi'(t) + b(t) \varphi(t) = 0$。

    方程变为 $\varphi(t) \frac{d^2 y}{dt^2} + [2 \varphi'(t) + a(t) \varphi(t)] \frac{dy}{dt} = f(t)$。

    令 $z = \frac{dy}{dt}$，则 $\varphi(t) \frac{dz}{dt} + [2 \varphi'(t) + a(t) \varphi(t)] z = f(t)$，一阶线性方程。

---

例：

$t(t-1) \frac{d^2 x}{dt^2} - 2t \frac{dx}{dt} + 2x = 0$

特解 $x = t$。令 $x = t y$

$$
\begin{aligned}
\frac{dx}{dt} &= y + t \frac{dy}{dt} \\
\frac{d^2 x}{dt^2} &= 2 \frac{dy}{dt} + t \frac{d^2 y}{dt^2}
\end{aligned}
$$

代入：

$t(t-1) (2 \frac{dy}{dt} + t \frac{d^2 y}{dt^2}) - 2t (y + t \frac{dy}{dt}) + 2t y = 0$

$2t(t-1) \frac{dy}{dt} + t^2(t-1) \frac{d^2 y}{dt^2} - 2t y - 2t^2 \frac{dy}{dt} + 2t y = 0$

$t^2(t-1) \frac{d^2 y}{dt^2} + [2t(t-1) - 2t^2] \frac{dy}{dt} = 0$

$t^2(t-1) \frac{d^2 y}{dt^2} - 2t \frac{dy}{dt} = 0$

令 $z = \frac{dy}{dt}$，则 $t^2(t-1) \frac{dz}{dt} - 2t z = 0$。

$\frac{dz}{z} = \frac{2}{t(t-1)} dt = 2(\frac{1}{t-1} - \frac{1}{t}) dt$

$\ln |z| = 2(\ln|t-1| - \ln|t|) + C_1$

$z = C_1 \frac{(t-1)^2}{t^2}$

$\frac{dy}{dt} = C_1 \left(1 - \frac{2}{t} + \frac{1}{t^2}\right)$

$y = C_1 (t - 2\ln|t| - \frac{1}{t}) + C_2$

$x = t y = C_1 (t^2 - 2t \ln|t| - 1) + C_2 t$

---

2.  若选择 $\varphi(t)$ 使得 $2 \varphi'(t) + a(t) \varphi(t) = 0$，则 $\varphi(t) = e^{-\frac{1}{2} \int a(t) dt}$。

    方程变为 $\varphi(t) \frac{d^2 y}{dt^2} + [\varphi''(t) + a(t) \varphi'(t) + b(t) \varphi(t)] y = f(t)$。

    可能简化。

---

例：方程 $\frac{d^2 x}{dt^2} + \sin t \frac{dx}{dt} + \frac{1}{4}(\sin^2 t + 2\cos t + 4) x = 0$

令 $\varphi(t) = e^{-\frac{1}{2} \int \sin t  dt} = e^{\frac{1}{2} \cos t}$

$x = \varphi(t) y$

计算略，结果可化为 $\frac{d^2 y}{dt^2} + y = 0$。

---

### 欧拉方程

$$
t^n \frac{d^n x}{dt^n} + a_1 t^{n-1} \frac{d^{n-1} x}{dt^{n-1}} + \cdots + a_{n-1} t \frac{dx}{dt} + a_n x = 0
$$

利用变量替换 $t = \begin{cases} e^s, & t > 0 \\ -e^s, & t < 0 \end{cases}$，令 $D = \frac{d}{ds}$。

则 $t \frac{dx}{dt} = D x$，$t^2 \frac{d^2 x}{dt^2} = D(D-1) x$，$\cdots$，$t^k \frac{d^k x}{dt^k} = D(D-1)\cdots(D-k+1) x$。

代入后化为常系数线性方程。

---

例：解 $t^2 \frac{d^2 x}{dt^2} - 4t \frac{dx}{dt} + 6x = t + t^2 \ln t$，$t>0$。

令 $t = e^s$，则 $D = \frac{d}{ds}$。

$t \frac{dx}{dt} = D x$
$t^2 \frac{d^2 x}{dt^2} = D(D-1) x$

代入：

$D(D-1)x - 4D x + 6x = e^s + s e^{2s}$

$(D^2 - 5D + 6)x = e^s + s e^{2s}$

特征方程 $r^2 - 5r + 6=0$，根 $r=2,3$。齐次通解 $x_h = C_1 e^{2s} + C_2 e^{3s}$。

特解：设 $x_p = A e^s + (B s + C) e^{2s}$？ 但 $e^s$ 不是齐次解，$e^{2s}$ 是齐次解。

修正：设 $x_p = A e^s + (B s^2 + C s) e^{2s}$？ 因为 $e^{2s}$ 是单根？ $D^2-5D+6 = (D-2)(D-3)$，$e^{2s}$ 对应根 $2$，是单根，所以特解形式为 $s \cdot (B s + C) e^{2s} = (B s^2 + C s) e^{2s}$。

代入求 $A,B,C$：

对 $A e^s$: $(1 -5 +6)A e^s = 2A e^s = e^s$ $\Rightarrow$ $A=\frac{1}{2}$。

对 $(B s^2 + C s) e^{2s}$:

$x_p = (B s^2 + C s) e^{2s}$
$D x_p = [2(B s^2 + C s) + (2B s + C)] e^{2s} = (2B s^2 + (2C+2B)s + C) e^{2s}$
$D^2 x_p = [4(B s^2 + C s) + 2(4B s + (2C+2B)) + 2B] e^{2s}$？ 直接计算 $D^2 x_p = D(D x_p)$。

$D x_p = e^{2s} [2B s^2 + (2C+2B)s + C]$
$D^2 x_p = 2 e^{2s} [2B s^2 + (2C+2B)s + C] + e^{2s} [4B s + (2C+2B)] = e^{2s} [4B s^2 + (4C+8B)s + (2C+4B)]$

代入 $(D^2 -5D+6)x_p$:

$[4B s^2 + (4C+8B)s + (2C+4B)] -5[2B s^2 + (2C+2B)s + C] +6[B s^2 + C s] = s e^{2s}$ 的系数？ 右边是 $s e^{2s}$，即 $0 \cdot s^2 + 1 \cdot s + 0$。

$s^2$ 项: $4B -10B +6B = 0$。
$s$ 项: $(4C+8B) -5(2C+2B) +6C = (4C+8B -10C -10B +6C) = (-2B) s$？ 系数为 $-2B$。
常数项: $(2C+4B) -5C = -3C +4B$。

所以：
$-2B = 1$ $\Rightarrow$ $B = -\frac{1}{2}$
$-3C + 4B = 0$ $\Rightarrow$ $-3C -2 = 0$ $\Rightarrow$ $C = -\frac{2}{3}$

所以 $x_p = \frac{1}{2} e^s + (-\frac{1}{2} s^2 - \frac{2}{3} s) e^{2s}$

通解 $x = C_1 e^{2s} + C_2 e^{3s} + \frac{1}{2} e^s - \frac{1}{2} s^2 e^{2s} - \frac{2}{3} s e^{2s}$

换回 $t$: $s = \ln t$，$e^s = t$，$e^{2s}=t^2$，$e^{3s}=t^3$。

$x = C_1 t^2 + C_2 t^3 + \frac{1}{2} t - \frac{1}{2} (\ln t)^2 t^2 - \frac{2}{3} (\ln t) t^2$

---

### 特定形式解（待定系数法）

对于常系数线性方程，若 $a(t), b(t), c(t)$ 是多项式，则可能有形如 $x(t) = e^{\lambda t} (多项式)$ 的解。

例：$x'' - (t+1)x' - 2(t-1)x = 0$ 有形如 $x = (a t + b) e^{\lambda t}$ 的解。

代入求 $\lambda, a, b$。

---

### 已知 $n-1$ 个线性无关解，求另一个特解（降阶法）

设 $\varphi_1(x), \cdots, \varphi_{n-1}(x)$ 是 $n$ 阶齐次线性方程的 $n-1$ 个线性无关解，求另一个特解。

利用朗斯基行列式性质，可构造一阶方程。

对于二阶方程 $x'' + a(t) x' + b(t) x = 0$，已知一解 $\varphi(t) \neq 0$。

由刘维尔公式的推导或直接考虑：

$$
\begin{vmatrix}
x & \varphi \\
x' & \varphi'
\end{vmatrix} = C e^{-\int a(t) dt}
$$

即 $\varphi x' - \varphi' x = C e^{-\int a(t) dt}$

$\Rightarrow x' - \frac{\varphi'}{\varphi} x = \frac{C}{\varphi} e^{-\int a(t) dt}$

一阶线性方程。

解为 $x = \varphi(t) \left[ C_1 + C_2 \int \frac{e^{-\int a(s) ds}}{\varphi^2(t)} dt \right]$

---

例：设 $y = \varphi(x)$ 是二阶齐次线性方程 $y'' + p(x)y' + q(x)y = 0$ 的一个非零解，求方程的通解。

解：由上述公式，

$y = \varphi(x) \left[ C_1 + C_2 \int \frac{e^{-\int p(x) dx}}{\varphi^2(x)} dx \right]$

---

例：$y_1 = -e^{x^2}$, $y_2 = e^{x^2}$ 为非齐次方程 $y'' - 4x y' + q(x) y = f(x)$ 的解。求通解。

齐次方程特解 $y_0 = y_2 - y_1 = 2e^{x^2}$？ 不对，$y_1, y_2$ 是非齐次方程的两个解，它们的差 $y_2 - y_1$ 是齐次方程的解。

所以齐次方程通解 $Y_h = C (y_2 - y_1) = C (e^{x^2} - (-e^{x^2})) = 2C e^{x^2}$。

非齐次方程一个特解可取 $y_1$ 或 $y_2$。

所以通解 $y = Y_h + y_p = C_1 e^{x^2} + y_1$？ 或者 $y = C_1 (y_2 - y_1) + y_1 = C_1 (2e^{x^2}) - e^{x^2} = (2C_1 - 1)e^{x^2}$，这只剩一个参数？ 检查：

$y_2 - y_1 = 2e^{x^2}$ 是齐次解。那么齐次通解是 $C \cdot 2e^{x^2}$。
非齐次通解 = 齐次通解 + 非齐次一个特解 = $2C e^{x^2} + y_1 = 2C e^{x^2} - e^{x^2} = (2C-1)e^{x^2}$。确实只有一个参数？ 这说明 $y_1$ 和 $y_2$ 线性相关？ $y_1 = -e^{x^2}$, $y_2 = e^{x^2}$，确实线性相关 ($y_2 = -y_1$)。所以它们不是两个线性无关的非齐次解，而是同一个非齐次方程的两个解（只差一个常数倍？ $-1$ 倍）。所以实际上我们只知道一个非齐次解和一个齐次解。齐次解空间是1维？ 原方程是二阶，齐次解空间应为2维。这里我们只找到一个齐次解 $2e^{x^2}$，还需要另一个齐次解。

由降阶法，已知一个齐次解 $\psi(x) = 2e^{x^2}$，求另一个齐次解。

设 $y = \psi(x) z = 2e^{x^2} z$，代入齐次方程 $y'' - 4x y' + q(x) y = 0$，可求出 $z$，从而得另一个齐次解。

---

例：$x = \varphi(t)$ 是 $\frac{dx}{dt} = A(t) x$ 的解，$y = \psi(t)$ 是 $\frac{dy}{dt} = -A^T(t) y$ 的解。证明 $\psi^T(t) \varphi(t)$ 为常数。

$\frac{d}{dt} (\psi^T \varphi) = \frac{d\psi^T}{dt} \varphi + \psi^T \frac{d\varphi}{dt} = (-A^T \psi)^T \varphi + \psi^T (A \varphi) = -\psi^T A \varphi + \psi^T A \varphi = 0$

所以 $\psi^T(t) \varphi(t)$ 为常数。

---

# 线性方程组求解方法

## 二阶线性方程（常数变易法公式）

方程：$x'' + a(t) x' + b(t) x = f(t)$。

相应的齐次方程基本解组为 $\varphi_1(t)$, $\varphi_2(t)$，则通解为

$$
x = C_1 \varphi_1(t) + C_2 \varphi_2(t) + \int_{t_0}^t \frac{\varphi_1(s)\varphi_2(t) - \varphi_2(s)\varphi_1(t)}{W(s)} f(s)  ds
$$

其中 $W(s) = \varphi_1(s)\varphi_2'(s) - \varphi_2(s)\varphi_1'(s)$ 是朗斯基行列式。

---

例：验证 $\Phi(t) = \begin{bmatrix} e^t & e^{3t} \\ -e^t & e^{3t} \end{bmatrix}$ 是 $X' = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} X$ 的基本解矩阵。

求 $X' = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} X + \begin{bmatrix} e^{3t} \\ 0 \end{bmatrix}$ 的通解。

**验证**：

$\frac{d}{dt} \begin{bmatrix} e^t \\ -e^t \end{bmatrix} = \begin{bmatrix} e^t \\ -e^t \end{bmatrix}$， $\begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} \begin{bmatrix} e^t \\ -e^t \end{bmatrix} = \begin{bmatrix} 2e^t - e^t \\ e^t - 2e^t \end{bmatrix} = \begin{bmatrix} e^t \\ -e^t \end{bmatrix}$。匹配。

$\frac{d}{dt} \begin{bmatrix} e^{3t} \\ e^{3t} \end{bmatrix} = \begin{bmatrix} 3e^{3t} \\ 3e^{3t} \end{bmatrix}$， $\begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} \begin{bmatrix} e^{3t} \\ e^{3t \end{bmatrix} = \begin{bmatrix} 2e^{3t} + e^{3t} \\ e^{3t} + 2e^{3t} \end{bmatrix} = \begin{bmatrix} 3e^{3t} \\ 3e^{3t} \end{bmatrix}$。匹配。

$W(0) = \det \begin{bmatrix} e^0 & e^0 \\ -e^0 & e^0 \end{bmatrix} = \det \begin{bmatrix} 1 & 1 \\ -1 & 1 \end{bmatrix} = 2 \neq 0$ $\Rightarrow$ 线性无关。$\Rightarrow$ $\Phi(t)$ 是基本解矩阵。

**求非齐次通解**：

常数变易公式，特解 $\psi_p(t) = \Phi(t) \int_0^t \Phi^{-1}(s) f(s)  ds$

$\Phi^{-1}(s) = \frac{1}{2} \begin{bmatrix} e^{-s} & -e^{-s} \\ e^{-3s} & e^{-3s} \end{bmatrix}$？ 计算：$\det \Phi(s) = e^s e^{3s} - e^{3t}(-e^t) = e^{4s} + e^{4s} = 2e^{4s}$。

伴随矩阵：$\operatorname{adj} \Phi(s) = \begin{bmatrix} e^{3s} & -e^{3s} \\ e^{s} & e^{s} \end{bmatrix}$？ 标准伴随矩阵是余子式矩阵的转置。

$\Phi(s) = \begin{bmatrix} e^s & e^{3s} \\ -e^s & e^{3s} \end{bmatrix}$，余子式：
$C_{11} = e^{3s}$, $C_{12} = -(-e^s)=e^s$, $C_{21} = -e^{3s}$, $C_{22} = e^s$。
所以伴随矩阵 $\operatorname{adj} \Phi(s) = \begin{bmatrix} C_{11} & C_{21} \\ C_{12} & C_{22} \end{bmatrix} = \begin{bmatrix} e^{3s} & -e^{3s} \\ e^s & e^s \end{bmatrix}$。

$\Phi^{-1}(s) = \frac{1}{\det \Phi(s)} \operatorname{adj} \Phi(s) = \frac{1}{2e^{4s}} \begin{bmatrix} e^{3s} & -e^{3s} \\ e^s & e^s \end{bmatrix} = \frac{1}{2} \begin{bmatrix} e^{-s} & -e^{-s} \\ e^{-3s} & e^{-3s} \end{bmatrix}$

$\Phi^{-1}(s) f(s) = \frac{1}{2} \begin{bmatrix} e^{-s} & -e^{-s} \\ e^{-3s} & e^{-3s} \end{bmatrix} \begin{bmatrix} e^{3s} \\ 0 \end{bmatrix} = \frac{1}{2} \begin{bmatrix} e^{2s} \\ e^{0} \end{bmatrix} = \frac{1}{2} \begin{bmatrix} e^{2s} \\ 1 \end{bmatrix}$

$\int_0^t \Phi^{-1}(s) f(s)  ds = \frac{1}{2} \int_0^t \begin{bmatrix} e^{2s} \\ 1 \end{bmatrix} ds = \frac{1}{2} \begin{bmatrix} \frac{1}{2}(e^{2t}-1) \\ t \end{bmatrix} = \begin{bmatrix} \frac{1}{4}(e^{2t}-1) \\ \frac{t}{2} \end{bmatrix}$

$\psi_p(t) = \Phi(t) \begin{bmatrix} \frac{1}{4}(e^{2t}-1) \\ \frac{t}{2} \end{bmatrix} = \begin{bmatrix} e^t & e^{3t} \\ -e^t & e^{3t} \end{bmatrix} \begin{bmatrix} \frac{1}{4}(e^{2t}-1) \\ \frac{t}{2} \end{bmatrix} = \begin{bmatrix} \frac{1}{4}e^t(e^{2t}-1) + \frac{t}{2} e^{3t} \\ -\frac{1}{4}e^t(e^{2t}-1) + \frac{t}{2} e^{3t} \end{bmatrix} = \begin{bmatrix} \frac{1}{4}(e^{3t}-e^t) + \frac{t}{2} e^{3t} \\ -\frac{1}{4}(e^{3t}-e^t) + \frac{t}{2} e^{3t} \end{bmatrix}$

通解 $X = \Phi(t) C + \psi_p(t)$，$C$ 为常向量。

---

(3) 设 $\varphi_1(x)$, $\varphi_2(x)$ 线性无关，证明以 $\varphi_1(x)$, $\varphi_2(x)$ 为基本解组的齐次方程组有以下形式：

$$
\begin{vmatrix}
x_1' & \varphi_{11}'(x) & \varphi_{21}'(x) \\
x_1 & \varphi_{11}(x) & \varphi_{21}(x) \\
x_2 & \varphi_{12}(x) & \varphi_{22}(x)
\end{vmatrix} = 0, \quad i = 1, 2
$$

其中 $x_1, x_2$ 是未知函数，$\varphi_{ij}$ 是 $\varphi_j$ 的第 $i$ 个分量。

这个行列式方程表示向量 $(x_1', x_2')$ 可由 $( \varphi_{11}', \varphi_{12}' )$ 和 $( \varphi_{21}', \varphi_{22}' )$ 线性表出，而这正是因为它们都是 $A(t) X$ 的值，其中 $A(t) = \Phi'(t) \Phi^{-1}(t)$。

---

# 常系数线性方程解法

## $n$ 阶常系数齐次线性方程

$$
\frac{d^n x}{dt^n} + a_1 \frac{d^{n-1} x}{dt^{n-1}} + \cdots + a_{n-1} \frac{dx}{dt} + a_n x = 0
$$

引入微分算子 $D = \frac{d}{dt}$，$D x = \frac{dx}{dt}$，$D^2 x = \frac{d^2 x}{dt^2}$，$\cdots$。

方程化为 $(D^n + a_1 D^{n-1} + \cdots + a_{n-1} D + a_n) x = 0$。

记 $P(D) = D^n + a_1 D^{n-1} + \cdots + a_n$，则 $P(D) x = 0$。

**特征方程**：$P(\lambda) = \lambda^n + a_1 \lambda^{n-1} + \cdots + a_n = 0$。

---

1.  若 $P(\lambda_0) = 0$，那么 $x = e^{\lambda_0 t}$ 是解。

    $P(D) e^{\lambda_0 t} = P(\lambda_0) e^{\lambda_0 t} = 0$。

2.  若 $P(\lambda)$ 有 $n$ 个不同的根 $\lambda_1, \lambda_2, \cdots, \lambda_n$，则 $e^{\lambda_1 t}, e^{\lambda_2 t}, \cdots, e^{\lambda_n t}$ 是基本解组。

    证明：朗斯基行列式 $W(t) = W(0) e^{-\int_0^t a_1 ds} = W(0) e^{-a_1 t}$。

    而 $W(0)$ 是范德蒙行列式，$\prod_{1 \le i < j \le n} (\lambda_j - \lambda_i) \neq 0$，所以 $W(t) \neq 0$。

3.  若 $\lambda_0$ 是 $P(\lambda) = 0$ 的 $k$ 重根，则 $e^{\lambda_0 t}, t e^{\lambda_0 t}, \ldots, t^{k-1} e^{\lambda_0 t}$ 是原方程 $k$ 个线性无关的解。

    $P(\lambda) = Q(\lambda)(\lambda - \lambda_0)^k$，$Q(\lambda_0) \neq 0$。

    $P(D) x = Q(D)(D - \lambda_0)^k x$

    引理：对于复数 $s$ 和整数 $m$，$D^m (e^{s t} x(t)) = e^{s t} (D + s)^m x(t)$。

    证明（归纳法）：$m=1$，$D(e^{s t} x) = s e^{s t} x + e^{s t} D x = e^{s t} (D + s) x$。

    假设 $m$ 时成立，$D^m (e^{s t} x) = e^{s t} (D+s)^m x$。

    $D^{m+1} (e^{s t} x) = D [ e^{s t} (D+s)^m x ] = e^{s t} (D+s) (D+s)^m x = e^{s t} (D+s)^{m+1} x$。

    现在，令 $s = -\lambda_0$，则 $(D - \lambda_0)^k x = e^{\lambda_0 t} D^k (e^{-\lambda_0 t} x)$。

    所以 $P(D) x = Q(D) e^{\lambda_0 t} D^k (e^{-\lambda_0 t} x) = 0$。

    由于 $Q(D)$ 和 $e^{\lambda_0 t}$ 可逆（在解空间中），等价于 $D^k (e^{-\lambda_0 t} x) = 0$。

    $\Rightarrow e^{-\lambda_0 t} x$ 为任意次数不超过 $k-1$ 的多项式：$C_0 + C_1 t + \cdots + C_{k-1} t^{k-1}$。

    $\Rightarrow x = e^{\lambda_0 t} (C_0 + C_1 t + \cdots + C_{k-1} t^{k-1})$。

    取 $C_i=1$，其余为 $0$，得到 $k$ 个线性无关解 $e^{\lambda_0 t}, t e^{\lambda_0 t}, \ldots, t^{k-1} e^{\lambda_0 t}$。

---

**定理 1.1** 如果特征多项式 $P(\lambda)$ 可分解为

$$
P(\lambda) = (\lambda - \lambda_1)^{n_1} (\lambda - \lambda_2)^{n_2} \cdots (\lambda - \lambda_r)^{n_r}
$$

其中 $n_1 + n_2 + \cdots + n_r = n$，$\lambda_i \neq \lambda_j (i \neq j)$，

则函数组

$$
e^{\lambda_1 t}, t e^{\lambda_1 t}, \ldots, t^{n_1-1} e^{\lambda_1 t} \\
e^{\lambda_2 t}, t e^{\lambda_2 t}, \ldots, t^{n_2-1} e^{\lambda_2 t} \\
\cdots \\
e^{\lambda_r t}, t e^{\lambda_r t}, \ldots, t^{n_r-1} e^{\lambda_r t}
$$

为基本解组。

---

## 矩阵指数函数

- 矩阵的指数函数定义：

$$
e^A \triangleq \sum_{n=0}^{\infty} \frac{1}{n!} A^n = E + A + \frac{1}{2!} A^2 + \cdots
$$

$$
e^{A t} \triangleq \sum_{n=0}^{\infty} \frac{1}{n!} (A t)^n = E + A t + \frac{1}{2!} A^2 t^2 + \cdots
$$

- 性质：
    - $\frac{d}{dt} e^{A t} = A e^{A t}$。
    - 若 $AB = BA$，则 $A e^{B t} = e^{B t} A$，且 $e^{(A+B)t} = e^{A t} e^{B t} = e^{B t} e^{A t}$。
    - $e^{A t}$ 可逆，$(e^{A t})^{-1} = e^{-A t}$。
    - 若 $T$ 可逆，则 $e^{(T A T^{-1}) t} = T e^{A t} T^{-1}$。

---

1.  $e^{A t}$ 是 $\frac{dX}{dt} = A X$ 的基本解矩阵 ($\Phi(0)=E$)。
2.  $\frac{dX}{dt} = A X + f(t)$ 的通解：$X = e^{A t} C + e^{A t} \int_{t_0}^{t} e^{-A s} f(s)  ds$。

    若初值 $X(t_0) = X_0$，则 $C = e^{-A t_0} X_0$，

    $X = e^{A (t-t_0)} X_0 + \int_{t_0}^{t} e^{A (t-s)} f(s)  ds$。

---

## $e^{A t}$ 的计算（若当标准型法）

设 $A = T J T^{-1}$，$J$ 为若当标准型。

则 $e^{A t} = T e^{J t} T^{-1}$。

$e^{J t} = \operatorname{diag}( e^{J_1 t}, e^{J_2 t}, \cdots, e^{J_r t} )$

对于若当块 $J_i = \lambda_i E + N$ ($N$ 为幂零矩阵)，

$e^{J_i t} = e^{\lambda_i t} (E + N t + \frac{N^2 t^2}{2!} + \cdots + \frac{N^{k-1} t^{k-1}}{(k-1)!})$

---

## 常系数方程解的渐近性质

$\frac{dX}{dt} = A X$。

- 若 $A$ 的所有特征根实部都小于零，即 $\operatorname{Re}(\lambda_i) < 0, \forall i$，则方程组的任意解 $\lim_{t \to +\infty} X(t) = 0$。
- 若 $A$ 至少有一个特征根实部大于零，即 $\exists i, \operatorname{Re}(\lambda_i) > 0$，则存在解 $\lim_{t \to +\infty} |X(t)| = \infty$。
- 若 $A$ 的所有特征根实部都小于等于零，且实部为零的特征根对应的初等因子是一次的（即若当块均为 $1\times 1$），则所有解有界。

---

## 例题

例：设 $y = \varphi(x)$ 是二阶齐次线性微分方程 $y'' + p(x)y' + q(x)y = 0$ 的一个非零解，其中 $p(x), q(x)$ 在 $[a,b]$ 上连续，求方程的通解。

解：由降阶法公式，

$y = \varphi(x) \left[ C_1 + C_2 \int \frac{e^{-\int p(x) dx}}{\varphi^2(x)} dx \right]$

---

例：$y_1 = -e^{x^2}, y_2 = e^{x^2}$ 为非齐次方程 $y'' - 4x y' + q(x) y = f(x)$ 的解。求通解。

齐次方程的一个特解 $y_0 = y_2 - y_1 = 2e^{x^2}$。

还需要另一个齐次解，用降阶法。

设 $y = z y_0 = 2z e^{x^2}$，代入齐次方程 $y'' - 4x y' + q(x) y = 0$，可求出 $z$。

但 $q(x)$ 未知？ 由 $y_1, y_2$ 是非齐次解，可求出 $f(x)$ 和 $q(x)$？

$y_1'' - 4x y_1' + q(x) y_1 = f(x)$
$y_2'' - 4x y_2' + q(x) y_2 = f(x)$

两式相减：$(y_2'' - y_1'') - 4x (y_2' - y_1') + q(x)(y_2 - y_1) = 0$

即 $(2e^{x^2}(2+4x^2)) - 4x (4x e^{x^2}) + q(x)(2e^{x^2}) = 0$？ 计算导数：

$y_1 = -e^{x^2}$, $y_1' = -2x e^{x^2}$, $y_1'' = -(2+4x^2)e^{x^2}$
$y_2 = e^{x^2}$, $y_2' = 2x e^{x^2}$, $y_2'' = (2+4x^2)e^{x^2}$

$y_2'' - y_1'' = 2(2+4x^2)e^{x^2}$
$y_2' - y_1' = 4x e^{x^2}$

代入：$2(2+4x^2)e^{x^2} - 4x (4x e^{x^2}) + q(x)(2e^{x^2}) = [4+8x^2 -16x^2 + 2q(x)] e^{x^2} = [4 -8x^2 + 2q(x)] e^{x^2} = 0$

所以 $q(x) = 4x^2 - 2$。

然后代入一个方程求 $f(x)$：$y_1'' - 4x y_1' + q(x) y_1 = [-(2+4x^2) -4x(-2x) + (4x^2-2)(-1)] e^{x^2} = [-2-4x^2+8x^2 -4x^2+2] e^{x^2} = 0$。

所以 $f(x)=0$？ 那原方程是齐次的？ 矛盾，因为 $y_1, y_2$ 是齐次方程的解且线性相关，不能作为两个不同的解给出。所以题目可能有问题。

---

例：$x = \varphi(t)$ 是 $\frac{dx}{dt} = A(t) x$ 的解，$y = \psi(t)$ 是 $\frac{dy}{dt} = -A^T(t) y$ 的解。证明 $\psi^T(t) \varphi(t)$ 为常数。

证明：$\frac{d}{dt} (\psi^T \varphi) = (\frac{d\psi}{dt})^T \varphi + \psi^T \frac{d\varphi}{dt} = (-A^T \psi)^T \varphi + \psi^T (A \varphi) = -\psi^T A \varphi + \psi^T A \varphi = 0$。

故 $\psi^T(t) \varphi(t)$ 为常数。