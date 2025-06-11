## Clase 1: Algoritmos Genéticos y Metaheurísticas Basadas en Poblaciones

### Introducción a Metaheurísticas Basadas en Poblaciones (MH-P)

A diferencia de algoritmos como Hill-Climbing, Tabu Search o Simulated Annealing que mejoran iterativamente una única solución, las metaheurísticas basadas en poblaciones trabajan con un conjunto o **población de soluciones** simultáneamente.

Estos algoritmos, en su mayoría inspirados en procesos naturales, comienzan con una población inicial y, en cada iteración, generan un nuevo conjunto de soluciones para reemplazar total o parcialmente la población actual. Este proceso puede o no utilizar una memoria para guiar la búsqueda.

**Esquema General de una MH-P:**

```
Algoritmo: Plantilla de P-metaheurísticas
1. P = Generar_Población_Inicial()
2. t = 0
3. Repetir
4.   P' = Generar_Nueva_Población(P_t)
5.   P_{t+1} = Seleccionar_Población(P_t U P')
6.   t = t + 1
7. Hasta que se cumpla el criterio de parada
8. Devolver la(s) mejor(es) solución(es) encontrada(s).
```

La **población inicial** es un paso crucial. Una población diversa permite una mayor exploración del espacio de búsqueda y ayuda a evitar la convergencia prematura hacia óptimos locales.

### Algoritmos Genéticos (GA)

Inspirados en la teoría de la evolución de Darwin y la genética, los Algoritmos Genéticos (GA) son una de las MH-P más conocidas. Se basan en los principios de selección natural, cruzamiento y mutación para evolucionar una población de soluciones hacia mejores resultados.

#### Componentes Clave de un GA

1. **Representación (Cromosoma)**: La solución a un problema se codifica en una estructura de datos llamada **cromosoma**. Cada componente del cromosoma se denomina **gen**. La colección de cromosomas forma la **población**.
    
    - _Ejemplo_: Un cromosoma binario `10110` puede representar una solución.
        
2. **Función de Fitness**: Evalúa qué tan "apta" es una solución (individuo). Generalmente, es la misma función objetivo del problema. La probabilidad de que un individuo sea seleccionado para reproducirse es proporcional a su fitness.
    
3. **Estrategia de Selección**: Mecanismo para elegir a los individuos "padres" que crearán la siguiente generación.
    
    - **Ruleta (Roulette Wheel)**: Asigna a cada individuo una porción de una "ruleta" proporcional a su fitness. Los individuos con mayor fitness tienen más probabilidades de ser seleccionados. Puede causar convergencia prematura si existen individuos excepcionales al inicio.
        
    - **Torneo (Tournament Selection)**: Se selecciona un subconjunto aleatorio de `k` individuos (grupo de torneo) y el de mejor fitness del grupo es elegido como padre. Este proceso se repite para seleccionar a todos los padres necesarios.
        
4. **Operadores Genéticos**:
    
    - **Cruzamiento (Crossover)**: Es el operador principal. Combina la información genética de dos padres para crear uno o más "hijos". El objetivo es que los hijos hereden las buenas características de sus padres.
        
        - **Cruzamiento de 1-Punto**: Se elige un punto de corte aleatorio y se intercambian los segmentos de los cromosomas de los padres.
            
        - **Cruzamiento de 2-Puntos**: Se eligen dos puntos y se intercambia el segmento central.
            
        - **Cruzamiento Uniforme**: Cada gen del hijo se elige aleatoriamente de uno de los padres con una probabilidad definida.
            
    - **Mutación**: Altera aleatoriamente uno o más genes de un cromosoma con una probabilidad baja (pm​, usualmente entre 0.01 y 0.05). Su función es introducir nueva diversidad en la población y prevenir la convergencia prematura.
        
        - _En dominios binarios_: Cambiar un 0 por un 1 o viceversa.
            
        - _En problemas de permutación (como el TSP)_: Intercambiar (swap) dos genes.
            
5. **Estrategia de Reemplazo**: Define cómo se forma la nueva generación.
    
    - **Reemplazo Generacional**: La nueva población de hijos reemplaza completamente a la población de padres.
        
    - **Elitismo**: Un pequeño porcentaje de los mejores individuos (la élite) de la generación actual se copia directamente a la siguiente generación, asegurando que las mejores soluciones encontradas no se pierdan.
        

#### Pseudocódigo General de un GA

1. Generar una población inicial de `N` individuos.
    
2. Evaluar el fitness de cada individuo en la población.
    
3. Mientras no se cumpla el criterio de parada:
    
    a. Seleccionar padres de la población actual.
    
    b. Aplicar operadores de cruzamiento y mutación para crear una nueva población de hijos.
    
    c. Aplicar la estrategia de reemplazo para formar la nueva generación.
    
    d. Guardar el mejor individuo encontrado hasta el momento.
    
