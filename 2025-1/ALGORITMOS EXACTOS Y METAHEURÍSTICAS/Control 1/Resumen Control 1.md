# **Parte 1: Fundamentos y Tipos de Problemas (Clases 06-03 y 10-03)**

1. **Conceptos Centrales:**
    
    - **Algoritmos Exactos:**
        
        - **Objetivo:** Encontrar la solución demostrablemente mejor o todas las soluciones.
            
        - **Garantía:** Se encuentra la solución óptima si existe y se dispone de suficientes recursos (tiempo/memoria).
            
        - **Método:** A menudo implican una exploración sistemática y exhaustiva del espacio de búsqueda, frecuentemente usando estructuras de árbol.
            
        - **Ejemplos:** Backtracking (cronológico/fuerza bruta), Branch and Bound, Programación Dinámica, búsqueda informada (como A*, Look-Ahead/Look-Back).
            
    - **Heurísticas:**
        
        - **Definición:** "Reglas prácticas" específicas del problema o funciones de evaluación diseñadas para tomar decisiones rápidamente. (Derivado del griego heuriskein: "encontrar/descubrir").
            
        - **Características:** Baratas de calcular, explotan conocimiento específico del problema, no garantizan optimalidad.
            
        - **Ejemplo:** En un problema de búsqueda de caminos, "moverse siempre hacia el objetivo" es una heurística simple.
            
    - **Metaheurísticas:**
        
        - **Definición:** Estrategias de nivel superior y propósito general que guían heurísticas subsidiarias (a menudo búsqueda local) para explorar eficazmente un espacio de búsqueda en problemas de optimización o satisfacción. (Meta: "más allá", Heurística: "encontrar").
            
        - **Características:** No específicas del problema (aunque pueden adaptarse), a menudo estocásticas, buscan buenas soluciones en tiempo razonable, no garantizan optimalidad. Pertenecen al grupo de técnicas **incompletas**.
            
        - **Caso de Uso:** Particularmente útiles para problemas **NP-Hard** donde los métodos exactos se vuelven computacionalmente inviables (tiempo exponencial).
            
        - **Desafío:** A menudo requieren **ajuste de parámetros** (parameter tuning).
            
2. **Modelamiento de Problemas:** (El curso usa modelos, pero no trata sobre modelamiento)
    
    - **Componentes de un Modelo:**
        
        - **Variables:** Las incógnitas para las que necesitamos determinar valores.
            
        - **Dominios:** El conjunto de posibles valores para cada variable (pueden ser discretos o continuos).
            
        - **Restricciones:** Condiciones que deben ser satisfechas por una solución válida. (0, 1, o más).
            
        - **Función(es) Objetivo:** Criterios usados para evaluar la calidad de una solución, a minimizar o maximizar. (0, 1, o más).
            
    - **Ejemplo (Lata de Jugo de Maqui):**
        
        - Variables: altura (h), radio (r)
            
        - Dominios: h > 0, r > 0 (números reales positivos, continuos)
            
        - Restricción: Volumen π * r² * h = 128 (restricción de igualdad)
            
        - Función Objetivo: Minimizar Área Superficial 2πrh + 2πr²
            
3. **Tipos de Problemas:**
    
    - **Según el Objetivo:**
        
        - **Problema de Optimización con Restricciones (COP - Constraint Optimization Problem):** Tiene variables, dominios, restricciones Y una o más funciones objetivo. Meta: encontrar una solución factible que optimice el/los objetivo(s).
            
            - Formal: min/max f(x) sujeto a g(x) <= 0 (desigualdad), h(x) = 0 (igualdad), x ∈ D (dominio).
                
        - **Problema de Satisfacción de Restricciones (CSP - Constraint Satisfaction Problem):** Tiene variables, dominios y restricciones, pero **SIN** función objetivo. Meta: encontrar cualquier o todas las soluciones factibles. Las soluciones no se pueden comparar en calidad según un objetivo.
            
    - **Según el Dominio:** Continuo vs. Discreto.
        
    - **Según las Restricciones:** Restringido vs. No Restringido.
        
    - **Según los Objetivos:** Mono-objetivo vs. Multi-objetivo.
        
4. **Soluciones y Espacio de Búsqueda:**
    
    - **Solución Factible:** Una asignación de valores a las variables que satisface todas las restricciones.
        
    - **Solución Infactible:** Una asignación que viola al menos una restricción.
        
    - **Espacio de Búsqueda:** El conjunto de todas las posibles asignaciones (factibles e infactibles) de valores a las variables definidas por sus dominios. Corresponde a la región donde buscamos soluciones.
        
    - **Optimalidad (para COP):** Una solución factible con el mejor valor posible de la función objetivo.
        
5. **Dificultad de los Problemas:**
    
    - **P:** Problemas resolubles en tiempo polinomial por un algoritmo determinista.
        
    - **NP:** Problemas donde una solución dada puede ser verificada en tiempo polinomial. Si P=NP es una de las grandes preguntas abiertas.
        
    - **NP-Completo:** Los problemas "más difíciles" dentro de NP. Si cualquier problema NP-Completo se puede resolver en tiempo polinomial, entonces todos los problemas en NP pueden.
        
    - **Enfoque del Curso:** Técnicas aplicables a problemas NP-Completos.
        
6. **Elección de Técnicas:**
    
    - **Exactas:** Usar cuando el tamaño del problema es pequeño, se requiere estrictamente optimalidad y los recursos computacionales lo permiten.
        
    - **Incompletas (Metaheurísticas):** Usar para problemas grandes/complejos (NP-Hard), cuando soluciones cercanas al óptimo son aceptables, o cuando el tiempo/recursos son limitados.
        
7. **Metodología General:**
    
    - Conocer el Problema -> Revisión del Estado del Arte -> Diseñar una Técnica -> Implementar -> Validar (Experimentos) -> Concluir.
        

---

# **Parte 2: Algoritmos Exactos (Clases 13-03 y 17-03)**

Enfoque en métodos de búsqueda basados en árboles para CSPs/COPs.

1. **Proceso de Búsqueda:**
    
    - **Búsqueda Completa:** Explora el espacio de búsqueda de manera exhaustiva y sistemática.
        
    - **Representación en Árbol:**
        
        - **Nodos:** Representan estados (asignaciones parciales). La raíz es el estado inicial.
            
        - **Aristas/Ramas:** Representan acciones (asignar un valor a una variable).
            
        - **Hojas:** Representan asignaciones completas (soluciones potenciales).
            
    - **Terminación:** Se encuentra(n) la(s) solución(es), se demuestra que no hay solución, agotamiento de recursos (RAM, límite de tiempo).
        
