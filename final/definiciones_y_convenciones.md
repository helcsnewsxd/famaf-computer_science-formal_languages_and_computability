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

Los siguientes puntos se definen en base a $\Sigma$ alfabeto no vacío y $\leq$ orden total sobre $\Sigma$, siendo $\Sigma=\{a_1,...,a_n\}$ con $a_1<a_2<...<a_n$. Luego:

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

1. Este caso se trata de **minimización de variable numérica**. Sea $\Sigma$ un alfabeto finito y sea $P:D_P\subseteq\omega\times\omega^n\times\Sigma^{*m}\to\omega$ un predicado, dado $(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}$, cuando exista al menos un $t\in\omega:P(t,\vec{x},\vec{\alpha})=1$, usaremos $\min_t P(t,\vec{x},\vec{\alpha})$ para denotar al menor de tales $t$'s. Con ello, definimos $$M(P)=\lambda\vec{x}\vec{\alpha}\left[\min_t P(t,\vec{x},\vec{\alpha})\right]$$ El cual cumple que: $$\begin{aligned} D_{M(P)}&=\{(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}:(\exists t\in\omega) P(t,\vec{x},\vec{\alpha})\}\\ \\ M(P)(\vec{x},\vec{\alpha})&=\min_t P(t,\vec{x},\vec{\alpha}),\ \forall(\vec{x},\vec{\alpha})\in D_{M(P)}\end{aligned}$$ Y diremos que $M(P)$ se obtiene por *minimización de variable numérica* a partir de $P$.
2. Definimos la función del *mayor factor primo* como $$\begin{aligned}Lt&:N\to\omega\\ \\ Lt(x)&=\begin{cases}\max\{i\in N:(x)_i\neq 0\} &\text{si }x\neq 1\\ 0 &\text{si }x=1\end{cases} \end{aligned}$$
3. Sea $\Sigma$ un alfabeto finito, un conjunto $\Sigma$-mixto $S$ es llamado *rectangular* si es de la forma $S_1\times ...\times S_n\times L_1\times ...\times L_m$ con $S_i\subseteq\omega$ y $L_j\subseteq\Sigma^*$
4. Dado un conjunto $\Sigma$-mixto $S$ y $n,m\in\omega:S\subseteq\omega^n\times\Sigma^{*m}$, entonces $S$ es de tipo $(n,m)$

## Combo 9

Defina:

1. "$I$ es una instrucción de $S^\Sigma$"
2. "$\mathcal{P}$ es un programa de $S^\Sigma$"
3. $I_i^\mathcal{P}$
4. $n(\mathcal{P})$
5. $Bas$

### Resolución

1. Una *instrucción de $\mathcal{S}^\Sigma$* es ya sea una instrucción básica de $\mathcal{S}^\Sigma$, o una palabra de la forma $\alpha I$, donde $\alpha\in\{L\bar{n}:n\in N\}$ e $I$ es una instrucción básica de $\mathcal{S}^\Sigma$.
    - Cuando $I$ es de la forma $L\bar{n}J$ con $J$ una instrucción básica, diremos que $L\bar{n}$ es la *label de $I$*
    - Una *instrucción básica de $\mathcal{S}^\Sigma$* es una palabra $(\Sigma\cup\Sigma_P)^*$ la cual es de alguna de las siguientes formas (donde $a\in\Sigma;\ k,n\in N$):
        - $N\bar{k}\leftarrow N\bar{k}+1$
        - $N\bar{k}\leftarrow N\bar{k}\dot{-}1$
        - $N\bar{k}\leftarrow N\bar{n}$
        - $N\bar{k}\leftarrow 0$
        - $P\bar{k}\leftarrow P\bar{k}.a$
        - $P\bar{k}\leftarrow\ ^\curvearrowright P\bar{k}$
        - $P\bar{k}\leftarrow P\bar{n}$
        - $P\bar{k}\leftarrow\varepsilon$
        - IF $N\bar{k}\neq 0$ GOTO $L\bar{n}$
        - IF $P\bar{k}$ BEGINS $a$ GOTO $L\bar{n}$
        - GOTO $L\bar{n}$
        - SKIP
