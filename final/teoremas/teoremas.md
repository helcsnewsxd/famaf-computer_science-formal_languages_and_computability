# Combos de teoremas

## Combo 1

- **Proposición 1 (Caracterización de conjuntos p.r.)** Un conjunto $S$ es $\Sigma$-p.r. sii $S$ es el dominio de alguna función $\Sigma$-p.r.
    - *Nota: en la inducción de la prueba, hacer solo el caso de la composición*
- **Teorema 2 (Neumann vence a Godel)** Si $h$ es $\Sigma$-recursiva, entonces $h$ es $\Sigma$-computable
    - *Nota: en la inducción de la prueba, hacer solo el caso $h=R(f,\mathcal{G})$*

### Resolución

## Combo 2

- **Lema 3 (Lema de división por casos para funciones p.r.)** Supongamos $f_i:D_{f_i}\subseteq\omega^n\times\Sigma^{*m}\to\Sigma^*$, $i=1,...,k$, son funciones $\Sigma$-p.r. tales que $D_{f_i}\cap D_{f_j}=\emptyset$ para $i\neq j$. Entonces $f_1\cup ...\cup f_k$ es $\Sigma$-p.r.
- **Proposición 4 (Caracterización básica de conjuntos enumerables)** Sea $S\subseteq\omega^n\times\Sigma^{*m}$ un conjunto no vacío. Entonces son equivalentes:
    1. $S$ es $\Sigma$-enumerable
    2. Hay un programa $\mathcal{P}\in Pro^\Sigma$ tal que:
        - Para cada $x\in\omega$, tenemos que $\mathcal{P}$ se detiene partiendo desde el estado $||x||$ y llega a un estado de la forma $((x_1,...,x_n,y_1,...),(\alpha_1,...,\alpha_m,\beta_1,...))$, donde $(x_1,...,x_n,\alpha_1,...,\alpha_m)\in S$
        - Para cada $(x_1,...,x_n,\alpha_1,...,\alpha_m)\in S$ hay un $x\in\omega$ tal que $\mathcal{P}$ se detiene partiendo desde el estado $||x||$ y llega a un estado de la forma $((x_1,...,x_n,y_1,...),(\alpha_1,...,\alpha_m,\beta_1,...))$
    - *Nota: hacer el caso $n=2$ y $m=1$*

### Resolución

## Combo 3

- **Teorema 5 (Godel vence a Neumann)** Si $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to\Sigma^*$ es $\Sigma$-computable, entonces $f$ es $\Sigma$-recursiva
- **Teorema 6 (Caracterización de conjuntos efectivamente computables)** Sea $S\subseteq\omega^n\times\Sigma^{*m}$. Son equivalentes:
    1. $S$ es $\Sigma$-efectivamente computable
    2. $S$ y $(\omega^n\times\Sigma^{*m})-S$ son $\Sigma$-efectivamente enumerables
    - *Nota: hacer solo $(2)\Rightarrow (1)$ (la prueba se encuentra al final de la guía 3)*

### Resolución

## Combo 4

- **Proposición 7 (Caracterización básica de conjuntos enumerables)** Sea $S\subseteq\omega^n\times\Sigma^{*m}$ un conjunto no vacío. Entonces son equivalentes:
    1. $S$ es $\Sigma$-enumerable
    2. Hay un programa $\mathcal{P}\in Pro^\Sigma$ tal que:
        - Para cada $x\in\omega$, tenemos que $\mathcal{P}$ se detiene partiendo desde el estado $||x||$ y llega a un estado de la forma $((x_1,...,x_n,y_1,...),(\alpha_1,...,\alpha_m,\beta_1,...))$, donde $(x_1,...,x_n,\alpha_1,...,\alpha_m)\in S$
        - Para cada $(x_1,...,x_n,\alpha_1,...,\alpha_m)\in S$ hay un $x\in\omega$ tal que $\mathcal{P}$ se detiene partiendo desde el estado $||x||$ y llega a un estado de la forma $((x_1,...,x_n,y_1,...),(\alpha_1,...,\alpha_m,\beta_1,...))$
    - *Nota: hacer el caso $n=2$ y $m=1$*
- **Lema 8 (Lema de la sumatoria)** Sea $\Sigma$ un alfabeto finito. Si $f:\omega\times S_1\times ...\times S_n\times L_1\times ...\times L_m\to\omega$ es $\Sigma$-p.r., con $S_1,...,S_n\subseteq\omega$ y $L_1,...,L_m\subseteq\Sigma^*$ no vacíos, entonces la función $\lambda xy\vec{x}\vec{\alpha}\left [\sum_{t=x}^{t=y} f(t,\vec{x},\vec{\alpha}) \right ]$ es $\Sigma$-p.r.

### Resolución

## Combo 5