2. **Backtracking (BT - Cronológico):**
    
    - **Concepto:** Una búsqueda básica en profundidad (DFS - Depth-First Search), no informada.
        
    - **Proceso:**
        
        1. Asignar un valor a una variable.
            
        2. Verificar si la asignación parcial es **consistente** (no viola restricciones que involucran variables asignadas actualmente).
            
        3. Si es consistente, pasar a la siguiente variable.
            
        4. Si es inconsistente, retroceder (backtrack): deshacer la última asignación e intentar el siguiente valor para esa variable. Si no hay más valores, retroceder más arriba en el árbol.
            
    - **Ejemplo (N-Reinas):** Colocar reina en columna 1, fila 1. Colocar reina en columna 2, fila 3 (consistente). Colocar reina en columna 3, fila ??? - si ninguna fila es consistente, retroceder a la columna 2 e intentar una fila diferente.
        
    - **Problema: Thrashing:** Puede fallar repetidamente en una parte del árbol debido a una decisión temprana errónea, sin identificar la causa raíz, llevando a trabajo redundante.
        
3. **Técnicas Look-Back (Mejorando BT):**
    
    - **Objetivo:** Reducir el thrashing saltando hacia atrás de forma más inteligente.
        
    - **Backjumping (BJ):** En lugar de retroceder cronológicamente (un paso atrás), saltar a la variable responsable del conflicto actual. Sigue siendo completo.
        
    - **Backjumping Dirigido por Conflictos (CBJ):**
        
        - **Mecanismo:** Mantener un **conjunto de conflictos** Conf(xi) para cada variable xi, almacenando las variables previamente asignadas que entran en conflicto con asignaciones potenciales para xi.
            
        - **Proceso:** Cuando una variable xi no tiene valores consistentes restantes (un **callejón sin salida** o **domain wipe-out**), retroceder a la variable asignada más recientemente que esté presente en Conf(xi).
            
        - **Beneficio:** Se salta variables intermedias irrelevantes para el conflicto. Más eficiente que BJ/BT simple, sigue siendo completo. Requiere memoria extra para los conjuntos de conflictos.
            
4. **Técnicas Look-Ahead:**
    
    - **Objetivo:** Podar el espacio de búsqueda antes de encontrar callejones sin salida, observando el impacto de las asignaciones actuales en variables futuras.
        
    - **Forward Checking (FC):**
        
        - **Proceso:** Cuando a la variable xi se le asigna un valor a, verificar todas las variables no asignadas xj conectadas a xi por restricciones. Eliminar cualquier valor del dominio de xj que sea inconsistente con xi = a. Si el dominio de alguna xj queda vacío, la asignación xi = a falla inmediatamente (retroceder).
            
        - **Beneficio:** Detecta fallos antes que BT. Reduce el tamaño del árbol.
            
        - **Costo:** Se realiza más trabajo en cada nodo en comparación con BT. El rendimiento general depende del problema.
            
    - **Minimal Forward Checking (MFC / Lazy FC):**
        
        - **Proceso:** Similar a FC, pero al verificar una variable futura xj, se detiene tan pronto como se encuentra un valor consistente en su dominio. Solo procede a la verificación completa del dominio si es necesario.
            
        - **Beneficio:** Menos sobrecarga de verificación por nodo que FC completo, mientras sigue detectando eliminaciones de dominio tempranamente. Sigue siendo completo.
            
5. **Heurísticas de Ordenamiento:**
    
    - **Impacto:** El orden en que se seleccionan las variables y se prueban los valores afecta significativamente el rendimiento.
        
    - **Ordenamiento de Variables:**
        
        - **Objetivo:** Elegir la variable que tiene más probabilidades de causar un fallo temprano ("Fail-First").
            
        - **Heurísticas:**
            
            - **Valores Mínimos Restantes (MRV) / Dom:** Elegir la variable con el dominio actual más pequeño.
                
            - **Heurística de Grado / Deg:** Elegir la variable involucrada en la mayor cantidad de restricciones con variables no asignadas. (Rompe empates para MRV).
                
            - **Dom/Deg:** Minimizar la relación entre el tamaño del dominio actual y el grado.
                
    - **Ordenamiento de Valores:**
        
        - **Objetivo:** Elegir el valor con más probabilidades de llevar a una solución ("Succeed-First"). Menos crítico que el ordenamiento de variables para CSPs, pero importante para COPs.
            
6. **Preprocesamiento (Técnicas de Consistencia):**
    
    - **Objetivo:** Simplificar el problema antes de que comience la búsqueda eliminando valores inconsistentes.
        
    - **Conceptos:** Consistencia de Nodo, Consistencia de Arco (AC-3 es un algoritmo común), Consistencia de Camino. (Mencionado brevemente, se basa en la representación de grafos).
        

---

# **Parte 3: Métodos Incompletos / Metaheurísticas (Clases 24-03 a 07-04)**

Enfoque en encontrar buenas soluciones (cercanas al óptimo) eficientemente, sin garantías de optimalidad.

1. **Panorama de Metaheurísticas:**
    
    - **Estrategias de Búsqueda:**
        
        - **Constructivas:** Construyen soluciones incrementalmente (ej. Greedy).
            
        - **Perturbadoras (De Mejora):** Comienzan con una solución completa y la modifican iterativamente (ej. Hill Climbing, TS, SA).
            
    - **Enfoque de Búsqueda:**
        
        - **Basadas en Trayectoria:** Operan sobre una única solución a la vez (ej. HC, TS, SA, ILS).
            
        - **Basadas en Población:** Mantienen y evolucionan un conjunto de soluciones (ej. Algoritmos Genéticos, Optimización por Colonia de Hormigas, Optimización por Enjambre de Partículas - se verán más adelante).
            
    - **Exploración vs. Explotación:**
        
        - **Exploración (Diversificación):** Buscar ampliamente en el espacio de búsqueda para encontrar regiones prometedoras.
            
        - **Explotación (Intensificación):** Enfocar la búsqueda dentro de una región prometedora para encontrar la mejor solución allí.
            
        - **Balance:** Las metaheurísticas efectivas equilibran estos dos aspectos (a menudo exploran primero, luego explotan).
            
2. **Algoritmos Greedy y GRASP (Clase 24-03):**
    
    - **Greedy (Heurística Constructiva):**
        
        - **Concepto:** Toma la decisión localmente óptima en cada paso, esperando alcanzar un óptimo global (a menudo no lo hace). Visión "miope".
            
        - **Necesita:** Representación de la solución, Función de Evaluación (miope).
            
        - **Tipos:** Determinista (siempre el mismo resultado) vs. Estocástico (elecciones probabilísticas).
            
    - **GRASP (Greedy Randomized Adaptive Search Procedure):**
        
        - **Concepto:** Una metaheurística multi-arranque que combina construcción aleatorizada con refinamiento por búsqueda local.
            
        - **Proceso:**
            
            1. **Construcción:** Construir una solución usando un enfoque greedy aleatorizado. En lugar de elegir siempre el mejor elemento, crear una Lista Restringida de Candidatos (RCL - Restricted Candidate List) de buenos elementos y elegir uno al azar de la RCL.
                
            2. **Búsqueda Local:** Mejorar la solución construida usando un algoritmo de búsqueda local (como Hill Climbing).
                
            3. **Repetir:** Iterar los pasos 1 y 2 múltiples veces, manteniendo la mejor solución global encontrada.
                
        - **Beneficio:** Introduce diversidad a través de la aleatorización, supera algunas limitaciones del greedy puro.
            
