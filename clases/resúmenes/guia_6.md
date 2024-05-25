# Paradigma de Godel (Parte 2)

## Continuación de $\Sigma$-p.r.

### Sumatoria, productoria y concatenatoria de funciones $\Sigma$-p.r.

- *Definiciones*: Sea $\Sigma$ un alfabeto finito y $f:\omega\times S_1\times...\times S_n\times L_1\times...\times L_m\to\omega$ con $S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ no vacíos, entonces $\forall x,y\in\omega, (\vec{x},\vec{\alpha})\in S_1\times...\times S_n\times L_1\times...\times L_m$ definimos:
    $$\begin{aligned}
    \sum_{t=x}^{t=y}f(t,\vec{x},\vec{\alpha})&=\begin{cases}
    0 & \text{si } x>y\\
    f(x,\vec{x},\vec{\alpha})+f(x+1,\vec{x},\vec{\alpha})+...+f(y,\vec{x},\vec{\alpha}) & \text{si } x\leq y
    \end{cases}\\ \\
    \prod_{t=x}^{t=y}f(t,\vec{x},\vec{\alpha})&=\begin{cases}
    1 & \text{si } x>y\\
    f(x,\vec{x},\vec{\alpha})\cdot f(x+1,\vec{x},\vec{\alpha})\cdot...\cdot f(y,\vec{x},\vec{\alpha}) & \text{si } x\leq y
    \end{cases}\\
    \end{aligned}$$
    Y, en forma similar, cuando $I_f\subseteq\Sigma^*$, definimos:
    $$\subset_{t=x}^{t=y}f(t,\vec{x},\vec{\alpha})=\begin{cases}
    \varepsilon & \text{si } x>y\\
    f(x,\vec{x},\vec{\alpha})f(x+1,\vec{x},\vec{\alpha})...f(y,\vec{x},\vec{\alpha}) & \text{si } x\leq y
    \end{cases}$$
    todas con dominio $\omega\times\omega\times S_1\times...\times S_n\times L_1\times...\times L_m$.
- *Lemas*: Sea $\Sigma$ un alfabeto finito
  - Si $f:\omega\times S_1\times...\times S_n\times L_1\times...\times L_m\to\omega$ es $\Sigma$-p.r. con $S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ no vacíos, entonces $\lambda xy\vec{x}\vec{\alpha}[\sum_{t=x}^{t=y}f(t,\vec{x},\vec{\alpha})]$ y $\lambda xy\vec{x}\vec{\alpha}[\prod_{t=x}^{t=y}f(t,\vec{x},\vec{\alpha})]$ son $\Sigma$-p.r.
  - Si $f:\omega\times S_1\times...\times S_n\times L_1\times...\times L_m\to\Sigma^*$ es $\Sigma$-p.r. con $S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ no vacíos, entonces $\lambda xy\vec{x}\vec{\alpha}[\subset_{t=x}^{t=y}f(t,\vec{x},\vec{\alpha})]$ es $\Sigma$-p.r.

### Cuantificación acotada de predicados $\Sigma$-p.r. con dominio rectangular