4. Devolver la mejor solución encontrada.
    

## Clase 2: Otros Algoritmos Evolutivos

### Differential Evolution (DE)

DE es un algoritmo evolutivo potente y simple, especialmente efectivo en problemas de optimización continua.

- **Codificación**: Las soluciones son vectores de números reales.
    
- Operador de Cruzamiento/Mutación: DE utiliza un operador único que combina tres vectores (individuos) distintos y aleatorios de la población (r1​,r2​,r3​) para crear un vector "mutante" vi​. La fórmula básica es:
    
    vij​=xr3​j​+F⋅(xr1​j​−xr2​j​)
    
    Donde F es un factor de escala (parámetro, ej. 0.8).
    
- **Recombinación**: El hijo ui​ se forma combinando genes del padre original xi​ y del vector mutante vi​, controlado por una tasa de cruzamiento CR (parámetro, ej. 0.9).
    
- **Selección**: La selección es determinista y "greedy". El hijo ui​ reemplaza al padre xi​ solo si tiene un mejor (o igual) valor de fitness.
    

### Algoritmos de Coevolución Cooperativa

Inspirados en la coevolución de especies en la naturaleza, estos algoritmos dividen un problema grande en subproblemas más pequeños.

- **Estructura**: Se mantienen múltiples poblaciones, donde cada una representa una "especie" que evoluciona un subcomponente de la solución global.
    
- **Evaluación**: Para evaluar el fitness de un individuo de una especie, se combina con representantes (los mejores individuos) de las otras especies para formar una solución completa.
    
- **Resultado**: Al final, los mejores representantes de cada especie se unen para formar la solución final. Es útil para problemas de optimización a gran escala.
    

### Scatter Search (SS)

SS es una metaheurística evolutiva que integra conceptos de los algoritmos basados en poblaciones y de búsqueda local.

- **Conjunto de Referencia (RefSet)**: Mantiene un conjunto pequeño (ej. 10 soluciones) de soluciones de alta calidad y diversidad, llamado `RefSet`.
    
- **Proceso**:
    
    1. Se genera una población inicial diversa, que puede ser mejorada con una búsqueda local.
        
    2. Se seleccionan las mejores y más diversas soluciones para construir el `RefSet`.
        
    3. Se generan subconjuntos de soluciones del `RefSet`.
        
    4. Se combinan las soluciones de estos subconjuntos para crear nuevas soluciones.
        
    5. A estas nuevas soluciones se les puede aplicar una búsqueda local para mejorarlas.
        
    6. El `RefSet` se actualiza con las mejores soluciones generadas.
        

## Clase 3: Inteligencia de Enjambre - Particle Swarm Optimization (PSO)

La Inteligencia de Enjambre (Swarm Intelligence) se inspira en el comportamiento social colectivo de animales como hormigas, aves o peces. La cooperación mediante comunicación indirecta es su característica principal.

### Particle Swarm Optimization (PSO)

Inspirado en el vuelo de las bandadas de aves, PSO es una MH-P diseñada originalmente para problemas continuos.

#### Componentes Clave de PSO

1. **Partículas**: Cada solución candidata es una "partícula" en el espacio de búsqueda.
    
2. **Posición y Velocidad**: Cada partícula `i` tiene:
    
    - Una **posición** xi​ (la solución actual).
        
    - Una **velocidad** vi​ (la dirección y magnitud del movimiento).
        
3. **Memoria**: Cada partícula recuerda:
    
    - Su **mejor posición personal** encontrada hasta ahora (pi​ o `pbest`).
        
    - La **mejor posición global** encontrada por cualquier partícula en el enjambre (pg​ o `gbest`).
        
4. **Vecindario**:
    
    - **gbest**: El vecindario es toda la población. La partícula es guiada por la mejor global.
        
    - **lbest**: Se define una topología (ej. un anillo) y la partícula es guiada por la mejor de su vecindario local.
        

#### Actualización de Movimiento

En cada iteración, la velocidad y la posición de cada partícula se actualizan:

- Actualización de Velocidad:
    
    vi​(t)=ω⋅vi​(t−1)+C1​⋅ρ1​⋅(pi​−xi​(t−1))+C2​⋅ρ2​⋅(pg​−xi​(t−1))
    
    - ω: **Peso de inercia**. Controla el balance entre exploración (valores altos) y explotación (valores bajos).
        
    - C1​: **Factor cognitivo** (atracción hacia su propio éxito).
        
    - C2​: **Factor social** (atracción hacia el éxito del enjambre).
        
    - ρ1​,ρ2​: Números aleatorios en [0, 1].
        