3. **Hill Climbing (HC) (Clase 27-03):**
    
    - **Concepto:** El método más simple de búsqueda local, basado en trayectoria y perturbador. Explotación pura.
        
    - **Proceso:**
        
        1. Comenzar con una solución inicial (aleatoria o greedy).
            
        2. Generar el **vecindario** (soluciones alcanzables por un 'movimiento' - ej., intercambiar dos elementos, invertir un bit).
            
        3. Evaluar los vecinos usando la función objetivo.
            
        4. Moverse al mejor vecino si es mejor que la solución actual.
            
        5. Repetir hasta que no exista un vecino mejor (atascado en un **óptimo local**).
            
    - **Manejo de Infactibilidad:** Penalizar la función objetivo o usar mecanismos de reparación.
        
    - **Variantes:**
        
        - **Mejor-Mejora (Best-Improvement):** Evaluar todos los vecinos, elegir el que mejora más.
            
        - **Alguna-Mejora (First-Improvement):** Elegir el primer vecino encontrado que mejora la solución (más rápido por paso si el vecindario es grande).
            
    - **Problema:** Se atasca fácilmente en óptimos locales.
        
    - **HC con Reinicios (Restarts):** Cuando se atasca, reiniciar desde una nueva solución inicial aleatoria. Ayuda a encontrar diferentes óptimos locales, potencialmente el global. Pierde el historial de búsqueda.
        
4. **Búsqueda Tabú (TS - Tabu Search) (Clase 31-03):**
    
    - **Concepto:** Una mejora de HC que permite movimientos que empeoran la solución para escapar de óptimos locales, mientras usa memoria para evitar ciclos.
        
    - **Mecanismo:**
        
        - **Lista Tabú:** Memoria a corto plazo (generalmente una cola FIFO) que almacena atributos de movimientos recientes (ej., el par de elementos intercambiados, el elemento movido). Los movimientos que involucran atributos tabú están prohibidos durante un cierto número de iteraciones (**Tenencia Tabú**).
            
        - **Proceso:** Similar a HC, pero selecciona el mejor vecino admisible (no tabú, o que cumple criterios de aspiración). Puede moverse a soluciones peores. Siempre rastrear la mejor solución global encontrada hasta ahora.
            
    - **Tenencia Tabú:** Controla el balance: Tenencia corta = más explotación, Tenencia larga = más exploración. Necesita ajuste.
        
    - **Criterios de Aspiración:** Reglas que anulan el estado tabú. Ejemplo común: Permitir un movimiento tabú si lleva a una solución mejor que la mejor-hasta-ahora encontrada.
        
    - **Beneficio:** Exploración más robusta que HC simple; forma sistemática de evitar ciclos a corto plazo.
        
5. **Recocido Simulado (SA - Simulated Annealing) (Clase 03-04):**
    
    - **Concepto:** Método basado en trayectoria inspirado en el recocido en metalurgia. Permite probabilísticamente movimientos que empeoran la solución para escapar de óptimos locales, reduciendo gradualmente esta probabilidad.
        
    - **Mecanismo:**
        
        - **Temperatura (T):** Parámetro de control. Comienza alta, disminuye gradualmente.
            
        - **Probabilidad de Aceptación:** Los movimientos que empeoran (delta_E > 0 para minimización) se aceptan con probabilidad P = exp(-delta_E / T). Los movimientos que mejoran siempre se aceptan.
            
        - **Proceso:**
            
            1. Comenzar con una solución inicial y temperatura alta T.
                
            2. Generar un vecino.
                
            3. Calcular el cambio en el objetivo delta_E.
                
            4. Si delta_E <= 0 (mejora o igual), aceptar el vecino.
                
            5. Si delta_E > 0 (empeora), aceptar con probabilidad P.
                
            6. Repetir los pasos 2-5 durante un número de iteraciones (bucle interno - alcanzar equilibrio).
                
            7. Disminuir la temperatura T (**Esquema de Enfriamiento**).
                
            8. Repetir los pasos 2-7 hasta el criterio de parada (ej., T es muy baja, límite de tiempo).
                
    - **Componentes Clave:** Ingredientes de HC + Función de Aceptación + T inicial/final + Esquema de Enfriamiento (ej., Geométrico: T = alpha * T, 0 < alpha < 1).
        
    - **Beneficio:** Bueno para escapar de óptimos locales; converge probabilísticamente al óptimo global bajo condiciones teóricas (enfriamiento muy lento).
        
6. **Otros Métodos de Trayectoria (Clase 07-04):**
    
    - **Búsqueda Local Iterada (ILS - Iterated Local Search):**
        
        - **Concepto:** Aplica iterativamente búsqueda local y perturbación.
            
        - **Proceso:** Encontrar óptimo local -> Perturbar solución (alejarla) -> Aplicar búsqueda local desde el nuevo punto -> Usar un Criterio de Aceptación para decidir si continuar desde el nuevo óptimo local o revertir al anterior. Equilibra intensificación (búsqueda local) y diversificación (perturbación). La fuerza de la perturbación es clave.
            
    - **Búsqueda de Vecindario Amplio (LNS - Large Neighborhood Search):**
        
        - **Concepto:** Explora un vecindario grande destruyendo y reparando parcialmente la solución actual.
            
        - **Proceso:** Solución inicial -> Destruir (eliminar estocásticamente parte de la solución) -> Reparar (reconstruir la parte faltante, a menudo usando una heurística o método exacto en el subproblema) -> Criterio de Aceptación. Define un vecindario grande implícitamente a través de los operadores de destruir/reparar.
            

---

# **Parte 4: Metodología Experimental (Discutido con Tarea 2 y a lo largo del curso)**

Crucial para validar cualquier algoritmo o técnica propuesta.

1. **Objetivo de Validación:** Proporcionar evidencia cuantitativa del rendimiento. Comparar contra el estado del arte o métodos base.
    
2. **Configuración:**
    
    - **Benchmarks:** Instancias de problemas estandarizadas de la literatura o instancias generadas bien definidas. Dificultad variable.
        
    - **Entorno:** Condiciones de hardware y software consistentes para todos los experimentos.
        
3. **Ejecución:**
    
    - **Múltiples Ejecuciones:** Esencial para algoritmos estocásticos (ej., 30+ ejecuciones por instancia) para capturar el rendimiento típico y la variabilidad.
        
4. **Métricas:**
    
    - **Exactos:** Número de nodos explorados, tiempo de CPU, uso de memoria.
        
    - **Incompletos:** Calidad de la solución (valor objetivo - promedio, mejor, desv. estándar), tiempo de CPU, número de iteraciones/evaluaciones.
        
5. **Ajuste de Parámetros:** Probar sistemáticamente diferentes valores de parámetros (ej., Tenencia Tabú, alpha de SA, tamaño de población) para encontrar buenas configuraciones. Técnicas incluyen búsqueda en grilla, búsqueda aleatoria, ajustadores automáticos.
    
