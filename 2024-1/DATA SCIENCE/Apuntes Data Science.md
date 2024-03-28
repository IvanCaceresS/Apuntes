# 11-03-24 
## INTRODUCCIÓN A LA CIENCIA DE DATOS
Data science is an inter-disciplinary field that uses scientific techneques from stastics and computer science to systematically extract knowledge.

**ROLES EN LA INDUSTRIA**
- Data scientist
- Data architect
- Data engineer
- Statistician
- Data science manager
- Machine learning engineer
- Decision scientist

**FRAMEWORKS DE DATA SCIENCE**
No son librerías de Python, sino que formas en que se ordena un equipo para llegar al objetivo

-KNOWLEDGE DISCOVER IN DATABASES (KDD): 
1. Seleccionar los datos
2. Procesado de datos
3. Transformación de datos
4. Data mining
5. Interpretación/evaluación
-OSEMN:
1. Obtain (Obtener datos)
2. Scrub (Limpiar los datos a formatos que la maquina entiende)
3. Explore (Encontrar patrones o tendencias usando métodos estadísticos)
4. Model (Construcción de modelos para predecir)
5. Interpret (Mostrar los resultados)
-CRISP-DM: The cross-industry standard process for data mining
1. Business understanding
2. Data understanding
3. Data preparation
4. Modeling
5. Evaluation
6. Deployment

**INTRODUCCION AL MACHINE LEARNING**


# 14-03-24
**Ppt clase 3**

## Distribución de los datos
---
Distribuciones de los datos, Train, dev y test
Tradicionalmente se utiliza la regla 60/20/20 para train, dev y test
O 70/30 para train y test.

En deep learning cambia y una distribución 98/1/1 train, dev, test esta bien

---
## Single number evaluation metric

Para medir si va bien o va mal.
si va bien es que tiene buena presicion

---
## Precisión y recall

Métricas para evaluar un clasificador.

**Precisión**: proporción de casos positivos identificados por el modelo sobre la cantidad de casos realmente positivos. Se usa para evitar una clasificación falsa positiva.
**Recall:** Relación entre los casos realmente positivos y la suma de los verdaderamente positivos y los falso negativos.

---

## Clasificador de gatos

Clasificador A tiene 95% probabilidad de que sea realmente un gato y hay un 10% que fue clasificado como gato pero no lo era

---
## F1 score 
se usa una media armonica entre precisión y recall



# 18-03-24
## Diferencia entre datos e información
Los datos hacen referencia al aspecto tecnologico de almacenamiento (persistente o no) de aspectos sensados de la realidad.
La informacion es el camino al conocimiento, se basa en datos y tiene un contexto
## Tipos de datos
Categorical:
	- Ordinal: categorico
	- Nominal: nombre, comuna
Numerical:
	- Discrete
	- Continuous: mg de un medicamento
## Cantidad de información
**Información de Shannon:** Mide la cantidad de información en una fuente de datos. 
**Entropía:** Mide el nivel de incertidumbre de una fuente de información, es decir, cuánta información falta.

Existen dos escenarios en los cuales una columna de un conjunto de datos no proporciona información útil, es decir, tiene entropía máxima. Por ejemplo, un identificador único o un valor repetitivo (como "alumnoUDP, alumnoUDP"), lo que resulta en una varianza nula.

 ## Problemas en los datos
1. Datos faltantes:
	1. **Missing at Random**: El dato se perdió pero depende de si mismo. ej: la gente vieja no entrega su edad
	2. **Missing Completly at Random**: Se perdió por alguna razon random
	3. **Missing not at Random**: El dato perdido depende de otros datos. La persona no quiere colocar el dato
2. Datos inútiles (o poco útiles)
	1. Features completamente concentrados
	2. Outliers 
	3. Skewed numerical features
	4. Clases desbalanceadas
	5. Maldicion de la dimensionalidad: Una tabla con muchas columnas al momento de entrenar perjudica el proceso.




# 21-03-24
## ¿Cuándo cambiar los conjuntos Dev/Test y las métricas?
PPT clase 4
- Es importante tener el objetivo del proyecto bien claro 
- Establecer correctamente los objetivos y la eleccion de metricas son fundamentales para el exito del proyecto

PPT clase 5
## Ideas de proyectos
- Sistema de recomendaciones:
	- Por usuarios similares
	- Por contenido consumido similar
- Sistema de detección de fraudes
- Clasificador de images
- Generador de descripción de fotos
- Reconocimiento de señales de tráfico



# 25-03-24
## Matriz de confusión

| **TRUE POSITIVE**  | **FALSE NEGATIVE** |
| -------------- | -------------- |
| **FALSE POSITIVE** | **TRUE NEGATIVE**  |
**Error tipo 1**: Falsos positivos
**Error tipo 2:** Falsos negativos

