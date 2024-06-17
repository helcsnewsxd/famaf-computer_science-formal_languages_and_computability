# Resultados básicos presentados en el paradigma recursivo

## Lema de división por casos para funciones $\Sigma$-recursivas

- *Lema*: Si $f_i: D_{f_i}\subseteq\omega^n\times\Sigma^{*m}\to O$ (con $O\in\{\omega, \Sigma^*\}$) para $i=1,..,k$ son funciones $\Sigma$-recursivas tales que $D_{f_i}\neq D_{f_j}$ para $i\neq j$, entonces la función $f_1\cup..\cup f_k$ es $\Sigma$-recursiva.
- *Lema*: Si $P:D_P\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es un predicado $\Sigma$-recursivo y $D_P$ es $\Sigma$-recursivo, entonces $M(P)$ es $\Sigma$-recursivo.
    - *No se cumple la recíproca*

## Lema de restricción de funciones $\Sigma$-recursivas

- *Lema*: Si $f: D_f\subseteq\omega^n\times\Sigma^{*m}\to O$ es una función $\Sigma$-recursiva y $S\subseteq D_f$ es $\Sigma$-recursivo enumerable, entonces la función $f|_S$ es $\Sigma$-recursiva.

## Conjuntos $\Sigma$-recursivamente enumerables y $\Sigma$-recursivos

- *Lema*: Si $S_1, S_2\subseteq\omega^n\times\Sigma^{*m}$ son $\Sigma$-recursivos, entonces $S_1\cup S_2$, $S_1\cap S_2$ y $S_1 - S_2$ son $\Sigma$-recursivos.
- *Lema*: Sea $\Sigma$ un alfabeto finito, se tiene que
    - Si $S_1, S_2\subseteq\omega^n\times\Sigma^{*m}$ son $\Sigma$-recursivamente enumerables, entonces $S_1\cup S_2$ y $S_1\cap S_2$ son $\Sigma$-recursivamente enumerables.
    - Si $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-recursivo, entonces $S$ es $\Sigma$-recursivamente enumerable.
- *Lema*: Sea $S\subseteq\omega^n\times\Sigma^{*m}$, si $S$ y $(\omega^n\times\Sigma^{*m})-S$ son $\Sigma$-recursivamente enumerables, entonces $S$ es $\Sigma$-recursivo.
    - Notar que no todo conjunto $\Sigma$-recursivamente enumerable es $\Sigma$-recursivo.
- *Teorema*: Dado $S\subseteq\omega^n\times\Sigma^{*m}$, las siguientes afirmaciones son equivalentes:
    - $S$ es $\Sigma$-recursivamente enumerable.
    - $S=I_F$ para alguna $F:D_F\subseteq\omega^k\times\Sigma^{*l}\to\omega^n\times\Sigma^{*m}$ tal que cada $F_{(i)}$ es $\Sigma$-recursiva.
    - $S=D_f$ para alguna función $\Sigma$-recursiva $f$.
    - $S=\emptyset$ o $S=I_F$ para alguna $F:\omega\to\omega^n\times\Sigma^{*m}$ tal que cada $F_{(i)}$ es $\Sigma$-p.r.

## El halting problem y los conjuntos $A$ y $N$

- *Definición*: Cuando $\Sigma\supseteq\Sigma_p$, podemos definir $AutoHalt^\Sigma=\lambda\mathcal{P}[(\exists t\in\omega) Halt^{0,1}(t,\mathcal{P},\mathcal{P})]$
    - Notar que $D_{AutoHalt^\Sigma}=Pro^\Sigma$ y que $\forall\mathcal{P}\in Pro^\Sigma, AutoHalt^\Sigma(\mathcal{P})=1$ sii $\mathcal{P}$ se detiene partiendo del estado $||\mathcal{P}||$.
- *Lema*: Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $AutoHalt^\Sigma$ no es $\Sigma$-recursivo.
- *Teorema*: Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $AutoHalt^\Sigma$ no es $\Sigma$-efectivamente computable. Es decir, no hay ningún procedimiento efectivo que decida si un programa de $\mathcal{S}^\Sigma$ termina partiendo de si mismo.
- *Lema*: Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $A=\{\mathcal{P}\in Pro^\Sigma: AutoHalt^\Sigma(\mathcal{P})=1\}$ es $\Sigma$-recursivamente enumerable pero no es $\Sigma$-recursivo. Mas aún, el conjunto $N=\{\mathcal{P}\in Pro^\Sigma: AutoHalt^\Sigma(\mathcal{P})=0\}$ no es $\Sigma$-recursivamente enumerable.
- *Proposición*: Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $A$ es $\Sigma$-efectivamente enumerable y no $\Sigma$-efectivamente computable. El conjunto $N$ no es $\Sigma$-efectivamente enumerable.
    - Es decir, $A$ puede ser enumerado por un procedimiento efectivo pero no hay ningún procedimiento efectivo que decida la pertenencia a $A$.
    - No hay ningún procedimiento efectivo que enumere $N$. Por ello, si un procedimiento efectivo da como salida siempre elementos de $N$, entonces hay una cantidad infinita de elementos de $N$ los cuales nunca da como salida
- *Proposición*: Supongamos $\Sigma\supseteq\Sigma_p$. Entonces, sea $P=C_1^{0,1}|_A\circ\lambda t\alpha[\alpha^{1\dot{-}t}\text{SKIP}^t]|_{\omega\times Pro^\Sigma}$ es $\Sigma$-recursivo pero $M(P)$ no es $\Sigma$-efectivamente computable (y por lo tanto no es $\Sigma$-recursiva).