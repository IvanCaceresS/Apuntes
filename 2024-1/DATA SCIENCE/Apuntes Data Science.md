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