## Overfitting vs Underfitting
- El problema aparece cuando hablamos del grado polinomial del modelo.
- El grado del polinomio determina la flexibilidad.
- Un modelo subajustado (Underfitting) es menos flexible y no es capaz de captar el problema (en algunos casos).
- Un modelo sobreajustado (Overfitting) es muy flexible pero no sirve para generalizar los problemas por lo que no es muy útil.
- Underfit: Tendrá error alto tanto en entrenamiento como en las pruebas.
- Overfit: Tendrá error extremadamente bajo en el entrenamiento pero un error alto en las pruebas.
## Validación cruzada
Genera una seríe de experimentos donde voy cambiando los datos para entrenar al modelo, estos datos que se cambian son los grupos de validación

**Obs**: Si tengo un modelo no supervisado no puedo saber si hay o no overfitting o underfitting

# 28-03-24
## Reconocimiento de aves en la ciudad de Paecetopia
- Este ejemplo está adaptado de una aplicación real en producción, pero con detalles disfrazados para proteger la confidencialidad.
Eres un famoso investigador en la Ciudad de Peacetopia. La gente de Peacetopia tiene una característica común: tienen miedo a las aves. Para salvarlos, tienes que construir un algoritmo que detecte cualquier ave volando sobre Peacetopia y alerte a la población.
El Ayuntamiento te da un conjunto de datos de 10,000,000 imágenes del cielo sobre Peacetopia, tomadas de las cámaras de seguridad de la ciudad. Están etiquetadas:
- y = 0: There is no bird on the image
- y = 1: There is a bird on the image

Tu objetivo es construir un algoritmo capaz de clasificar nuevas imágenes tomadas por las cámaras de seguridad de Peacetopia.

Hay muchas decisiones que tomar:
**¿Cuál es la métrica de evaluación? ¿Cómo estructuras tus datos en conjuntos de entrenamiento/desarrollo/prueba?**
### Métrica de éxito
El Ayuntamiento te dice que quieren un algoritmo que:
- Tenga una alta precisión. 
- Funciona rápidamente y solo tarda un corto tiempo en clasificar una nueva imagen. 
- Pueda caber en una pequeña cantidad de memoria, para que pueda ejecutarse en un pequeño procesador al que la ciudad conectará a muchas cámaras de seguridad diferentes.

**Preguntas respecto al caso:**
1. Tener tres métricas de evaluación hace que sea más difícil para ti elegir rápidamente entre dos algoritmos diferentes y ralentizará la velocidad con la que tu equipo puede iterar. ¿Verdadero/Falso? **R:** Verdadero

Después de más discusiones, la ciudad reduce sus criterios a:
Necesitamos un algoritmo que pueda informarnos de que un ave está volando sobre Peacetopia con la mayor precisión posible”. “Queremos que el modelo entrenado no tarde más de 10 segundos en clasificar una nueva imagen”. “Queremos que el modelo quepa en 10MB de memoria”

2. Si tuvieras los tres siguientes modelos, ¿cuál elegirías?
	1. Precisión de  98%
	2. Tiempo de ejecución 9 segundos
	3. Tamaño de memoria 9MB
	**R:** El tamaño de la memoria, ya que si eso no se cumple el proyecto es inviable
3. Antes de implementar tu algoritmo, necesitas dividir tus datos en conjuntos de entrenamiento/desarrollo/prueba. ¿Cuál de estos crees que es la mejor opción?
	- entrenamiento: 50% desarrollo 10%, test: 40%
	- entrenamiento: 90% desarrollo 5%, test: 5%
	- entrenamiento: 50% desarrollo 40%, test: 10%
	- entrenamiento: 50% desarrollo 25%, test: 25%
	**R:** Ya que hay muchisimos datos (10 millones), la mejor opción es entrenamiento 90%, desarrollo 5% y test 5% ya que de esta forma se entrena un sistema robusto.

Después de configurar tus conjuntos de entrenamiento/desarrollo/prueba, el Ayuntamiento encuentra otras 1.000.000 de imágenes, llamadas “datos de los ciudadanos”. Aparentemente, los ciudadanos de Peacetopia están tan asustados de los pájaros que se ofrecieron voluntariamente para tomar fotos del cielo y etiquetarlas, contribuyendo así con estas 1.000.000 de imágenes adicionales. Estas imágenes son diferentes a la distribución de imágenes que el Ayuntamiento te había dado originalmente, pero crees que podrían ayudar a tu algoritmo.
4. No deberías agregar los datos de los ciudadanos al conjunto de entrenamiento, porque esto hará que las distribuciones de los conjuntos de entrenamiento y desarrollo/prueba sean diferentes, lo que perjudicará el rendimiento de los conjuntos de desarrollo y prueba. ¿Verdadero/Falso? **R:** Verdadero,no se debe ensuciar el set de datos
5. Un miembro del Ayuntamiento sabe un poco sobre el aprendizaje automático y cree que deberías agregar las 1.000.000 de imágenes de datos de los ciudadanos al conjunto de prueba. Te opones porque: 
	1. Las 1.000.000 de imágenes de datos de los ciudadanos no tienen una asignación consistente de x–>y como el resto de los datos
	2. Un conjunto de prueba más grande reducirá la velocidad de iteración debido al costo computacional de evaluar modelos en el conjunto de prueba.
	3. Esto haría que las distribuciones de los conjuntos de desarrollo y prueba sean diferentes. Esto es una mala idea porque no estás apuntando a donde quieres llegar.
	4. El conjunto de prueba ya no refleja la distribución de datos (cámaras de seguridad) que más te importa.
	**R:** 4
