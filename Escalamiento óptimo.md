# Introducción a los procedimientos de escalamiento óptimo de datos categóricos [👉](https://www.ibm.com/docs/es/spss-statistics/SaaS?topic=categories-introduction-optimal-scaling-procedures-categorical-data)

Los procedimientos de categorías utilizan el escalamiento óptimo para analizar datos que son difíciles o imposibles de analizar mediante los procedimientos estadísticos estándar.

## ¿Qué es el escalamiento óptimo?

La idea que subyace tras el escalamiento óptimo es asignar cuantificaciones numéricas a las categorías de cada variable, lo que permite utilizar los procedimientos estándar para obtener una solución con las variables cuantificadas.

Los valores de escala óptimos se asignan a las categorías de cada variable de acuerdo con el criterio de optimización del procedimiento que se esté utilizando. A diferencia de las etiquetas originales de las variables nominales u ordinales del análisis, estos valores de escala tienen propiedades métricas.

En la mayoría de los procedimientos de categorías, la cuantificación óptima de cada variable escalada se obtiene mediante un método iterativo denominado **mínimos cuadrados alternantes** en el que, después de que se utilicen las cuantificaciones actuales para encontrar una solución, las cuantificaciones se actualizan utilizando dicha solución. A continuación, se utilizan las cuantificaciones actualizadas para buscar una nueva solución, que a su vez se utiliza para actualizar las cuantificaciones y así sucesivamente, hasta que se alcanza algún criterio que indica al proceso que finalice.

## ¿Por qué utilizar el escalamiento óptimo?

Los datos categóricos se utilizan con frecuencia en los estudios de mercado, los estudios de encuestas y la investigación en las ciencias sociales y del comportamiento. De hecho, muchos investigadores trabajan casi exclusivamente con datos categóricos.

Aunque existen adaptaciones de la mayoría de los modelos estándar que permiten analizar específicamente datos categóricos, con frecuencia no funcionan bien con conjuntos de datos con las siguientes características:

- Observaciones insuficientes
- Demasiadas variables
- Demasiados valores por cada variable

Mediante la cuantificación de categorías, las técnicas de escalamiento óptimo evitan los problemas de estas situaciones. Además, son muy útiles incluso cuando es apropiado utilizar técnicas especializadas.

En vez de interpretar las estimaciones de los parámetros, la interpretación de los resultados del escalamiento óptimo muchas veces se basa en representaciones gráficas. Las técnicas de escalamiento óptimo ofrecen excelentes análisis exploratorios. Mediante el acotamiento del objetivo de la investigación, la visualización de los datos mediante el escalamiento óptimo puede formar la base de un análisis que se centre en la interpretación de los parámetros del modelo.

## Nivel de escalamiento óptimo y nivel de medición

Este concepto puede resultar muy confuso cuando se utilizan por primera vez los procedimientos de categorías. Al especificar el nivel, no se especifica el nivel al que se miden las variables, sino el nivel al que se escalan. La idea es que las variables que se van a cuantificar pueden tener relaciones no lineales independientemente de cómo se midan.

En categorías, hay tres niveles básicos de mediciones:

- El nivel nominal implica que los valores de una variable representan categorías desordenadas. Algunos ejemplos de variables que pueden ser nominales serían la región, el área del código postal, la confesión religiosa y las categorías con varias opciones.
- El nivel ordinal implica que los valores de una variable representan categorías ordenadas. Entre los ejemplos se incluyen escalas de actitud que representan el grado de satisfacción o confianza y las puntuaciones de evaluación de las preferencias.
- El nivel numérico implica que los valores de una variable representan categorías ordenadas con una métrica significativa, de modo que las comparaciones de distancia entre categorías son adecuadas. Entre los ejemplos se incluyen la edad en años y los ingresos en dólares.

Por ejemplo, suponga que las variables región, trabajo y edad se codifican como se muestra en la siguiente tabla.

*Tabla 1. Esquema de codificación para región, trabajo y edad*

|Código de región |Valor de región |Código de trabajo |Valor de trabajo |Edad |
|------------|-------------|--------------|------------|------------|
|1	|Norte	|1	|trabajador en prácticas	|20 |
|2	|Sur	|2	|vendedor	|22 |
|3	|Este	|3	|administrador	|25 |
|4	|Oeste	| 	| 	|27 |

Los valores mostrados representan las categorías de cada variable. Región sería una variable nominal. Hay cuatro categorías de región, sin ningún orden intrínseco. Los valores del 1 al 4 sencillamente representan las cuatro categorías; el esquema de codificación es completamente arbitrario. Trabajo, por otra parte, se podría considerar como variable ordinal. Las categorías originales forman una progresión desde trabajador en prácticas hasta administrador. Los códigos mayores representan un trabajo superior en la escala corporativa. Sin embargo, sólo se conoce la información acerca del orden, no se puede decir nada acerca de la distancia existente entre categorías adyacentes. Por el contrario, edad se podría considerar como una variable numérica. En el caso de edad, las distancias entre los valores son intrínsecamente significativas. La distancia entre 20 y 22 es la misma que la que hay entre 25 y 27, mientras que la distancia entre 22 y 25 es superior a las dos anteriores.

