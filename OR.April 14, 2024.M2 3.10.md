Desarrolle los siguientes ejercicios: 

A) En el siguiente problema, determine la nueva fila $Z$ para la tabla inicial considerando las variables artificiales para aquellas restricciones que no tengan holgura. Determine por el método simplex si existe una solución óptima y argumente el resultado.

$Max Z = 3x_1 + 2x_2 +5x_3$

Sujeto a

$x_1 + 2x_2 + x_3 = 430$

$3x_1 + 2x_3 <= 460$

$x_1 + 4x_2 >= 420$

$x_1,x_2 >= 0$

Dadas las restriciones:
   
### Definición de ecuaciones

> Identificamos las restricciones que poseen holgura. Identificamos las restricciones que no poseen holgura, a estás les agregaremos variables artificiales.

$Z - 3x_1 - 2x_2 - 5x_3 + MR_1 + 0s_1 - 0S_1 + MR_2= 0$

$x_1 + 2x_2 + x_3 + R_1 = 430$

$3x_1 + 2x_3 + s_1 = 460$

$x_1 + 4x_2 - S_1 + R_2 = 420$


> $m=\textrm{numero de ecuaciones}$
>
> $n=\textrm{numero de variables}$
>
> Para calcular la cantidad de puntos de esquina
> $C_m^n=\frac{n!}{m(n-m)!}$

$m=3, n=7$

$C_m^n=\frac{7!}{3(7-3)!}=70$

### Identificar variables básicas ($V_B$) y variables no básicas ($V_{NB}$)

> Las variables básicas para el primer punto son las holguras.

Para el punto $A$ todas las holguras son son nuestras $V_B$, es decir: $R_1,s_1,R_2$

| $V_B$ | $Z$ | $x_1$ | $x_2$ | $x_3$ | $R_1$ | $s_1$ | $S_1$ | $R_2$ | $Solución$ |
| ----- | --- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ---------- |
| $Z$   | $1$ | $-3$  | $-2$  | $-5$  | $0$   | $0$   | $0$   | $0$   | $0$        |
| $R_1$ | $0$ | $1$   | $2$   | $2$   | $1$   | $0$   | $0$   | $0$   | $430$      |
| $s_1$ | $0$ | $3$   | $0$   | $2$   | $0$   | $1$   | $0$   | $0$   | $460$      |
| $R_2$ | $0$ | $1$   | $4$   | $0$   | $0$   | $0$   | $-1$  | $1$   | $420$      |

> Seleccionamos una M lo suficientemente grande para penalizar nuestra función objetivo.

$M=100$

$Z - 3x_1 - 2x_2 - 5x_3 + MR_1 + MR_2 = 0$

$Z = 3x_1 + 2x_2 +5x_3 - MR_1 - MR_2$

$Z = 3x_1 + 2x_2 +5x_3 - 100R_1 - 100R_2$

$Z = 0 \neq  3(0) + 2(0) +5(0) - 100(430) - 100(420) = -85000$

### Corregir la ecuación de $Z$

> Tenemos que nivelar la función Z por que es incongruente.
> Para esto evaluaruemos las variables artificiales en terminos de las
> variables (y superávits), y sustituiremos sus valores en la ecuación Z.

De $x_1 + 2x_2 + x_3 + R_1 = 430$ :

$R_1$ = - x_1 - 2x_2 - x_3 + 430$

De $x_1 + 4x_2 - S_1 + R_2 = 420$

$R_2 = - x_1 - 4x_2 + S_1 + 420$

Sustituyendo en $Z - 3x_1 - 2x_2 - 5x_3 + MR_1 + MR_2 = 0$

$Z - 3x_1 - 2x_2 - 5x_3 + 100(- x_1 - 2x_2 - x_3 + 430) + 100(- x_1 - 4x_2 + S_1 + 420) = 0$

$Z - 3x_1 - 2x_2 - 5x_3 - 100x_1 - 200x_2 - 100x_3 + 43000 - 100x_1 - 400x_2 + 100S_1 + 42000 = 0$

$Z - 203x_1 - 602x_2 - 105x_3 + 85000 + 100S_1 = 0$

$Z - 203x_1 - 602x_2 - 105x_3 + 100S_1 = -85000$

> Una vez que obtenemos la nueva ecuación de Z, la colocamos en su lugar en la tabla.