6. Entrenas un sistema y sus errores son los siguientes (error = 100% - Precisión): Error del conjunto de entrenamiento 4.0% Error del conjunto de desarrollo 4.5%. Esto sugiere que una buena forma de mejorar el rendimiento es entrenar una red más grande para reducir el error de entrenamiento del 4.0%. ¿Estás de acuerdo?
	1. Sí, porque tener un error de entrenamiento del 4.0% muestra que tienes un sesgo alto.
	2. Sí, porque esto muestra que tu sesgo es mayor que tu varianza.
	3. No, porque esto muestra que tu varianza es mayor que tu sesgo.
	4. No, porque no hay suficiente información para decirlo.
	**R:** Si tengo mucha varianza aumenta la probabilidad de que los conjuntos de entrenamiento queden distintos. Por lo tanto 3.
Pides a algunas personas que etiqueten el conjunto de datos para averiguar cuál es el rendimiento a nivel humano. Encuentras los siguientes niveles de precisión: Experto en observación de aves #1 error del 0.3% Experto en observación de aves #2 error del 0.5% Persona normal #1 (no es un experto en observación de aves) error del 1.0% Persona normal #2 (no es un experto en observación de aves) error del 1.2%

7. Si tu objetivo es que el “rendimiento a nivel humano” sea un proxy (o estimación) del error de Bayes, ¿cómo definirías el “rendimiento a nivel humano”?
	1. 0.0% (porque es imposible hacerlo mejor que esto)
	2. 0.3% (precisión del experto #1)
	3. 0.4% (promedio de 0.3 y 0.5)
	4. 0.75% (promedio de los cuatro números anteriores)
	**R:** 0.3% 
8. ¿Con cuál de las siguientes afirmaciones estás de acuerdo?
	1. El rendimiento del algoritmo de aprendizaje puede ser mejor que el rendimiento a nivel humano pero nunca puede ser mejor que el error de Bayes.
	2. El rendimiento del algoritmo de aprendizaje nunca puede ser mejor que el rendimiento a nivel humano pero puede ser mejor que el error de Bayes.
	3. El rendimiento del algoritmo de aprendizaje nunca puede ser mejor que el rendimiento a nivel humano ni mejor que el error de Bayes.
	4. El rendimiento del algoritmo de aprendizaje puede ser mejor que el rendimiento a nivel humano y mejor que el error de Bayes.
	**R:** 1
Imaginemos que has creado un algoritmo para reconocer aves en fotografías. Después de muchas pruebas y ajustes, descubres que un equipo de ornitólogos puede identificar las aves en las imágenes con un rendimiento del 0,1% mejor que tu algoritmo. A partir de ese momento, decides que ese nivel de rendimiento debe ser considerado como "rendimiento a nivel humano".

Sin embargo, no te rindes y sigues trabajando en mejorar tu algoritmo. Finalmente, consigues reducir el error en el conjunto de entrenamiento al 2,0% y el error en el conjunto de validación al 2,1%. Es decir, tu algoritmo ya supera el rendimiento humano en esta tarea en particular.

9. Basado en la evidencia que tienes, ¿cuáles de las siguientes cuatro opciones parecen las más prometedoras para probar? (Selecciona dos opciones).
	1. Entrenar un modelo más grande para intentar mejorar en el conjunto de entrenamiento.
	2. Conseguir un conjunto de entrenamiento más grande para reducir la varianza.
	3. Intentar aumentar la regularización
	4. Intentar disminuir la regularización
	**R:** 1,2 y 3
10. También evalúas tu modelo en el conjunto de prueba y encuentras lo siguiente: rendimiento a nivel humano 0,1%, error en el conjunto de entrenamiento 2,0%, error en el conjunto de desarrollo 2,1%, error en el conjunto de prueba 7,0%. ¿Qué significa esto? (Verifique las dos mejores opciones).
	1. Deberías intentar obtener un conjunto de desarrollo más grande.
	2. Te has ajustado demasiado al conjunto de desarrollo.
	3. Deberías obtener un conjunto de prueba más grande.
	4. Te has ajustado insuficientemente al conjunto de desarrollo.
	**R:** 