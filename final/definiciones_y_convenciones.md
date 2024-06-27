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

1. Para $d,d'\in Des,n\geq 0$, escribiremos $d\overset{n}{\vdash}d'$ si $\exists d_1,...,d_{n+1}$ tales que $d=d_1,d'=d_{n+1}$ y $d_i\vdash d_{i+1}\forall i=1,...,n$.
    - *Notar que $d\overset{0}{\vdash}d'\Leftrightarrow d=d'$*
2. Diremos que una palabra $\alpha\in\Sigma^*$ es aceptada por $M$ por *alcance de estado final* cuando $\lfloor q_0B\alpha\rfloor\overset{*}{\vdash}d$, con $d:St(d)\in F$. Luego, el *lenguaje aceptado por $M$ por alcance de estado final* se define como $L(M)=\{\alpha\in\Sigma^*:\alpha\text{ es aceptada por }M\text{ por alcance de estado final}\}$
3. Diremos que una palabra $\alpha\in\Sigma^*$ es aceptada por $M$ por *detención* cuando $M$ se detiene partiendo de $\lfloor q_0B\alpha\rfloor$. Luego, el *lenguaje aceptado por $M$ por detención* se define como $H(M)=\{\alpha\in\Sigma^*:\alpha\text{ es aceptada por }M\text{ por detención}\}$
4. Si $f$ es una función $\Sigma$-mixta y $n,m\in\omega:D_f\subseteq\omega^n\times\Sigma^{*m}$,
    - Si $I_f\subseteq\omega$, decimos que $f$ es de tipo $(n,m,\#)$
    - Si $I_f\subseteq\Sigma^*$, decimos que $f$ es de tipo $(n,m,*)$
4. Dado $x\in N$, usaremos $(x)$ para denotar a la única infinitupla $(s_1,s_2,...)\in\omega^{[N]}$ tal que $x=\langle s_1,s_2,...\rangle=\prod_{i=1}^\infty pr(i)^{s_i}$
5. Para cada $i\in N$, usaremos $(x)_i$ para denotar a $s_i$ de la anterior infinitupla. Es decir, $(x)_i$ es el exponente de $pr(i)$ en la única factorización prima de $x$

## Combo 3

Defina:

1. Cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-recursivamente enumerable (no hace falta que defina "función $\Sigma$-recursiva")
2. $s^\leq$
3. $*^\leq$
4. $\#^\leq$

### Resolución

1. Diremos que un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-recursivamente enumerable cuando sea vacío o haya una función $F:\omega\to\omega^n\times\Sigma^{*m}$ tal que $I_F=S$ y $F_{(i)}$ sea $\Sigma$-recursiva $\forall i\in\{1,...,n+m\}$

Los siguientes puntos se definen en base a $\Sigma$ alfabeto no vacío y $\leq$ orden total sobre $\Sigma$, siendo $\Sigma=\{a_1,...,a_n\}$ con $a_1\lt a_2\lt ...\lt a_n$. Luego:
2. La función *siguiente* se define como $$\begin{aligned}s^\leq&:\Sigma^*\to\Sigma^*\\ \\ s^\leq((a_n)^m)&=(a_1)^{m+1}\ \forall m\geq 0\\ \\ s^\leq(\alpha a_i(a_n)^m)&=\alpha a_{i+1} (a_1)^m\ \forall\alpha\in\Sigma^*,\ i\in\{1,...,n-1\},\ m\geq 0\end{aligned}$$
3. Función que asigna a cada $n\in\omega$ la $n+1$-ésima palabra de la lista: $$\begin{aligned}*^\leq&:\omega\to\Sigma^*\\ \\ *^\leq(0)&=\varepsilon\\ \\ *^\leq(n+1)&=s^\leq(*^\leq(n))\end{aligned}$$
4. Inversa de la anterior: $$\begin{aligned}\#^\leq&:\Sigma^*\to\omega\\ \\ \#^\leq(\varepsilon)&=0\\ \\ \#^\leq(a_{i_k}...a_{i_0})&=\sum_{j=0}^k i_jn^j\end{aligned}$$

## Combo 4

Defina cuándo una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es llamada $\Sigma$-efectivamente computable y defina "el procedimiento $\mathbb{P}$ computa a la función $f$".

### Resolución

Una función $\Sigma$-mixta $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to O$ (para $O\in\{\omega,\Sigma^*\}$) es $\Sigma$-efectivamente computable si hay un procedimiento $\mathbb{P}$ tal que:
- El conjunto de datos de entrada de $\mathbb{P}$ es $\omega^n\times\Sigma^{*m}$
- El conjunto de datos de salida está contenido en $O$
- Si $(\vec{x},\vec{\alpha})\in D_f$, entonces $\mathbb{P}$ se detiene partiendo de $(\vec{x},\vec{\alpha})$ y da como salida $f(\vec{x},\vec{\alpha})$
- Si $(\vec{x},\vec{\alpha})\notin D_f$, entonces $\mathbb{P}$ no se detiene partiendo de $(\vec{x},\vec{\alpha})$
En estos casos, diremos que este $\mathbb{P}$ computa a la función $f$.

## Combo 5

Defina cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-efectivamente computable y defina "el procedimiento efectivo $\mathbb{P}$ decide la pertenencia a $S$".

### Resolución

Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente computable cuando la función $\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-efectivamente computable.

Es decir, $S$ es $\Sigma$-efectivamente computable si existe un procedimiento $\mathbb{P}$ tal que:
- El conjunto de datos de entrada de $\mathbb{P}$ es $\omega^n\times\Sigma^{*m}$, siempre termina y da como dato de salida un elemento de $\{0,1\}$
- Dado $(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}$, $\mathbb{P}$ se detiene partiendo de $(\vec{x}, \vec{\alpha})$ y da como salida $1$ si $(\vec{x},\vec{\alpha})\in S$ y $0$ en caso contrario.

En este caso, decimos que el procedimiento efectivo $\mathbb{P}$ decide la pertenencia a $S$.

## Combo 6

Defina cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-recursivamente enumerable y defina "el procedimiento efectivo $\mathbb{P}$ enumera a $S$".

### Resolución

Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente enumerable si es vacío o $\exists F:\omega\to\omega^n\times\Sigma^{*m}$ tal que $I_F=S$ y $F_{(i)}$ es $\Sigma$-efectivamente computable $\forall i\in\{1,...,n+m\}$.

Es decir, $S\neq\emptyset$ es $\Sigma$-efectivamente enumerable si existe un procedimiento efectivo $\mathbb{P}$ tal que:
- El conjunto de datos de entrada de $\mathbb{P}$ es $\omega$
- $\mathbb{P}$ se detiene para cada $x\in\omega$
- El conjunto de datos de salida de $\mathbb{P}$ es igual a $S$

En este caso, decimos que el procedimiento efectivo $\mathbb{P}$ enumera a $S$.

## Combo 7

Defina cuándo una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es llamada $\Sigma$-Turing computable y defina "la máquina de Turing $M$ computa a la función $f$".

### Resolución

Diremos que $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es $\Sigma$-Turing computable si existe una máquina de Turing con *unit* $M=(Q,\Sigma,\Gamma,\delta,q_0,B,\shortmid,F)$ tal que:
- Si $(\vec{x},\vec{\alpha})\in D_f$, entonces $\exists p\in Q:\lfloor q_0B\shortmid^{x_1}B...B\shortmid^{x_n}B\alpha_1B...B\alpha_m\rfloor\overset{*}{\vdash}\lfloor pB\shortmid^{f(\vec{x},\vec{\alpha})}\rfloor$ y $\lfloor pB\shortmid^{f(\vec{x},\vec{\alpha})}\rfloor\not\vdash d\forall d\in Des$
- Si $(\vec{x},\vec{\alpha})\in (\omega^n\times\Sigma^{*m})-D_f$, entonces $M$ **no** se detiene partiendo de $\lfloor q_0B\shortmid^{x_1}B...B\shortmid^{x_n}B\alpha_1B...B\alpha_m\rfloor$

En este caso, diremos que la máquina de Turing $M$ computa a la función $f$.

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