| $V_B$ | $Z$ | $x_1$  | $x_2$  | $x_3$  | $R_1$ | $s_1$ | $S_1$ | $R_2$ | $Solución$ |
| ----- | --- | ------ | ------ | ------ | ----- | ----- | ----- | ----- | ---------- |
| $Z$   | $1$ | $-203$ | $-602$ | $-105$ | $0$   | $0$   | $100$ | $0$   | $-85000$   |
| $R_1$ | $0$ | $1$    | $2$    | $1$    | $1$   | $0$   | $0$   | $0$   | $430$      |
| $s_1$ | $0$ | $3$    | $0$    | $2$    | $0$   | $1$   | $0$   | $0$   | $460$      |
| $R_2$ | $0$ | $1$    | $4$    | $0$    | $0$   | $0$   | $-1$  | $1$   | $420$      |

> Realizamos el método SIMPLEX.

## Primera iteración

### Seleccionar variable de entrada ($V_E$)

> ¿Qué variable de mi función $Z$ afecta más a mi modelo?

El modelo busca maximizar, por esto la variable que afecta más es la más negativa.

$V_E=x_2$

| $V_B$ | Columna $V_E$ | Columna $Solución$ | Relación mínima         | Válida |
| ----- | ------------- | ------------------ | ----------------------- | ------ |
| $R_1$ | $2$           | $430$              | $\frac{430}{2}=215$     | Sí     |
| $s_1$ | $0$           | $460$              | $\frac{460}{0}=\infty$  | No     |
| $R_2$ | $4$           | $420$              | ==$\frac{420}{4}=105$== | Sí     |

$R_2$ es nuestra variable pivote ($V_P$)

### Actualizar la fila de la variable pivote ($V_P$)

$M_{V_P,V_E}=4$.

> $M_{V_P},j=\frac{M_{V_P,j}}{M_{V_P,V_E}}$ 

$R_2 \to x_2$

| $V_B$ | $Z$ | $x_1$         | $x_2$           | $x_3$ | $R_1$ | $s_1$ | $S_1$          | $R_2$         | $Solución$          |
| ----- | --- | ------------- | --------------- | ----- | ----- | ----- | -------------- | ------------- | ------------------- |
| $x_2$ | $0$ | $\frac{1}{4}$ | $\frac{4}{4}=1$ | $0$   | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$ | $\frac{420}{4}=105$ |

| $V_B$ | $Z$ | $x_1$         | $x_2$  | $x_3$  | $R_1$ | $s_1$ | $S_1$          | $R_2$         | $Solución$ |
| ----- | --- | ------------- | ------ | ------ | ----- | ----- | -------------- | ------------- | ---------- |
| $Z$   | $1$ | $-203$        | $-602$ | $-105$ | $0$   | $0$   | $100$          | $0$           | $-85000$   |
| $R_1$ | $0$ | $1$           | $2$    | $1$    | $1$   | $0$   | $0$            | $0$           | $430$      |
| $s_1$ | $0$ | $3$           | $0$    | $2$    | $0$   | $1$   | $0$            | $0$           | $460$      |
| $x_2$ | $0$ | $\frac{1}{4}$ | $1$    | $0$    | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$ | $105$      |

### Actualizar las demás filas respecto a la fila pivote
> Para todas las filas $M_i$: <br>
> $M_i = M_i -  M_{i,V_E} \cdot M_{V_P}$

#### Actualizar $Z$

| $V_B$               | $Z$ | $x_1$            | $x_2$      | $x_3$  | $R_1$ | $s_1$ | $S_1$            | $R_2$            | $Solución$ |
| ------------------- | --- | ---------------- | ---------- | ------ | ----- | ----- | ---------------- | ---------------- | ---------- |
| $Z$                 | $1$ | $-203$           | ==$-602$== | $-105$ | $0$   | $0$   | $100$            | $0$              | $-85000$   |
| $x_2$               | $0$ | $\frac{1}{4}$    | $1$        | $0$    | $0$   | $0$   | $\frac{-1}{4}$   | $\frac{1}{4}$    | $105$      |
| $-602x_2$           | $0$ | $\frac{-301}{2}$ | $-602$     | $0$    | $0$   | $0$   | $\frac{301}{2}$  | $\frac{-301}{2}$ | $-63210$   |
| $Z = Z - (-602x_2)$ | $1$ | $\frac{-105}{2}$ | $0$        | $-105$ | $0$   | $0$   | $\frac{-101}{2}$ | $\frac{301}{2}$  | $-21790$   |

#### Actualizar $R_1$

