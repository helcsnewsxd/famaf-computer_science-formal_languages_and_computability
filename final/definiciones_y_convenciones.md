# Definiciones y convenciones notacionales

## Combo 1

Defina:

1. Cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-recursivo (no hace falta que defina "función $\Sigma$-recursiva")
2. $\langle s_1,s_2,...\rangle$
3. "$f$ es una función $\Sigma$-mixta"
4. "familia $\Sigma$-indexada de funciones"
5. $R(f,\mathcal{G})$

### Resolución

1. Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-recursivo si su función característica $\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-recursiva.
2. Dada una infinitupla $(s_1,s_2,...)\in\omega^{[N]}$, se usa $\langle s_1,s_2,...\rangle$ para denotar al número $x=\prod_{i=1}^\infty pr(i)^{s_i}$
3. Sea $\Sigma$ un alfabeto finito y sea $f$ una función, diremos que es $\Sigma$-mixta si $\exists n,m\geq 0:D_f\subseteq\omega^n\times\Sigma^{*m}$ e $I_f\subseteq O$ donde $O\in\{\omega,\Sigma^*\}$
4. Dado un alfabeto $\Sigma$, una familia $\Sigma$-indexada de funciones es una función $\mathcal{G}$ tal que $D_\mathcal{G}=\Sigma$ y $\forall a\in D_\mathcal{G}$, $\mathcal{G}(a)$ es una función.
5. La recursión primitiva para el caso de *variable alfabética* se define de forma distinta para los casos de *valores numéricos* o *alfabéticos*. Por ello, veamos cada uno:
    - **Valores numéricos**: Sea $\Sigma$ un alfabeto finito, y sean $f$ una función y $\mathcal{G}$ una familia $\Sigma$-indexada de funciones tales que: $$\begin{aligned}f&:S_1\times ...\times S_n\times L_1\times ...\times L_m\to\omega\\ \\ \mathcal{G}_a&:\omega\times S_1\times ...\times S_n\times L_1\times ...\times L_m\times\Sigma^*\to\omega\end{aligned}$$ para cada $a\in\Sigma$, y con $S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ conjuntos no vacíos, entonces definimos $$\begin{aligned} R(f,\mathcal{G})&:S_1\times ...\times S_n\times L_1\times ...\times L_m\times\Sigma^*\to\omega\\ \\ R(f,\mathcal{G})(\vec{x},\vec{\alpha},\varepsilon)&=f(\vec{x},\vec{\alpha})\\ \\ R(f,\mathcal{G})(\vec{x},\vec{\alpha},\alpha a)&=\mathcal{G}_a(R(f,\mathcal{G})(\vec{x},\vec{\alpha},\alpha),\vec{x},\vec{\alpha},\alpha) \end{aligned}$$ y decimos que $R(f,\mathcal{G})$ es obtenida por recursión primitiva a partir de $f$ y $\mathcal{G}$.
    - **Valores alfabéticos**: Sea $\Sigma$ un alfabeto finito, y sean $f$ una función y $\mathcal{G}$ una familia $\Sigma$-indexada de funciones tales que: $$\begin{aligned}f&:S_1\times ...\times S_n\times L_1\times ...\times L_m\to\Sigma^*\\ \\ \mathcal{G}_a&:S_1\times ...\times S_n\times L_1\times ...\times L_m\times\Sigma^*\times\Sigma^*\to\Sigma^*\end{aligned}$$ para cada $a\in\Sigma$, y con $S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ conjuntos no vacíos, entonces definimos $$\begin{aligned} R(f,\mathcal{G})&:S_1\times ...\times S_n\times L_1\times ...\times L_m\times\Sigma^*\to\Sigma^*\\ \\ R(f,\mathcal{G})(\vec{x},\vec{\alpha},\varepsilon)&=f(\vec{x},\vec{\alpha})\\ \\ R(f,\mathcal{G})(\vec{x},\vec{\alpha},\alpha a)&=\mathcal{G}_a(\vec{x},\vec{\alpha},\alpha,R(f,\mathcal{G})(\vec{x},\vec{\alpha},\alpha)) \end{aligned}$$ y decimos que $R(f,\mathcal{G})$ es obtenida por recursión primitiva a partir de $f$ y $\mathcal{G}$.

## Combo 2

Defina:

1. $d\overset{n}{\vdash}d'$ (no hace falta que defina $\vdash$)
2. $L(M)$
3. $H(M)$
4. "$f$ es una función de tipo $(n,m,s)$"
5. $(x)$
6. $(x)_i$

### Resolución

## Combo 3

Defina:

1. Cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-recursivamente enumerable (no hace falta que defina "función $\Sigma$-recursiva")
2. $s^\leq$
3. $*^\leq$
4. $\#^\leq$

### Resolución

## Combo 4

Defina cuándo una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es llamada $\Sigma$-efectivamente computable y defina "el procedimiento $\mathbb{P}$ computa a la función $f$".

### Resolución

## Combo 5

Defina cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-efectivamente computable y defina "el procedimiento efectivo $\mathbb{P}$ decide la pertenencia a $S$".

### Resolución

## Combo 6

Defina cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-recursivamente enumerable y defina "el procedimiento efectivo $\mathbb{P}$ enumera a $S$".

### Resolución

## Combo 7

Defina cuándo una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es llamada $\Sigma$-Turing computable y defina "la máquina de Turing $M$ computa a la función $f$".

### Resolución

## Combo 8

Defina:

1. $M(P)$
2. $Lt$
3. Conjunto rectangular
4. "$S$ es un conjunto de tipo $(n,m)$"

### Resolución

## Combo 9

Defina:
1. "$I$ es una instrucción de $S^\Sigma$"
2. "$\mathcal{P}$ es un programa de $S^\Sigma$"
3. $I_i^\mathcal{P}$
4. $n(\mathcal{P})$
5. $Bas$

### Resolución

## Combo 10

Defina, relativo al lenguaje $S^\Sigma$:

1. "Estado"
2. "Descripción instantánea"
3. $S_\mathcal{P}$
4. "Estado obtenido luego de $t$ pasos, partiendo del estado $(\vec{s},\vec{\sigma})$"
5. "$\mathcal{P}$ se detiene (luego de $t$ pasos), partiendo del estado $(\vec{s},\vec{\sigma})$"

### Resolución

## Combo 11

Defina:

1. $\Psi_\mathcal{P}^{n,m,\#}$
2. "$f$ es $\Sigma$-computable"
3. "$\mathcal{P}$ computa a $f$"
4. $M^\leq(P)$

### Resolución

## Combo 12

Defina cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-computable, cuándo es llamado $\Sigma$-enumerable y defina "el programa $\mathcal{P}$ enumera a $S$".

### Resolución

## Combo 13

Defina:

1. $i^{n,m}$
2. $E_\#^{n,m}$
3. $E_*^{n,m}$
4. $E_{\#j}^{n,m}$
5. $E_{*j}^{n,m}$
6. $Halt^{n,m}$
7. $T^{n,m}$
8. $AutoHalt^\Sigma$
9. Los conjuntos $A$ y $N$

### Resolución

## Combo 14

Explique en forma detallada la notación lambda.

### Resolución

## Combo 15

Dada una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$, describa qué tipo de objeto es y qué propiedades debe tener el macro: $$[V2\leftarrow f(V1,W1)]$$

### Resolución

## Combo 16

Dado un predicado $P:D_P\subseteq\omega^n\times\Sigma^{*m}\to\omega$, describa qué tipo de objeto es y qué propiedades debe tener el macro: $$[\text{IF }P(V1,W1)\text{ GOTO }A1]$$

### Resolución
