
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
				- ![[Pasted image 20250313121452.png]]
				- Hemos llegado a un camino sin salida (deadend). Esto debido a que existe un vacío de dominio (domain wipe-out) 
				- Dado que la última variable que está en conflicto es X4 , entonces volvemos a ese punto del árbol. 
				- No se pierden soluciones en este proceso, es decir, la técnica sigue siendo completa.
- EJERCICIO
	- Supongamos que deseamos pintar un automóvil, cuyas partes son: Parachoques, Techo, Alerones, Carrocería, Puertas, Capot. Para esto tenemos los siguientes colores: Blanco, Rosado, Rojo, Negro. Sea A\B, A más claro que B, entonces BLANCO\ROSADO\ROJO\NEGRO
	- Considere las sig. restricciones:
		- El parachoques debe ser blanco
		- El techo debe ser rojo
		- Los alerones no pueden ser ni blancos ni negros
		- La carrocería, las puertas y el capot deben ser del mismo color
		- El parachoques, el techo y los alerones deben ser más claros que la carrocería
	- Utilice el algoritmo BT para encontrar (en caso de existir) una solucion
# Clase 17-03-25
## Forward checking
- Pertenece a un grupo de técnicas clasificadas como Técnicas Look-Ahead. 
- Se basa en la idea de mirar hacia adelante en el árbol de búsqueda, para ver si al hacer una instanciación hace imposible asignarle un valor a otra variable no instanciada. 
- Veamos cómo se aplicaría usando el ejemplo de las N-Reinas…
- Disminuye el trashing
- A pesar de que podrían existir menos nodos en el árbol, se podrían eventualmente realizar más chequeos, en comparación a las otras técnicas estudiadas. 
- Continuar con el ejemplo…
- ¿Es siempre FC mejor que eun BT simple? depende del tiempo
## MFC -Minimal Forward Checking-(Variante de forward checking)
- Es conocido también por “Lazy forward checking” 
- Revisa hacia adelante al igual que FC, sin embargo al encontrar un valor asignación factible para una variable pasa inmediatamente a la otra. 
- De esta manera, eventualmente, podríamos detectar vacíos de dominio (al igual que FC), pero sin realizar tantos chequeos. 
- Sigue siendo completo
## Orden de instanciación
- El orden en el cual son instanciadas las variables afecta el tamaño del árbol de búsqueda → desempeño del algoritmo de búsqueda. 
- Heurísticas de selección de variable: Procedimiento generalmente no costoso computacionalmente, el cual tiene por objetivo seleccionar la siguiente variable a ser instanciada. Generalmente son tecnicas offline, y en este curso se centrará en técnicas offline y no online.
- En general están basadas en la premisa fail-first “Para tener éxito, se debe intentar primero en donde más probablemente se fallará”
## Heurísticas de selección de variable 
- Generalmente entre más información utilicemos, mejor funcionará—> más costo de CPU. 
- Algunos ejemplos (generales): 
	- Dom: Se selecciona la de menor dominio. 
	- Dom+Deg: Lo mismo que dom, sin embargo, si hay empate se elige aquella que aparece en más restricciones. 
	- Dom/Deg: Se selecciona aquella que minimiza el cuociente dom/deg. 
- Dependiente del problema 
- Su propuesta…
## Técnicas de preproceso: Consistencia de arcos y nodos
- Antes de ver esto, es necesario saber ciertas propiedades de CSP/COP (se pueden demostrar, pero no lo veremos en este curso): 
	- Todo CSP/COP puede ser transformado a un conjunto de restricciones binarias y unarias. 
	- Todo CSP/COP con restricciones binarias y unarias puede ser modelado a través de un grafo. 
- Con lo anterior, podemos aplicar técnicas de preproceso para CSP/COP: Nodo consistencia, Arco consistencia, Camino consistencia.

## Actividad
Dado el siguiente CSP:
X_1<X_2
X_2<X_3
X_3<X_1
X_4<X_2
X_1=X_4
X_1<X_2<X_3
X_3<X_1
x_1<x_3<x_1
con dominios D_i={1,2,3,4}
- Utilice el algoritmo Forward Checking para buscar todas las soluciones al problema. Utilice el orden X_1,X_2,X_3,X_4. ¿Existirá un orden de instanciación/asignación que permita reducir el árbol? si, X_3,X_2,X_1,X_4
	X_1 = {1,2,3,4}
	X_2 = {2,3,4}
	X_3 = {1}
	X_4 = {1,2,3,4}
- ¿Existirá un orden de instanciación/asignación que permita encontrar más soluciones que la propuesta por ud.? No, ya que al ser un algoritmo completo no importa el orden, debe encontrar todas las soluciones

# Clase 24-03-25
- Algoritmos Greedy: Deterministas y Estocásticos.
- Greedy randomized adaptive search procedure (GRASP)
## Técnicas de resolución
- Búsqueda aproximada (técnicas incompletas): 
	- Normalmente estocásticas. 
	- Entregan la mejor solución encontrada sin garantía de optimalidad. 
	- Capaces de manejarse en grandes espacios de búsqueda. 
	- No es necesario conocimiento a priori del problema.
