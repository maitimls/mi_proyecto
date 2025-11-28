# Análisis de las Ventas de una Cafetería

Este proyecto analiza un dataset de las ventas de una cafetería con el objetivo de analizar qué productos son los más deseados y cuáles están generando más revenue. Además, tratar de buscar relaciones a través de la visualización de los resultados tras una previa limpieza del dataset.

## Estructura
- `/data`: dataset original y dataset limpio
- `/notebooks`: EDA: Descripción, Limpieza y Visualización

## Requerimientos
Python 3.13.7
Pandas, Seaborns, Matplotlib, Numpy.

## Notas: 
### Primer Notebook
En el primer notebook encontramos la Descripción del dataset:
- Tamaño de 10.000 filas x 8 columnas
- Todas las variables estaban en formato "objeto" por ello lo primero que se hizo en la Limpieza fue atribuirles el valor correspondiente.
- El nombre de las columnas venía correctamente, sin símbolos, ni guiones, por ello no se ha cambiado ningun nombre.
- Para medir la calidad del dataset, empezamos viendo qué tipo de datos teníamos y qué cantidad de NaN, Errores o valores desconocidos. 
- Pudimos ver que no había datos duplicados ya que el .value_counts del ID era igual al nº de filas del dataset.
- Había datos nulos o valores erroneos en todas las columnas, pero sobre todo en Location y Payment Method.

### Segundo Notebook
En el segundo notebook encontraremos la Limpieza del dataset:
- El primer cambio que se ha hecho es el de atribuirle el valor correspondiente a cada columna, a las str el formarto str, a los enteros formato int y a los números decimales float, y por último a las fechas el formato time.
- Tras darle formato type a cada variable, el proceso de limpieza se realizó de izquierda a derecha. 
- Partiendo de la base de que las 2 primeras columnas se relacionan entre sí con Item y su Price Per Unit que sabiamos que el café costaba 2.0, y la ensalada 5.0, por ello se elimimaron aquellas filas que contuviesen un Error, Nan o Unknown en ambas filas. 
- Tras esto, se atribuyó el Price Per Unit a aquellas filas que contuviesen un Error, NaN o Unknown pero sí sabiamos el Item, ya que, si sabemos que es un café, sabemos que el precio de los cafés es de 2.0.
- Partiendo de la base de la relación de las 3 columnas = Quantity * Price = Total Spent, se eliminaron las columnas donde faltasen 2 de estos 3 valores ya que no se podría deducir el valor de éstos de otra manera.
- Tras finalizar la limpieza de las 4 primeras columnas seguimos con la columna de Payment Method que es la que más valores nulos tenía de todas las columnas y se decidió unificar los errores y nulos a la variable "Otros", ya que sería demasiada información para eliminar.
- Lo mismo ocurrió con la variable Location, por ello se creó la variable "Not Saved".
- Por último, la columna en formato fecha contenía varios NaT que se les otorgó la variable "Not Time", y se invirtió el formato de año/mes/día a dia/mes/año. (El cuál se ejecutó pero ahora genera error.)

### Tercer Notebook
En el tercer Notebook encontraremos la visualización del dataset resultado de la limpieza:
- El dataset resultado tiene una longitud de 9331 filas.
- Lo primero que podemos ver es la de un gráfico de barras que representa la cantidad de productos que se han vendido, un gráfico de tarta que representa el método de pago que han escogido los clientes y también uno que representa dónde se han consumido los productos comprados en la cafetería.
- También se ha hecho un histograma que nos muestra que las variables tienen una distribución razonable y que el grosso de las compras están entre los 1 y 6€.
- Cómo varían los valores a lo largo del tiempo en un gráfico de barras.
- Por último un análisis de como los valores "Not Time" y "Not Saved" no han alterado al resultado final.