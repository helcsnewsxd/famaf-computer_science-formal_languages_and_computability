# Guía 1: Conceptos básicos

## Conjuntos

### General

- $\R\rightarrow$ Conjunto de números reales
- $\Z\rightarrow$ Conjunto de números enteros
- $\N\rightarrow$ Conjunto de números naturales
- $\omega=\N\cup\{0\}$, y $\forall x,y\in\omega$:
  - $x\dot{-}y=x-y$ si $x\geq y$ y $0$ cc.
  - $x|y$ si $\exists z\in w$ tal que $y=x\cdot z$
  - Por convención nuestra, $0^0=1$
- $P(A)=\{S:S\subseteq A\}\rightarrow$ partes de A
- $|A|\rightarrow$ cardinalidad de A

### Propiedades

- *Extensionalidad*: $A=B\Leftrightarrow\forall x, (x\in A\Leftrightarrow x\in B)$
  - Es decir, $A=B$ si $A\subseteq B$ y $B\subseteq A$

### Producto cartesiano

- Dados $A_1,..,A_n$ con $n\geq 2$, $A_1\times ..\times A_n$ denota su producto cartesiano, es decir, al conjunto formado por todas las $n$-uplas $(a_1,..,a_n)$ con $a_i\in A_i$ para $i=1,..,n$
- Si $A_1=..=A_n=A$, se denota $A^n$
- Denotamos con $\Diamond$ a la única $0$-upla, por lo que definimos $A^0=\{\Diamond\}$
- $A^N$ denota al conjunto formado por todas las *infinituplas* $(a_1,a_2,..)$ con $a_i\in A$ para todo $i\in\N$

## Alfabetos

- Un *alfabeto* es un conjunto finito de símbolos ($\emptyset$ es un alfabeto)
- Si $\Sigma$ es un alfabeto, $\Sigma^*$ denota al conjunto de todas las palabras finitas formadas por símbolos de $\Sigma$
  - La única palabra de longitud $0$ es $\varepsilon$
  - Nótese que $\emptyset^*=\{\varepsilon\}$ y $\varepsilon\in\Sigma^*\forall\Sigma$
  - $\Sigma^+=\Sigma^*-\{\varepsilon\}$
- $|\alpha|$ denota la longitud de la palabra $\alpha$
  - Si $\alpha\in\Sigma^*$ y $\sigma\in\Sigma$, $|\alpha|_\sigma$ denota el número de veces que $\sigma$ aparece en $\alpha$
- Si $\alpha_1,..,\alpha_n\in\Sigma^*$, $\alpha_1..\alpha_n$ denota la concatenación de las palabras
  - Si $\alpha_1=..=\alpha_n=\alpha$, denotamos $\alpha^n$
  - $\alpha^0=\varepsilon$
- $\alpha$ es *subpalabra (propia)* de $\beta$ si ($\alpha\not\in\{\varepsilon,\beta\}$ y) $\exists\delta,\gamma\in\Sigma^*$ tal que $\beta=\delta\alpha\gamma$
  - $\beta$ es *tramo inicial (propio)* de $\alpha$ si $\exists\gamma\in\Sigma^*$ tal que $\alpha=\beta\gamma$ (y $\beta\not\in\{\varepsilon,\alpha\}$)
  - La definición de *tramo final (propio)* es análoga
- Dados $i\in\omega,\alpha\in\Sigma^*$, definimos $[\alpha_i]=\text{el i-ésimo símbolo de }\alpha$ si $1\leq i\leq|\alpha|$ y $\varepsilon$ cc.
- Dada $\gamma\in\Sigma^*$, definimos $\gamma^{R}=[\gamma_{|\gamma|}]..[\gamma_1]$ si $|\gamma|\geq 1$ y $\varepsilon$ cc. $\rightarrow$ *recíproca de $\gamma$*

### Ocurrencias

- Dadas $\alpha,\beta\in\Sigma^*$ con $|\alpha|,|\beta|\geq 1$ e $i\in\{1,..,|\beta|\}$, decimos que $\alpha$ *ocurre* a partir de $i$ en $\beta$ si $\exists \delta,\gamma\in\Sigma^*$ tales que $\beta=\delta\alpha\gamma$ y $|\delta|=i-1$
- **Reemplazos de ocurrencias**:
  - Cuando todas las ocurrencias de $\alpha$ en $\beta$ son disjuntas entre sí, podemos aplicar los reemplazos
  - Notar que los reemplazos se hacen simultáneamente (de forma *atómica*) y no secuencialmente
  - Se pueden hacer reemplazos simultáneos de distintas palabras en una misma palabra dada (siempre y cuando se cumpla la condición de disyunción)