- *Definiciones*:
    - *Variable numérica*: Sea $P:S\times S_1\times...\times S_n\times L_1\times...\times L_m\to\omega$ un predicado con $S,S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ no vacíos, y $\bar{S}\subseteq S$, entonces definimos:
        $$\begin{aligned}
        \lambda x\vec{x}\vec{\alpha}[(\forall t\in\bar{S})_{t\leq x} P(t,\vec{x},\vec{\alpha})]&=\begin{cases}
        1 & \text{si } P(t,\vec{x},\vec{\alpha})=1\ \forall t\leq x\\
        0 & \text{en otro caso}
        \end{cases}\\
        \lambda x\vec{x}\vec{\alpha}[(\exists t\in\bar{S})_{t\leq x} P(t,\vec{x},\vec{\alpha})]&=\begin{cases}
        1 & \text{si } P(t,\vec{x},\vec{\alpha})=1\ \text{para algún } t\leq x\\
        0 & \text{en otro caso}
        \end{cases}
        \end{aligned}$$
        Ambos con dominios $\omega\times S_1\times...\times S_n\times L_1\times...\times L_m$.
        - Cabe destacar que $\lambda x\vec{x}\vec{\alpha}[(\exists t\in\bar{S})_{t\leq x} P(t,\vec{x},\vec{\alpha})]=\neg\lambda x\vec{x}\vec{\alpha}[(\forall t\in\bar{S})_{t\leq x}\neg P(t,\vec{x},\vec{\alpha})]$.
    - *Variable alfabética*: De forma similar, sea $P:S_1\times...\times S_n\times L_1\times...\times L_m\times L\to\omega$ un predicado con $S_i\subseteq\omega$ y $L,L_i\subseteq\Sigma^*$ no vacíos, y $\bar{L}\subseteq L$, entonces definimos
        $$\begin{aligned}
        \lambda x\vec{x}\vec{\alpha}[(\forall\alpha\in\bar{L})_{|\alpha|\leq x} P(\vec{x},\vec{\alpha},\alpha)]&=\begin{cases}
        1 & \text{si } P(\vec{x},\vec{\alpha},\alpha)=1\ \forall\alpha\in\{\beta\in\bar{L}:|\beta|\leq x\}\\
        0 & \text{en otro caso}
        \end{cases}\\
        \lambda x\vec{x}\vec{\alpha}[(\exists\alpha\in\bar{L})_{|\alpha|\leq x} P(\vec{x},\vec{\alpha},\alpha)]&=\begin{cases}
        1 & \text{si } \exists\alpha\in\{\beta\in\bar{L}:|\beta|\leq x\}:P(\vec{x},\vec{\alpha},\alpha)=1\\
        0 & \text{en otro caso}
        \end{cases}
        \end{aligned}$$
        Ambos con dominios $\omega\times S_1\times...\times S_n\times L_1\times...\times L_m$.
        - Cabe destacar que $\lambda x\vec{x}\vec{\alpha}[(\exists\alpha\in\bar{L})_{|\alpha|\leq x} P(\vec{x},\vec{\alpha},\alpha)]=\neg\lambda x\vec{x}\vec{\alpha}[(\forall\alpha\in\bar{L})_{|\alpha|\leq x}\neg P(\vec{x},\vec{\alpha},\alpha)]$.
- *Lemas*: Sea $\Sigma$ un alfabeto finito
  - Si $P:S\times S_1\times...\times S_n\times L_1\times...\times L_m\to\omega$ es un predicado $\Sigma$-p.r. con $S,S_i\subseteq\omega$ y $L_i\subseteq\Sigma^*$ no vacíos, y $\bar{S}\subseteq S$ un conjunto $\Sigma$-p.r., entonces $\lambda x\vec{x}\vec{\alpha}[(\forall t\in\bar{S})_{t\leq x} P(t,\vec{x},\vec{\alpha})]$ y $\lambda x\vec{x}\vec{\alpha}[(\exists t\in\bar{S})_{t\leq x} P(t,\vec{x},\vec{\alpha})]$ son predicados $\Sigma$-p.r.
  - Si $P:S_1\times...\times S_n\times L_1\times...\times L_m\times L\to\omega$ es un predicado $\Sigma$-p.r. con $S_i\subseteq\omega$ y $L,L_i\subseteq\Sigma^*$ no vacíos, y $\bar{L}\subseteq L$ un conjunto $\Sigma$-p.r., entonces $\lambda x\vec{x}\vec{\alpha}[(\forall\alpha\in\bar{L})_{|\alpha|\leq x} P(\vec{x},\vec{\alpha},\alpha)]$ y $\lambda x\vec{x}\vec{\alpha}[(\exists\alpha\in\bar{L})_{|\alpha|\leq x} P(\vec{x},\vec{\alpha},\alpha)]$ son predicados $\Sigma$-p.r.
- *Idea*: En muchos casos de predicados obtenidos por cuantificación a partir de otros predicados, la variable cuantificada tiene una cota natural en términos de las otras variables y entonces componiendo adecuadamente se lo puede presentar como un caso de cuantificación acotada.

## Minimización y funciones $\Sigma$-recursivas

### Definición de función $\Sigma$-recursiva