- ![[Pasted image 20250324113842.png]]
- **Heurísticas:**
	- Derivado del griego heuriskein: encontrar, descubrir
	- No garantizan encontrar la mejor solución
	- Yo la diseño para el problema
	- Se requiere de alguien que sepa como funciona el problema y que sepa valorar que aspectos son importantes en el problema
	- El objetivo es resolver un problema rápidamente
- **Metaheurísticas:**
	- Es una combinación de heurísticas, es una heurística pero más general. Usa heurísticas para buscar/construir soluciones.
	- No son diseñadas para un problema especifico
	- No requiere de mucha información del problema a resolver.
	- **Problema:** requieren de tiempo para poder ajustar su(s) parámetro(s).
- Dos tipos de técnicas incompletas:
	- Constructivas:
		- No requieren de una solución inicial.
		- Van construyendo una solución: asignando iterativamente valores a las variables del problema.
		- Manejan soluciones parciales
	- Perturbadores
		- Requiere de una o varias soluciones iniciales
		- Modifican una solución: Aplicando un movimiento o función de vecindario
		- Manejan soluciones completas.
- Heurísticas constructivas (Greddy o Voraces):
	- Son reglas locales para seleccionar los valores de las variables del problema
	- Utilizan la información del problema para definir estas reglas.
	- El objetivo es encontrar soluciones al problema de manera rápida.
	- **¿Qué necesitamos para definir un Greedy?** 
		- Representación: Interpretación de la estructura de la solución. 
		- Función de evaluación o miope: Función para evaluar la acción a realizar. 
	- Greedy determinista vs estocástico: Determinista llega siempre a la misma solución. Estocástico…no. 
	- Greedy estocástico: en vez de movernos a la mejor solución, asignamos una probabilidad a las alternativas a partir de la función miope.
	- **GRASP: Greedy Randomized Adaptive Search Procedure.**
		- Metaheurística la cual consiste en dos pasos: un greedy aleatorio y un algoritmo de búsqueda local. 
		- En vez de elegir la mejor alternativa con la función miope, se hace un ranking con las alternativas posibles y le es asignado una probabilidad a cada una de ellas. De esta forma tendremos variabilidad en las soluciones. 
		- Una vez construida la solución intentamos mejorarla utilizando búsqueda local. 
		- Existen muchas otras variantes: agregar ruido a las soluciones, a partir de soluciones parciales aplicar búsqueda local, entre otras. 
		- También se podría generar una población (conjunto de soluciones) y utilizarla como soluciones iniciales en un algoritmo de este tipo.
# Clase 27-03-25
## Metaheurísticas
- No garantizan el óptimo global
- Pueden encontrar soluciones aceptables en tiempos razonables
- Cuando diseñamos una metaheuristica nos encontramos con 2 criterios contradictorios:
	- Por un lado tenemos la **exploración**: Deben buscarse zonas prometedoras del espacio de búsqueda. También se le conoce como **diversificación**. 
	- También tenemos la **explotación**: Centrar la búsqueda dentro de una región en particular del espacio de búsqueda. También se le conoce como **intensificación**.
	- De manera general lo mejor es primero explorar y luego explotar
- Hill Climbing
	- Tecnica de búsqueda local (Solo explota)
	- De solución única que va cambiando en cada iteración
	- Es pertubativo, es decir parto de una solución inicial (factible o infactible) y esa va mejorando en el tiempo, esto lo hace mediante **operadores de movimiento** buscando que valor de la función de dicha solución sea mejor que la solución actual mediante cambios minimos a la solución, esto genera un vecinadario (conjunto de soluciones cercanas a la actual) luego me muevo a la mejor en base a la funcion objetivo y que cumpla con las restricciones.
	- Como manejar las coluciones infactibles? Reparar o penalizar (reparar es transformarmar la infactible a factible y la penalización le quita o agrega cosas a la funcion objetivo para cuando la solucion es infactible, agrega cuando es minimizar y quita cuando es maximizar.)
- Hill Climbing Mejor-Mejora
	-  Inicialización: Crear una solución a partir de algún criterio heurístico o aleatorio. 
	- Mientras no se cumpla el criterio de parada (no hay mejora, tiempo, iteraciones,...) 
		- Generar vecindario a partir del movimiento elegido y conservar la mejor solución del vecindario como solución actual. 
	- Mostrar solución + valor f.o + tiempo
- Hill Climbing Alguna-Mejora
	-  En algunas ocasiones nos encontraremos con problemas en que el vecindario de una solución es muy grande. 
	- En tal caso, solo generamos el vecindario hasta el punto de encontrar la primera solución que mejore la actual, en vez de generar el vecindario completo
- Hill Climbing con restart
	- Un gran problema de este algoritmo es que puede estancarse en óptimos locales. 
	- La idea es recomenzar con el algoritmo con una nueva solución cuando este se quede estancado. 
	- Desventaja del Hill-Climbing con restart: Pérdida de información valiosa durante la búsqueda. 
	- ¿Qué pasa si utilizo Hill-Climbing con restart, creando la solución inicial con un greedy determinista? Siempre llegará a lo mismo, ya que no es aleatorio.
