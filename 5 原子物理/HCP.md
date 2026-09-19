# 六方最密堆积（Hexagonal Close-Packing, 简称 HCP）

## 例1: 证理想六方密堆结构中 $\dfrac{c}{a} \approx 1.633$

解析：由于 $AO=\dfrac{c}2$, $BC=a$, 且图形 $ABCD$ 为正四面体，有

$$
\begin{aligned}
|AO|^2+|BO|^2&=|AB|^2\\
|BF|^2+|CF|^2&=|BC|^2\\
|BO|&=\dfrac{2}{3}|BF|
\end{aligned}
$$

计算，得

$$
c=\dfrac{2\sqrt{6}}{3}a,
$$

所以

$$
\therefore \dfrac{c}{a}\approx1.633.
$$

---

## 例2: 计算理想六方密堆结构的原子空间利用率.

解析：由例1，知 

$$
AO=\frac{c}{2}=\frac{\sqrt{6}}{3}a, BF=\frac{\sqrt{3}}{2}a.
$$

由“总原子数目：2+1+3=6”,
所以 

$$
V_a=\frac{4}{3}\pi(a/2)^3\times6=\pi a^3,
$$

六方体积：

$$
V=\frac{1}{2}\times\frac{\sqrt{3}}{2}a\times a\times6\times\frac{2\times\sqrt{6}}{3}a=3\sqrt2 a^3,
$$

故：

$$
\frac{V_a}{V}\times 100\%\approx74.05\%.
$$