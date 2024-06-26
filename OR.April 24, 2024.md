# Modelo de transporte
El *modelo de transporte* busca minimizar costes.
Los modelos de transporte tienen costos y distancias.

En el ejemplo tenemos el costo de transporte de mover una unidad de una planta a otra,
y la distancia entre las plantas.

El modelo de transporte debe estar balanceado, es decir que la oferta debe ser igual a la demanda.

La cantidad de variables básicas nos la dará la ecuación $n+m-1$.

Todas las casillas en donde coloquemos valores resultarán ser una variable básica de la solución óptima que se encuentre.

<iframe
  src="https://adrigondo.github.io/UACH-operations-research/OR.April%2024,%202024.NorthwestCorner.html"
  width="270"
  height="225"
  style="background-color: white; border-radius:4px"
  frameborder="0"
  >
</iframe>

Llevando a cabo el *método de la Esquina Noroeste* obtenemos la siguiente función objetivo con la solución:

$\textrm{Min} Z=10(5)+2(10)+7(5)+9(15)+20(5)+18(10)=520$


<iframe
  src="https://adrigondo.github.io/UACH-operations-research/OR.April%2024,%202024.MinimalCost.html"
  width="270"
  height="225"
  style="background-color: white; border-radius:4px"
  frameborder="0"
  >
</iframe>

Llevando a cabo el *método de los costos mínimos* obtenemos la siguiente función objetivo con la solución:

$\textrm{Min} Z=2(15)+5(4)+9(15)+11(0)+20(10)+18(5)=475$
