
# CLASE 06-03-25
- Buscar siempre la mejor solución a un problema, siempre va a encontrar la mejor solución.
- Se utilizan árboles (la estructura) para buscar de manera ordenada y sistemática
	- Ejemplos: Sin información (backtracking cronológica - Fuerza bruta), con información (mirar hacia el pasado, mirar hacia el futuro)
- ¿Qué es una metaheurística? 
	- Antes necesitamos saber **qué es una heurística**: 
		- Es una función muy barata, y evalua las posibles decisiones que puedo tomar.
		- No usa aprendizaje, es la foto del momento.
		- Están hechas para un problema en particular.
	- Meta: “Más allá” (de nivel superior), heurística: “encontrar” 
	- Por tanto las metaheurísticas son técnicas de propósito general no como las heurísticas.
	- Pertenecen a un grupo de técnicas llamadas incompletas.
- NP-HARD: Problemas de computacion muy dificiles que no tienen de momento una solución(Algoritmo) que lo resuelva en un tiempo no exponencial, aquí acudiría a una metaheurística.
- Tipo de problemas que abordaremos
	- Problemas Combinatoriales: Optimización y satisfacción con restricciones. 
	- Problemas Continuos: Lo mismo a lo anterior.
	- Sin restricciones (recordar funciones de costo “J” en machine learning.
- Algo que queda en el aire… 
	- ¿Qué queremos resolver? 
	- ¿Cuándo aplicar cada técnica? 
	- Necesitamos una metodología: 
		- Conocer el problema 
		- Revisión del estado del arte 
		- Diseñar una técnica 
		- Implementar 
		- Validar (experimentos) 
		- Concluir

FECHAS  (Se entregan o rinden)
- Tarea 1 -> Semana 24 marzo
- Tarea 2 y Control 1-> Semana 14 abril
- Tarea 3 -> Semana 19 mayo
- Tarea 4 y Control 2-> Semana 16 junio

# Clase 10-03-25
Exactos/Completas -> Mejor solución
Metaheurísticas/Incompletas - Buena solución

Objetivos
- “Recordar” cómo se realiza modelamiento. 
- Estudiar los tipos de problemas que veremos durante el curso. 
- Conocer las técnicas empleadas para resolver instancias (benchmarks) de estos problemas.
¿Qué define el modelo de un problema?
- Una o más variables 
- Dominios de cada variable, pueden ser discretos o continuos. 
- 0, 1 o más restricciones. 
- 0, 1 o más funciones objetivo. (Si puedo comparar las soluciones es porque tiene al menos una función objetivo)
- Ejemplo: Un estudiante de la UDP desea diseñar un envase de lata para vender jugos en base a maqui. Supongamos que la lata debe tener forma cilíndrica, en donde la superficie deberá ser la menor posible, pero el volumen total de la lata deberá ser de 128 ml.
	- Variables: Altura (h), radio (r)
	- Dominios: Numeros positivos h y r >0
	- Función objetivo: Minimizar la superficie. 2pirh+2pir^2
	- Restricciones: hpir^2 = 128ml
## Problema de optimización con restricciones (COP)
- Se pueden tener restricciones de 2 tipos:
	- Restricciones de desigualdad
	- Restricciones de igualdad
- Se pueden tener muchas restricciones (m) y tambien muchas variables (n)
- g(x) hace referencia a las de desigualdad
- h(x) hace referencia a las de igualdad
- El objetivo es buscar valores en D (Dominio) que satisfagan las restricciones y que el valor de f sea máximo o mínimo (Según sea el caso)
## Problema de satisfacción con restricciones (CSP)
- Exactamente lo mismo a lo anterior pero ya no tengo funcion objetivo, las soluciones no se puede comparar.
- El objetivo es encontrar una o todas las soluciones al problema.
## Soluciones y espacio de búsqueda
- **Solución factible**: Corresponde a aquella solución en donde, una vez asignado un valor a cada variable a partir del dominio, cumple con todas las restricciones del problema. 
- **Solución infactible:** Corresponde a aquella solución que no satisface una o más restricciones del problema 
- Una vez que tenemos una solución factible (en caso de existir), si estamos frente a un problema de optimización, la evaluamos utilizando la función objetivo (medir calidad de la solución). Si es un problema de minimización (resp. maximización), tratamos de buscar el menor (resp. mayor) valor de dicha función. 
- Si es un problema de satisfacción, los limitaremos a encontrar soluciones, pues no las podemos comparar 
- **Espacio de búsqueda**: Corresponde a la región en donde buscaremos las soluciones.
## Dificultad de los problemas 
- **Problemas Р**: Problemas que puedan ser resueltos en tiempo polinomial por una máquina de Turing determinista (todo algoritmo computacional puede ser emulado a través de una máquina de Turing). 
- **Problemas ΝР**: No se conoce algoritmo que los resuelva en tiempo polinomial, pero dada una solución se puede verificar en tiempo polinomial que esta es correcta. 
- En este curso abordaremos problemas del tipo ΝР-Completo, que son los más difíciles dentro de lo que es la categoría anterior
## ¿Cómo resolvemos este tipo de problemas?
- Técnicas exactas o completas
	- Con árboles
	- backtracking (no usa ningún tipo de información, me equivoco voy un paso para atrás)
	- look-back (usan experiencia previa, para ver donde es el origen del error)
	- look-ahead(dado algo que hago ahora veo el impacto en el futuro)
- Técnicas de aproximación o incompletas
	- Búsqueda local
	- MH de trayectoria
	- Algoritmos evolutivos (MH población)
	- Algoritmos de iteligencia de enjambre (MH de enjambre)
## EJEMPLO (ACTIVIDAD EN CLASE)
Suponga que el profe quiere viajar a Iquique con una maleta de bodega. Según la normativa del aeropuerto, la maleta (con su contenido) puede pesar a lo más 22 kg. Suponga que el profe debe elegir entre 1…n artículos de ropa y 1…m videojuegos (cada pieza de ropa/juego tiene un peso distinto, todos conocidos). Además, el profe quiere llevar a lo más 6 juegos y a lo menos 20 artículos de ropa (aunque en la realidad, el profe llevaría más juegos que ropa 😆). Cada juego/artículo tiene una cierta importancia (conocida) para el profe (distintos entre ellos), en donde si g_i > g_j implica que la importancia del juego/artículo i tiene mayor importancia para el profesor.
	•	Construir el modelo: definir variables, dominios, restricciones, funciones objetivo.
	•	¿Cuál es el espacio de búsqueda?
	
- Variables:
	- Juegos J_i
	- Ropa R_j
- Parámetros:
	- n, cantidad juegos
	- m, cantidad ropa
	- peso juego i (PJ_i)
	- peso ropa j (PR_i)
	- peso maximo ropa (22kg)
	- importancia juego i (g_i)
	- importancia ropa j (g_j)
- Dominios:
	- R_i y J_j pertenece [0,1]. Con i y j enteros.
- Restricciones:
	- sum(J_j) < =6
	- sum(R_i) > = 20
	- sum(J_ixPJ_i) + sum(R_jxPR_j) < = 22kg
- Funciones objetivos:
	- max sum(g_ixR_i) + sum(g_jxJ_j) 
	- maximizar cantidad de juegos/ropa importantes
- Espacio de búsqueda:
	- 2^(n+m), n cantidad de ropa, m cantidad de juegos. 2^n x 2^m 
# Clase 13-03-25
Con esta materia se puede resolver la pregunta 2 de la tarea, con la clase pasada se puede resolver la pregunta 1.

- Backtracking
	- CSP: N-Reinas
		- Posicionar en un tablero de N X N, N reinas de tal manera que no se ataquen entre ellas.
			- Considerando un tablero de 4 x 4, con 4 reinas
			- Definir variables y dominios
				- Variables: Ubicaciones
				- Dominio: 16
			- Definir restricciones
				- Q_i!=Q_j, con i y j pertenecientes a las columnas, (horizontal)
				- lo mismo pero en vertical
			- ¿Cuál es el espacio de búsqueda?: 16x16x16x16 = 16^4. Si se analiza por columna, sabiendo que no puede haber mas de una reina en una misma columna, el espacio de busqueda se reduce a 4x4x4x4 = 4^4
	- Proceso de búsqueda: 
		- Búsqueda completa
			- Se explora el espacio de búsqueda del problema, de manera exhaustiva y ordenada
			- El proceso termina cuando:
				- Se encuentra una sokucion o todas(CSP), la óptima (COP)
				- Se demuestra que no hay solución
				- Se agotan los recursos computacionales (RAM)
				- Hay timeout
		- Árbol
			- Elementos presentes:
				- Estado inicial: nodo raíz, ejemplo: tablero vacío sin reinas
				- Estado : Nodo que representa la “Foto” del momento de la búsqueda. Por ejemplo, ubicación de las reinas. Los nodos no-hoja corresponden a soluciones incompletas. 
				- Acciones: A partir de un estado, que conjunto (finito) de acciones podemos realizar. Estas podrían tener un costo asociado. Generan nodos hijo. 
				- Nodos hojas: si cumplen con las restricciones del problema, serían soluciones
			- Backtracking cronológico (BT)
				- Se realiza en profundidad 
				- En cada rama del árbol hacemos una asignación, es decir le asignamos un valor a una variable o hacemos una acción dependiendo del problema. 
				- Cada vez que hacemos una asignación debemos chequear si esta es consistente (Que cumpla con todas las restricciones del problema). Esto quiere decir que todas las otras variables tienen al menos un valor en su dominio que soporta dicha asignación.
			- Backjumping 
				- ¿Hay algún problema con lo anterior? 
					- Si, como se puede ver en el ejemplo, la primera asignación es incompatible con todas las decisiones posteriores. 
					- Generamos nodos innecesarios en la búsqueda. Esto es conocido como Thrashing. 
				- Una solución: Técnicas Look-Back 
					- Hacer saltos hacia atrás más eficientes (Backjumping) 
					- Salta a una variable responsable del bloqueo. 
					- No enumera algunas asignaciones parciales que no conducen a una posible solución. 
					- Reduce el Thrashing. 
					- IMPORTANTE: Sigue siendo completa la búsqueda
			- Backjumping dirigido por conflictos (CBJ) 
				- Salta a la variable responsable del bloqueo 
				- No enumera algunas asignaciones parciales que no conducen a la solución. 
				- Para cada variable, guardar el conjunto de conflictos Conf(xi ). (Se gasta un poco más de memoria)
				- Por cada valor erróneo, registrar en Conf(xi ) la variable más prematuramente instanciada (o todas las variables asociadas a la restricción donde esté la más prematuramente instanciada) y en conflicto con el intento actual de instanciación. 
				- Cuando no queden valores por intentar, el conjunto entrega las causas del problema y el punto de regreso será la variable más reciente en el conjunto de conflictos