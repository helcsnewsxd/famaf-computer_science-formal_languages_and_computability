# Guía 2: Codificación de infinituplas de números y biyección entre $\omega$ y $\Sigma^*$

## Codificación de infinituplas de números

### Definiciones

- *De infinituplas*:
  - $\omega^N=\{(s_1,s_2,...):s_i\in\omega\forall i\in N\}$
  - $\omega^{[N]}=\{(s_1,s_2,...)\in\omega^N:(\exists n\in N:s_i=0\forall i\geq n)\}$
    - Es decir, tiene una cantidad finita de coordenadas no nulas
- *De números*:
  - $pr$: Definimos
    $$pr:N\rightarrow\omega$$
    $$n\rightarrow n\text{-ésimo número primo}$$
  - Si $p,p_1,..,p_n$ son números primos (con $n\geq 1$) y $p|p_1..p_n\Rightarrow\exists i:p=p_i$
- *Codificación* (Teorema Fundamental de la Aritmética reversionado): $\forall x\in N, \exists! (s_1,s_2,...)\in\omega^{[N]}:x=\prod_{i=1}^{\infty}pr(i)^{s_i}$
- *Notación*:
  - Dada una infinitupla $(s_1,s_2,...)\in\omega^{[N]}$, usaremos $\langle s_1,s_2,...\rangle$ para denotar al número $x=\prod_{i=1}^{\infty}pr(i)^{s_i}$
  - Dado $x\in N$, usaremos $(x)$ para denotar a la única infinitupla $(s_1,s_2,...)\in\omega^{[N]}$ tal que $x=\langle s_1,s_2,...\rangle=\prod_{i=1}^{\infty}pr(i)^{s_i}$
  - Para cada $i\in N$, usaremos $(x)_i$ para denotar a $s_i$ de dicha infinitupla

### Consecuencias de la codificación

- *Por la notación*:
  - $(x)=((x)_1,(x)_2,...)$
  - $(x)_i$ es el exponente de $pr(i)$ en la única factorización prima de $x$
  - $\langle (x)_1,(x)_2,...\rangle=x\forall x\in N$
  - $\forall (s_1,s_2,...)\in\omega^{[N]}, (\langle s_1,s_2,...\rangle)=(s_1,s_2,...)$
- Si $x,y\in N$, entonces:
  - $(x)_i\leq x\forall i\in N$
  - $(x.y)_i=(x)_i+(y)_i\forall i\in N$
  - $x|y\Leftrightarrow\forall i\in N,(x)_i\leq(y)_i$
- Las funciones:
  $$N\rightarrow\omega^{[N]}$$
  $$x\rightarrow(x)$$
  y
  $$\omega^{[N]}\rightarrow N$$
  $$(s_1,s_2,...)\rightarrow\langle s_1,s_2,...\rangle$$
  son biyectivas, una inversa de la otra
- Dados $x,i\in N$, $(x)_i=\max\{t\in N:pr(i)^t|x\}$
- *Mayor factor primo*: Sea
  $$Lt:N\rightarrow\omega$$
  $$x\rightarrow\begin{cases}\max\{i\in N:(x)_i\neq 0\}&\text{si }x\neq 1\\0&\text{si }x=1\end{cases}$$
  entonces se cumple que:
  - $Lt(x)=0\Leftrightarrow x=1$
  - $x=\prod_{i=1}^{Lt(x)}pr(i)^{(x)_i}$

## Órdenes totales

### Repaso de conceptos

- *Relación binaria*: sea $A$ un conjunto, una relación binaria en $A$ es un subconjunto de $A^2$
  - *Notación*: si $R$ es una relación binaria en $A$, escribimos $aRb$ para denotar que $(a,b)\in R$
  - Si $R$ es una relación binaria sobre $A$ y $A\subseteq B$, entonces $R$ es una relación binaria sobre $B$
- *Orden parcial*: una relación binaria $R$ sobre $A$ es un *orden parcial sobre $A$* ($\leq$) si cumple
  - *Reflexividad*: $\forall x\in A, xRx$
  - *Transitividad*: $\forall x,y,z\in A, xRy\land yRz\Rightarrow xRz$
  - *Antisimetría*: $\forall x,y\in A, xRy\land yRx\Rightarrow x=y$