- Actualización de Posición:
    
    xi​(t)=xi​(t−1)+vi​(t)
    

#### Pseudocódigo de PSO

1. Inicializar aleatoriamente la posición y velocidad de cada partícula en el enjambre.
    
2. Evaluar el fitness de cada partícula. Inicializar `pbest` y `gbest`.
    
3. Mientras no se cumpla el criterio de parada:
    
    a. Para cada partícula i:
    
    i. Actualizar su velocidad vi​.
    
    ii. Actualizar su posición xi​.
    
    iii. Evaluar el fitness de la nueva posición f(xi​).
    
    iv. Si f(xi​) es mejor que f(pi​), actualizar pi​=xi​.
    
    v. Si f(xi​) es mejor que f(pg​), actualizar pg​=xi​.
    
4. Devolver pg​ como la mejor solución encontrada.
    

## Clase 4: Inteligencia de Enjambre - Ant Colony Optimization (ACO)

ACO se inspira en cómo las hormigas encuentran el camino más corto entre su nido y una fuente de alimento.

### Principio de Estigmergia

Las hormigas se comunican de forma indirecta depositando una sustancia química llamada **feromona** en su camino.

- Las otras hormigas tienden a seguir los caminos con mayor concentración de feromonas.
    
- Como los caminos más cortos se recorren más rápido, acumulan feromona a un ritmo mayor.
    
- La feromona se **evapora** con el tiempo, lo que evita que los caminos subóptimos sigan siendo atractivos indefinidamente.
    

Este mecanismo de comunicación indirecta a través del entorno se llama **estigmergia**.

### ACO para Problemas de Optimización

ACO es muy adecuado para problemas que se pueden representar como un grafo, como el Problema del Agente Viajero (TSP).

1. **Construcción de Soluciones**: Un conjunto de "hormigas" artificiales construye soluciones de forma probabilística, moviéndose de un nodo a otro en el grafo del problema.
    
2. **Regla de Transición Probabilística**: La probabilidad de que una hormiga `k` en el nodo `i` elija ir al nodo `j` depende de dos factores:
    
    - La cantidad de **feromona** en el arco (τij​).
        
    - La **información heurística** (visibilidad), que es el atractivo del movimiento (ej., para el TSP, ηij​=1/dij​, donde dij​ es la distancia).
        
    
    La probabilidad se calcula así:
    
    Pijk​=∑l∈Nik​​(τil​)α(ηil​)β(τij​)α(ηij​)β​
    
    Donde α y β son parámetros que controlan la importancia relativa de la feromona y la heurística.
    
3. **Actualización de Feromonas**: Una vez que todas las hormigas han construido una solución, las trazas de feromona se actualizan.
    
    - Evaporación: Todas las trazas de feromona se reducen por un factor ρ (tasa de evaporación).
        
        τij​=(1−ρ)⋅τij​
        
    - Depósito: Las hormigas depositan feromona en los arcos que usaron, en una cantidad proporcional a la calidad de su solución (ej. 1/Lk​, donde Lk​ es la longitud del tour de la hormiga k).
        
        τij​=τij​+∑k​Δτijk​
        

Este proceso se repite, y con el tiempo, los arcos que pertenecen a las mejores soluciones reciben más feromona y son elegidos con mayor frecuencia, guiando la búsqueda hacia regiones prometedoras.

## Clase 5: Sintonización de Parámetros

El rendimiento de una metaheurística depende fuertemente de los valores de sus parámetros (ej. tasa de mutación en GA, peso de inercia en PSO, tasa de evaporación en ACO). La **sintonización de parámetros** es el proceso de encontrar los valores óptimos para estos.

### Sintonización vs. Control

- **Sintonización de Parámetros (Offline)**: Encontrar un conjunto de valores fijos para los parámetros _antes_ de ejecutar el algoritmo en el problema real. Es un proceso costoso en tiempo que se realiza sobre un conjunto de instancias de benchmark.
    
- **Control de Parámetros (Online)**: Ajustar los valores de los parámetros _durante_ la ejecución del algoritmo.
    
    - **Control Dinámico**: Los cambios son deterministas (ej. disminuir la temperatura en SA cada `n` iteraciones).
        
    - **Control Adaptativo**: Los cambios se basan en la retroalimentación de la búsqueda (ej. aumentar la mutación si la población pierde diversidad).
        
    - **Control Auto-Adaptativo**: Los parámetros se codifican en los propios individuos y evolucionan junto con las soluciones.
        

### Métodos de Sintonización

1. **Manual**: Basado en la experiencia y prueba y error. Es tedioso e ineficaz.
    