# Clase 31-03-25
## Tabu Search
- Previene ciclos de corta duración.
- Elementos claves de Tabu Search
	- Operador de movimiento
	- Solución inicial
	- La representación de la solución
	- Función de evaluacion (F.O)
	- Lista tabú
	- Criterio de aspiración: Libera la búsqueda por medio de una función de memoria a corto plazo (olvido estratégico)
- La lista tabú almacena movimientos prohibidos, en cada iteración se elige el movimiento factible no-tabú. (memoria a corto plazo). Es del tipo FIFO
- Una lista tabu muy pequeña, estoy explotando mucho más
- Una lista tabú muy grande, estoy explorando mucho más
- El tamaño de la lista depende del problema, se puede definir mediante pruebas evaluando la calidad de la solución con un conjunto de pruebas (benchmarks)
- El algoritmo para de iterar segun el criterio definido, por ej: el tiempo transcurrido o la solución no ha mejorado en cierta cantidad de iteraciones, etc.

EJERCICIO
La penalizacion será de F.O+nx20 donde n es unidades de falla en restricciones.
- (x1,x4,x5,x6) -> F.O=16, infactible->F.0=56, Lista Tabu={} 
	Vecinadario (Remplazando x1 por todas las demas opciones)
	(x2,x4,x5,x6)-> F.O=19, infactible-> 39
	(x3,x4,x5,x6)-> F.O=28, factible 
	(x7,x4,x5,x6)-> F.O=27, factible->1ERA MEJOR
- (x7,x4,x5,x6)-> F.O=27, factible, Lista Tabu={(x1,x7)} 
	Vecinadario (Remplazando x4 por todas las demas opciones)
	(x7,x1,x5,x6)-> F.O=26, infactible->46
	(x7,x2,x5,x6)-> F.O=29, infactible-> 49
	(x7,x3,x5,x6)-> F.O=38, factible -> No es mejor que la mejor pero nos movemos
- (x7,x3,x5,x6)-> F.O=38, factible, Lista Tabu={(x1,x7),(x4,x3)} 
	Vecinadario (Remplazando x5 por todas las demas opciones)
	(x7,x3,x1,x6)-> F.O=44, factible
	(x7,x3,x2,x6)-> F.O=47, infactible->67
	(x7,x3,x4,x6)-> F.O=40, factible -> No es mejor que la mejor pero nos movemos
- (x7,x3,x4,x6)-> F.O=40, factible, Lista Tabu={(x4,x3),(x5,x4)}
	Vecinadario (Remplazando x6 por todas las demas opciones)
	(x7,x3,x4,x1)-> F.O=38, factible
	(x7,x3,x4,x2)-> F.O=41,factible
	(x7,x3,x4,x5)-> F.O=32, factible
Luego de 4 iteraciones la mejor solucion es:
(x7,x4,x5,x6)-> F.O=27, factible->1ERA MEJOR

# Clase 03-04-25
## Simulated Annealing
- Modelamiento del proceso de los cambios energéticos en un sistema de partículas conforme decrece la temperatura, hasta que converge a un estado estable (congelado).
- Incorpora una estrategia explícita para impedir óptimos locales.
- Tiene una componente probabilistica
### Idea

- Permitir movimientos a soluciones que empeoren la F.O, de forma de poder escapar de los óptimos locales
- Permitir movimientos que empeoren la calidad de la F.O de acuerdo a una probabilidad asociada a la temperatura del sistema.
- Parto con una temperatura alta y a medida que hay más iteraciones la temperatura baja, de esta manera se puede explorar para luego explotar
- Mientras que las soluciones que mejoran la función objetivo siempre son aceptadas, las soluciones que la empeoran son aceptadas con mayor probabilidad si la temperatura es más alta.
## Probabilidad de aceptación y temperatura
- De manera clásica, la probabilidad de acepetación sigue la distribución de Boltzmann y solo se aplica cuando la nueva solución es peor que la actual, si la nueva es mejor no aplica la probabilidad ya que solo te mueves.
- La temperatura es un parámetro y determina la probabilidad de aceptación de soluciones que no mejoran la solución actual.
## Ingredientes para el SA
- Ingredientes de HC (representación, evaluación, operadores de vecindario) 
- Función de probabilidad de aceptación (Boltzmann) 
- Temperatura inicial y final 
- Proceso de enfriamiento: Esto es clave para la eficiencia y efectividad del algoritmo.
# Clase 07-04-25
## Algoritmos de trayectoria
- Iterated Local Search (ILS)
	- Dada una solución s’, se aplica una perturbación (random-walk) o pequeño cambio. 
	- Luego, a partir de dicha nueva solución, se aplica una búsqueda local, es decir, con operadores de movimiento buscar en la vecindad por mejores soluciones. Con esto llegamos a s’’ 
	- Si s’’ cumple con ciertos criterios (por ejemplo es “mejor” que s’), entonces, será nuestra nueva solución y repetimos el proceso, si no, volvemos a s’. 
	- La clave está en la perturbación: Si es pequeña probablemente no mejore mucho, si es muy grande será muy aleatoria la búsqueda.
