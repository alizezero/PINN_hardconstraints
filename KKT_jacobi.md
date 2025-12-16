# 硬约束雅可比解析
## 1.y向量表
### 气相摩尔分率 11个
* y1 = C2H4g
* y2 = C4H8g
* y3 = H2g
* y4 = N2g
* y5 = CH4g
* y6 = C2H6g
* y7 = C4H10g
* y8 = C5H12g
* y9 = Catg
* y10 = CoCatg
* y11 = LLDPEg
### 液相摩尔分率 11个
* y12 = C2H4p
* y13 = C4H8p
* y14 = H2p
* y15 = N2p
* y16 = CH4p
* y17 = C2H6p
* y18 = C4H10p
* y19 = C5H12p
* y20 = Catp
* y21 = CoCatp
* y22 = LLDPEp
### 催化剂位点流量 24个
* y23 = Cps
* y24 = Cds
* y25 = Cvs1
* y26 = Cvs2
* y27 = Cvs3
* y28 = Cvs4
* y29 = P101
* y30 = P102
* y31 = P103
* y32 = P104
* y33 = P201
* y34 = P202
* y35 = P203
* y36 = P204
* y37 = D0
* y38 = P111
* y39 = P112
* y40 = P113
* y41 = P114
* y42 = P211
* y43 = P212
* y44 = P213
* y45 = P214
* y46 = D1
### 其他指标
* y47 = Mn
* y48 = Moleout_gas
* y49 = Moleout_poly
* y50 = rhogas_bar
* y51 = rhopoly_bar

## 2.z向量表
### PolySL EOS
* z1 = $y50^2$
* z2 = $log(y50)$
* z3 = $log(y50^2)$
* z4 = $1-y50$
* z5 = $log(1-y50)$
* z6 = $y51^2$
* z7 = $log(y51)$
* z8 = $log(y51^2)$
* z9 = $1-y51$
* z10 = $log(1-y51)$

## 3.方程变换与Jacobi矩阵解析
### PolySL EOS
#### log-exp变换后方程
$$
\begin{aligned}
    z1 + \overline{T} * z5 + \overline{T} * (1-r_{mix}^-1) * y50 = -\overline{P} \\
    z3 - z2 = 0 \\
    z4 + y50 = 1 \\ 
    y50 - \exp(z2) = 0 \\
    z1 - \exp(z3) = 0 \\
    z4 - \exp(z5) = 0
\end{aligned}
$$

#### Jacobi矩阵

$$
J_y =
\begin{bmatrix}
    \overline{T} * (1-r_{mix}^-1) \\
    0 \\
    1 \\
    1 \\
    0 \\
    0
\end{bmatrix}
$$

$$
J_z =
\begin{bmatrix}
    1 & 0 & 0 & 0 & \overline{T} \\
    0 & -2 & 1 & 0 & 0 \\
    0 & 0 & 0 & 1 & 0 \\
    0 & -\exp(z2) & 0 & 0 & 0 \\
    1 & 0 & -\exp(z3) & 0 & 0 \\
    0 & 0 & 0 & 1 & -\exp(z5) \\
\end{bmatrix}
$$




