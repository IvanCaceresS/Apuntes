# Primera Clase 09-08
Correo: nicolas.hidalgo@mail.udp.cl
Presentaciones eligiendo alguno de los papers.
Proyectos, slides y papers se escriben en inglés.

Article presentation: Nos toca Storage, entonces presentamos 7 octubre. Rúbrica: Evaluacion Presentaciones Articulos.pdf

Para lo del paper: Semana del 9 sept. Se tiene que tener listo que se va a hacer individualmente (La definición del problema relacionado con Big Data, lo que sea) y lo evaluado es el papaer a entregar (Formato IEEE), hay presentaciones voluntarias para guíar el trabajo.

Luego en grupos de 3 se selecciona uno de los trabajos y se continua con ese.
![[Pasted image 20240827144951.png]]
Topics:
- Introduction to big data
- Resources Management
- Storage
- Batch Processing
- Stream Processing
- Adaptative Processing System

- Research oriented
	- Article presentations (De a 3)
	- Problem definition (se hace individual datos)
	- State of the art (de aqui en adelante es en grupo, eligiendo uno de los problemas del grupo)
	- Solution proposal
	- Final proyect: article draft
NF = AP x 0,3 + PD x 0,1 + SA+S x

Condicion aprovacion:
- FP >=4.0
- Asistencia 70%
# Clase 13-08
Paper: https://www.usenix.org/system/files/atc23-song.pdf
- **Abstract**: El abstract debe presentar una contextualización clara del problema abordado en la investigación y una propuesta específica para solucionarlo. Esta propuesta debe estar respaldada por una contribución claramente definida y relevante en el campo de estudio.
- **Introducción**: La introducción debe ofrecer un contexto adecuado que permita al lector comprender la importancia del problema investigado. Además, es crucial que se incluyan citas relevantes que refuercen y justifiquen las ideas presentadas, subrayando la relevancia del estudio.
- **Background o marco teórico**: Es fundamental proporcionar al lector una contextualización exhaustiva en esta sección, de modo que pueda entender completamente los conceptos y teorías clave relacionados con la investigación.
- **State of the Art**: En esta sección se debe cubrir exhaustivamente todo lo relacionado con el problema en cuestión, incluyendo cómo ha sido abordado en investigaciones previas. El objetivo es identificar y destacar las lagunas o brechas en el conocimiento existente que aún no han sido abordadas, lo cual justifica la necesidad del presente estudio.

# Clase 16-08
Paper: https://people.eecs.berkeley.edu/~sylvia/papers/pht.pdf
Prefix Hash Tree An Indexing Data Structure over Distributed Hash Tables
Hacer 3 slides diciendo:
- Problema:
	- El problema principal que aborda el paper es la limitación de las Distributed Hash Tables (DHTs) para soportar consultas más sofisticadas, específicamente **consultas de rango** (range queries). Las DHTs, que son robustas y escalables, están diseñadas para manejar búsquedas exactas de claves (exact match lookups), pero su estructura de hash dificulta la implementación eficiente de consultas de rango. Estas consultas son comunes en muchas aplicaciones, como bases de datos, computación distribuida, y sistemas de computación científica, donde es necesario recuperar todos los objetos dentro de un rango específico de valores.
- Diseño (Lo que se propone):
	- El paper propone una nueva estructura de datos distribuida llamada **Prefix Hash Tree (PHT)**. La PHT es un árbol basado en un trie que se construye sobre una DHT existente utilizando únicamente la interfaz de búsqueda (lookup) de la DHT. Esto significa que:
		- **Eficiencia**: Las actualizaciones en el PHT son logarítmicas dobles en el tamaño del dominio que se está indexando.
		- **Autoorganización**: El PHT se autoorganiza sin necesidad de configuración manual o autoridad centralizada.
		- **Tolerancia a fallos**: El fallo de un nodo en el PHT no afecta la disponibilidad de los datos almacenados en otros nodos.
		- **Compatibilidad**: El PHT puede funcionar sobre cualquier DHT sin necesidad de modificar la estructura o el algoritmo de enrutamiento de la DHT subyacente.
	En resumen, el PHT permite realizar consultas de rango, consultas de proximidad, y consultas de máximos/mínimos, expandiendo así las capacidades de las DHTs de manera eficiente y robusta.
