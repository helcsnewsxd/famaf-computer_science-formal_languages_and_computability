# Guía 3: Procedimientos efectivos

## Procedimientos efectivos

- Un procedimiento $P$ es *procedimiento efectivo* si posee las siguientes características:
    - El ejecutante de $P$ es una persona que trabajará con papel y lápiz (ambos recursos disponibles en forma ilimitada)
    - Cada paso o tarea que $P$ encomiende a realizar debe ser simple y fácil de hacer en forma *efectiva* por cualquier persona
    - El procedimiento $P$ comienza a funcionar siempre a partir de cierto dato de entrada y una vez que haya comenzado:
        - O bien se detiene y da cierto dato de salida (estos forman su *conjunto de salida*)
        - O bien nunca se detiene
    - $\exists n,m\in\omega$ y un alfabeto $\Sigma$ tales que el conjunto de datos de entrada de $P$ es $\omega^n\times\Sigma^{*m}$.

## Función $\Sigma$-efectivamente computable

- Una función $\Sigma$-mixta $f:D_f\subseteq\omega^n\times\Sigma^{*m}\to O$ (para $O\in\{\omega,\Sigma^*\}$) es $\Sigma$-efectivamente computable si hay un procedimiento $P$ tal que:
    - El conjunto de datos de entrada de $P$ es $\omega^n\times\Sigma^{*m}$
    - El conjunto de datos de salida está contenido en $O$
    - Si $(\vec{x}, \vec{a})\in D_f$, entonces $P$ se detiene partiendo de $(\vec{x}, \vec{a})$ y da como salida $f(\vec{x}, \vec{a})$
    - Si $(\vec{x}, \vec{a})\notin D_f$, entonces $P$ no se detiene partiendo de $(\vec{x}, \vec{a})$
    *En estos casos diremos que $P$ computa a $f$*
- *Propiedades:*
    - $\emptyset$ es $\Sigma$-efectivamente computable $\forall\Sigma$
    - Sean $f,f_1,..,f_n$ con $n\geq 1$ funciones $\Sigma$-efectivamente computables tales que $\exists k:D_f\subseteq\omega^k\times\Sigma^{*(n-k)}\wedge I_{f_i}\subseteq\omega\forall i\in\{1,..,k\}\wedge I_{f_i}\subseteq\Sigma^*\forall i\in\{k+1,..,n\}$, entonces $f\circ [f_1,..,f_n]$ es $\Sigma$-efectivamente computable.

## Conjunto $\Sigma$-efectivamente computable

- Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente computable cuando la función $\chi_S^{\omega^n\times\Sigma^{*m}}$ es $\Sigma$-efectivamente computable.
    - Es decir, $S$ es $\Sigma$-efectivamente computable si existe un procedimiento $P$ tal que:
        - El conjunto de datos de entrada de $P$ es $\omega^n\times\Sigma^{*m}$, siempre termina y da como dato de salida un elemento de $\{0,1\}$
        - Dado $(\vec{x}, \vec{a})\in\omega^n\times\Sigma^{*m}$, $P$ se detiene partiendo de $(\vec{x}, \vec{a})$ y da como salida $1$ si $(\vec{x}, \vec{a})\in S$ y $0$ en caso contrario.
- *Propiedades*:
    - $\emptyset$ es $\Sigma$-efectivamente computable $\forall\Sigma$
    - Sean $S_1,S_2\subseteq\omega^n\times\Sigma^{*m}$ conjuntos $\Sigma$-efectivamente computables, entonces $S_1\cup S_2$, $S_1\cap S_2$ y $(\omega^n\times\Sigma^{*m})-S_1$ son $\Sigma$-efectivamente computables.

## Conjunto $\Sigma$-efectivamente enumerable

- *Consideraciones*: Sean $k,l,m,n\in\omega$ con $n+m\geq 1$ y $F:D_F\subseteq\omega^k\times\Sigma^{*l}\to\omega^n\times\Sigma^{*m}$, entonces denotaremos con $F_{(i)}$ a la función $p_i^{n,m}\circ F$.
    - Notar que:
        - $Im_{F_{(i)}}\subseteq\omega\forall i\in\{1,..,n\}$ e $Im_{F_{(i)}}\subseteq\Sigma^*\forall i\in\{n+1,..,n+m\}$
        - $F_{(i)}$ es $\Sigma$-mixta $\forall i\in\{1,..,n+m\}$
        - $F=[F_{(1)},..,F_{(n+m)}]$
- *Definiciones y resultados*:
    - Un conjunto $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente enumerable si es vacío o $\exists F:\omega\to\omega^n\times\Sigma^{*m}$ tal que $Im_F=S$ y $F_{(i)}$ es $\Sigma$-efectivamente computable $\forall i\in\{1,..,n+m\}$
    - $S\neq\emptyset\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente enumerable $\Leftrightarrow$ hay un procedimiento efectivo $P$ tal que:
        - El conjunto de datos de entrada de $P$ es $\omega$
        - $P$ se detiene para cada $x\in\omega$
        - El conjunto de datos de salida de $P$ es igual a $S$
        *En este caso, P enumera a S*
    - $S$ es $\Sigma$-efectivamente enumerable $\Leftrightarrow$ es vacío o hay un procedimiento efectivo que lo enumera.
- *Notar* que $\emptyset$ y $\{\Diamond\}$ son $\Sigma$-efectivamente enumerables $\forall\Sigma$.
- *Propiedades*:
    - Sean $S_1,S_2\subseteq\omega^n\times\Sigma^{*m}$ conjuntos $\Sigma$-efectivamente enumerables, entonces $S_1\cup S_2$, $S_1\cap S_2$ son $\Sigma$-efectivamente enumerables.
    - Si $S\subseteq\omega^n\times\Sigma^{*m}$ es $\Sigma$-efectivamente computable, entonces $S$ es $\Sigma$-efectivamente enumerable.