2. **Estadística (Racing)**: Se ejecutan varias configuraciones de parámetros en paralelo ("carrera"). Aquellas que muestran un rendimiento estadísticamente inferior son eliminadas tempranamente.
    
3. **Meta-Algoritmos**: Usar otra metaheurística para optimizar los parámetros de la primera. Un ejemplo es **ParamILS**, que utiliza Iterated Local Search (ILS) para buscar en el espacio de configuraciones de parámetros.
    

### Análisis de Desempeño

Para asegurar la validez de los resultados de una metaheurística, es crucial un buen diseño experimental:

- **Benchmarks**: Seleccionar un conjunto representativo de instancias del problema.
    
- **Mediciones**: Realizar múltiples ejecuciones para cada instancia debido a la naturaleza estocástica. Analizar estadísticamente los resultados (media, mínimo, máximo, desviación estándar).
    
- **Reporte**: Presentar los resultados de forma clara (tablas, gráficos de convergencia, diagramas de caja) para garantizar la **reproducibilidad**.
    

## Clase 6: Optimización Multi-objetivo (MOP)

Muchos problemas del mundo real implican optimizar varios objetivos a la vez, que a menudo están en conflicto (ej. minimizar costo y maximizar calidad).

### Conceptos Fundamentales

- Problema Multi-objetivo: Minimizar/Maximizar un vector de funciones objetivo:
    
    F(x)=(f1​(x),f2​(x),...,fM​(x))
    
- **Dominancia de Pareto**: Una solución x1​ **domina** a una solución x2​ si y solo si:
    
    1. x1​ no es peor que x2​ en todos los objetivos.
        
    2. x1​ es estrictamente mejor que x2​ en al menos un objetivo.
        
- **Soluciones No Dominadas (Pareto-óptimas)**: Son aquellas que no son dominadas por ninguna otra solución en el espacio factible.
    
- **Frontera de Pareto (Frente de Pareto)**: Es el conjunto de todas las soluciones no dominadas en el espacio de los objetivos. El objetivo en MOP es encontrar una buena aproximación de esta frontera.
    

### Algoritmos Evolutivos para MOP

Los algoritmos evolutivos son ideales para MOP porque:

1. Trabajan con una población, lo que les permite encontrar múltiples soluciones de la frontera de Pareto en una sola ejecución.
    
2. No requieren que la frontera de Pareto sea continua o convexa.
    

### NSGA-II (Non-dominated Sorting Genetic Algorithm II)

NSGA-II es uno de los algoritmos evolutivos multi-objetivo más populares y efectivos. Sus componentes clave son:

1. **Ordenamiento No Dominado (Non-dominated Sorting)**:
    
    - La población se particiona en frentes (ranks) basados en la dominancia.
        
    - **Frente 1 (Rank 1)**: Contiene todas las soluciones no dominadas de la población.
        
    - **Frente 2 (Rank 2)**: Contiene las soluciones no dominadas una vez que se ha eliminado el Frente 1.
        
    - Este proceso continúa hasta que todos los individuos están clasificados.
        
    - Las soluciones con un ranking más bajo (ej. en el Frente 1) son preferidas.
        
2. **Distancia de Aglomeración (Crowding Distance)**:
    
    - Cuando dos soluciones tienen el mismo ranking (están en el mismo frente), se prefiere la que esté en una región menos poblada de la frontera.
        
    - La **distancia de aglomeración** mide la densidad de soluciones alrededor de un punto en particular. Se calcula como el tamaño del paralelepípedo formado por los vecinos más cercanos a lo largo de cada eje objetivo.
        
    - Una mayor distancia de aglomeración es mejor, ya que promueve la **diversidad** a lo largo de la frontera de Pareto.
        
3. **Selección, Cruzamiento y Mutación**:
    
    - **Selección**: Se utiliza una selección por torneo, donde el ganador se decide primero por el **ranking** (mejor ranking gana) y, en caso de empate, por la **distancia de aglomeración** (mayor distancia gana).
        
    - **Cruzamiento y Mutación**: Se utilizan operadores estándar de GA.
        
4. **Estrategia de Reemplazo (Elitista)**:
    
    - En cada generación, la población de padres (Pt​) y la de hijos (Qt​) se combinan.
        
    - La nueva población (Pt+1​) se construye seleccionando los mejores frentes de la población combinada.
        
    - Si el último frente que puede entrar en la nueva población no cabe por completo, se seleccionan los individuos de ese frente con la mayor distancia de aglomeración hasta llenar la población.
        

Esta estrategia asegura tanto la **convergencia** hacia la verdadera frontera de Pareto (a través del ranking) como la **diversidad** de las soluciones (a través de la distancia de aglomeración).