- Experimento:
	- El paper presenta una **evaluación experimental** de la Prefix Hash Tree para validar sus propiedades de eficiencia, escalabilidad, y tolerancia a fallos. Los experimentos demuestran que:
		- **Escalabilidad**: El PHT mantiene su eficiencia incluso a medida que crece el tamaño del dominio y el número de nodos en el sistema.
		- **Tolerancia a fallos**: La estructura puede continuar funcionando correctamente incluso cuando fallan nodos individuales, preservando la integridad de los datos restantes.
		- **Carga equilibrada**: La carga de trabajo se distribuye de manera uniforme entre los nodos, evitando cuellos de botella o sobrecargas en nodos específicos.

En conclusión, los experimentos confirman que el PHT es una solución práctica y efectiva para habilitar consultas más complejas sobre DHTs sin sacrificar las propiedades fundamentales de escalabilidad y robustez que hacen a las DHTs tan útiles en sistemas distribuidos.
# Clase 20-08
¿Que es Big Data?
Las 3 V's
- Volume: the amount of data matters. Data size challenging to store and process (e.g how to index?)
- Velocity: data generation rate and analysis rate (e.g )
- Variety: data heterogeneity because of different data types (e.g text, audio, video) and degree of structure.
# Clase 27-08
## Big data process (ciclo)
1. Acquisition:
	1. Requiere
		1. Seleccionar datos
		2. Filtrado de datos
		3. Generar metadata
		4. Gestionar la provenencia de la data
2. Extraction
	1. Requiere:
		1. Transformación
		2. Normalización
		3. Limpieza
		4. Agregación
		5. Manejo de errores
3. Integration
	1. Requiere
		1. Estandarización
		2. Eliminación de conflictos
		3. Reconciliar datos de fuentes diferentes
		4. Mapear esos datos a estructuras que permitan manejarla
4. Analysis
	1. Requiere
		1. Exploración de los datos
		2. Minería de los datos
		3. Aplicación de técnicas de machine learning
		4. Visualización
5. Interpretation
	1. Requiere
		1. Conocimiento del dominio
		2. Conocimiento de la provenencia
		3. Identificación de patrones de interés
		4. Flexibilidad del proceso
6. Decision
## Best Practices
- Alineación de los datos con el proposito del proyecto.
- Alinear las cosas estructuradas con las no estructuradas.
- Alinear con el Cloud
# Clase 30-08
## Resource Management
- Outline
	- Motivation (Por qué RM)
			- Big data evolution: increase of data is generating resource management issues
			- Offline to online
		- Posible solution
			- Run multiple frameworks on a single cluster
			- Partición de maquinas de manera estática.
			- No es muy eficiente ya que hay veces que la carga puede variar, funcionaría si las tareas son homogeneas siempre. Eso no ocurre.
	- Apache Mesos (Manejador de recursos)
		- Poder desplegar servicios de gran escala.
		- Generar una capa de software que permite abstraerse de las maquinas.
		- Las maquinas tendrán tareas de todos.
		- Metas de Apache mesos
			- Ser un sistema aprueba de fallas.
		- Cada framework tiene unos trabajos y esos trabajos son un conjunto de tareas
		- Mesos trabaja a un nivel de grado fijo, poder administrar las tareas mediante monitorio de las tareas y detectar fallos. Si una tarea está pegada mata la tarea y libera el recurso, asignandoselo a otro framework que lo requiere.
		- Arquitectura
			- Maestro-esclavo
			- El esclavo publica los recursos disponibles al maestro
			- El maestro ofrece los recursos a los frameworks
			- Punto unico de falla si muere el maestro.
			- Es centralizado para evitar el costo que implicaría tener una red distribuida de maestros porque la comunicación entre ellos sería muy costosa
			- El maestro al tener muy poca carga es más facil escalarlo, ya que el maestro funciona como un proxy.
			- Ya que cada planificador (Hadoop scheduler) planifica su framework no hay un vision general de los recursos para optimizar la carga de los recursos.
			- Si se cae un maestro, se elige a otra maquina para realizar la tarea de maestro
	- Apache YARN (Manejador de recursos)
		- Manejo de localidad
		- Alta optimización utilización de recursos
		- Es confiable
		- Es escalable
	- MESOS vs YARN
		- Slide 43 de la ppt