| $V_B$              | $Z$ | $x_1$         | $x_2$   | $x_3$ | $R_1$ | $s_1$ | $S_1$          | $R_2$          | $Solución$ |
| ------------------ | --- | ------------- | ------- | ----- | ----- | ----- | -------------- | -------------- | ---------- |
| $R_1$              | $0$ | $1$           | ==$2$== | $1$   | $1$   | $0$   | $0$            | $0$            | $430$      |
| $x_2$              | $0$ | $\frac{1}{4}$ | $1$     | $0$   | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$  | $105$      |
| $2x_2$             | $0$ | $\frac{1}{2}$ | $2$     | $0$   | $0$   | $0$   | $\frac{-1}{2}$ | $\frac{1}{2}$  | $210$      |
| $R_1 = R_1 - 2x_2$ | $0$ | $\frac{1}{2}$ | $0$     | $1$   | $1$   | $0$   | $\frac{1}{2}$  | $\frac{-1}{2}$ | $220$      |

#### Actualizar $s_1$

| $V_B$              | $Z$ | $x_1$         | $x_2$   | $x_3$ | $R_1$ | $s_1$ | $S_1$          | $R_2$         | $Solución$ |
| ------------------ | --- | ------------- | ------- | ----- | ----- | ----- | -------------- | ------------- | ---------- |
| $s_1$              | $0$ | $3$           | ==$0$== | $2$   | $0$   | $1$   | $0$            | $0$           | $460$      |
| $x_2$              | $0$ | $\frac{1}{4}$ | $1$     | $0$   | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$ | $105$      |
| $0x_2$             | $0$ | $0$           | $1$     | $0$   | $0$   | $0$   | $0$            | $0$           | $0$        |
| $s_1 = s_1 - 0x_2$ | $0$ | $3$           | $0$     | $2$   | $0$   | $1$   | $0$            | $0$           | $460$      |


### Actualizar tabla con las filas actualizadas

| $V_B$ | $Z$ | $x_1$            | $x_2$ | $x_3$  | $R_1$ | $s_1$ | $S_1$            | $R_2$           | $Solución$ |
| ----- | --- | ---------------- | ----- | ------ | ----- | ----- | ---------------- | --------------- | ---------- |
| $Z$   | $1$ | $\frac{-105}{2}$ | $0$   | $-105$ | $0$   | $0$   | $\frac{-101}{2}$ | $\frac{301}{2}$ | $-21790$   |
| $R_1$ | $0$ | $\frac{1}{2}$    | $0$   | $1$    | $1$   | $0$   | $\frac{1}{2}$    | $\frac{-1}{2}$  | $220$      |
| $s_1$ | $0$ | $3$              | $0$   | $2$    | $0$   | $1$   | $0$              | $0$             | $460$      |
| $x_2$ | $0$ | $\frac{1}{4}$    | $1$   | $0$    | $0$   | $0$   | $\frac{-1}{4}$   | $\frac{1}{4}$   | $105$      |

Esté $PE$ es $B$, donde $x_1=0, x_2=105, x_3=0$ y obtenemos una $Z$ de $-21790$

## Segunda iteración

### Seleccionar variable de entrada ($V_E$)

$V_E=x_3$

| $V_B$ | Columna $V_E$ | Columna $Solución$ | Relación mínima         | Válida |
| ----- | ------------- | ------------------ | ----------------------- | ------ |
| $R_1$ | $1$           | $220$              | ==$\frac{220}{1}=220$== | Sí     |
| $s_1$ | $2$           | $460$              | $\frac{460}{2}=230$     | sí     |
| $x_2$ | $0$           | $105$              | $\frac{105}{0}=\infty$  | No     |

$R_1$ es nuestra variable pivote ($V_P$)

### Actualizar la fila de la variable pivote ($V_P$)

$M_{V_P,V_E}=1$.

> $M_{V_P},j=\frac{M_{V_P,j}}{M_{V_P,V_E}}$ 

$R_1 \to x_3$

| $V_B$ | $Z$ | $x_1$         | $x_2$ | $x_3$ | $R_1$ | $s_1$ | $S_1$         | $R_2$          | $Solución$ |
| ----- | --- | ------------- | ----- | ----- | ----- | ----- | ------------- | -------------- | ---------- |
| $x_3$ | $0$ | $\frac{1}{2}$ | $0$   | $1$   | $1$   | $0$   | $\frac{1}{2}$ | $\frac{-1}{2}$ | $220$      |

| $V_B$ | $Z$ | $x_1$            | $x_2$ | $x_3$  | $R_1$ | $s_1$ | $S_1$            | $R_2$           | $Solución$ |
| ----- | --- | ---------------- | ----- | ------ | ----- | ----- | ---------------- | --------------- | ---------- |
| $Z$   | $1$ | $\frac{-105}{2}$ | $0$   | $-105$ | $0$   | $0$   | $\frac{-101}{2}$ | $\frac{301}{2}$ | $-21790$   |
| $x_3$ | $0$ | $\frac{1}{2}$    | $0$   | $1$    | $1$   | $0$   | $\frac{1}{2}$    | $\frac{-1}{2}$  | $220$      |
| $s_1$ | $0$ | $3$              | $0$   | $2$    | $0$   | $1$   | $0$              | $0$             | $460$      |
| $x_2$ | $0$ | $\frac{1}{4}$    | $1$   | $0$    | $0$   | $0$   | $\frac{-1}{4}$   | $\frac{1}{4}$   | $105$      |