### Selección del nivel de escalamiento óptimo

Es importante comprender que no hay propiedades intrínsecas de una variable que predefinan automáticamente el nivel de escalamiento óptimo que se debería definir para ella. Puede explorar los datos de cualquier manera lógica que facilite la interpretación. Mediante el análisis de una variable de nivel numérico a nivel ordinal, por ejemplo, el uso de una transformación no lineal puede permitir una solución con menos dimensiones.

Los dos ejemplos siguientes ilustran cómo el nivel de medición "obvio" no siempre es el mejor nivel de escalamiento óptimo. Supongamos que una variable ordena objetos en dos grupos de edad. Aunque la edad se puede escalar como una variable numérica, puede ocurrir que en las personas menores de 25 años, la seguridad tenga una relación positiva con la edad, mientras que en las personas mayores de 60 años, la seguridad tenga una relación negativa con la edad. En este caso, puede ser mejor tratar la edad como una variable nominal.

Tomemos otro ejemplo, una variable que ordena a las personas por preferencia política parece ser básicamente nominal. Sin embargo, si se ordenan los partidos desde la izquierda política hasta la derecha política, puede que le interese que la cuantificación de los partidos respete este orden mediante un nivel ordinal de análisis.

Aunque no haya propiedades predefinidas de una variable que la coloquen exclusivamente en un nivel o en otro, existen algunas normas generales que pueden ayudar al usuario inexperto. Con la cuantificación nominal simple, habitualmente no se conoce el orden de las categorías pero se desea que el análisis imponga una. Si se conoce el orden de las categorías, debería intentarse la cuantificación ordinal. Si las categorías no se pueden ordenar, puede intentar la cuantificación nominal múltiple.

### Gráficos de transformación

Los diferentes niveles en los que se puede escalar cada variable imponen diferentes restricciones sobre las cuantificaciones. Los gráficos de transformación ilustran la relación entre las cuantificaciones y las categorías originales que resultan del nivel de escalamiento óptimo seleccionado. Por ejemplo, se genera un gráfico de transformación lineal cuando una variable se trata como numérica. Las variables tratadas como ordinales generan gráficos de transformación no decreciente. Los gráficos de transformación de variables tratadas nominalmente que tienen forma de U (o la inversa) muestran una relación cuadrática. Las variables nominales también pueden generar gráficos de transformación sin tendencias aparentes mediante el cambio completo del orden de las categorías. La siguiente figura muestra un gráfico de transformación de ejemplo.

Los gráficos de transformación son especialmente adecuados para determinar si funciona bien el nivel de escalamiento óptimo seleccionado. Si varias categorías reciben cuantificaciones similares, la agrupación de estas categorías en una categoría puede estar justificada. Otra posibilidad, si una variable tratada como nominal recibe cuantificaciones que muestran una tendencia creciente, una transformación ordinal puede generar un ajuste similar. Si esta tendencia es lineal, el tratamiento numérico puede resultar adecuado. Sin embargo, si la agrupación de categorías o el cambio de los niveles de escalamiento están justificados, el análisis no cambiará de manera significativa.

### Códigos de la categoría

Se debe tener cierto cuidado al codificar las variables categóricas ya que algunos esquemas de codificación pueden generar resultados no deseados o análisis incompletos. En la siguiente tabla se muestran algunos posibles esquemas de codificación para el trabajo.

*Tabla 1. Esquemas de codificación alternativos para el trabajo*

|Categoría |A |B |C |D |
|--------|-------|-------|-------|-------|
|trabajador en prácticas	|1	|1	|5	|1 |
|vendedor	|2	|2	|6	|5 |
|administrador	|3	|7	|7	|3 |

Algunos procedimientos de categorías requieren que se defina el rango de cada variable. Todo valor fuera de este rango se tratará como un valor perdido. El valor de categoría mínima es siempre 1. El valor de categoría máxima lo indica el usuario. Este valor no es el número de categorías de una variable, sino el valor mayor de la categoría. Por ejemplo, en la tabla, el esquema A tiene un valor de categoría máxima de 3 y el esquema B tiene un valor de categoría máxima de 7, aunque ambos esquemas codifican las mismas tres categorías.

El rango de la variable determina las categorías que se omitirán del análisis. Todas las categorías con códigos fuera del rango definido se omitirán del análisis. Se trata de un método sencillo de omitir categorías, pero puede generar análisis no deseados. Una categoría máxima incorrectamente definida puede omitir categorías válidas del análisis. Por ejemplo, para el esquema B, si se define que el valor de categoría máxima sea 3 indica que trabajo tiene categorías codificadas de 1 a 3; la categoría administrador se tratará como valor perdido. Como no hay ninguna categoría que se haya codificado realmente como 3, la tercera categoría del análisis no contendrá ningún caso. Si desea omitir todas las categorías de administrador, este análisis sería adecuado. Sin embargo, si desea incluir a los administradores, la categoría máxima deberá definirse como 7 y los valores perdidos deberán codificarse con valor por encima de 7 o por debajo de 1.

Link: https://www.ibm.com/docs/es/spss-statistics/SaaS?topic=level-category-codes