- *Orden total*: un orden total sobre $A$ es un orden parcial $\leq$ sobre $A$ que cumple que $\forall a,b\in A, a\leq b\lor b\leq a$
- *I-ésimo elemento de A*: si $A$ es un conjunto finito y no vacío, y $\leq$ es un orden total sobre $A$, sea:
    $$f:\{1,2,...,|A|\}\rightarrow A$$
    $$f(1)=\text{menor elemento de }A$$
    $$f(i+1)=\text{menor elemento de }A-\{f(1),f(2),...,f(i)\}$$

### Órdenes naturales sobre $\Sigma^*$

#### $Num$

- Llamaremos *numerales* a los siguientes símbolos: $0,1,2,3,4,5,6,7,8,9$
- Consideraremos $Num$ como el alfabeto de numerales (notar que $Num\cap\omega=\emptyset$)
- Las palabras de $Num^*$ denotarán (en notación decimal) a los números de $\omega$ (notar que $Num^*\cap\omega=\emptyset$)
- La representación decimal de números de $\omega$ mediante palabras de $Num^*$ *no nos da una biyección* entre $Num^*$ y $\omega$ ya que hay palabras que representan al mismo número (por ejemplo, $016$ y $16$)

#### $\widetilde{Num}$

- Definimos $\widetilde{Num}=\{1,2,3,4,5,6,7,8,9,d\}$ donde $d$ denota al número $10$
- Los números de $\omega$ se representarán mediante la siguiente lista infinita de palabras de $\widetilde{Num}^*$: $1,2,3,..,9,d,11,12,..,19,1d,21,..,29,2d,..,9d,d1,d2,..,dd,111,..$
  - *Siguiente*: la siguiente a una palabra $\alpha$ de la lista anterior se obtiene aplicando lo siguiente:
    1. Si $\alpha=d^n$ con $n\geq 0$, entonces el siguiente de $\alpha$ es $1^{n+1}$
    2. Si $\alpha$ no es de la forma $d^n$ con $n\geq 0$, entonces el siguiente de $\alpha$ se obtiene así:
         - Buscar de derecha a izquierda el primer símbolo no igual a $d$
         - Reemplazar dicho símbolo por su siguiente en la lista $1,2,3,4,5,6,7,8,9,d$
         - Reemplazar por el símbolo $1$ a todos los símbolos iguales a $d$ que ocurrían a la derecha del símbolo reemplazado
  - *Propiedades*:
    - $(S)$ Toda palabra de $\widetilde{Num}^*$ aparece en la lista descripta
    - $(I)$ Ninguna palabra de $\widetilde{Num}^*$ aparece más de una vez en la lista descripta
    - *Para la demo*:
      - Consideremos la lista representada por $B_0;B_1;B_2;...$ donde $B_i$ es la parte de la lista en la cual las palabras tienen longitud exactamente $i$
      - Si $B_n=\alpha_1,..,\alpha_k$, entonces $a_1=1^n$ y $a_k=d^n$
      - Si $d^n$ ocurre en $B_n$, lo hace en la última posición
      - Sea $\sigma\in\widetilde{Num}$ y $\alpha\neq d^n\in\widetilde{Num}^*$, entonces el siguiente de $\sigma\alpha$ es $\sigma\beta$ donde $\beta$ es el siguiente de $\alpha$
      - Si $B_n=\alpha_1,..,\alpha_k$, entonces $B_{n+1}=1\alpha_1,..,1\alpha_k,2\alpha_1,..,2\alpha_k,..,d\alpha_1,..,d\alpha_k$
      - $B_n$ es una lista sin repeticiones de todas las palabras de longitud $n$ de $\widetilde{Num}^*$
        - De esta, claramente se deduce $(S)$ y $(I)$
