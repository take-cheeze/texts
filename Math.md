* [Online text books of statistics.](http://id.fnshr.info/2013/08/11/online-stat-books/)

## Writing Formula
### Tex
* [Tex Reference Card](http://www.math.brown.edu/~jhs/ReferenceCards/TeXRefCard.v1.5.pdf)
* [Japanese TeX Reference](http://www002.upp.so-net.ne.jp/latex/)
* [TeX reference](http://www.miwie.org/tex-refs/tex-refs.html)

## 累乗 
  * 二乗: Square
  * 三乗: Cube

## Wavelet 
  * フーリエ変換的なもの
  * 計算量が比較的少ない

## Eulerの公式 
```math
e^{\imath\theta}= \cos\theta + \imath\sin\theta
```

## de Morgan's laws 
```math
\lnot(P \bigvee Q) = \lnot{P} \bigwedge \lnot{Q}
```

```math
\lnot(P \bigwedge Q) = \lnot{P} \bigvee \lnot{Q}
```

```math
\overline{(A \bigcap B)} = \overline{A} \bigcup \overline{B}
```

```math
\overline{(A \bigcup B)} = \overline{A} \bigcap \overline{B}
```

##  群 
* 可換群・アーベル群
  * AB = B*A
* 非可換群・非アーベル群
  * A*B != B*A

## 最大・最小化 
* 二次関数では平方完成
* 相加相乗平均
```math
x \geq 0, y \geq 0, {x + y \over 2} \geq \sqrt{xy}
```

## 点と直線の距離 
```math
(x_{0}, y_{0}), ax + by + c = 0
```

```math
d = {|ax_{0} + by_{0} + c| \over \sqrt{a^2 + b^2}}
```

## 行列 
* 行列値
* トレース
* 一次変換
  * 横ベクトル
  * 回転
    * 原点周りの角度θ（反時計回り）
```math

R_{\theta} =
\begin{pmatrix}
\cos\theta &\sin\theta &0 \\
-\sin\theta &\cos\theta &0 \\
0 &0 &1
\end{pmatrix}

```
  * 移動
```math

T_{t} =
\begin{pmatrix}
1 &0 &0 \\
0 &1 &0 \\
t_{x} &t_{y} &1
\end{pmatrix}

```
  * 拡大・縮小
```math

S_{s} =
\begin{pmatrix}
s_{x} &0 &0 \\
0 &s_{y} &0 \\
0 &0 &1
\end{pmatrix}

```

## ベクトル 
* 和・差
* 長さ
```math
|a| = \sqrt{\sum a_{i}^2}
```
* 内積
```math
\overrightarrow{a}\cdot\overrightarrow{b} = |a||b|\cos\theta = \sum a_{i}b_{i}
```
* 外積
* |a|*|b|*sinθ
* Av= λv

## 奇関数・偶関数
* 奇関数
```math
f(-x) = -f(x)
```
* 偶関数
```math
f(-x) = f(x)
```
* 奇関数×偶関数 = 奇関数
* 偶関数×偶関数 = 偶関数
* 奇関数×奇関数 = 偶関数

##  微積分 
```math
(\sin \theta)' = \cos \theta
```

```math
(\cos \theta)' = -\sin \theta
```

```math
(x^n)' = nx^{n-1}
```

##  三角関数 
* 余弦定理
```math
\cos A = {b^2 + c^2 - a^2 \over 2bc}
```

```math
a^2 = b^2 + c^2 - 2bc\cos A
```

* 正弦定理
```math
{a \over \sin A} = {b \over \sin B} = {c \over \sin C} = 2R
```

* 性質
```math
\tan \theta = {\sin \theta \over \cos \theta}
```

```math
\sin \theta ^ 2 + \cos \theta ^2 = 1
```

```math
1 + \tan \theta ^ 2 = {1 \over \cos \theta ^ 2}
```

```math
\sin 2\theta = 2\sin\theta\cos\theta
```

```math
\cos 2\theta = \cos \theta ^ 2 - \sin \theta ^ 2 = 2\cos \theta ^ 2 - 1 = 1 - 2\sin \theta ^ 2
```

##  幾何学 
* 三角形
```math
S = {b c \sin A \over 2}
```

```math
s = {a + b + c \over 2}, S = \sqrt{s(s - a)(s - b)(s - c)}
```

```math
S = {r(a + b + c) \over 2}
```

* 球
  * 表面積
```math
S = 4\pi r^2
```
  * 体積
```math
V = {4 \over 3}\pi r^3
```

## 集合 
* ∪: 和集合
* ∩: 積集合
```math
n(A \bigcup B) = n(A) + n(B) - n(A \bigcap B)
```

```math
n(\overline{A}) = n(U) - n(A)
```

## 確率
* 順列
  * n P r = n! / (n - r)!
* n! / n = (n - 1)!
* 組合せ
  * n C r = n! / r!(n-r)!
* (a + b)^n = n Σ r=0 (n C r a^(n-r) * b^r)
* P(A ∪ B) = P(A) + P(B)
* P(!A) = 1 - P(A)
* ベイズの定理
  * P(A | B) = P(B | A) P(A) / P(B)