6. **Comparación y Análisis:**
    
    - **Pruebas Estadísticas:** Usar pruebas apropiadas (ej., t-test, U de Mann-Whitney/Wilcoxon rank-sum) para determinar si las diferencias de rendimiento son estadísticamente significativas.
        
    - **Visualización:** Usar tablas y gráficos (gráficos de convergencia, diagramas de caja/box plots) eficazmente. Asegurarse de que sean complementarios, no redundantes.
        
    - **Interpretación:** Discutir por qué el algoritmo funciona bien/mal. Relacionar el rendimiento con las características del algoritmo y del problema. Establecer claramente las contribuciones.
        

---

**Repaso del Curso ("El Repaso"):**

- ¿Características de CSP/COP? (Variables, Dominios, Restricciones, +/- Objetivos)
    
- Técnicas Completas vs. Incompletas: ¿Cuándo usar cada una? ¿Limitaciones? (Optimalidad vs. Escalabilidad)
    
- Técnicas Completas: Ejemplos (BT, CBJ, FC) y ¿Cómo funcionan? (Búsqueda en árbol, consistencia, look-back/ahead)
    
- Técnicas Incompletas: ¿Constructivas vs. Perturbación? ¿Trayectoria vs. Población? (Cómo exploran el espacio)
    
- Incompletas (Trayectoria): Ejemplos (Greedy, GRASP, HC, TS, SA, ILS, LNS) y ¿Cómo funcionan? (Movimientos locales, memoria, probabilidad, perturbación, destruir/reparar)




# TABLAS RESUMEN
**Tabla 1: Conceptos Fundamentales y Tipos de Problemas**

| Concepto/Término                   | Definición / Descripción Breve                                                                                                     | Características Clave / Ejemplo                                                                                                                             |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Problema**                       | Una pregunta a resolver o una tarea a realizar que requiere encontrar una configuración, asignación o valor.                       | Puede ser de optimización, satisfacción, decisión, etc.                                                                                                     |
| **Modelo**                         | Representación formal y simplificada de un problema.                                                                               | Incluye variables, dominios, restricciones y (opcionalmente) función objetivo.                                                                              |
| **Variables**                      | Incógnitas del problema cuyos valores necesitamos determinar.                                                                      | Ej: Altura (h), Radio (r) de una lata; Asignación de tarea a máquina (X_ij).                                                                                |
| **Dominios**                       | Conjunto de posibles valores que puede tomar cada variable.                                                                        | Discretos (ej: {Rojo, Verde, Azul}, {0, 1}) o Continuos (ej: h > 0).                                                                                        |
| **Restricciones**                  | Condiciones que deben cumplir las variables para que una solución sea válida (factible).                                           | Igualdad (ej: Volumen = 128), Desigualdad (ej: Peso <= 22kg). Pueden ser unarias, binarias, n-arias.                                                        |
| **Función Objetivo (F.O.)**        | Criterio para medir la "calidad" de una solución factible. Se busca minimizar o maximizar.                                         | Ej: Minimizar Costo, Maximizar Ganancia, Minimizar Distancia. Puede haber una (mono-objetivo) o varias (multi-objetivo).                                    |
| **Solución Factible**              | Asignación de valores a todas las variables que satisface todas las restricciones.                                                 | Una configuración válida del problema.                                                                                                                      |
| **Solución Infactible**            | Asignación de valores que viola al menos una restricción.                                                                          | Una configuración inválida.                                                                                                                                 |
| **Espacio de Búsqueda**            | Conjunto de todas las posibles asignaciones de valores a las variables (factibles e infactibles).                                  | El "universo" donde buscamos la(s) solución(es). Su tamaño puede ser enorme.                                                                                |
| **COP (Opt. con Restricciones)**   | Problema con Variables, Dominios, Restricciones y **Función Objetivo**. Busca la mejor solución factible.                          | Ej: Problema de la Mochila, TSP (Traveling Salesperson Problem).                                                                                            |
| **CSP (Satisf. de Restricciones)** | Problema con Variables, Dominios y Restricciones, pero **SIN Función Objetivo**. Busca una o todas las soluciones factibles.       | Ej: N-Reinas, Coloreado de Mapas, Sudoku. Las soluciones no se comparan por calidad.                                                                        |
| **Complejidad P**                  | Problemas resolubles en **tiempo polinomial** por un algoritmo determinista.                                                       | Considerados "fáciles" computacionalmente. Ej: Ordenación, Búsqueda del camino más corto (Dijkstra).                                                        |
| **Complejidad NP**                 | Problemas cuya solución puede ser **verificada** en tiempo polinomial. Incluye a P.                                                | No se sabe si todos los problemas NP pueden resolverse en tiempo polinomial (P vs NP).                                                                      |
| **Complejidad NP-Completo**        | Los problemas "más difíciles" dentro de NP. Si uno se resuelve en P, todos en NP se resuelven en P.                                | Muchos COPs y CSPs comunes son NP-Completos/NP-Hard. Ej: TSP, SAT (Satisfacibilidad Booleana), Coloreado de Grafos.                                         |
| **Heurística**                     | Técnica específica del problema, rápida, "regla práctica", que guía la búsqueda pero **no garantiza optimalidad**.                 | Ej: En TSP, "siempre ir a la ciudad no visitada más cercana". Barata computacionalmente.                                                                    |
| **Metaheurística**                 | Estrategia de búsqueda de **propósito general**, de alto nivel, que guía a heurísticas subsidiarias. **No garantiza optimalidad**. | Aplicable a una amplia gama de problemas (NP-Hard). Busca buenas soluciones en tiempo razonable. Requiere ajuste de parámetros. Ej: SA, TS, Alg. Genéticos. |

---

**Tabla 2: Algoritmos Exactos (Basados en Búsqueda en Árbol)**