- Dada la función
  $$*:\omega\rightarrow\widetilde{Num}^*$$
  $$n\rightarrow(n+1)\text{-ésima palabra de la lista descripta}$$
  por $(S)$ sabemos que es sobreyectiva, y por $(I)$ que es inyectiva. Luego, esta es una **biyección** con inversa:
  $$\#:\widetilde{Num}^*\rightarrow\omega$$
  $$\alpha\rightarrow\text{posición de }\alpha\text{ en la lista descripta}-1$$
  - Si $\alpha=s_1s_2..s_k$ con $k\geq 1$ y $s_i\in\widetilde{Num}\forall i\in\{1,2,..,k\}$, entonces $\#(\alpha)=\sum_{i=1}^k \#(s_i)\times 10^{k-i}$

#### Caso general

- Sea $\Sigma$ un alfabeto no vacío y supongamos $\leq$ es un orden total sobre $\Sigma$, y sea $\Sigma=\{a_1,..,a_n\}$ con $a_1<a_2<..<a_n$, podemos considerar la siguiente lista de palabras de $\Sigma^*$:
  $$\varepsilon,a_1,..,a_n$$
  $$a_1a_1,..,a_1a_n,a_2a_1,..,a_2a_n,..,a_na_1,..,a_na_n$$
  $$...$$
  la cual enumera sin repeticiones todas las palabras de $\Sigma^*$ (i.e., produce una **biyección** entre $\omega$ y $\Sigma^*$)
  - La lista se define formalmente con la función *siguiente* $s^{\leq}:\Sigma^*\rightarrow\Sigma^*$
    $$s^{\leq}((a_n)^m)=(a_1)^{m+1}\forall m\geq 0$$
    $$s^{\leq}(\alpha a_i(a_n)^m)=\alpha a_{i+1}(a_1)^m\forall\alpha\in\Sigma^*,i\in\{1,2,..,n-1\},m\geq 0$$
    - *Propiedades*:
      - $\varepsilon\neq s^{\leq}(\alpha)\forall\alpha\in\Sigma^*$
      - $\alpha\neq\varepsilon\Rightarrow\exists\beta\in\Sigma^*:s^{\leq}(\beta)=\alpha$
    - Luego, la lista puede ser descripta como:
      $$\varepsilon,s^{\leq}(\varepsilon),s^{\leq}(s^{\leq}(\varepsilon)),s^{\leq}(s^{\leq}(s^{\leq}(\varepsilon))),..$$
      y se puede demostrar que:
        - $(S)$ Toda palabra de $\Sigma^*$ aparece en la lista descripta
        - $(I)$ Ninguna palabra de $\Sigma^*$ aparece más de una vez en la lista descripta
- Para esta **biyección**, definimos $*^{\leq}:\omega\rightarrow\Sigma^*$ como la función que asigna a cada $n\in\omega$ la $n+1$-ésima palabra de la lista descripta, y $\#^{\leq}:\Sigma^*\rightarrow\omega$ como la función que asigna a cada $\alpha\in\Sigma^*$ la posición de $\alpha$ en la lista descripta menos uno (las dos son *inversas* una de la otra). Es decir:
  $$*^{\leq}:\omega\rightarrow\Sigma^*$$
  $$*^{\leq}(0)=\varepsilon$$
  $$*^{\leq}(n+1)=s^{\leq}(*^{\leq}(n))$$
  $$---$$
  $$\#^{\leq}:\Sigma^*\rightarrow\omega$$
  $$\epsilon\rightarrow 0$$
  $$a_{i_k}...a_{i_0}\rightarrow \sum_{j=0}^k i_jn^j$$
- Sea $n\geq 1$, entonces $\forall x\geq 1, x=\sum_{j=0}^k i_jn^j$ con $k\geq 0,1\leq i_j\leq n\forall j\in\{0,1,..,k\}$

##### Extensión del orden total de $\Sigma$ a $\Sigma^*$

- $\alpha\leq\beta\Leftrightarrow\#^{\leq}(\alpha)\leq\#^{\leq}(\beta)$ y $\leq$ es un orden total sobre $\Sigma^*$
- $S\neq\emptyset\subseteq\Sigma^*\Rightarrow\exists\alpha\in S:\alpha\leq\beta\forall\beta\in S$