2. Un *programa* de $\mathcal{S}^\Sigma$ es una palabra de la forma $I_1I_2..I_n$ donde $n\geq 1,I_1,..,I_n\in Ins^\Sigma$ y además se cumple la *ley de los GOTO*: $\forall i\in\{1,..,n\}$, si GOTO$L\bar{m}$ es un tramo final de $I_i$, entonces $\exists j\in\{1,..,n\}$ tal que $I_j$ tiene label $L\bar{m}$
3. Definimos $I_i^\mathcal{P}$ como la $i$-ésima instrucción de $\mathcal{P}$ y, además, $I_i^\mathcal{P}=\varepsilon$ cuando $i=0$ o $i>n(\mathcal{P})$
4. Definimos $n(\mathcal{P})$ como la cantidad de instrucciones de $\mathcal{P}$
5. Definimos $Bas:Ins^\Sigma\to(\Sigma\cup\Sigma_p)^*$ dada por $$Bas(I)=\begin{cases} J & \text{si }I\text{ es de la forma }L\bar{k}J\text{ con }J\in Ins^\Sigma\\ I & \text{en otro caso} \end{cases}$$

## Combo 10

Defina, relativo al lenguaje $S^\Sigma$:

1. "Estado"
2. "Descripción instantánea"
3. $S_\mathcal{P}$
4. "Estado obtenido luego de $t$ pasos, partiendo del estado $(\vec{s},\vec{\sigma})$"
5. "$\mathcal{P}$ se detiene (luego de $t$ pasos), partiendo del estado $(\vec{s},\vec{\sigma})$"

### Resolución

1. Un estado es un par $(\vec{s},\vec{\sigma})=((s_1,s_2,...),(\sigma_1,\sigma_2,...))\in\omega^{[N]}\times\Sigma^{*[N]}$ y, si $i\geq 1$, entonces diremos que $s_i$ es el contenido o valor de la variable $N\bar{i}$ en el estado $(\vec{s},\vec{\sigma})$ y $\sigma_i$ es el contenido o valor de la variable $P\bar{i}$ en el estado $(\vec{s},\vec{\sigma})$
2. Una descripción instantánea es una terna $(i,\vec{s},\vec{\sigma})$ tal que $(\vec{s},\vec{\sigma})$ es un estado e $i\in\omega$. Intuitivamente, $(i,\vec{s},\vec{\sigma})$ nos dice que las variables están en el estado $(\vec{s},\vec{\sigma})$ y que la instrucción que debemos realizar es $I_i^\mathcal{P}$
3. Dado un programa $\mathcal{P}$, definimos $S_\mathcal{P}:\omega\times\omega^{[N]}\times\Sigma^{*[N]}\to\omega\times\omega^{[N]}\times\Sigma^{*[N]}$ como la función que asignará a una descripción instantánea $(i,\vec{s},\vec{\sigma})$ la descripción instantánea sucesora de $(i,\vec{s},\vec{\sigma})$ con respecto a $\mathcal{P}$. Es decir, hay varios casos posibles:
    -  Si $i\notin\{1,..,n(\mathcal{P})\}$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i,\vec{s},\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=N\bar{k}\leftarrow N\bar{k}\dot{-}1$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,(s_1,..,s_{k-1},s_k\dot{-}1,s_{k+1},..),\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=N\bar{k}\leftarrow N\bar{k}+1$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,(s_1,..,s_{k-1},s_k+1,s_{k+1},..),\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=N\bar{k}\leftarrow N\bar{n}$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,(s_1,..,s_{k-1},s_n,s_{k+1},..),\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=N\bar{k}\leftarrow 0$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,(s_1,..,s_{k-1},0,s_{k+1},..),\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=\text{IF }N\bar{k}\neq 0\text{ GOTO }L\bar{m}$, entonces hay dos posibilidades:
        - Si el valor de $N\bar{k}$ es $0$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},\vec{\sigma})$
        - Si el valor de $N\bar{k}$ es no nulo, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(\min\{l:I_l^\mathcal{P}\text{ tiene label }L\bar{m}\},\vec{s},\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=P\bar{k}\leftarrow\ ^\curvearrowright P\bar{k}$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},(\sigma_1,..,\sigma_{k-1},\ ^\curvearrowright\sigma_k,\sigma_{k+1},..))$
    - Si $Bas(I_i^\mathcal{P})=P\bar{k}\leftarrow P\bar{k}.a$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},(\sigma_1,..,\sigma_{k-1},\sigma_k a,\sigma_{k+1},..))$
    - Si $Bas(I_i^\mathcal{P})=P\bar{k}\leftarrow P\bar{n}$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},(\sigma_1,..,\sigma_{k-1},\sigma_n,\sigma_{k+1},..))$
    - Si $Bas(I_i^\mathcal{P})=P\bar{k}\leftarrow\varepsilon$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},(\sigma_1,..,\sigma_{k-1},\varepsilon,\sigma_{k+1},..))$
    - Si $Bas(I_i^\mathcal{P})=\text{IF }P\bar{k}\text{ BEGINS }a\text{ GOTO }L\bar{m}$, entonces hay dos posibilidades:
        - Si el valor de $P\bar{k}$ comienza con $a$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(\min\{l:I_l^\mathcal{P}\text{ tiene label }L\bar{m}\},\vec{s},\vec{\sigma})$
        - Si el valor de $P\bar{k}$ no comienza con $a$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=\text{GOTO }L\bar{m}$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(\min\{l:I_l^\mathcal{P}\text{ tiene label }L\bar{m}\},\vec{s},\vec{\sigma})$
    - Si $Bas(I_i^\mathcal{P})=\text{SKIP}$, entonces $S_\mathcal{P}(i,\vec{s},\vec{\sigma})=(i+1,\vec{s},\vec{\sigma})$