- *Definición*: Con el nuevo constructor (que se define más abajo), podemos definir los conjuntos $R_0^\Sigma\subseteq R_1^\Sigma\subseteq R_2^\Sigma\subseteq...\subseteq R^\Sigma$ de la siguiente manera:
    $$\begin{aligned}
    R_0^\Sigma&=PR_0^\Sigma \\ \\
    R_{k+1}^\Sigma&=R_k^\Sigma\cup\{f\circ [f_1,..,f_r]:f,f_i\in R_k^\Sigma,r\geq 1]\} \\
    \cup&\{R(f,\mathcal{G}):f,\mathcal{G}_a\in R_k^\Sigma\forall a\in\Sigma\}\cup\{R(f,g):f,g\in R_k^\Sigma\} \\
    \cup&\{M(P):P\text{ es }\Sigma\text{-total y }P\in R_k^\Sigma\} \\ \\
    R^\Sigma&=\bigcup_{k\in\omega}R_k^\Sigma
    \end{aligned}$$
    Con ello, diremos que una función $f$ es $\Sigma$-recursiva si $f\in R^\Sigma$.
        - *Notar que $PR_k^\Sigma\subseteq R_k^\Sigma\forall k\in\omega$, por lo que $PR^\Sigma\subseteq R^\Sigma$*
- *Proposiciones*:
    - Si $f\in R^\Sigma$, entonces $f$ es $\Sigma$-efectivamente computable.
    - Sea $\Sigma$ un alfabeto finito, entonces no toda función $\Sigma$-recursiva es $\Sigma$-p.r. Es decir, $PR^\Sigma\subseteq R^\Sigma$ y $PR^\Sigma\neq R^\Sigma$.

### Minimización de variable numérica

- *Definición*: Sea $\Sigma$ un alfabeto finito y sea $P:D_P\subseteq\omega\times\omega^n\times\Sigma^{*m}\to\omega$ un predicado, dado $(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}$, cuando exista al menos un $t\in\omega$ tal que $P(t,\vec{x},\vec{\alpha})=1$, usaremos $\min_tP(t,\vec{x},\vec{\alpha})$ para denotar al menor de tales $t$'s. Con ello, definimos:
    $$M(P)=\lambda\vec{x}\vec{\alpha}[\min_tP(t,\vec{x},\vec{\alpha})]$$
    El cual cumple que:
    $$\begin{aligned}
    D_{M(P)}&=\{(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}:(\exists t\in\omega) P(t,\vec{x},\vec{\alpha})\}\\
    M(P)(\vec{x},\vec{\alpha})&=\min_t P(t,\vec{x},\vec{\alpha}), \forall(\vec{x},\vec{\alpha})\in D_{M(P)}
    \end{aligned}$$
    Y diremos que $M(P)$ se obtiene por *minimización de variable numérica* a partir de $P$.
- *Regla U*: Si tenemos una función $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\omega$ y buscamos un predicado $P$ tal que $f=M(P)$, muchas veces es útil tratar de diseñar $P$ de modo que para cada $(\vec{x},\vec{\alpha})\in D_f$ se cumpla que $f(\vec{x},\vec{\alpha})=$ único $t\in\omega$ tal que $P(t,\vec{x},\vec{\alpha})$.
- *Lemas*:
    - Si $P:D_P\subseteq\omega\times\omega^n\times\Sigma^{*m}\to\omega$ es un predicado $\Sigma$-efectivamente computable y $D_P$ es $\Sigma$-efectivamente computable, entonces $M(P)$ es $\Sigma$-efectivamente computable.
    - *Minimización acotada de variable numérica de predicados $\Sigma$-p.r.*: Sean $n,m\geq 0$ y $P:D_P\subseteq\omega\times\omega^n\times\Sigma^{*m}\to\omega$ un predicado $\Sigma$-p.r., entonces
        - $M(P)$ es $\Sigma$-recursiva
        - Si hay una función $\Sigma$-p.r. $f:\omega^n\times\Sigma^{*m}\to\omega$ tal que $M(P)(\vec{x},\vec{\alpha})=\min_t P(t,\vec{x},\vec{\alpha})\leq f(\vec{x},\vec{\alpha})\forall(\vec{x},\vec{\alpha})\in D_{M(P)}$, entonces $M(P)$ es $\Sigma$-p.r.
- *Ejemplos*: Sea $\Sigma$ un alfabeto finito, entonces
    - $Q:\omega\times N\to\omega$ con $(x,y)\to$ (cociente de la división de $x$ por $y$), es $\Sigma$-p.r.
    - $R:\omega\times N\to\omega$ con $(x,y)\to$ (resto de la división de $x$ por $y$), es $\Sigma$-p.r.
    - $M=\lambda xy[mcd(x,y)]$ es $\Sigma$-p.r.
    - $G=\lambda xy[mcm(x,y)]$ es $\Sigma$-p.r.
    - $pr:N\to\omega$ con $n\to$ (el $n$-ésimo número primo), es $\Sigma$-p.r.
    - $\lambda xi[(x)_i]$ es $\Sigma$-p.r.
    - $Lt$ es $\Sigma$-p.r.