# Clase 03-09
## Presentación de resource management
SLA-Aware Energy-Efficient Scheduling Scheme for Hadoop YARN
- Resumen(lineas): Es un esquema para mejorar el manejo de recursos..
	- Conexto: Optimizar recursos tipicos de computación pero con un gran enfoque en la energía. 
		- SLA: un acuerdo que tiene el proveedor de la app con el cliente, para ver lo que se espera del rendimiento de la app. Limites de tiempos (Deadlines). 
	- YARN, componentes
		- Resource manager
		- NodeManager
		- ApplicationMaster
		- Container
	- Problematica:
		- Asignación generalizada y uniforme de los recursos, no prioriza
		- Eficiencia energética no contemplada
		- Impacto en rendimiento ya que las apps requieren tiempos significativos
	- Propuesta:
		- Caracterizar el rendimiento de las aplicaciones, adoptando el peor caso posible
		- Energía, diseñar un esquema DVFS. Toma la diferencia entre el tiempo real con el tiempo teorico de lo que demora la tarea.
		- Obtener información de la tarea para un posterior uso en el calendarizador.
	- Estructura:
		- Job Profiler: le llega el trabajo y debe obtener la info de entrada, deadline, paralelismo,etc. Debe poder extraer las metricas mas importantes de cada fase: initialize, map, shuffle y reduce.
		- Parallelism Estimator: calcula el grado minimo de paralelismo para enviar el resultado al calendarizador
		- Calendarizador: asigna tareas de acuerdo a los resultado previos. usa el algoritmo EDF (Early Deadline First)
		- Performance monitor: Obtiene todos los trabajos en el momento y los divide en 3: Los terminados, los que aun no inician, y los en trabajo actual.
		- Frequency Estimator: Ajusta la frecuencia dentro del procesador con DVFS para cada app.
	- La solucion que propone el paper es eficiente y reduce el consumo energetico. ya que permite cumplir con los deadlines con un uso eficiente de la energía y recursos.
- 2 Preguntas:
	- 1. Como funciona el paralelismo de las aplicación, se utilizan varios nucleos para asignar cada tarea a cada nucleo?: Cada aplicacion tiene el performance monitor y frequency estimator. Por lo que cada procesador puede paralelisar varias tareas segun la frecuencia definida para la tarea.
	- 2. 
- Nota sugerida: 7.0
- RESUMEN: Este esquema propone una mejora en la gestión de recursos en entornos de computación distribuidos, enfocándose particularmente en la eficiencia energética sin comprometer los acuerdos de nivel de servicio (SLA). El esquema está diseñado para optimizar el uso de recursos, asegurando que las aplicaciones cumplan con sus plazos establecidos mientras se minimiza el consumo de energía.
- Pregunta 1: **¿Cómo funciona el paralelismo de las aplicaciones en este esquema?**
	- **Respuesta**: Cada aplicación utiliza el Performance Monitor y el Frequency Estimator, lo que permite que el procesador paralelice varias tareas, ajustando la frecuencia de cada tarea según sea necesario.
- Pregunta 2: **¿Qué impacto tendría este esquema en la latencia de las aplicaciones?**
- Nota sugerida: 7.0
# Clase 11-10
Presentación phdfs
- contexto
	- auge de IA
	- Deeplearning
	- Ayuda a mejorara en los archivos pequeños a hdfs
- Problemas de hdfs
	- Complicado manejar archivos pequeños.
	- Deeplearning necesita manejar archivos pequeños.
	- Sobrecarga del namenode.
	- Ya que necesita escribir y leer multiples veces realentiza el rendimiento.
- Motivación
	- HDFS es el mas popular de almacenamiento en la nube.
	- La presicion de un modelo de deeplearning mejora a medida aumenta la cantidad de datasets.
	- file aggregation system, PILE.
- Propuesta
	- PHDFS
		- archivos pequeños agrupados en piles
		- para leer un batch el proceso debe completarse con solo una solicitud
	- Arquitectura
		- generation module
		- management module
		- storage module
- Experimentos y resultados
	- rendimiento lectura y escritura: phdfs es el ganador
	- impacto en rendimiento dependiendo de los tamaños de los datasets: 
- preguntas: 
- nota: 6,9

presentación CPHARIF
- Reducir costos y gran rendimiento
- Experimento:
	- Benchmark
	- 3 replicaciones por cada archivo
- harif es optimo en relacion a otros modelos que usa hdfs como pipeline, parallel, laz