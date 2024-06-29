# Combos de teoremas

## Combo 1

### Proposición 1 (Caracterización de conjuntos p.r.)

Un conjunto $S$ es $\Sigma$-p.r. sii $S$ es el dominio de alguna función $\Sigma$-p.r.

- *Nota: en la inducción de la prueba, hacer solo el caso de la composición*

#### Demostración

Supongamos que $S\subseteq\omega^n\times\Sigma^{*m}$ con $n,m\in\omega$ y veamos los dos casos:

- **(Caso $\Rightarrow$)**: Como $S$ es $\Sigma$-p.r., entonces $\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-p.r. por definición. Luego, por definición de $PR^\Sigma$, $Pred\circ\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-p.r., por lo que se demuestra dado que $S=D_{Pred\circ\chi_S^{\omega^n\times\Sigma^{*m}}}$ $\blacksquare$
- **(Caso $\Leftarrow$)**: Se probará por inducción en $k$ que $D_F$ es $\Sigma$-p.r. $\forall F\in PR_k^\Sigma$.
    - *Caso base ($k=0$)*: Trivial.
    - *HI ($k$)*: Supongamos que $D_F$ es $\Sigma$-p.r. $\forall F\in PR_k^\Sigma$.
    - *Paso inductivo $(k+1)$*: Supongamos $F\in PR_{k+1}^\Sigma$ y veremos que $F$ es $\Sigma$-p.r. Hay varios casos según cómo se define $PR_{k+1}$ (composición, recursión con variable alfabética, recursión con variable numérica o función de $PR_k^\Sigma$), pero solo vamos a considerar el de *composición*.
      
      Entonces, veamos que $F=g\circ[g_1,...,g_r]$ con $g,g_1,...,g_r\in PR_k^\Sigma$.

        - Si $F=\emptyset$, es trivial ver que $D_F$ es $\Sigma$-p.r..
        - Si $F\neq\emptyset$, entonces tenemos que (sean $O\in\{\omega,\Sigma^*\}\text{ y }p,q\in\omega$): $$\begin{aligned} r&=n+m\\ g&:D_g\subseteq\omega^n\times\Sigma^{*m}\to O\\ g_i&:D_{g_i}\subseteq\omega^p\times\Sigma^{*q}\to\omega\forall i=1,...,n\\ g_i&:D_{g_i}\subseteq\omega^p\times\Sigma^{*q}\to\Sigma^*\forall i=n+1,...,r \end{aligned}$$ Ahora, por lemas sabemos que:
            - $\exists\bar{g_1},...,\bar{g_r}$ $\Sigma$-p.r. y $\Sigma$-totales tales que $g_i=\bar{g_i}|_{D_{g_i}}\forall i=1,...,r$
            - $S=\cap_{i=1}^r D_{g_i}$ es $\Sigma$-p.r.
          
          Entonces, como $\chi_{D_F}^{\omega^p\times\Sigma^{*q}}=\chi_S^{\omega^p\times\Sigma^{*q}}\wedge\left(\chi_{D_g}^{\omega^n\times\Sigma^{*m}}\circ\left[\bar{g_1},...,\bar{g_r}\right]\right)$, notar que:

            - $S,D_g$ son $\Sigma$-p.r. $\Rightarrow$ Por def., $\chi_S^{\omega^p\times\Sigma^{*q}}$ y $\chi_{D_g}^{\omega^n\times\Sigma^{*m}}$ son $\Sigma$-p.r.
            - Sean $P,Q$ dos predicados $\Sigma$-p.r. con igual dominio, entonces $P\wedge Q$ es $\Sigma$-p.r. (por *lema*)
          
          por lo que $\chi_{D_F}^{\omega^p\times\Sigma^{*q}}$ es $\Sigma$-p.r.. Luego, por def., llegamos a que $D_F$ es $\Sigma$-p.r.

  Finalmente, se demuestra por inducción. $\blacksquare$

### Teorema 2 (Neumann vence a Godel)

Si $h$ es $\Sigma$-recursiva, entonces $h$ es $\Sigma$-computable

- *Nota: en la inducción de la prueba, hacer solo el caso $h=R(f,\mathcal{G})$*

#### Demostración

Se probará por inducción en $k$ que si $h\in R_k^\Sigma$, entonces $h$ es $\Sigma$-computable.