| Técnica                          | Concepto Principal                                                                                                         | Pseudocódigo Simplificado / Pasos Clave                                                                                                                             | Ventajas                                                                   | Desventajas/Costos                                                                       | ¿Cuándo Usar?                                                                       |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Búsqueda en Árbol**            | Exploración sistemática del espacio de búsqueda representado como árbol (estados y acciones).                              | Nodos = Estados (asignaciones parciales), Ramas = Acciones (asignar valor).                                                                                         | Base para algoritmos completos.                                            | El tamaño del árbol puede ser exponencial.                                               | Base conceptual.                                                                    |
| **Backtracking (BT)**            | DFS (Búsqueda en Profundidad) simple. Retrocede cronológicamente al fallar una restricción.                                | BT(asignacion):<br> Si asignacion_completa Y factible -> guardar<br> Para cada valor v de variable_actual:<br> Si consistente(asignacion + v) -> BT(asignacion + v) | Simple de implementar. Completo (encuentra sol. si existe).                | **Thrashing** (fallos repetidos por mala decisión temprana). Ineficiente.                | Problemas pequeños, como base o comparación.                                        |
| **Backjumping (BJ)**             | Retrocede a la variable causante del conflicto, no necesariamente la anterior.                                             | Similar a BT, pero al fallar, identifica la variable más profunda en conflicto y salta allí.                                                                        | Reduce algo de Thrashing comparado con BT. Completo.                       | Aún puede ser ineficiente. Determinar la causa puede tener costo.                        | Mejora sobre BT simple.                                                             |
| **CBJ (BJ Dirigido por Confl.)** | Mantiene "conjuntos de conflicto" para cada variable. Salta a la variable más reciente del conflicto.                      | Al fallar xi, calcula Conf(xi). Retrocede a la variable más reciente en Conf(xi).                                                                                   | Reduce significativamente el Thrashing. Más eficiente que BJ/BT. Completo. | Requiere **memoria extra** para los conjuntos de conflicto. Más complejo de implementar. | Cuando la memoria no es una limitación extrema y se busca eficiencia en la poda.    |
| **Forward Checking (FC)**        | Al asignar xi = a, elimina valores inconsistentes de los dominios de variables futuras xj.                                 | Asignar(xi=a):<br> Para cada xj futura conectada a xi:<br> Eliminar v de Dom(xj) si inconsistente(xi=a, xj=v)<br> Si Dom(xj) vacio -> Fallar/Retroceder             | **Detecta fallos antes**. Poda el árbol más eficazmente. Completo.         | **Mayor costo por nodo** (verificaciones hacia adelante).                                | Cuando el costo de la propagación de restricciones es menor que el ahorro en nodos. |
| **MFC (Minimal FC)**             | Variante "perezosa" de FC. Para una variable futura xj, detiene la verificación tan pronto encuentra un valor consistente. | Similar a FC, pero la verificación de dominios futuros es menos exhaustiva inicialmente.                                                                            | Menos costo por nodo que FC. Detecta fallos antes que BT. Completo.        | Menos poda que FC completo en algunos casos.                                             | Buen compromiso entre FC y BT en algunos problemas.                                 |
| **Heurísticas de Orden**         | Estrategias para decidir qué variable asignar a continuación y qué valor probar primero.                                   | **Variable:** MRV (Min Remaining Values), Grado (Deg), Dom/Deg (Fail-First). <br> **Valor:** LCV (Least Constraining Value) (Succeed-First).                        | Pueden **reducir drásticamente** el tamaño del árbol explorado.            | Calcular la heurística tiene un costo (generalmente bajo).                               | ¡Casi siempre! Mejoran mucho el rendimiento de los algoritmos exactos.              |

---

**Tabla 3: Metaheurísticas - Conceptos Generales y Constructivas**

| Concepto/Técnica                  | Descripción                                                                                                  | Características / Ejemplo                                                                                                                                                                          | Pseudocódigo Simplificado / Pasos Clave                                                                                                                                                                                           |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Metaheurística (General)**      | Estrategia de alto nivel para guiar una búsqueda heurística, buscando buenas soluciones en tiempo razonable. | No garantiza optimalidad. Usada para problemas NP-Hard.                                                                                                                                            | -                                                                                                                                                                                                                                 |
| **Exploración (Diversificación)** | Buscar ampliamente en diferentes regiones del espacio de búsqueda.                                           | Evita quedarse atascado prematuramente. Objetivo: Encontrar regiones prometedoras.                                                                                                                 | -                                                                                                                                                                                                                                 |
| **Explotación (Intensificación)** | Buscar profundamente dentro de una región considerada prometedora.                                           | Refina soluciones en áreas buenas. Objetivo: Encontrar el mejor punto en la región actual.                                                                                                         | -                                                                                                                                                                                                                                 |
| **Balance Expl./Explot.**         | Combinación efectiva de ambas estrategias.                                                                   | Crucial para el buen rendimiento. A menudo se explora más al inicio y se explota más al final.                                                                                                     | -                                                                                                                                                                                                                                 |
| **Estrategia Constructiva**       | Construye una solución desde cero, añadiendo componentes iterativamente.                                     | No necesita solución inicial. Maneja soluciones parciales. Ej: Greedy.                                                                                                                             | -                                                                                                                                                                                                                                 |
| **Estrategia Perturbadora**       | Empieza con una solución completa y la modifica (perturba) iterativamente.                                   | Necesita solución inicial. Maneja soluciones completas. Ej: HC, TS, SA.                                                                                                                            | -                                                                                                                                                                                                                                 |
| **Búsqueda por Trayectoria**      | Mantiene y modifica una solución candidata a lo largo del tiempo.                                            | HC, TS, SA, ILS, LNS.                                                                                                                                                                              | -                                                                                                                                                                                                                                 |
| **Búsqueda Basada en Población**  | Mantiene y evoluciona un conjunto (población) de soluciones candidatas.                                      | Algoritmos Genéticos, Colonias de Hormigas, Enjambre de Partículas (se verán después).                                                                                                             | -                                                                                                                                                                                                                                 |
| **Algoritmo Greedy**              | Heurística constructiva. En cada paso, toma la decisión que parece mejor localmente (miope).                 | Rápido, simple. A menudo subóptimo. Puede ser determinista o estocástico.                                                                                                                          | Sol = {}<br> Mientras Sol no completa:<br> c = Elegir_mejor_componente_local()<br> Añadir c a Sol<br> Devolver Sol                                                                                                                |
| **GRASP**                         | Metaheurística multi-arranque: Fase de Construcción (Greedy Aleatorizado) + Fase de Búsqueda Local (Mejora). | 1. **Construcción:** Crear RCL (Lista Restringida Candidatos) de los mejores elementos, elegir uno al azar, repetir. <br> 2. **Mejora:** Aplicar Búsqueda Local (ej. HC) a la solución construida. | MejorSolGlobal = NULL<br> Para i=1 to MaxIter:<br> SolConst = Construccion_Greedy_Aleatoria(RCL)<br> SolMejorada = Busqueda_Local(SolConst)<br> Si SolMejorada mejor que MejorSolGlobal -> Actualizar<br> Devolver MejorSolGlobal |

---

**Tabla 4: Metaheurísticas - Basadas en Trayectoria (Perturbadoras/De Mejora)**

