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
- 