# Lenguajes Formales y Computabilidad

## Edición 2024

Repositorio que contiene todo el material correspondiente a la materia de Lenguajes Formales y Computabilidad de 4to año de la Licenciatura en Ciencias de la Computación de FAMAF.


## Equipo Docente

- Teóricos: Diego Vaggione
- Prácticos:  Martín Vilela y Mariana Badano

## Material de Estudio

### Guías y Resúmenes

| Unidad | Tema | Material | Resumen |
|--------|------|----------| ------- |
| 1 | Notación + Conceptos básicos + Funciones/Conjuntos $\Sigma$-mixtos + Notación $\lambda$ | [Guía 1](./clases/material/guia_1.pdf) | [MD](./clases/resúmenes/guia_1.md) y [PDF](./clases/resúmenes/guia_1.pdf) |
| 2 | Infinituplas + Órdenes totales + Orden natural sobre $\Sigma^*$ | [Guía 2](./clases/material/guia_2.pdf) | [MD](./clases/resúmenes/guia_2.md) y [PDF](./clases/resúmenes/guia_2.pdf) |
| 3 | Procedimientos efectivos + Funciones/Conjuntos $\Sigma$-efectivamente computables + Conjuntos $\Sigma$-efectivamente enumerables | [Guía 3](./clases/material/guia_3.pdf) | [MD](./clases/resúmenes/guia_3.md) y [PDF](./clases/resúmenes/guia_3.pdf) |
| 4 | Paradigma de Turing (Máquina de Turing + Funciones $\Sigma$-Turing computables)  | [Guía 4](./clases/material/guia_4.pdf) | [MD](./clases/resúmenes/guia_4.md) y [PDF](./clases/resúmenes/guia_4.pdf) |
| 5 | Paradigma de Godel (Funciones/Conjuntos $\Sigma$-recursiva y recursivas primitivas) | [Guía 5](./clases/material/guia_5.pdf) | [MD](./clases/resúmenes/guia_5.md) y [PDF](./clases/resúmenes/guia_5.pdf) |
| 6 | Sumatoria, productoria, concatenatoria, cuantificación acotada de predicados y minimización de funciones $\Sigma$-recursivas + Conjuntos $\Sigma$-recursivamente enumerables + Independencia del alfabeto | [Guía 6](./clases/material/guia_6.pdf) | [MD](./clases/resúmenes/guia_6.md) y [PDF](./clases/resúmenes/guia_6.pdf) |
| 7 | Paradigma imperativo de Neumann: El lenguaje $S^{\Sigma}$ (Funciones/Conjuntos $\Sigma$-computables + Conjuntos $\Sigma$-enumerables + Macros) | [Guía 7](./clases/material/guia_7.pdf) | [MD](./clases/resúmenes/guia_7.md) y [PDF](./clases/resúmenes/guia_7.pdf) |
| 8 | Comparación entre paradigmas + Tesis de Church | [Guía 8](./clases/material/guia_8.pdf) | [MD](./clases/resúmenes/guia_8.md) y [PDF](./clases/resúmenes/guia_8.pdf) |
| 9 | Resultados básicos de computabilidad | [Guía 9](./clases/material/guia_9.pdf) | [MD](./clases/resúmenes/guia_9.md) y [PDF](./clases/resúmenes/guia_9.pdf) |

### Lista de Combos (Examen Final - Parte Teórica)

#### Definiciones y convenciones notacionales