## Matemática orientada a objetos

- Nuestras *categorías de objetos* son *disjuntas* entre sí y son las siguientes (no consideramos existencia de $1$-uplas):
  - NÚMERO
  - CONJUNTO
  - PALABRA (*incluye a los símbolos*)
  - $0$-UPLA
  - $2$-UPLA
  - $3$-UPLA
  - ...
  - INFINITUPLA
- Definimos $Ti$ como la función que asigna a cada objeto de la categoría $i$ su tipo


## Función

- Definiciones:
  - Una función es un conjunto $f$ de pares ordenados tales que si $(x,y),(x,z)\in f$, entonces $y=z$
    - *Notar que $\emptyset$ es una función*
  - Definimos
    - $D_f=Dom(f)=\text{dominio de }f=\{x:(x,y)\in f\text{ para algún }y\}$
    - $I_f=Im(f)=\text{imagen de }f=\{y:(x,y)\in f\text{ para algún }x\}$
  - Escribiremos $f:A\rightarrow B$ para denotar que $f$ es una función con $D_f=A$ e $I_f\subseteq B$
  - Una función $f$ se puede definir dando su *dominio* y su *regla de asignación*.
  - *Composición*: Dadas funciones $f,g$, definimos $f\circ g$ como
    $$D_{f\circ g}=\{x\in D_g:g(x)\in D_f\}$$
    $$(f\circ g)(x)=f(g(x))$$
    *Notar que entonces* $f\circ g=\{(u,v):\exists z:(u,z)\in g\text{ y }(z,v)\in f\}$
- *"Agrupadas"*: Dadas funciones $f_1,..,f_n$ con $n\in\N$, definimos $[f_1,..,f_n]$ como
    $$D_{[f_1,..,f_n]}=D_{f_1}\cap ..\cap D_{f_n}$$
    $$[f_1,..,f_n](x)=(f_1(x),..,f_n(x))$$
    Notar que $I_{[f_1,..,f_n]}\subseteq I_{f_1}\times ..\times I_{f_n}$ y $[f_1]=f_1$.
- Propiedades
  - *Igualdad de funciones*: $f=g\Leftrightarrow D_f=D_g\text{ y }\forall x\in D_f, f(x)=g(x)$
  - *Sobre composición de funciones*: $f\circ g\neq\emptyset\Leftrightarrow I_g\cap D_f\neq\emptyset$
  - *Inyectividad*: $f$ es inyectiva si $\forall x,y\in D_f, f(x)=f(y)\Rightarrow x=y$
  - *Suryectividad*: Sea $f:A\rightarrow B$, $f$ es suryectiva si $I_f=B$
  - *Biyectividad*: $f:A\rightarrow B$ es biyectiva si es inyectiva y suryectiva
    - Podemos definir la *inversa* de $f$ como $f^{-1}:B\rightarrow A$ tal que $f^{-1}(y)=x\Leftrightarrow f(x)=y$
    
        Notar que $f\circ f^{-1}=Id_B$ y $f^{-1}\circ f=Id_A$
  - *Condición de biyectividad*: Sean $f:A\rightarrow B$ y $g:B\rightarrow A$ tales que $f\circ g=Id_B$ y $g\circ f=Id_A$, entonces $f,g$ son biyectivas, $f=g^{-1}$ y $g=f^{-1}$.
- Ejemplos
  - *Identidad*: $Id_A=\{(x,x):x\in A\}$ para cualquier conjunto $A$

### Funciones $\Sigma$-mixtas

#### Definiciones

- *Notación*: Sea $\Sigma$ un alfabeto finito, y dados $n,m\in\omega$, usamos $\omega^n\times\Sigma^{*m}$ para abreviar a $\omega\times..\times\omega\times\Sigma^*\times..\times\Sigma^*$ ($n$ veces $\omega$ y $m$ veces $\Sigma^*$)
  - Casos a tener en cuenta:
    - Si $n=m=0$, $\omega^n\times\Sigma^{*m}=\{\Diamond\}$
    - Si $n=0$, $\omega^n\times\Sigma^{*m}=\Sigma^{*m}$
    - Si $m=0$, $\omega^n\times\Sigma^{*m}=\omega^n$
  - Un elemento de $\omega^n\times\Sigma^{*m}$ es una $n+m$-upla $(x_1,..,x_n,\alpha_1,..,\alpha_m)$ con $x_i\in\omega$ y $\alpha_i\in\Sigma^*$ para todo $i$
    - Para abreviar, escribiremos $(\vec{x},\vec{\alpha})$ en lugar de $(x_1,..,x_n,\alpha_1,..,\alpha_m)$