- *Caso base ($k=0$)*: Trivial, dado que son funciones con las que siempre trabajamos ($Pred,Suc,C^{0,0}_0,C^{0,0}_\varepsilon,p^{n,m}_j,d_a$ con $n,m,j\in\omega,a\in\Sigma$ y $1\leq j\leq n+m$)
- *HI ($k$)*: Supongamos que si $h\in R_k^\Sigma$, entonces $h$ es $\Sigma$-computable.
- *Paso inductivo ($k+1$)*: Supongamos $h\in R_{k+1}^\Sigma$, entonces tenemos varios casos (composición, minimización, recursión con variable alfabética o numérica, o función de $R_k^\Sigma$). En esta demostración nos vamos a concentrar en la *recursión con variable alfabética*.
  
  Como las demostraciones de los dos casos de valor numérico y alfabético son similares, vamos a considerar este último. Entonces, consideraremos $h=R(f,\mathcal{G})$ con $$\begin{aligned} f&:S_1\times ...\times S_n\times L_1\times ...\times L_m\to\Sigma^*\\ \mathcal{G}_a&:S_1\times ...\times S_n\times L_1\times ...\times L_m\times\Sigma^*\times\Sigma^*\to\Sigma^*\forall a\in\Sigma \end{aligned}$$ con $S_1,...,S_n\subseteq\omega$ y $L_1,...,L_m\subseteq\Sigma^*$, y tales que $f,\mathcal{G}_a\in R_k^\Sigma\forall a\in\Sigma$.
  Sea $\Sigma={a_1,...,a_r}$ nuestro alfabeto, como por *HI* sabemos que $f,\mathcal{G}_a\forall a\in\Sigma$ son $\Sigma$-computables, entonces podemos considerar el siguiente programa $\mathcal{P}\in Pro^\Sigma$ (dado que las *macros* existen en $S^\Sigma$): $$\begin{aligned} & [P\overline{m+3}\leftarrow f(N1,...,N\bar{n},P1,...,P\bar{m})]\\ L\overline{r+1}\hspace{1cm} & \text{IF }P\overline{m+1}\text{ BEGINS }a_1\text{ GOTO }L1\\ & ...\\ & \text{IF }P\overline{m+1}\text{ BEGINS }a_r\text{ GOTO }L\bar{r}\\ & \text{GOTO }L\overline{r+2}\\ L1\hspace{1cm} & P\overline{m+1}\leftarrow\ ^\curvearrowright P\overline{m+1}\\ & [P\overline{m+3}\leftarrow\mathcal{G}_{a_1}(N1,...,N\bar{n},P1,...,P\bar{m},P\overline{m+2},P\overline{m+3})]\\ & P\overline{m+2}\leftarrow P\overline{m+2}.a_1\\ & \text{GOTO }L\overline{r+1}\\ & ...\\ L\bar{r}\hspace{1cm} & P\overline{m+1}\leftarrow\ ^\curvearrowright P\overline{m+1}\\ & [P\overline{m+3}\leftarrow\mathcal{G}_{a_r}(N1,...,N\bar{n},P1,...,P\bar{m},P\overline{m+2},P\overline{m+3})]\\ & P\overline{m+2}\leftarrow P\overline{m+2}.a_r\\ & \text{GOTO }L\overline{r+1}\\ L\overline{r+2}\hspace{1cm} & P1\leftarrow P\overline{m+3}\\ \end{aligned}$$ Luego, para ver que $h$ es $\Sigma$-computable, debemos demostrar que $\mathcal{P}$ computa $h$. Esto es fácil de chequear notando que, sea $R(f,\mathcal{G})(\vec{x},\vec{\alpha},\beta)$, entonces:

    - $\mathcal{P}$ tiene un estado inicial de la forma $||(x_1,...,x_n,\alpha_1,...,\alpha_m)||$
    - $P\overline{m+1}$ es la variable que contiene a $\beta$
    - $P\overline{m+2}$ es la variable que contiene nuestro "paso actual de la recursión" (el $\beta$ construido de izquierda a derecha)
    - $P\overline{m+3}$ es la variable que contiene el resultado de la recursión
  
  Teniendo esto en cuenta, entonces:
  
    - Si $\beta=\varepsilon$, entonces $\mathcal{P}$ se detiene con $f(\vec{x},\vec{\alpha})$ en $P1$
    - Si $\beta=\alpha a_i$ con $a_i\in\Sigma$, entonces nos vamos a la instrucción con label $L\bar{i}$ y cada variable va a tener los siguientes valores:
        - $P\overline{m+1}$ tiene $\alpha$
        - $P\overline{m+2}$ tiene $\gamma$ tal que $\beta=\gamma\alpha$
        - $P\overline{m+3}$ tiene $\mathcal{G}_{a_i}(\vec{x},\vec{\alpha},\gamma,R(f,\mathcal{G})(\vec{x},\vec{\alpha},\gamma))$
      
      y se direcciona a $L\overline{r+1}$ para seguir con el próximo símbolo (o terminar si es $\varepsilon$)
  
  Por lo que podemos ver que $\mathcal{P}$ computa $h$ y, por lo tanto, $h$ es $\Sigma$-computable.

Finalmente, se demuestra por inducción. $\blacksquare$

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