- Large Neighbourhood Search (LNS)
	- Utiliza dos métodos: destroy y repair. 
	- El método destroy destruye parte de la solución (estocásticamente), mientras el método repair reconstruye la parte destruida. Dicho esto, el vecindario es definido como las soluciones a las cuales se puede llegar a partir de dicha nueva (incompleta) configuración. 
	- Para la reparación puede ser utilizado un método heurístico.
# Tarea 2
- Son 2 casos, 1 con una pista y el otro con 2 pistas. Se hace todo para 1 pista, y luego todo para 2 pistas.
- El costo asociado por diferencia de tiempo respecto a preferente son 1 unidad de costo por cada minuto de tiempo.
- El componente restart en el grasp, no se debe hacer solo una unica vez, sino que se haga varias veces para ver como afecta ese reinicio en la solución final. La cantidad de restart debe definirse mediante pruebas, para ver que valor da mejores resultados.
- En tabu y en SA, las 5 variaciones pueden ser 5 variaciones del tamaño de la lista con saltos grandes, y en SA la temperatura con variaciones notorias.
- No es item necesario el modelamiento pero es util para una breve explicación, no es requerido.


# Clase 12-05-25

## Repaso Clase 11 y 12

### Metaheurísticas Basadas en Poblaciones (MH-P)

Hasta ahora, hemos explorado metaheurísticas que mejoran iterativamente una única solución, como Hill-Climbing (HC), Tabu Search (TS), y Simulated Annealing (SA). Ahora nos enfocamos en técnicas que trabajan con un conjunto o **población de soluciones** simultáneamente. Estas pertenecen en su mayoría a la categoría estocástica y suelen tener parámetros que ajustar.

**Conceptos Comunes de MH-P:**
* Comienzan con una **población inicial** de soluciones. La diversidad en esta población es crucial para evitar la convergencia prematura. 
* Iterativamente, se genera un nuevo grupo de individuos y se actualiza la población actual. 
* La generación y reemplazo pueden o no involucrar memoria (recordar soluciones previas). 
* Muchas de estas técnicas se inspiran en procesos naturales. 

