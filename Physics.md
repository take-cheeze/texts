==Seebeck effect== 
* Same as Thermocouple.
* Use in thermoelectric generator.
* When joint of different metal gains heat generates electricity.

==流体力学==
* Force
```math
\rho_{1} u_{1} A_{1} [= \rho_{2} u_{2} A_{2} [N](N])
```

  * ```math
\rho_{1}[u_{1}[m/s](kg/m^3],), A_{1}[m^2]
```: Input value
  * ```math
\rho_{2}[u_{2}[m/s](kg/m^3],), A_{2}[m^2]
```: Output value
  * if volume won't change
```math
u_{1} A_{1} = u_{2} A_{2} (\rho_{1} = \rho_{2})
```

* Momentum change
```math
\rho_{2} [A_{2} [m^2](kg/m^3]) u_{2} [^2  - \rho_{1} [kg/m^3](m/s]) A_{1} [u_{1} [m/s](m^2])^2 = p_{1} [A_{1} [m^2](Pa]) - p_{2} [A_{2} [m^2](Pa]) + F[N]
```

* レイノルズ数
  * 小さい: 層流
  * 大きい: 乱流
  * 遷移点: 層流から乱流に変化する点

* 渦
  * 双子渦
  * カルマン渦

* ナビエ・ストークス方程式
* 流体要素
* 流線
  * 接線が速度ベクトルの向き
* 流跡線
  * 流体要素が移動した軌跡
* 流脈線
  * ある点を通る流体要素が描く線
* 粘性
  * 完全流体：粘性の無い流体
  * 境界層：表面周りの粘性の及ぶ範囲
  * 粘性係数・粘度：kg/(m*s)=Pa
  * 流体の圧縮性によって生じる現象：音波
  * 新幹線のカモノハシ型は，音波の抑制のため
* マッハ数：流速÷音速
  * コンコルドは約㍅2

==コンデンサ==
* クーロン定数 ```math
k_{0} = 9.0 \times 10^9 [m^2 / C^2](N))
```
* Q,q: 電気量 [[A*s](C],)
* E: 電場の強さ[[V/m](N/C],)
* V: 電位差 [V]
* C: 電気容量 [F]
* ε: 誘電率 [(=8.85 * 10^-12 [F/m](F/m]))
* ε0: 比誘電率
* クーロン力：F = k0 * q1 * q2 / r^2 [N]
* E = k0 * Q / r^2
* V = k0 * Q / r
* W = q * V
* F = q * E
* N = 4π * k0 * Q = Q / ε0
* W = Q* V / 2 = C * V^2 / 2 = Q^2 /2C
* V = E * d
* C0 = ε0 * S / d = S / (d * 4π * k0)
* C = ε * S / d = εr * C0
* εr = ε / ε0
* ε0 = 1 / (4π * k0)
* 極板間引力: F = Q * E / 2
* Q = C*V

== 合成容量 ==
* 並列: ```math
 C = {\sum C_{k}} 
```
* 直列: ```math
{1 \over C} = {\sum {1 \over C_{k}}}
```

==温度特性==
温度による容量の変化の誤差
これを逆手に取って，一定の温度変化による特性の変化が一定の電子部品は温度センサーに使える

==周波数特性==
高周波での安定性
漏電量は```math
\tan \delta
```でわかる

==合成抵抗==
* 並列: ```math
{1 \over C} = {\sum {1 \over C_{k}}}
```
* 直列: ```math
 C = {\sum C_{k}} 
```

==耐圧==
かけられる電圧の上限の目安

==ボルツマン定数==
```math
k [/ K](J) = R / N_{A} = 1.380658 \times 10^23
```
* N: Avogadro数
* R: 気体定数

==質量の持つエネルギー==
```math
e[= {m[kg](J]) c[\over \sqrt{1 - {v[m/s](m/s]^2)^2 /\over c[m/s]^2}}}
```

c: Speed of light

==等加速度運動==
```math
v[= v_{0}[m/s](m/s]) + a[t[s](m^2/2])
```

```math
x[= v_{0}[m/s](m]) t[+ {1 \over 2}a[m^2/2](s]) t^2
```

```math
v[- v_{0}[m](m]^2)^2 = 2 a[x[m](m^2/s])
```

==万有引力==
* Newton
```math
F[= G[{N m^2 \over kg^2}](N]) {M[m[kg](kg]) \over r[m]^2}
```

```math
G = 6.673 * 10^-11
```

==熱力学==
```math
d{ ln W (E) \over d E} = {1 \over kT}
```

```math
{mv^2 \over 2} = {3\over 2}kT
```

==同位体解析==
* ```math
_{14} C
```
* ```math
_{129} I
```

==Four dynamics== 
* Fluid dynamics
* Thermodynamics
* Strength of materials
* Mechanical dynamics

==Gas law== 
* Ideal gas
  * p [Pa]
  * V [L]
  * n [mol]
  * T [K]
  * R [J/(K*mol)]
```math
pV = nRT
```

==Wave== 
```math
v = f \lambda = {\lambda \over T}
```

```math
f = {1 \over T}
```

```math
n_{1,2} = {\sin \theta_{1} \over \sin \theta_{2}} = {v_{1} \over v_{2}} = {\lambda_{1} \over \lambda_{2}} = {n_{1} \over n_{2}}
```

```math
y = A \sin({2\pi \over T}(t - {x \over v})) = A \sin 2\pi({t \over T} - {x \over \lambda})
```

==Fluid Dynamics== 
* Mach
  * The speed of wave in trasmission medium.
```math
c = \sqrt{\gamma R T} = \sqrt{\gamma p \over \rho}
```