### Minimización de variable alfabética

- *Definición*: Sea $\Sigma\neq\emptyset$ un alfabeto con $\leq$ un orden total sobre este, y sea $P:D_P\subseteq\omega^n\times\Sigma^{*m}\times\Sigma^*\to\omega$ un predicado, dado $(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}$, cuando exista al menos un $\alpha\in\Sigma^*$ tal que $P(\vec{x},\vec{\alpha},\alpha)=1$, usaremos $\min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha)$ para denotar al menor de tales $\alpha$'s. Con ello, definimos:
    $$M^\leq(P)=\lambda\vec{x}\vec{\alpha}[min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha)]$$
    El cual cumple que:
    $$\begin{aligned}
    D_{M^\leq(P)}&=\{(\vec{x},\vec{\alpha})\in\omega^n\times\Sigma^{*m}:(\exists\alpha\in\Sigma^*) P(\vec{x},\vec{\alpha},\alpha)=1\}\\ \\
    M^\leq(P)(\vec{x},\vec{\alpha})&=min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha), \forall(\vec{x},\vec{\alpha})\in D_{M^\leq(P)}
    \end{aligned}$$
    Y diremos que $M^\leq(P)$ se obtiene por *minimización de variable alfabética* a partir de $P$.
- *Lemas*:
    - *Minimización acotada de variable alfabética de predicados $\Sigma$-p.r.*: Sea $\Sigma\neq\emptyset$ un alfabeto, $\leq$ un orden total sobre $\Sigma$ y $n,m\geq 0$ tales que $P:D_P\subseteq\omega^n\times\Sigma^{*m}\times\Sigma^*\to\omega$ es un predicado $\Sigma$-p.r., entonces:
        - $M^\leq(P)$ es $\Sigma$-recursiva
        - Si existe una función $\Sigma$-p.r. $f:\omega^n\times\Sigma^{*m}\to\omega$ tal que $|M^\leq(P)(\vec{x},\vec{\alpha})|=|min_\alpha^\leq P(\vec{x},\vec{\alpha},\alpha)|\leq f(\vec{x},\vec{\alpha})\forall(\vec{x},\vec{\alpha})\in D_{M^\leq(P)}$, entonces $M^\leq(P)$ es $\Sigma$-p.r.

### Conjuntos $\Sigma$-recursivamente enumerables

- *Definición*: Diremos que un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-recursivamente enumerable cuando sea vacío o haya una función $F:\omega\to\omega^n\times\Sigma^{*m}$ tal que $I_F=S$ y $F_{(i)}$ sea $\Sigma$-recursiva $\forall i\in\{1,...,n+m\}$.

### Conjuntos $\Sigma$-recursivos

- *Definición*: Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-recursivo si su función característica $\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-recursiva.
- *Lemas*: Sea $\Sigma$ un alfabeto finito
    - Si $P:S\subseteq\omega^n\times\Sigma^{*m}\to\omega$ y $Q:S\subseteq\omega^n\times\Sigma^{*m}\to\omega$ son predicados $\Sigma$-r., entonces $P\land Q$, $P\lor Q$ y $\neg P$ son predicados $\Sigma$-r también.
    - Si $S_1,S_2\subseteq\omega^n\times\Sigma^{*m}$ son conjuntos $\Sigma$-r., entonces $S_1\cup S_2$, $S_1\cap S_2$ y $S_1-S_2$ son conjuntos $\Sigma$-r también.

## Independencia del alfabeto

- *Teorema*: Sean $\Sigma$ y $\Gamma$ dos alfabetos finitos cualesquiera:
    - Sea $f$ una función $\Sigma$-mixta y $\Gamma$-mixta, entonces $f$ es $\Sigma$-(r./p.r.) $\Leftrightarrow$ $f$ es $\Gamma$-(r./p.r.).
    - Sea $S$ un conjunto $\Sigma$-mixto y $\Gamma$-mixto, entonces $S$ es $\Sigma$-(r./p.r./r.e.) $\Leftrightarrow$ $S$ es $\Gamma$-(r./p.r./r.e.).