- **Lema 9** Sean $S_1,S_2\subseteq\omega^n\times\Sigma^{*m}$ conjuntos $\Sigma$-efectivamente enumerables. Entonces $S_1\cap S_2$ es $\Sigma$-efectivamente enumerable.
    - *Nota: es ejercicio de la guía 3 y en el apunte está probado*
- **Lema 10 (Lema de cuantificación acotada)** Sea $\Sigma$ un alfabeto finito. Sea $P:S\times S_1\times ...\times S_n\times L_1\times ...\times L_m\to\omega$ un predicado $\Sigma$-p.r., con $S,S_1,...,S_n\subseteq\omega$ y $L_1,...,L_m\subseteq\Sigma^*$ no vacíos. Supongamos $\bar{S}\subseteq S$ es $\Sigma$-p.r.. Entonces $\lambda x\vec{x}\vec{\alpha} \left [(\forall t\in\bar{S})_{t\leq x} P(t,\vec{x},\vec{\alpha}) \right ]$ es $\Sigma$-p.r.

### Resolución

## Combo 6

- **Lema 11 (Efectivamente computable implica efectivamente enumerable)** Si $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente computable entonces $S$ es $\Sigma$-efectivamente enumerable.
- **Teorema 12 (Caracterización de conjuntos r.e.)** Dado $S\subseteq\omega^n\times\Sigma^{*m}$, son equivalentes:
    1. $S$ es $\Sigma$-recursivamente enumerable
    2. $S=I_F$, para alguna $F:D_F\subseteq\omega^k\times\Sigma^{*l}\to\omega^n\times\Sigma^{*m}$ tal que cada $F_{(i)}$ es $\Sigma$-recursiva
    3. $S=D_f$, para alguna función $\Sigma$-recursiva $f$
    - *Nota: haga solo la prueba de $(2)\Rightarrow (3)$, caso $k=l=1$ y $n=m=2$*

### Resolución

## Combo 7

- **Lema 13 (Lema de minimización acotada)** Sean $n,m\geq 0$. Sea $P:D_P\subseteq\omega\times\omega^n\times\Sigma^{*m}\to\omega$ un predicado $\Sigma$-p.r.. Entonces:
    1. $M(P)$ es $\Sigma$-recursiva
    2. Si hay una función $\Sigma$-p.r. $f:\omega^n\times\Sigma^{*m}\to\omega$ tal que $$M(P)(\vec{x},\vec{\alpha})=\min_t P(t,\vec{x},\vec{\alpha})\leq f(\vec{x},\vec{\alpha})\forall (\vec{x},\vec{\alpha})\in D_{M(P)}$$ entonces $M(P)$ es $\Sigma$-p.r.
- **Lema 14** Supongamos $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to O$ es $\Sigma$-recursiva y $S\subseteq D_f$ es $\Sigma$-r.e., entonces $f|_S$ es $\Sigma$-recursiva.

### Resolución

## Combo 8

- **Lema 15** Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $AutoHalt^\Sigma$ no es $\Sigma$-recursivo.
- **Teorema 16** Supongamos $\Sigma\supseteq\Sigma_p$. Entonces $AutoHalt^\Sigma$ no es $\Sigma$-efectivamente computable. Es decir, no hay ningún procedimiento efectivo que decida si un programa de $S^\Sigma$ termina partiendo de sí mismo.
- **Lema 17** Supongamos que $\Sigma\supseteq\Sigma_p$. Entonces $$A=\{\mathcal{P}\in Pro^\Sigma:AutoHalt^\Sigma(\mathcal{P})=1\}$$ es $\Sigma$-r.e. y no es $\Sigma$-recursivo. Más aún, el conjunto $$N=\{\mathcal{P}\in Pro^\Sigma:AutoHalt^\Sigma(\mathcal{P})=0\}$$ no es $\Sigma$-r.e.
- **Teorema 18 (Neumann vence a Godel)** Si $h$ es $\Sigma$-recursiva, entonces $h$ es $\Sigma$-computable.
    - *Nota: en la inducción de la prueba, hacer solo el caso $h=M(P)$*

### Resolución

## Combo 9

- **Lema 19 (Lema de división por casos para funciones recursivas)** Supongamos $f_i:D_{f_i}\subseteq\omega^n\times\Sigma^{*m}\to O$, $i=1,...,k$, son funciones $\Sigma$-recursivas tales que $D_{f_i}\cap D_{f_j}=\emptyset$ para $i\neq j$. Entonces la función $f_1\cup ...\cup f_k$ es $\Sigma$-recursiva.
    - *Nota: haga el caso $k=2,n=m=1$ y $O=\omega$*
- **Lema 20** $Halt^{n,m}$ es $(\Sigma\cup\Sigma_p)$-p.r.
- **Proposición 21** $T^{n,m}$ es $(\Sigma\cup\Sigma_p)$-recursiva.

### Resolución