- *Definición*: Sea $\Sigma$ un alfabeto finito y sea $f$ una función, diremos que es $\Sigma$-mixta si
  - (M1) $\exists n,m\geq 0:D_f\subseteq\omega^n\times\Sigma^{*m}$
  - (M2) O bien $I_f\subseteq\omega$ o bien $I_f\subseteq\Sigma^*$
- Una función $\Sigma$-mixta es $\Sigma$-total si $\exists n,m\geq 0:D_f=\omega^n\times\Sigma^{*m}$
- *Tipo*: Si $f$ es $\Sigma$-mixta y $n,m\in\omega:D_f\subseteq\omega^n\times\Sigma^{*m}$:
  - Si $I_f\subseteq\omega$, decimos que $f$ es de tipo $(n,m,\#)$
  - Si $I_f\subseteq\Sigma^*$, decimos que $f$ es de tipo $(n,m,*)$
  - *Notar que si $f\neq\emptyset$, entonces hay únicos $n,m\in\omega$ y $s\in\{\#,*\}$ tales que $f$ es de tipo $(n,m,s)$.*

#### Propiedades

- Sean $\Sigma\subseteq\Gamma$ alfabetos finitos y $f$ una función $\Sigma$-mixta, entonces $f$ es $\Gamma$-mixta

#### Ejemplos

- *Suc*: Sucesor de un número:
    $$Suc:\omega\rightarrow\omega$$
    $$n\rightarrow n+1$$
- *Pred*: Predecesor de un número:
    $$Pred:\N\rightarrow\omega$$
    $$n\rightarrow n-1$$
- *Derecha*: Sea $\Sigma$ un alfabeto no vacío, entonces $\forall b\in\Sigma$ definimos
    $$d_b:\Sigma^*\rightarrow\Sigma^*$$
    $$\alpha\rightarrow\alpha b$$
- *Proyecciones*: Sea $\Sigma$ un alfabeto, para $n,m\in\omega$ e $i:1\leq i\leq n$, definimos
    $$p_i^{n,m}: \omega^n\times\Sigma^{*m}\rightarrow\omega$$
    $$(\vec{x},\vec{\alpha})\rightarrow x_i$$
    Y para $i:n+1\leq i\leq n+m$, definimos
    $$p_i^{n,m}: \omega^n\times\Sigma^{*m}\rightarrow\Sigma^*$$
    $$(\vec{x},\vec{\alpha})\rightarrow\alpha_{i-n}$$
- *Constantes*: Sea $\Sigma$ un alfabeto, para $n,m,k\in\omega$ y $\alpha\in\Sigma^*$ definimos
    $$C_k^{n,m}:\omega^n\times\Sigma^{*m}\rightarrow\omega$$
    $$(\vec{x},\vec{\alpha})\rightarrow k$$
    y
    $$C_\alpha^{n,m}:\omega^n\times\Sigma^{*m}\rightarrow\Sigma^*$$
    $$(\vec{x},\vec{\alpha})\rightarrow\alpha$$
    (Notar que $C_k^{0,0}: \{\Diamond\}\rightarrow\{k\}$ y $C_\alpha^{0,0}: \{\Diamond\}\rightarrow\{\alpha\}$)
- *Predicado*: Un predicado $\Sigma$-mixto es una función $f$ tal que es $\Sigma$-mixta e $I_f\subseteq\{0,1\}$
  
  Dados predicados $P:S\subseteq\omega^n\times\Sigma^{*m}\rightarrow\{0,1\}$ y $Q:S\subseteq\omega^n\times\Sigma^{*m}\rightarrow\{0,1\}$, con el mismo dominio, definimos nuevos predicados:
  - *Negación*:
    $$\neg P:S\rightarrow\{0,1\}$$
    $$(\vec{x},\vec{\alpha})\rightarrow\begin{cases} 1 & \text{si }P(\vec{x},\vec{\alpha})=0 \\ 0 & \text{si }P(\vec{x},\vec{\alpha})=1 \end{cases}$$
  - *Conjunción*:
    $$P\wedge Q:S\rightarrow\{0,1\}$$
    $$(\vec{x},\vec{\alpha})\rightarrow\begin{cases} 1 & \text{si }P(\vec{x},\vec{\alpha})=1\text{ y }Q(\vec{x},\vec{\alpha})=1 \\ 0 & \text{cc.} \end{cases}$$
  - *Disyunción*:
    $$P\vee Q:S\rightarrow\{0,1\}$$
    $$(\vec{x},\vec{\alpha})\rightarrow\begin{cases} 1 & \text{si }P(\vec{x},\vec{\alpha})=1\text{ o }Q(\vec{x},\vec{\alpha})=1 \\ 0 & \text{cc.} \end{cases}$$

### Conjuntos $\Sigma$-mixtos

- Un conjunto $S$ es $\Sigma$-mixto si $\exists n,m\in\omega:S\subseteq\omega^n\times\Sigma^{*m}$
  - *Notar que $\emptyset$ y $\{\Diamond\}$ son conjuntos $\Sigma$-mixtos, cualesquiera sea el alfabeto $\Sigma$*
- $S$ es $\Sigma$-mixto $\Leftrightarrow S=D_f$ para alguna función $\Sigma$-mixta $f$
- Dado un conjunto $\Sigma$-mixto $S$ y $n,m\in\omega:S\subseteq\omega^n\times\Sigma^{*m}$, entonces $S$ es de tipo $(n,m)$

    *Notar que si $S\neq\emptyset$, entonces hay únicos $n,m\in\omega$ tales que $S$ es de tipo $(n,m)$.*

## Notación Lambda

- Una expresión es *lambdificable* con respecto a $\Sigma$ si cumple las siguientes características:
  - Involucra variables numéricas (que se valuaran en números de $\omega$), y variables alfabéticas (que se valuaran en palabras del alfabeto previamente fijado)
    - En cuanto a notación, las numéricas son con letras latinas minúsculas ($x,y,z$) y las alfabéticas con letras griegas minúsculas ($\alpha,\beta,\gamma$)
  - Para ciertas valuaciones de sus variables la expresión puede *no* estar definida (por ejemplo, $Pred(|\alpha|)$ para $\alpha=\varepsilon$)
  - Sea $E$ la expresión, los valores que asuma cuando hayan sido asignados los valores de $\omega$ a sus variables numéricas y valores de $\Sigma^*$ a sus variables alfabéticas, deberán ser *siempre* elementos de $O\in\{\omega,\Sigma^*\}$ (es decir, no puede tomar valores mixtos)
  - La expresión puede involucrar lenguaje coloquial castellano (i.e., no únicamente operaciones matemáticas). Por ejemplo, "el menor número primo que es mayor que $x$"
  - A las *expresiones booleanas* (como $x=0$), se les considerará que asumen valores de $\{0,1\}\subseteq\omega$
- *Definición*: sea $\Sigma$ un alfabeto finito fijo, $E$ una expresión lambdificable respecto a $\Sigma$ y $x_1,..,x_n,\alpha_1,..,\alpha_m$ variables distintas tales que las numéricas que ocurren en $E$ están en $\{x_1,..,x_n\}$ y las alfabéticas en $\{\alpha_1,..,\alpha_m\}$, entonces $\lambda_{x_1..x_n\alpha_1..\alpha_m}[E]$ denota la función definida por:
  - $D_{\lambda_{x_1..x_n\alpha_1..\alpha_m}[E]}=\{(k_1,..,k_n,\beta_1,..,\beta_m)\in\omega^n\times\Sigma^{*m}:E$ está definida cuando asignamos a cada $x_i$ el valor $k_i$, y a cada $\alpha_i$, el valor $\beta_i \}$
  - $\lambda_{x_1..x_n\alpha_1..\alpha_m}[E](k_1,..,k_n,\beta_1,..,\beta_m)=$ valor que asume o representa $E$ cuando asignamos a cada $x_i$ el valor $k_i$, y a cada $\alpha_i$, el valor $\beta_i$

### Propiedades

- $\lambda_{x_1..x_n\alpha_1..\alpha_m}[E]$ es $\Sigma$-mixta de tipo $(n,m,s)$, donde $s\in\{\#,*\}$.
- Para $S\subseteq\omega^n\times\Sigma^{*m}$, $\chi_S^{\omega^n\times\Sigma^{*m}}=\lambda_{x_1..x_n\alpha_1..\alpha_m}[(\vec{x},\vec{\alpha})\in S]$.