4. Diremos que $S_\mathcal{P}(S_\mathcal{P}(...(S_\mathcal{P}(1,\vec{s},\vec{\sigma}))...))=(j,\vec{u},\vec{\eta})$ con $S_\mathcal{P}$ aplicado $t$ veces, es la *descripción instantánea obtenida luego de $t$ pasos partiendo del estado $(\vec{s},\vec{\sigma})$*, y $(\vec{u},\vec{\eta})$ es el estado obtenido luego de $t$ pasos partiendo del estado $(\vec{s},\vec{\sigma})$
5. Cuando la primer coordenada de $S_\mathcal{P}(S_\mathcal{P}(...(S_\mathcal{P}(1,\vec{s},\vec{\sigma}))...))$ (con $S_\mathcal{P}$ aplicado $t$ veces) es $n(\mathcal{P})+1$, diremos que $\mathcal{P}$ se detiene (luego de $t$ pasos), partiendo desde el estado $(\vec{s},\vec{\sigma})$

## Combo 11

Defina:

1. $\Psi_\mathcal{P}^{n,m,\#}$
2. "$f$ es $\Sigma$-computable"
3. "$\mathcal{P}$ computa a $f$"
4. $M^\leq(P)$

### Resolución

1. Dado $\mathcal{P}\in Pro^\Sigma$, definimos $\Psi_\mathcal{P}^{n,m,\#}$ como: $$\begin{aligned}D_{\Psi_\mathcal{P}^{n,m,\#}} &= \{(\vec{x}, \vec{\alpha})\in\omega^n\times\Sigma^{*m}:\mathcal{P}\text{ termina partiendo de }||\vec{x}, \vec{\alpha}||\}\\ \\ \Psi_\mathcal{P}^{n,m,\#}(\vec{x}, \vec{\alpha}) &= \text{valor de N1 cuando }\mathcal{P}\text{ termina partiendo de }||\vec{x}, \vec{\alpha}||\end{aligned}$$
2. Una función $\Sigma$-mixta $f:S\subseteq\omega^n\times\Sigma^{*m}\to\omega$ es $\Sigma$-computable si existe un programa $\mathcal{P}\in \mathcal{S}^\Sigma$ tal que $f=\Psi_\mathcal{P}^{n,m,\#}$
    - Se define de forma análoga para funciones $\Sigma$-mixtas $f:S\subseteq\omega^n\times\Sigma^{*m}\to\Sigma^*$ con $f=\Psi_\mathcal{P}^{n,m,*}$
3. En el caso anterior, decimos que $f$ es *computada* por $\mathcal{P}$
4. Sea $\Sigma\neq\emptyset$ un alfabeto con $\leq$ un orden total sobre este, y sea $P:D_P\subseteq\omega^n\times\Sigma^{*m}\times\Sigma^*\to\omega$ un predicado, dado $(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}$, cuando exista al menos un $\alpha\in\Sigma^*$ tal que $P(\vec{x},\vec{\alpha},\alpha)=1$, usaremos $\min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha)$ para denotar al menor de tales $\alpha$'s. Con ello, definimos: $$M^\leq(P)=\lambda\vec{x}\vec{\alpha}[min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha)]$$ El cual cumple que: $$\begin{aligned} D_{M^\leq(P)}&=\{(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}:(\exists\alpha\in\Sigma^*) P(\vec{x},\vec{\alpha},\alpha)=1\}\\ \\ M^\leq(P)(\vec{x},\vec{\alpha})&=min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha), \forall(\vec{x},\vec{\alpha})\in D_{M^\leq(P)}\end{aligned}$$ Y diremos que $M^\leq(P)$ se obtiene por *minimización de variable alfabética* a partir de $P$.

## Combo 12

Defina cuándo un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es llamado $\Sigma$-computable, cuándo es llamado $\Sigma$-enumerable y defina "el programa $\mathcal{P}$ enumera a $S$".

### Resolución

- Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-computable si $\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-computable. Es decir, es $\Sigma$-computable si y solo si hay un programa $\mathcal{P}\in Pro^\Sigma$ que computa a $\chi_S^{\omega^n\times\Sigma^{*m}}$:
        - Si $(\vec{x}, \vec{\alpha})\in S$, entonces $\mathcal{P}$ se detiene partiendo de $||x_1, .., x_n, \alpha_1, .., \alpha_m||$ y la variable $N1$ queda con contenido igual a $1$
        - Si $(\vec{x}, \vec{\alpha})\notin S$, entonces $\mathcal{P}$ se detiene partiendo de $||x_1, .., x_n, \alpha_1, .., \alpha_m||$ y la variable $N1$ queda con contenido igual a $0$
    Decimos que $\mathcal{P}$ decide la pertenencia a $S$ respecto al conjunto $\omega^n\times\Sigma^{*m}$
- Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-enumerable si es vacío o existe una función $F:\omega\to\omega^n\times\Sigma^{*m}$ tal que $I_F=S$ y $F_{(i)}$ sea una función $\Sigma$-computable para todo $i\in{1,..,n+m}$
- Propiedad: Sea $S\subseteq\omega^n\times\Sigma^{*m}$ un conjunto no vacío, entonces son equivalentes:
    - $S$ es $\Sigma$-enumerable
    - Hay un programa $\mathcal{P}\in Pro^\Sigma$ tal que
        - $\forall x\in\omega$, $\mathcal{P}$ se detiene partiendo de $||x||$ y llega a un estado de la forma $((x_1, .., x_n, y_1, ...) , (\alpha_1, .., \alpha_m, \beta_1, ..))$ con $(x_1, .., x_n, \alpha_1, .., \alpha_m)\in S$
        - $\forall (x_1, .., x_n, \alpha_1, .., \alpha_m)\in S$, $\exists x\in\omega$ tal que $\mathcal{P}$ se detiene partiendo de $||x||$ y llega a un estado de la forma $((x_1, .., x_n, y_1, ...) , (\alpha_1, .., \alpha_m, \beta_1, ..))$
    Decimos que $\mathcal{P}$ *enumera* a $S$

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

- Sean $n,m\in\omega$, definimos las siguientes funciones: $$\begin{aligned} i^{n,m} &: \omega\times\omega^n\times\Sigma^{*m}\times Pro^\Sigma\to\omega\\ E^{n,m}_\# &: \omega\times\omega^n\times\Sigma^{*m}\times Pro^\Sigma\to\omega^{[N]}\\ E^{n,m}_* &: \omega\times\omega^n\times\Sigma^{*m}\times Pro^\Sigma\to\Sigma^{[N]}\\ \end{aligned}$$ de modo que $(i^{n,m}(t, \vec{x}, \vec{\alpha}, \mathcal{P}), E^{n,m}_\#(t, \vec{x}, \vec{\alpha}, \mathcal{P}), E^{n,m}_*(t, \vec{x}, \vec{\alpha}, \mathcal{P}))$ es la descripción instantánea que se obtiene luego de correr $\mathcal{P}$ una cantidad $t$ de pasos partiendo del estado $||x_1, .., x_n, \alpha_1, .., \alpha_m||$.
- Definimos también las funciones $$\begin{aligned} E^{n,m}_{\#j}: \omega\times\omega^n\times\Sigma^{*m}\times Pro^\Sigma\to\omega\\ E^{n,m}_{*j}:\omega\times\omega^n\times\Sigma^{*m}\times Pro^\Sigma\to\Sigma^*\end{aligned}$$ que marcan el valor de la $j$-ésima componente de $E^{n,m}_\#$ y $E^{n,m}_*$, respectivamente.
- Dados $n,m\in\omega$, definimos $Halt^{n,m}=\lambda t\vec{x}\vec{\alpha}\mathcal{P} [i^{n,m}(t, \vec{x}, \vec{\alpha}, \mathcal{P}) = n(\mathcal{P}) + 1]$
    - Básicamente, $Halt^{n,m}$ es un predicado que dice si $\mathcal{P}$ se detiene luego de $t$ pasos partiendo del estado $||x_1, .., x_n, \alpha_1, .., \alpha_m||$.
- Definimos $T^{n,m}=M(Halt^{n,m})$
    - $D_{T^{n,m}}=\{(\vec{x}, \vec{\alpha}, \mathcal{P}): \mathcal{P}\text{ se detiene partiendo de }||x_1, .., x_n, \alpha_1, .., \alpha_m||\}$
    - Para $(\vec{x}, \vec{\alpha}, \mathcal{P})\in D_{T^{n,m}}$, $T^{n,m}(\vec{x}, \vec{\alpha}, \mathcal{P})$ indica la cantidad de pasos necesarios para que $\mathcal{P}$ se detenga partiendo de $||x_1, .., x_n, \alpha_1, .., \alpha_m||$.
- Cuando $\Sigma\supseteq\Sigma_p$, podemos definir $AutoHalt^\Sigma=\lambda\mathcal{P}[(\exists t\in\omega) Halt^{0,1}(t,\mathcal{P},\mathcal{P})]$
    - Notar que $D_{AutoHalt^\Sigma}=Pro^\Sigma$ y que $\forall\mathcal{P}\in Pro^\Sigma, AutoHalt^\Sigma(\mathcal{P})=1$ sii $\mathcal{P}$ se detiene partiendo del estado $||\mathcal{P}||$.
- Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $A=\{\mathcal{P}\in Pro^\Sigma: AutoHalt^\Sigma(\mathcal{P})=1\}$ y $N=\{\mathcal{P}\in Pro^\Sigma: AutoHalt^\Sigma(\mathcal{P})=0\}$.

## Combo 14

Explique en forma detallada la notación lambda.

### Resolución

## Combo 15

Dada una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$, describa qué tipo de objeto es y qué propiedades debe tener el macro: $$[V2\leftarrow f(V1,W1)]$$

### Resolución

## Combo 16

Dado un predicado $P:D_P\subseteq\omega^n\times\Sigma^{*m}\to\omega$, describa qué tipo de objeto es y qué propiedades debe tener el macro: $$[\text{IF }P(V1,W1)\text{ GOTO }A1]$$

### Resolución
