
## 基础微分相关

| 数学概念         | LaTeX 语法                                                                 | 示例（课程场景）                                                                                           |
| ------------ | ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| 一阶导数（函数形式）   | `f'(x)` 或 `\frac{df}{dx}` 或 `\dot{y}`（时间导数）                              | \(f'(x) = \sin x\)、\(\frac{dy}{dx} + y = 0\)（一阶线性 ODE）、\(\dot{x}(t) = v(t)\)                       |
| 二阶导数         | `f''(x)` 或 `\frac{d^2f}{dx^2}` 或 `\ddot{y}`                              | \(f''(x) = -\cos x\)、\(\frac{d^2y}{dx^2} + \omega^2 y = 0\)（简谐振动 ODE）                              |
| n 阶导数        | `f^{(n)}(x)` 或 `\frac{d^n f}{dx^n}`                                      | \(f^{(n)}(x) = e^x\)、\((uv)^{(n)} = \sum_{k=0}^n \binom{n}{k} u^{(k)} v^{(n-k)}\)（莱布尼茨公式）          |
| 偏导数（二元函数）    | `\frac{\partial f}{\partial x}` 或 `f_x`                                  | \(\frac{\partial f(x,y)}{\partial x} = 2xy\)、\(f_y(x,y) = x^2\)                                    |
| 混合偏导数        | `\frac{\partial^2 f}{\partial x \partial y}` 或 `f_{xy}`                  | \(\frac{\partial^2 f}{\partial x \partial y} = \frac{\partial^2 f}{\partial y \partial x}\)（克莱罗定理） |
| 全微分          | `dz = \frac{\partial z}{\partial x}dx + \frac{\partial z}{\partial y}dy` | \(dz = 2xdx + 3y^2dy\)（\(z=x^2+y^3\) 的全微分）                                                         |
| 微分算子（ODE 专用） | `\frac{d}{dx}` 或 `D`（简洁记号）                                               | \(\frac{d}{dx}(y) + P(x)y = Q(x)\)、\(Dy + y = e^x\)                                                |

## 二、积分相关（数学分析核心）

| 数学概念       | LaTeX 语法                                                                           | 示例（课程场景）                                                                                 |
| ---------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| 不定积分       | `\int f(x) dx`                                                                     | $\int \sin x dx = -\cos x + C$                                                           |
| 定积分（闭区间）   | `\int_a^b f(x) dx`                                                                 | \(\int_0^\pi \sin x dx = 2\)（牛顿 - 莱布尼茨公式）                                                |
| 反常积分（无穷区间） | `\int_a^{+\infty} f(x) dx` 或 `\int_{-\infty}^b f(x) dx`                            | \(\int_0^{+\infty} e^{-x} dx = 1\)、\(\int_{-\infty}^{+\infty} \frac{1}{1+x^2} dx = \pi\) |
| 反常积分（瑕点）   | `\int_a^b f(x) dx`（瑕点隐含）                                                           | \(\int_0^1 \frac{1}{\sqrt{x}} dx\)（瑕点 \(x=0\)）                                           |
| 二重积分（直角坐标） | `\iint_D f(x,y) dxdy` 或 `\int_a^b dx \int_{\varphi_1(x)}^{\varphi_2(x)} f(x,y) dy` | \(\iint_D xy dxdy\)、\(\int_0^1 dx \int_0^x (x+y) dy\)                                    |
| 三重积分（直角坐标） | `\iiint_\Omega f(x,y,z) dxdydz`                                                    | \(\iiint_\Omega xyz dxdydz\)（\(\Omega\) 为长方体）                                            |
| 第一类曲线积分    | `\int_L f(x,y) ds`                                                                 | \(\int_L (x+y) ds\)（L 为线段 \(y=x\)）                                                       |
| 第二类曲线积分    | `\int_L P dx + Q dy`                                                               | \(\int_L x dy - y dx\)（格林公式应用）                                                           |
| 第一类曲面积分    | `\iint_\Sigma f(x,y,z) dS`                                                         | \(\iint_\Sigma (x^2+y^2+z^2) dS\)（\(\Sigma\) 为球面）                                        |
| 第二类曲面积分    | `\iint_\Sigma P dydz + Q dzdx + R dxdy`                                            | \(\iint_\Sigma x dydz + y dzdx + z dxdy\)（高斯公式应用                                         |
## 三、多元微积分核心（梯度 / 散度 / 旋度）

| 数学概念                 | LaTeX 语法                                         | 示例（课程场景）                                             |      |      |
| ------------------------ | -------------------------------------------------- | ------------------------------------------------------------ | ---- | ---- |
| 梯度（标量场）           | `\nabla f` 或 `\text{grad}\, f`                    | \(\nabla f(x,y,z) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right)\) |      |      |
| 散度（向量场）           | `\nabla \cdot \vec{F}` 或 `\text{div}\, \vec{F}`   | \(\nabla \cdot \vec{F} = \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}\)（高斯公式核心） |      |      |
| 旋度（向量场）           | `\nabla \times \vec{F}` 或 `\text{curl}\, \vec{F}` | \(\nabla \times \vec{F} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ P & Q & R \end{vmatrix}\)（斯托克斯公式核心） |      |      |
| 拉普拉斯算子             | `\Delta f` 或 `\nabla^2 f`                         | \(\Delta f = \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2}\)（拉普拉斯方程 \(\Delta f = 0\)） |      |      |
| 雅可比行列式（变量替换） | `\frac{\partial(x,y)}{\partial(u,v)}`              | $\iint_D f(x,y) dxdy = \iint_{D'} f(x(u,v),y(u,v)) \frac{\partial(x,y)}{\partial(u,v)}  dudv$ |      |      |

## 四、极限与级数（数学分析核心）

| 数学概念               | LaTeX 语法                                                   | 示例（课程场景）                                             |      |      |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---- | ---- |
| 数列极限               | `\lim_{n \to \infty} a_n = A`                                | \(\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e\)（重要极限） |      |      |
| 函数极限（趋于有限值） | `\lim_{x \to x_0} f(x) = A`                                  | \(\lim_{x \to 0} \frac{\sin x}{x} = 1\)（重要极限）          |      |      |
| 左极限                 | `\lim_{x \to x_0^-} f(x)` 或 `\lim_{x \uparrow x_0} f(x)`    | $\lim_{x \to 0^-} \frac{x}{x} = -1$                          |      |      |
| 右极限                 | `\lim_{x \to x_0^+} f(x)` 或 `\lim_{x \downarrow x_0} f(x)`  | $\lim_{x \to 0^+} \frac{x}{x} = 1$                           |      |      |
| 数项级数求和           | `\sum_{n=1}^\infty u_n`                                      | \(\sum_{n=1}^\infty \frac{1}{n^2} = \frac{\pi^2}{6}\)（p - 级数） |      |      |
| 幂级数                 | `\sum_{n=0}^\infty a_n x^n`                                  | \(\sum_{n=0}^\infty \frac{x^n}{n!} = e^x\)（指数函数展开）   |      |      |
| 傅里叶级数             | `\frac{a_0}{2} + \sum_{n=1}^\infty (a_n \cos nx + b_n \sin nx)` | \(f(x) \sim \frac{a_0}{2} + \sum_{n=1}^\infty (a_n \cos nx + b_n \sin nx)\)（周期 \(2\pi\) 展开） |      |      |
| 乘积级数               | `\prod_{n=1}^\infty u_n`                                     | \(\prod_{n=2}^\infty \left(1 - \frac{1}{n^2}\right) = \frac{1}{2}\) |      |      |

## 五、常微分方程专用语法

| 数学概念                   | LaTeX 语法                                          | 示例（课程场景）                                             |
| -------------------------- | --------------------------------------------------- | ------------------------------------------------------------ |
| 一阶线性非齐次 ODE         | `\frac{dy}{dx} + P(x)y = Q(x)`                      | \(\frac{dy}{dx} + 2xy = x e^{-x^2}\)                         |
| 伯努利方程                 | `\frac{dy}{dx} + P(x)y = Q(x)y^n`                   | \(\frac{dy}{dx} - \frac{1}{x}y = x y^2\)（\(n=2\)）          |
| 二阶线性齐次 ODE           | `\frac{d^2y}{dx^2} + p(x)\frac{dy}{dx} + q(x)y = 0` | \(\frac{d^2y}{dx^2} - 3\frac{dy}{dx} + 2y = 0\)              |
| 通解（任意常数）           | `y = C_1 f(x) + C_2 g(x)`                           | \(y = C_1 e^x + C_2 e^{2x}\)（二阶 ODE 通解）                |
| 特解                       | `y^*` 或 `\tilde{y}`                                | \(y^* = \frac{1}{2}x e^x\)（非齐次 ODE 特解）                |
| 初值条件（IVP）            | `y(x_0) = y_0, \quad y'(x_0) = y_0'`                | \(y(0) = 1, \quad y'(0) = 0\)（简谐振动初值）                |
| 边值条件（BVP）            | `y(a) = \alpha, \quad y(b) = \beta`                 | \(y(0) = 0, \quad y(\pi) = 0\)（弦振动边值）                 |
| 线性微分方程组（向量形式） | `\vec{y}'(x) = A \vec{y}(x)`                        | \(\vec{x}' = \begin{pmatrix}2&1\\1&2\end{pmatrix}\vec{x}\) 或 \(\begin{cases} \dot{x}_1 = 2x_1 + x_2 \\ \dot{x}_2 = x_1 + 2x_2 \end{cases}\) |
| 特征方程（二阶 ODE）       | `r^2 + p r + q = 0`                                 | \(r^2 - 3r + 2 = 0\)（对应二阶齐次 ODE）                     |

