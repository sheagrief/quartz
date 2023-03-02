---
aliases: 
tags: math
title: edge of the wedge theorem
feed: show
date: 2022-10-13
---

Schwarzの鏡像原理の多変数への一般化みたいな定理。

## 設定
$\Gamma$ を $\mathbb{R}^n$ のopen coneとする。 $V$ を $\Gamma$ と、中心を $\mathbb{R}^n$ の原点にもつ有界開球の共通部分とする。 $E$ を $\mathbb{R}^n$ の空でない開集合とする。

$$W^+=E+iV,\quad W^-=E-iV$$

と定める。すなわち、 $W^+,W^-$ が「wedge」であり、 $E$ が「edge」である。

## 定理
$E,W^+,W^-$ が上のように与えられたとする。このとき、 $W^+\cup E\cup W^-$ を含むある開集合 $\Omega \subset \mathbb{C}^n$ が存在して、次の性質を持つ：

$W^+\cup E\cup W^-$ 上の任意の連続関数 $f$ が $W^+\cup W^-$ 上で正則であるならば、 $\Omega$ 上の正則関数 $F$ に拡張できる。