#### Actualizar $Z$

| $V_B$               | $Z$ | $x_1$            | $x_2$ | $x_3$      | $R_1$  | $s_1$ | $S_1$            | $R_2$           | $Solución$ |
| ------------------- | --- | ---------------- | ----- | ---------- | ------ | ----- | ---------------- | --------------- | ---------- |
| $Z$                 | $1$ | $\frac{-105}{2}$ | $0$   | ==$-105$== | $0$    | $0$   | $\frac{-101}{2}$ | $\frac{301}{2}$ | $-21790$   |
| $x_3$               | $0$ | $\frac{1}{2}$    | $0$   | $1$        | $1$    | $0$   | $\frac{1}{2}$    | $\frac{-1}{2}$  | $220$      |
| $-105x_3$           | $0$ | $\frac{-105}{2}$ | $0$   | $-105$     | $-105$ | $0$   | $\frac{-105}{2}$ | $\frac{105}{2}$ | $-23100$   |
| $Z = Z - (-105x_3)$ | $1$ | $0$              | $0$   | $0$        | $105$  | $0$   | $2$              | $98$            | $1310$     |

#### Actualizar $s_1$

| $V_B$              | $Z$ | $x_1$         | $x_2$ | $x_3$   | $R_1$ | $s_1$ | $S_1$         | $R_2$          | $Solución$ |
| ------------------ | --- | ------------- | ----- | ------- | ----- | ----- | ------------- | -------------- | ---------- |
| $s_1$              | $0$ | $3$           | $0$   | ==$2$== | $0$   | $1$   | $0$           | $0$            | $460$      |
| $x_3$              | $0$ | $\frac{1}{2}$ | $0$   | $1$     | $1$   | $0$   | $\frac{1}{2}$ | $\frac{-1}{2}$ | $220$      |
| $2x_3$             | $0$ | $1$           | $0$   | $2$     | $2$   | $0$   | $1$           | $-1$           | $440$      |
| $s_1 = s_1 - 2x_3$ | $0$ | $2$           | $0$   | $0$     | $-2$  | $1$   | $-1$          | $1$            | $20$       |

#### Actualizar $x_2$

| $V_B$              | $Z$ | $x_1$         | $x_2$ | $x_3$   | $R_1$ | $s_1$ | $S_1$          | $R_2$          | $Solución$ |
| ------------------ | --- | ------------- | ----- | ------- | ----- | ----- | -------------- | -------------- | ---------- |
| $x_2$              | $0$ | $\frac{1}{4}$ | $1$   | ==$0$== | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$  | $105$      |
| $x_3$              | $0$ | $\frac{1}{2}$ | $0$   | $1$     | $1$   | $0$   | $\frac{1}{2}$  | $\frac{-1}{2}$ | $220$      |
| $0x_3$             | $0$ | $0$           | $0$   | $0$     | $1$   | $0$   | $0$            | $0$            | $0$        |
| $x_2 = x_2 - 0x_3$ | $0$ | $\frac{1}{4}$ | $1$   | $0$     | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$  | $105$      |

### Actualizar tabla con las filas actualizadas

| $V_B$ | $Z$ | $x_1$         | $x_2$ | $x_3$ | $R_1$ | $s_1$ | $S_1$          | $R_2$          | $Solución$ |
| ----- | --- | ------------- | ----- | ----- | ----- | ----- | -------------- | -------------- | ---------- |
| $Z$   | $1$ | $0$           | $0$   | $0$   | $105$ | $0$   | $2$            | $98$           | $1310$     |
| $x_3$ | $0$ | $\frac{1}{2}$ | $0$   | $1$   | $1$   | $0$   | $\frac{1}{2}$  | $\frac{-1}{2}$ | $220$      |
| $s_1$ | $0$ | $2$           | $0$   | $0$   | $-2$  | $1$   | $-1$           | $1$            | $20$       |
| $x_2$ | $0$ | $\frac{1}{4}$ | $1$   | $0$   | $0$   | $0$   | $\frac{-1}{4}$ | $\frac{1}{4}$  | $105$      |


Esté $PE$ es $B$, donde $x_1=0, x_2=105, x_3=220$ y obtenemos una $Z$ de $1310$. Dado que ya no hay más variables que
impacten en nuestro modelo, está es la $Z$ máxima.
