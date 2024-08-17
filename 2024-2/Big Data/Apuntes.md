# Primera Clase 09-08
Correo: nicolas.hidalgo@mail.udp.cl
Presentaciones eligiendo alguno de los papers.
Proyectos, slides y papers se escriben en inglés.

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