| Técnica                          | Concepto Principal                                                                                 | Componentes Clave                                                                                                    | Pseudocódigo Simplificado / Pasos Clave                                                                                                                                                                                                                                                                                                                                                      | Fortalezas                                                                                          | Debilidades / Consideraciones                                                                                                           |
| -------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **Hill Climbing (HC)**           | Búsqueda local simple. Se mueve al mejor vecino si mejora la solución actual. Explotación pura.    | Solución inicial, Vecindario/Movimiento, F. Objetivo.                                                                | SolActual = SolInicial<br> Repetir:<br> MejorVecino = Mejor_Vecino(SolActual)<br> Si FO(MejorVecino) mejora FO(SolActual):<br> SolActual = MejorVecino<br> Sino: Terminar<br> Devolver SolActual                                                                                                                                                                                             | Simple, rápido (por iteración).                                                                     | **Se atasca en óptimos locales**. Muy sensible a la solución inicial.                                                                   |
| **HC con Reinicios**             | Reinicia HC desde una nueva solución aleatoria cuando se atasca.                                   | HC + Mecanismo de Reinicio Aleatorio.                                                                                | Ejecutar HC múltiples veces desde inicios aleatorios, guardar la mejor solución encontrada globalmente.                                                                                                                                                                                                                                                                                      | Puede encontrar mejores óptimos locales (potencialmente el global). Simple de implementar sobre HC. | Pierde información entre reinicios. No hay garantía de mejora significativa. Puede ser ineficiente si los reinicios son frecuentes.     |
| **Búsqueda Tabú (TS)**           | HC mejorado. Permite movimientos que empeoran. Usa memoria (Lista Tabú) para evitar ciclos cortos. | HC + Lista Tabú (memoria corto plazo, FIFO) + Tenencia Tabú + Criterio Aspiración (opcional) + Mejor Solución Global | SolActual = SolInicial; MejorSol = SolActual<br> ListaTabu = {}<br> Mientras no CriterioParada:<br> Candidatos = Vecinos(SolActual) no_tabu O cumplen_aspiracion<br> SolSiguiente = Mejor_Vecino(Candidatos)<br> Actualizar ListaTabu con mov(SolActual -> SolSiguiente)<br> SolActual = SolSiguiente<br> Si FO(SolActual) mejora FO(MejorSol) -> MejorSol = SolActual<br> Devolver MejorSol | Robusto para escapar óptimos locales. Explora más sistemáticamente que HC.                          | Requiere **ajuste de parámetros** (Tenencia Tabú). Más complejo que HC. La memoria puede prohibir buenas soluciones (aspiración ayuda). |
| **Recocido Simulado (SA)**       | Permite movimientos que empeoran con una probabilidad que disminuye con la "Temperatura".          | HC + Temperatura (T) + Prob. Aceptación (ej. exp(-dE/T)) + Esquema Enfriamiento + Cond. Equilibrio (bucle interno)   | SolActual = SolInicial; MejorSol = SolActual; T = T_inicial<br> Mientras T > T_final:<br> Para i=1 to IteracionesPorTemp:<br> SolVecino = Vecino(SolActual)<br> dE = FO(SolVecino) - FO(SolActual)<br> Si dE < 0 O aleatorio() < exp(-dE/T):<br> SolActual = SolVecino<br> Si FO(SolActual) mejora FO(MejorSol) -> MejorSol = SolActual<br> T = Enfriar(T)<br> Devolver MejorSol             | Buena capacidad de escape de óptimos locales. Base teórica sólida (convergencia probabilística).    | Requiere **ajuste de parámetros** (T inicial, enfriamiento, iter/temp). Puede ser lento si el enfriamiento es muy gradual.              |
| **ILS (Búsqueda Local Iterada)** | Ciclo: Búsqueda Local -> Perturbación -> Búsqueda Local -> Aceptación.                             | Búsqueda Local (ej. HC), Perturbación (alejar la solución), Criterio de Aceptación (ej. Metropolis, siempre mejorar) | SolActual = Busqueda_Local(SolInicial)<br> MejorSol = SolActual<br> Mientras no CriterioParada:<br> SolPerturbada = Perturbar(SolActual)<br> SolNuevaLocal = Busqueda_Local(SolPerturbada)<br> SolActual = Criterio_Aceptacion(SolNuevaLocal, SolActual)<br> Actualizar MejorSol<br> Devolver MejorSol                                                                                       | Buen balance exploración/explotación. Efectivo en muchos problemas. Modular.                        | Requiere **ajuste de parámetros** (fuerza perturbación, criterio aceptación). Rendimiento depende de componentes BL y Perturbación.     |
| **LNS (Búsqueda Vec. Amplio)**   | Ciclo: Destruir parte de la solución -> Reparar la parte destruida -> Aceptación.                  | Operador Destruir (aleatorio), Operador Reparar (heurístico/exacto), Criterio Aceptación.                            | SolActual = SolInicialFactible<br> MejorSol = SolActual<br> Mientras no CriterioParada:<br> SolParcial = Destruir(SolActual)<br> SolNueva = Reparar(SolParcial)<br> Si Criterio_Aceptacion(SolNueva, SolActual):<br> SolActual = SolNueva<br> Actualizar MejorSol<br> Devolver MejorSol                                                                                                      | Explora vecindarios grandes eficazmente. Adaptable (operadores destruir/reparar específicos).       | Requiere **diseño de operadores** Destruir/Reparar. Requiere **ajuste de parámetros** (grado destrucción, criterio aceptación).         |

---

**Tabla 5: Metodología Experimental**

| Componente                 | Descripción / Objetivo                                                                             | Consideraciones Clave                                                                                                                                                           |
| -------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Propósito**              | Validar cuantitativamente el rendimiento de una propuesta (algoritmo, heurística, etc.).           | Comparar con estado del arte o baseline. Demostrar la contribución.                                                                                                             |
| **Benchmarks**             | Conjunto de instancias de prueba estandarizadas (o bien generadas).                                | Usar instancias conocidas si existen. Incluir variedad de tamaños y dificultades.                                                                                               |
| **Ejecuciones**            | Realizar múltiples ejecuciones para algoritmos estocásticos.                                       | Mínimo 30-50 ejecuciones por instancia para análisis estadístico robusto. Fijar semilla aleatoria para reproducibilidad si es necesario.                                        |
| **Métricas (Exactos)**     | Medidas de eficiencia y recursos.                                                                  | Tiempo CPU, Número de nodos explorados, Uso de memoria.                                                                                                                         |
| **Métricas (Incompletos)** | Medidas de calidad de solución y eficiencia.                                                       | Calidad: Mejor valor F.O., Promedio F.O., Desv. Estándar F.O., Gap (%) respecto al óptimo (si conocido). Eficiencia: Tiempo CPU, # Iteraciones, # Eval F.O.                     |
| **Ajuste Parámetros**      | Encontrar buenos valores para los parámetros del algoritmo (ej. Tenencia Tabú, Tasa Enfriamiento). | Realizar experimentos preliminares (ej. barrido paramétrico, diseño de experimentos) sobre un subconjunto de instancias. No ajustar sobre el test final.                        |
| **Comparación/Análisis**   | Determinar si las diferencias observadas son significativas y entender por qué ocurren.            | Usar **pruebas estadísticas** (t-test, Wilcoxon, ANOVA, etc.) para comparar medias/distribuciones. Analizar fortalezas y debilidades, explicar resultados.                      |
| **Visualización**          | Presentar resultados de forma clara y concisa.                                                     | Tablas resumen (promedios, desv. std). Gráficos: Convergencia (calidad vs tiempo/iter), Box plots (distribución de calidad), Trade-off (calidad vs tiempo). Evitar redundancia. |