**Plantilla General de una Metaheurística Basada en Poblaciones:**
1.  $P = P_0$; /* Generación de la población inicial */ 
2.  $t = 0$;
3.  **Repeat**
4.  Generar ($P'_t$); /* Generación de una nueva población */ 
5.  $P_{t+1} = \text{Select-Population}(P_t \cup P'_t)$; /* Seleccionar la nueva población */ 
6.  $t = t+1$;
7.  **Until** Criterio de parada satisfecho 
8.  **Output**: Mejor(es) solución(es) encontrada(s). 

---

### Algoritmos Evolutivos: Algoritmos Genéticos (GA)

Los Algoritmos Genéticos (GA) son un tipo de algoritmo evolutivo inspirado en la teoría de la evolución de Darwin: los individuos mejor adaptados al medio ambiente tienen más posibilidades de sobrevivir y reproducirse, transmitiendo sus características genéticas. 

**Componentes Clave de un GA:**

1.  **Representación:** 
    * **Gen:** Unidad básica de información (e.g., un bit, un número).
    * **Cromosoma (Individuo):** Conjunto de genes que representa una solución al problema.
    * **Población:** Conjunto de cromosomas (individuos).

2.  **Función de Fitness:** 
    * Mide qué tan "apta" es una solución (individuo). 
    * Generalmente es la función objetivo del problema. 
    * La probabilidad de selección para reproducción se basa en este valor. 
    * Manejo de restricciones: Se debe decidir cómo tratar a individuos que no cumplen restricciones (penalizar fitness, reparar, descartar). 

3.  **Estrategias de Selección (Elección de Padres):**
    * **Ruleta (Roulette Wheel Selection):** 
        * A cada individuo se le asigna una probabilidad de selección proporcional a su fitness. 
        * Si se está maximizando, la probabilidad de selección $p_i$ para el individuo $i$ con fitness $f_i$ es $p_i = f_i / (\sum f_j)$. 
        * Puede causar convergencia prematura si individuos excepcionales dominan al inicio. 
    * **Torneo (Tournament Selection):** 
        * Se seleccionan aleatoriamente K individuos de la población (tamaño del torneo K). 
        * El individuo con el mejor fitness dentro de ese grupo es elegido como padre. 
        * Se repite T veces si se necesitan T padres. 

4.  **Operadores Genéticos:**
    * **Cruzamiento (Crossover):** 
        * Operador binario que combina información de dos padres para generar uno o más hijos, heredando características. 
        * **Cruzamiento en 1-Punto:** Se elige un punto de corte aleatorio en los cromosomas padres. Los segmentos se intercambian para formar dos hijos. 
        * **Cruzamiento en 2-Puntos:** Se eligen dos puntos de corte. El material genético entre los dos puntos se intercambia. 
        * **Cruzamiento Uniforme:** Para cada gen, se decide (usualmente con una probabilidad de 0.5) de cuál padre heredará el hijo ese gen. 
    * **Mutación:** 
        * Operador unario que introduce variabilidad alterando aleatoriamente uno o más genes de un individuo. 
        * La probabilidad de mutación ($p_m$) suele ser baja (e.g., $p_m \in [0.01, 0.05]$). 
        * Ayuda a escapar de óptimos locales y a mantener la diversidad.
        * Ejemplo en dominio binario: cambiar un bit (0 a 1 o 1 a 0). 
        * Ejemplo en TSP: intercambiar dos ciudades en la ruta (swap). 

5.  **Estrategias de Reemplazo (Selección de Sobrevivientes):** 
    * Determina qué individuos formarán la siguiente generación, manteniendo el tamaño de la población constante. 
    * **Reemplazo Generacional:** Todos los padres son reemplazados por los hijos. 
    * **Elitismo:** Un porcentaje de los mejores individuos de la población actual se mantiene directamente en la siguiente generación. 

**Pseudocódigo General de un GA:** 
1.  Generar una población inicial N.
2.  Evaluar el fitness de todos los individuos.
3.  **Mientras** no se cumpla el criterio de término:
    a.  Definir si se realizará mutación o cruzamiento (según probabilidades). 
    b.  Si es cruzamiento, seleccionar padres según la estrategia.
    c.  Generar la siguiente generación (considerar reemplazo generacional, elitismo, etc.). 
    d.  No olvidar guardar el mejor individuo encontrado hasta el momento. 
4.  Entregar resultados.

---

### Otros Algoritmos Evolutivos

#### Differential Evolution (DE)

Es otro algoritmo evolutivo, efectivo en problemas de optimización continua. 

* **Población Inicial:** Se genera una población inicial de $k$ individuos, donde cada individuo $X_i$ es un vector de D números reales (punto flotante). Cada elemento $x_{ij}$ se genera aleatoriamente en un rango $[x_j^l, x_j^u]$:
    $x_{ij} = x_j^l + \text{rand}_j[0,1] \cdot (x_j^u - x_j^l)$. 
* **Mutación y Recombinación (Cruzamiento):** Es diferente al GA. Para cada individuo $X_i$ (padre): 
    1.  Se seleccionan aleatoriamente tres individuos distintos $r_1, r_2, r_3$ de la población, diferentes de $i$. 
    2.  Se crea un vector "mutante" o "donante" $V_i$ (a menudo llamado $u_i$ en la formulación de la diapositiva):
        $v_{ij} = x_{r_3j} + F \cdot (x_{r_1j} - x_{r_2j})$ para una de las estrategias de DE. 
        Donde $F$ es el factor de escala (diferencial), usualmente en $[0,1]$, e.g., 0.8. 
    3.  Se crea un individuo "de prueba" $U_i$ mediante cruzamiento entre el padre $X_i$ y el vector mutante $V_i$. Para cada dimensión $j$:
        $u_{ij} = v_{ij}$ si $(\text{rand}_j[0,1] < CR)$ o $(j == j_{\text{rand}})$
        $u_{ij} = x_{ij}$ en otro caso. 
        $CR$ es la tasa de cruzamiento (probabilidad), usualmente en $[0,1]$, e.g., 0.9. $j_{\text{rand}}$ asegura que al menos una variable del hijo sea del vector mutante. 
* **Selección:** El individuo de prueba $U_i$ reemplaza al padre $X_i$ en la siguiente generación si tiene mejor (o igual) fitness.
    $X_i(t+1) = U_i$ si $f(U_i) \le f(X_i(t))$ (para minimización). 
    $X_i(t+1) = X_i(t)$ en otro caso.
* **Aplicaciones:** Optimización continua con restricciones, funciones no diferenciables, problemas multiobjetivo. 

#### Algoritmos de Coevolución Cooperativa

* **Concepto:** Inspirados en la evolución complementaria de especies cercanas (e.g., plantas e insectos polinizadores). 
* A diferencia de los GA clásicos, aquí múltiples poblaciones (especies) evolucionan en paralelo. 
* Cada especie desarrolla un subcomponente de la solución global. 
* Los representantes de cada especie se unen (e.g., concatenan) para formar una solución completa que luego es evaluada. 
* **Idea Principal:** Dividir un problema grande en subproblemas más pequeños y resolverlos de manera cooperativa e independiente. 
* **Aplicaciones:** Problemas grandes de optimización, entrenamiento de redes neuronales. 

#### Scatter Search

* Comienza generando una población inicial diversa y de calidad. 
* Construye y mantiene un **Conjunto de Referencia (RefSet)** de tamaño moderado (e.g., ~10 soluciones). 
* El RefSet incluye soluciones con buen fitness y otras que aportan diversidad. 
* **Proceso General:** 
    1.  Crear población inicial.
    2.  Mejorar la población inicial (opcionalmente usando una heurística local).
    3.  Generar el RefSet a partir de la población mejorada.
    4.  Generar subconjuntos de soluciones a partir del RefSet.
    5.  Combinar soluciones de estos subconjuntos para crear nuevas soluciones.
    6.  Mejorar estas nuevas soluciones (opcionalmente).
    7.  Actualizar el RefSet con las mejores y más diversas soluciones generadas.
* Integra elementos de algoritmos basados en poblaciones y de metaheurísticas de una sola solución. 

---
---

## Inteligencia de Enjambre (Swarm Intelligence)

Los algoritmos de Inteligencia de Enjambre se inspiran en el **comportamiento colectivo y social de especies** como hormigas, abejas, peces, aves, murciélagos, etc. Estos comportamientos surgen, por ejemplo, al competir por comida. 

* **Característica Principal:** La "cooperación" mediante comunicación indirecta entre los agentes (individuos) para explorar el espacio de búsqueda. 
* **Categoría:** Metaheurísticas basadas en poblaciones. 

### Particle Swarm Optimization (PSO)

Propuesto por James Kennedy y Russell Eberhart en 1995, el PSO se inspira en el **movimiento de las bandadas de aves** o cardúmenes de peces. 

* **Idea Central:** 
    * Inicialmente propuesto para problemas continuos.
    * La comunicación entre "partículas" (agentes) maneja el balance entre diversificación (exploración) e intensificación (explotación).

* **Conceptos Fundamentales:**
    1.  Cada **partícula `i`** es una solución candidata al problema y se representa por un vector de **posición** $X_i$ en el espacio de búsqueda D-dimensional. 
    2.  Cada partícula tiene su propia **posición** $X_i = (x_{i1}, x_{i2}, ..., x_{iD})$ y una **velocidad** $V_i = (v_{i1}, v_{i2}, ..., v_{iD})$. La velocidad indica la dirección y la magnitud del movimiento. 
    3.  Es un algoritmo **cooperativo**: las mejores partículas (o sus experiencias) influyen en el comportamiento de las demás. 

**Componentes del Movimiento de una Partícula:** 
Cada partícula ajusta su posición basándose en dos factores principales:
1.  **La mejor posición encontrada por ella misma (experiencia personal):** Denotada como $P_i = (p_{i1}, p_{i2}, ..., p_{iD})$ (también llamada `pbest`). 
2.  **La mejor posición encontrada por el enjambre o un subconjunto de él (experiencia social):** Denotada como $P_g = (p_{g1}, p_{g2}, ..., p_{gD})$ (también llamada `gbest` o `lbest` según el vecindario). 

**Vecindario de Partículas:** 
Define la componente social y cómo se comparte la información.
* **`gbest` (Mejor Global):** El vecindario es toda la población. Todas las partículas son influenciadas por la mejor solución encontrada globalmente por cualquier partícula del enjambre. (Ver imagen 'Complete graph' )
* **`lbest` (Mejor Local):** Se define una topología (e.g., anillo, estrella) y el vecindario de una partícula es un conjunto más pequeño de partículas conectadas. La partícula es influenciada por la mejor solución encontrada dentro de su vecindario local. (Ver imagen 'Local structure: a ring' )

**Composición de una Partícula:** 
* Vector de posición actual: $X_i(t)$. 
* Vector de la mejor posición personal encontrada: $P_i$ (`pbest`). 
* Vector de velocidad: $V_i(t)$. 

**Actualizaciones en Cada Iteración:** 

1.  **Actualización de la Velocidad:** 
    La velocidad de cada partícula `i` en cada dimensión `d` se actualiza como:
    $v_{id}(t) = \omega \cdot v_{id}(t-1) + c_1 \cdot \rho_{1d} \cdot (p_{id} - x_{id}(t-1)) + c_2 \cdot \rho_{2d} \cdot (p_{gd} - x_{id}(t-1))$
    Donde:
    * $v_{id}(t-1)$: Velocidad anterior.
    * $\omega$: **Peso de inercia**. Controla la influencia de la velocidad anterior. Valores grandes favorecen la exploración global, valores pequeños la explotación local. 
    * $c_1, c_2$: Coeficientes de aceleración (constantes). $c_1$ es el factor cognitivo (atracción hacia su propio mejor) y $c_2$ es el factor social (atracción hacia el mejor del vecindario). 
    * $\rho_{1d}, \rho_{2d}$: Números aleatorios uniformemente distribuidos en $[0,1]$, generados para cada dimensión y partícula. Introducen un componente estocástico.
    * $x_{id}(t-1)$: Posición actual (anterior a la actualización).
    * $p_{id}$: Mejor posición personal de la partícula `i`.
    * $p_{gd}$: Mejor posición del vecindario (gbest o lbest).

    *Nota: La fórmula original sin inercia es: $v_{i}(t) = v_{i}(t-1) + \rho_{1}C_{1}\times(p_{i}-x_{i}(t-1)) + \rho_{2}C_{2}\times(g_{i}-x_{i}(t-1))$.* 

2.  **Actualización de la Posición:** 
    La nueva posición se calcula sumando la nueva velocidad a la posición actual:
    $x_{id}(t) = x_{id}(t-1) + v_{id}(t)$ 

3.  **Actualización de las Mejores Posiciones:** 
    * **Actualizar `pbest`:** Si la nueva posición $X_i(t)$ es mejor (según la función de fitness $f$) que $P_i$, entonces $P_i = X_i(t)$.
      `Si f(xi) < f(pbesti) Entonces pbesti = xi` (para minimización) 
    * **Actualizar `gbest` (o `lbest`):** Si la nueva posición $X_i(t)$ es mejor que la actual $P_g$, entonces $P_g = X_i(t)$.
      `Si f(xi) < f(gbest) Entonces gbest = xi` (para minimización y usando gbest) 

**Representación Gráfica del Movimiento:** 
Una partícula en $x(t)$ se mueve a $x(t+1)$ influenciada por su velocidad actual $v(t)$, su mejor experiencia personal $p_i$, y la mejor experiencia de sus vecinos $p_g$.

**Pseudocódigo del PSO:** 
1.  Inicializar aleatoriamente la población de partículas (posiciones $X_i$ y velocidades $V_i$).
2.  Para cada partícula, inicializar $P_i = X_i$.
3.  Identificar $P_g$ entre todos los $P_i$.
4.  **Repeat**
5.  Para cada partícula $i$:
    a.  Evaluar $f(X_i)$.
    b.  Actualizar $P_i$ si $f(X_i)$ es mejor que $f(P_i)$.
    c.  Actualizar $P_g$ si $f(X_i)$ es mejor que $f(P_g)$ (o el $P_{lbest}$ correspondiente).
    d.  Actualizar velocidad $V_i(t)$ usando la ecuación de velocidad. 
    e.  Actualizar posición $X_i(t) = X_i(t-1) + V_i(t)$. 
    f.  `If f(xi) < f(pbesti) Then pbesti = xi` 
    g.  `If f(xi) < f(gbest) Then gbest = xi` 
6.  **Until** Criterio de parada satisfecho (e.g., número de iteraciones, convergencia). 
7.  **Output**: $P_g$ (la mejor solución encontrada).

**Parámetros del algoritmo**
- $C_1$
- $C_2$
- $w$
- N (Cantidad de individuos)

## Actividad

Se busca encontrar el mínimo de la función:
$f(x) = \sum_{i=1}^{N-1} [100(x_{i+1} - x_i^2)^2 + (1 - x_i)^2]$
donde $x_i \in [-10, 10]$ y $N=3$. Para $N=3$, la función es:
$f(x_1, x_2, x_3) = [100(x_2 - x_1^2)^2 + (1 - x_1)^2] + [100(x_3 - x_2^2)^2 + (1 - x_2)^2]$

Dados los siguientes parámetros de una partícula en un algoritmo PSO:

A. Posición actual de la partícula: $x(t-1) = (x_1, x_2, x_3) = (0.4, 1.2, -3.2)$
B. Mejor posición personal: $p = (p_1, p_2, p_3) = (1.2, 2.5, -2.1)$
C. Mejor posición global: $g = (g_1, g_2, g_3) = (1.4, 1.1, -0.4)$
D. Constantes del PSO: $C_1 = 1$, $C_2 = 1$, $\omega = 1$
E. Velocidad actual de la partícula: $v(t-1) = (v_1, v_2, v_3) = (-0.8, 0.2, -1.2)$
F. Números aleatorios proporcionados: Se utilizará $\rho_1 = 0.21$ para el componente cognitivo y $\rho_2 = 0.43$ para el componente social.

Se pide calcular la nueva posición de la partícula $x(t)$.

---

### Resolución

Las ecuaciones para la actualización de la velocidad y la posición de una partícula en PSO son:

1.  **Actualización de la velocidad (para cada dimensión $d$):**
    $v_d(t) = \omega \cdot v_d(t-1) + C_1 \cdot \rho_1 \cdot (p_d - x_d(t-1)) + C_2 \cdot \rho_2 \cdot (g_d - x_d(t-1))$

2.  **Actualización de la posición (para cada dimensión $d$):**
    $x_d(t) = x_d(t-1) + v_d(t)$

En este cálculo, utilizaremos $\rho_1 = 0.21$ y $\rho_2 = 0.43$ como los números aleatorios escalares aplicados a los componentes cognitivo y social, respectivamente, para todas las dimensiones.

#### Paso 1: Calcular la nueva velocidad $v(t)$

* **Para la dimensión 1 ($d=1$):**
    $v_1(t-1) = -0.8$
    $x_1(t-1) = 0.4$
    $p_1 = 1.2$
    $g_1 = 1.4$
    $v_1(t) = (1 \cdot -0.8) + (1 \cdot 0.21 \cdot (1.2 - 0.4)) + (1 \cdot 0.43 \cdot (1.4 - 0.4))$
    $v_1(t) = -0.8 + (0.21 \cdot 0.8) + (0.43 \cdot 1.0)$
    $v_1(t) = -0.8 + 0.168 + 0.43$
    $v_1(t) = -0.8 + 0.598$
    $v_1(t) = -0.202$

* **Para la dimensión 2 ($d=2$):**
    $v_2(t-1) = 0.2$
    $x_2(t-1) = 1.2$
    $p_2 = 2.5$
    $g_2 = 1.1$
    $v_2(t) = (1 \cdot 0.2) + (1 \cdot 0.21 \cdot (2.5 - 1.2)) + (1 \cdot 0.43 \cdot (1.1 - 1.2))$
    $v_2(t) = 0.2 + (0.21 \cdot 1.3) + (0.43 \cdot -0.1)$
    $v_2(t) = 0.2 + 0.273 - 0.043$
    $v_2(t) = 0.2 + 0.23$
    $v_2(t) = 0.43$

* **Para la dimensión 3 ($d=3$):**
    $v_3(t-1) = -1.2$
    $x_3(t-1) = -3.2$
    $p_3 = -2.1$
    $g_3 = -0.4$
    $v_3(t) = (1 \cdot -1.2) + (1 \cdot 0.21 \cdot (-2.1 - (-3.2))) + (1 \cdot 0.43 \cdot (-0.4 - (-3.2)))$
    $v_3(t) = -1.2 + (0.21 \cdot (-2.1 + 3.2)) + (0.43 \cdot (-0.4 + 3.2))$
    $v_3(t) = -1.2 + (0.21 \cdot 1.1) + (0.43 \cdot 2.8)$
    $v_3(t) = -1.2 + 0.231 + 1.204$
    $v_3(t) = -1.2 + 1.435$
    $v_3(t) = 0.235$

Por lo tanto, la nueva velocidad es $v(t) = (-0.202, 0.43, 0.235)$.

#### Paso 2: Calcular la nueva posición $x(t)$

* **Para la dimensión 1 ($d=1$):**
    $x_1(t) = x_1(t-1) + v_1(t)$
    $x_1(t) = 0.4 + (-0.202)$
    $x_1(t) = 0.198$

* **Para la dimensión 2 ($d=2$):**
    $x_2(t) = x_2(t-1) + v_2(t)$
    $x_2(t) = 1.2 + 0.43$
    $x_2(t) = 1.63$

* **Para la dimensión 3 ($d=3$):**
    $x_3(t) = x_3(t-1) + v_3(t)$
    $x_3(t) = -3.2 + 0.235$
    $x_3(t) = -2.965$

La nueva posición de la partícula es $x(t) = (0.198, 1.63, -2.965)$.

Verificamos si los componentes de la nueva posición están dentro del dominio $x_i \in [-10, 10]$:
* $x_1(t) = 0.198$ (Dentro del rango)
* $x_2(t) = 1.63$ (Dentro del rango)
* $x_3(t) = -2.965$ (Dentro del rango)
Todos los componentes están dentro de los límites permitidos.

---

**Respuesta Final:**
La nueva posición de la partícula es $x(t) = (0.198, 1.63, -2.965)$.

# Clase 22-05-25

## Sintonización de Parámetros

La sintonización de parámetros es un problema fundamental y costoso en el diseño de Algoritmos Exactos y Metaheurísticas (MHs). Consiste en asignar valores a los elementos numéricos de un algoritmo para optimizar su rendimiento.

### Decisiones de Diseño en MHs

Diferentes metaheurísticas tienen parámetros específicos que requieren sintonización:

- **Tabu Search**: Tamaño de la lista Tabú.
    
- **Simulated Annealing**: Temperatura inicial, parámetro de enfriamiento, y cantidad de iteraciones para enfriamiento y calentamiento.
    
- **Algoritmos Genéticos (GA)**: Probabilidad de cruzamiento/mutación, operadores y porcentaje de elitismo.
    
- **ACO**: Tasa de evaporación.
    
- **PSO**: Ponderación global best-local best-inertia.
    

### Consideraciones Clave

Un buen algoritmo debe explorar el espacio de búsqueda y luego explotar las zonas favorables. Los parámetros están interrelacionados, lo que complejiza el proceso de diseño. Los valores de los parámetros se determinan a partir de un conjunto de benchmarks.

### Sintonización vs. Control

Es importante diferenciar entre sintonización y control de parámetros:

- **Sintonización**: Proceso previo a la ejecución del algoritmo, consume mucho tiempo, y los valores de los parámetros son fijos durante la ejecución. (Estrategia offline)
    
- **Control**: Proceso que ocurre durante la ejecución del algoritmo, con valores variables, y puede ser dinámico, adaptativo o auto-adaptativo. (Estrategia online)
    

### Técnicas de Sintonización de Parámetros

Existen varias técnicas para la sintonización de parámetros:

- **Manual**: Ajuste manual de los parámetros.
    
- **Estadística (Racing)**: Basada en pruebas estadísticas, donde los algoritmos son evaluados iterativamente y eliminados si se encuentra evidencia de inferioridad. Un ejemplo es el test de Friedman. Ejemplos incluyen Pygmo e irace.
    
- **Meta-Algoritmos**: Utilizan otros algoritmos para encontrar la mejor configuración de parámetros.
    - **Búsqueda Local**: Consiste en experimentar cambiando un parámetro y aceptando la nueva configuración solo si mejora el desempeño. Esto puede optimizarse con Iterated Local Search (ILS).
        
    - **ParamILS**: Un ejemplo de meta-algoritmo que utiliza un enfoque de búsqueda local iterativa con perturbación y un criterio de aceptación para encontrar la mejor configuración de parámetros.
        

### Análisis de Desempeño en MHs

Para analizar el desempeño de las metaheurísticas, se consideran:

- **Diseño experimental**: Selección de benchmarks.
    
- **Mediciones**: Análisis estadístico de resultados (tiempo de CPU, valor de la función objetivo) y comparación con técnicas del estado del arte.
    
- **Reporte**: Gráficos de convergencia, gráficos de cajas, reporte de tiempo de CPU y generaciones, asegurando la reproducibilidad de los experimentos.

