#### 予想
$$\mathrm{spec}\alpha=\mathrm{supp}\hat{\alpha}$$
これは成り立たなさそう。
では
$$
\mathrm{spec}\alpha\subseteq\mathrm{supp}\hat{\alpha}
$$
だろうか？

ちゃんと考えてみる。

$$
\mathrm{spec}\alpha=\{\chi\in \hat{G}\mid \alpha(f)=0 \Rightarrow \hat{f}(\chi)=0, \forall f\in L^1(G,dg)\}
$$

である。


証明
($\mathrm{spec}\alpha \subseteq \mathrm{supp}\hat{\alpha}$)
まず、 $\chi\notin \mathrm{supp}\hat{\alpha}$ とする。すなわち
$$
\hat{\alpha}(\chi)=\int_G \alpha_g \overline{\chi(g)}dg=0
$$
である。このとき、ある $f_0\in L^1(G,dg)$ でいい感じのものが取れるかを考えたい。