# Control 1 Ejemplo
**1. (10 puntos) Explique claramente como la técnica Tabu-Search es capaz de explorar y explotar el espacio de búsqueda.**

- **Explotación (Intensificación):** Tabu Search explota el espacio de búsqueda de manera similar a Hill Climbing. En cada iteración, examina el vecindario de la solución actual (generado por operadores de movimiento) y tiende a seleccionar el "mejor" vecino según la función objetivo. Aunque TS puede aceptar movimientos que empeoran la solución, la selección del mejor vecino no tabú representa una intensificación de la búsqueda en la región actual. Un **Tamaño de lista Tabú corta** favorece la explotación, ya que permite volver a visitar regiones cercanas más rápidamente. Además, siempre se guarda la mejor solución global encontrada, lo cual es un elemento de explotación del conocimiento adquirido.
    
- **Exploración (Diversificación):** Tabu Search explora el espacio de búsqueda principalmente a través de dos mecanismos:
    
    - **Permitir Movimientos que Empeoran:** A diferencia de Hill Climbing simple, TS no se queda atascado en el primer óptimo local que encuentra, ya que puede moverse a vecinos con peor valor objetivo. Esto le permite salir optimos locales.
        
    - **Lista Tabú:** Este es el mecanismo clave de diversificación dirigida. Al prohibir movimientos recientes (o atributos asociados a ellos) durante un número de iteraciones (Tenencia Tabú), la lista fuerza a la búsqueda a tomar direcciones diferentes a las que acaba de tomar, evitando ciclos cortos y empujándola hacia regiones no exploradas recientemente del espacio de búsqueda. Una **Tamaño de lista Tabú larga** promueve una mayor exploración al prohibir volver a estados/regiones similares durante más tiempo.
        

**2. (10 puntos) Comente la siguiente aseveración: Una metaheurística no puede encontrar el óptimo global en problemas de optimización de la categoría NP-Difícil, pero una técnica completa si puede.**

La aseveración tiene partes correctas e incorrectas:

- **Parte Metaheurística ("...no puede encontrar el óptimo global..."):** Esta parte es **incorrecta** en su formulación absoluta. Una metaheurística podría encontrar el óptimo global por casualidad o si la búsqueda es guiada eficazmente. Sin embargo, la característica fundamental de las metaheurísticas es que **no ofrecen garantía** de encontrar el óptimo global. Están diseñadas para encontrar soluciones de muy buena calidad en un tiempo razonable, especialmente para problemas NP-Difíciles donde encontrar el óptimo garantizado es inviable. Por lo tanto, aunque no se puede afirmar que nunca lo encontrarán, no se puede asegurar que sí lo harán.
    
- **Parte Técnica Completa ("...pero una técnica completa si puede."):** Esta parte es **correcta en teoría**. Los algoritmos exactos o técnicas completas (como Backtracking, Branch & Bound) están diseñados para explorar sistemáticamente todo el espacio de búsqueda relevante y, por definición, **garantizan encontrar el óptimo global** si se les proporciona suficiente tiempo y memoria.
    
- **Contexto NP-Difícil:** La clave está en "suficiente tiempo y memoria". Para problemas NP-Difíciles, el tiempo requerido por una técnica completa a menudo crece exponencialmente con el tamaño del problema. Esto significa que, aunque teóricamente pueden encontrar el óptimo, en la práctica pueden ser **computacionalmente inviables** para instancias de tamaño realista, ya que requerirían tiempos astronómicos.
    

**Conclusión:** La aseveración simplifica demasiado. Las metaheurísticas no garantizan el óptimo (pero podrían hallarlo), mientras que las técnicas completas sí lo garantizan, pero pueden ser impracticables para problemas NP-Difíciles debido a requerimientos exponenciales de recursos.

**3. (10 puntos) ¿En qué consisten las heurísticas de selección de variable? ¿Qué impacto tienen en las técnicas completas?**

- **¿En qué consisten?:** Las heurísticas de selección de variable son estrategias o "reglas prácticas" utilizadas dentro de algoritmos de búsqueda completa (como Backtracking, Forward Checking, CBJ) para decidir **cuál variable no asignada elegir a continuación** para intentar asignarle un valor. No afectan la corrección o completitud del algoritmo subyacente, sino su eficiencia. Generalmente se basan en el principio "Fail-First", que sugiere elegir la variable que parece más restringida o que probablemente cause un fallo (violación de restricción) más temprano, para así podar el árbol de búsqueda lo antes posible.
    
    - **Ejemplos:**
        
        - **MRV (Minimum Remaining Values) / Dom:** Elegir la variable con el menor número de valores posibles restantes en su dominio actual.
            
        - **Grado (Degree Heuristic) / Deg:** Elegir la variable que participa en el mayor número de restricciones con otras variables aún no asignadas.
            
        - **Dom/Deg:** Elegir la variable que minimiza la relación (tamaño de dominio / grado).
            
- **¿Qué impacto tienen?:** Tienen un **impacto potencialmente enorme** en el rendimiento (eficiencia) de las técnicas completas. Un buen ordenamiento de variables puede reducir drásticamente el tamaño del árbol de búsqueda que necesita ser explorado, llevando a tiempos de ejecución órdenes de magnitud menores. Al identificar conflictos o callejones sin salida más temprano, se podan ramas enteras del árbol. Por el contrario, un mal ordenamiento puede llevar a un rendimiento cercano al de la fuerza bruta. Si bien no cambian la capacidad teórica de encontrar la solución óptima, sí determinan en gran medida si esa solución se puede encontrar en un tiempo práctico.
    

**4. (15 puntos) ¿Puede un problema del tipo CSP tener más de una formulación para su modelo, y que esto tenga incidencia en el tamaño del espacio de búsqueda? Explique. En caso de que su respuesta sea afirmativa, ejemplifique con un problema.**

**Sí**, un problema de tipo CSP (Constraint Satisfaction Problem) puede tener **múltiples formulaciones** para su modelo, y esta elección de formulación tiene una **incidencia directa y significativa** en el tamaño del espacio de búsqueda.

- **Explicación:** La formulación de un CSP implica definir las variables, sus dominios y las restricciones. Diferentes elecciones sobre qué representa una variable y cuáles son sus posibles valores pueden llevar a modelos equivalentes (que representan el mismo problema subyacente) pero con características muy distintas. Algunas formulaciones pueden incorporar implícitamente ciertas restricciones en la definición de las variables o dominios, mientras que otras las dejan como restricciones explícitas a verificar. Una formulación que resulta en menos variables o dominios más pequeños (o ambos) generalmente conducirá a un espacio de búsqueda más pequeño.
    