| Combo | Tema | Material |
|-------|------|----------|
| 1 | Conjunto $\Sigma$-r, $\langle s_1,s_2,..\rangle$, función $\Sigma$-mixta, "familia $\Sigma$-indexada de funciones", $R(f,\mathcal{G})$ | [LyX](./final/definiciones_y_convenciones/combo_1_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_1_def.23.pdf) |
| 2 | $d\overset{n}{\vdash}d'$, $L(M)$, $H(M)$, "función de tipo $(n,m,s)$ ", $(x)$, $(x)_i$ | [LyX](./final/definiciones_y_convenciones/combo_2_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_2_def.23.pdf) |
| 3 | Conjunto $\Sigma$-r.e., $s^\leq$, $*^\leq$, $\\#^\leq$ | [LyX](./final/definiciones_y_convenciones/combo_3_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_3_def.23.pdf) |
| 4 | Función $\Sigma$-efectivamente computable y procedimiento efectivo que la computa | [LyX](./final/definiciones_y_convenciones/combo_4_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_4_def.23.pdf) |
| 5 | Conjunto $\Sigma$-efectivamente computable y procedimiento efectivo que decide la pertenencia | [LyX](./final/definiciones_y_convenciones/combo_5_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_5_def.23.pdf) |
| 6 | Conjunto $\Sigma$-efectivamente enumerable y procedimiento efectivo que lo enumera | [LyX](./final/definiciones_y_convenciones/combo_6_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_6_def.23.pdf) |
| 7 | Función $\Sigma$-Turing computable y máquina que la computa | [LyX](./final/definiciones_y_convenciones/combo_7_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_7_def.23.pdf) |
| 8 | $M(P)$, $Lt$, conjunto rectangular, conjunto de tipo $(n,m)$ | [LyX](./final/definiciones_y_convenciones/combo_8_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_8_def.23.pdf) |
| 9 | " $I$ es instrucción de $S^\Sigma$ ", $\mathcal{P}$ es programa de $S^\Sigma$, $I_i^\mathcal{P}$, $n(\mathcal{P})$, $Bas$ | [LyX](./final/definiciones_y_convenciones/combo_9_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_9_def.23.pdf) |
| 10 | (Relativo a $S^\Sigma$) "Estado", "descripción instantánea", $S_\mathcal{P}$, "estado obtenido luego de $t$ pasos", " $\mathcal{P}$ se detiene luego de $t$ pasos" | [LyX](./final/definiciones_y_convenciones/combo_10_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_10_def.23.pdf) |
| 11 | $\Psi_\mathcal{P}^{n,m,\\#}$, función $\Sigma$-computable y programa que la computa, $M^\leq(P)$ | [LyX](./final/definiciones_y_convenciones/combo_11_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_11_def.23.pdf) |
| 12 | Conjunto $\Sigma$-computable, conjunto $\Sigma$-enumerable y programa que lo enumera | [LyX](./final/definiciones_y_convenciones/combo_12_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_12_def.23.pdf) |
| 13 | $i^{n,m}$, $E_{\\#}^{n,m}$, $E_*^{n,m}$, $E_{\\#j}^{n,m}$, $E_{*j}^{n,m}$, $Halt^{n,m}$, $T^{n,m}$, $AutoHalt^\Sigma$ y los conjuntos $A$ y $N$ | [LyX](./final/definiciones_y_convenciones/combo_13_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_13_def.23.pdf) |
| 14 | Notación lambda | [LyX](./final/definiciones_y_convenciones/combo_14_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_14_def.23.pdf) |
| 15 | Macro de asignación | [LyX](./final/definiciones_y_convenciones/combo_15_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_15_def.23.pdf) |
| 16 | Macro IF | [LyX](./final/definiciones_y_convenciones/combo_16_def.23.lyx) y [PDF](./final/definiciones_y_convenciones/combo_16_def.23.pdf) |

#### Teoremas

| Combo | Tema | Material |
|-------|------|----------|
| 1 | Caracterización de conjuntos p.r., Neumann vence a Godel | [LyX](./final/teoremas/combo_1_teo.23.lyx) y [PDF](./final/teoremas/combo_1_teo.23.pdf) |
| 2 | Lema de división por casos para funciones p.r., Caracterización básica de conjuntos enumerables | [LyX](./final/teoremas/combo_2_teo.23.lyx) y [PDF](./final/teoremas/combo_2_teo.23.pdf) |
| 3 | Godel vence a Neumann, Caracterización de conjuntos efectivamente computables | [LyX](./final/teoremas/combo_3_teo.23.lyx) y [PDF](./final/teoremas/combo_3_teo.23.pdf) |
| 4 | Caracterización básica de conjuntos enumerables, Lema de la sumatoria | [LyX](./final/teoremas/combo_4_teo.23.lyx) y [PDF](./final/teoremas/combo_4_teo.23.pdf) |
| 5 | Lema de intersección de conjuntos $\Sigma$-efectivamente enumerables, Lema de cuantificación acotada | [LyX](./final/teoremas/combo_5_teo.23.lyx) y [PDF](./final/teoremas/combo_5_teo.23.pdf) |
| 6 | Efectivamente computable implica efectivamente enumerable, Caracterización de conjuntos r.e. | [LyX](./final/teoremas/combo_6_teo.23.lyx) y [PDF](./final/teoremas/combo_6_teo.23.pdf) |
| 7 | Lema de minimización acotada, función con clausura | [LyX](./final/teoremas/combo_7_teo.23.lyx) y [PDF](./final/teoremas/combo_7_teo.23.pdf) |
| 8 | $AutoHalt^\Sigma$ no $\Sigma$-r., $AutoHalt^\Sigma$ no $\Sigma$-efectivamente computable, $A$ $\Sigma$-r.e. y no $\Sigma$-r. y $N$ no $\Sigma$-r.e., Neumann vence a Godel | [LyX](./final/teoremas/combo_8_teo.23.lyx) y [PDF](./final/teoremas/combo_8_teo.23.pdf) |
| 9 | Lema de división por casos para funciones recursivas, $Halt^{n,m}$ es $(\Sigma\cup\Sigma_p)$-p.r., $T^{n,m}$ es $(\Sigma\cup\Sigma_p)$-r. | [LyX](./final/teoremas/combo_9_teo.23.lyx) y [PDF](./final/teoremas/combo_9_teo.23.pdf) |