- **Ejemplo: Problema de las N-Reinas** (Clásico ejemplo visto en clase)
    
    - **Formulación 1:**
        
        - **Variables:** Q_i, donde i va de 1 a N (una variable por cada reina).
            
        - **Dominio para cada Q_i:** Las N² casillas del tablero (ej., representadas por pares (fila, columna) o un número del 1 al N²).
            
        - **Restricciones:** Explícitas para no ataque horizontal, vertical y diagonal entre todas las parejas de reinas Q_i y Q_j.
            
        - **Tamaño Espacio de Búsqueda:** (N²) ^ N. Para N=4, es 16⁴ = 65,536.
            
    - **Formulación 2 (Más eficiente):**
        
        - **Variables:** R_i, donde i va de 1 a N (una variable por cada columna, representando la fila donde se coloca la reina en esa columna). Se asume implícitamente que solo habrá una reina por columna.
            
        - **Dominio para cada R_i:** Las N filas posibles {1, 2, ..., N}.
            
        - **Restricciones:**
            
            - No ataque horizontal: R_i ≠ R_j para todo i ≠ j.
                
            - No ataque diagonal: |R_i - R_j| ≠ |i - j| para todo i ≠ j.
                
            - (La restricción vertical está implícita en la definición de variables).
                
        - **Tamaño Espacio de Búsqueda:** N ^ N. Para N=4, es 4⁴ = 256.
            
    
    Como se ve en el ejemplo, la Formulación 2 reduce drásticamente el tamaño del espacio de búsqueda (de 65,536 a 256 para N=4) al codificar una de las restricciones (una reina por columna) directamente en la definición de las variables. Esto hace que la búsqueda sea mucho más eficiente.

5. Con respecto a la presentación del invitado: ¿En qué se diferencia la estrategia greedy con la A⋆ para el CPMP?
	**Diferencia Principal:** Greedy es miope y local, optimiza solo el siguiente paso. A* es informado y global, optimiza combinando el costo real pasado (g(n)) con una estimación del costo futuro (h(n)) para garantizar (bajo condiciones de admisibilidad) la optimalidad del camino completo.
# Control 2 Ejemplo
**1. (15 puntos) Considere un problema NP-Difícil de optimización discreta, dominios binarios {0, 1}. 5 instancias: 3 con 10 variables, 2 con 60 variables. Tiempo total: 12 horas. Verificación/asignación completa: 1 segundo. Resolver una instancia a la vez. Sin usar greedy. ¿Cómo abordar la problemática?**

Este problema presenta una clara división entre instancias pequeñas y grandes, con una limitación de tiempo significativa. La estrategia debe adaptarse a esta realidad:

- **Análisis Instancias Pequeñas (10 variables):**
    
    - Espacio de búsqueda: 2¹⁰ = 1024 asignaciones.
        
    - Tiempo de verificación exhaustiva (peor caso si no hay poda): 1024 segundos ≈ 17 minutos por instancia.
        
    - Total para 3 instancias: ≈ 51 minutos.
        
    - **Conclusión:** Estas instancias son **factibles** de resolver utilizando **técnicas completas (exactas)** dentro del tiempo disponible. Estas técnicas garantizan encontrar la solución óptima.
        
- **Análisis Instancias Grandes (60 variables):**
    
    - Espacio de búsqueda: 2⁶⁰ ≈ 1.15 x 10¹⁸ asignaciones.
        
    - Tiempo de verificación exhaustiva: ≈ 1.15 x 10¹⁸ segundos. Esto equivale a miles de millones de años.
        
    - **Conclusión:** Estas instancias son **computacionalmente inviables** para cualquier técnica completa/exacta dentro del límite de 12 horas (o cualquier marco temporal práctico).
        
- **Estrategia Propuesta:**
    
    1. **Para las 3 instancias de 10 variables:** Utilizar un **algoritmo exacto**. Dado que son binarias y de optimización, **Branch and Bound** sería una opción adecuada. Alternativamente, un **Backtracking** optimizado (quizás con heurísticas de ordenamiento o propagación como Forward Checking si hay restricciones claras) también funcionaría. El objetivo aquí es obtener la **solución óptima garantizada**, ya que el tiempo lo permite. Se podría asignar un tiempo máximo por instancia (ej. 20-30 minutos) para asegurar que no se exceda.
        
    2. **Para las 2 instancias de 60 variables:** Utilizar una **Metaheurística**. Dado que los algoritmos greedy están explícitamente excluidos, las opciones vistas en clase son:
        
        - Hill Climbing con Reinicios (HC+Restart)
            
        - Búsqueda Tabú (TS)
            
        - Recocido Simulado (SA)
            
        - Búsqueda Local Iterada (ILS)
            
        - Búsqueda de Vecindario Amplio (LNS)  
            La elección entre ellas dependería de la estructura específica del problema (no dada), pero cualquiera de ellas es un candidato válido. El objetivo aquí es encontrar una **solución de muy buena calidad** dentro del tiempo disponible (aproximadamente (12 horas - 1 hora) / 2 ≈ 5.5 horas por instancia). Se necesitaría definir operadores de movimiento/vecindario apropiados para dominios binarios (ej. flip de un bit, swap de bits).
            
- **Justificación:** Esta estrategia híbrida aprovecha la garantía de optimalidad de los métodos exactos donde son factibles (instancias pequeñas) y recurre a la eficiencia de las metaheurísticas para obtener buenas soluciones en un tiempo razonable donde los métodos exactos fallan (instancias grandes). Se respeta la restricción de no usar greedy explícitamente como algoritmo principal (aunque una metaheurística podría usar un greedy internamente para generar una solución inicial o reparar, pero las mencionadas no lo requieren fundamentalmente).
    

**4. (14 puntos) Indique la diferencia sustancial en cómo los algoritmos Tabú Search y Simulated Annealing escapan de óptimos locales.**

La diferencia sustancial radica en el **mecanismo fundamental** que utilizan para permitir movimientos a soluciones peores y así salir de óptimos locales:

- **Tabú Search (TS):** Escapa de óptimos locales mediante el uso de **memoria determinista a corto plazo (Lista Tabú)**. Permite movimientos que empeoran la solución, pero prohíbe activamente revertir movimientos recientes (o usar atributos asociados a ellos) durante un período (Tenencia Tabú). Este mecanismo dirige la búsqueda fuera del óptimo local al forzarla a explorar vecinos que no han sido visitados recientemente o que no usan componentes "tabú". Es un escape **basado en el historial** y **determinista** (dado el estado y la lista tabú, el conjunto de movimientos permitidos está definido).
    
- **Recocido Simulado (SA):** Escapa de óptimos locales mediante un **criterio de aceptación probabilístico controlado por la Temperatura (T)**. También permite movimientos que empeoran, pero la decisión de aceptar uno se toma al azar, con una probabilidad (exp(-dE/T)) que depende de cuánto empeora la solución (dE) y del estado global del sistema (la Temperatura T). No utiliza memoria de movimientos específicos pasados para prohibir algo, sino que la probabilidad de aceptar malos movimientos disminuye gradualmente a medida que T baja. Es un escape **probabilístico** y **controlado por un parámetro global que evoluciona en el tiempo**.
    

**En esencia:** TS usa **memoria histórica** para dirigir el escape, mientras que SA usa **probabilidad controlada por temperatura**.