# Patrones de Arquitectura
### Solución de Diseño a una Necesidad
Un patrón de arquitectura proporciona una solución de diseño reutilizable y probada para abordar una necesidad específica en el desarrollo de software.
### Características
- **Esquema genérico:** Los patrones ofrecen una solución abstracta y generalizable que puede ser aplicada en diversos contextos.
- **Probado:** Han sido validados en múltiples proyectos y escenarios, demostrando su eficacia.
- **Recurrente:** Se utilizan repetidamente para resolver problemas similares.
### Especificación
- **Componentes:** Definición de las partes individuales que componen la solución.
- **Responsabilidades:** Asignación clara de las funciones y responsabilidades de cada componente.
- **Relaciones:** Descripción de cómo interactúan los componentes entre sí.
# Descripción de un Patrón
### Nombre del Patrón
Cada patrón tiene un nombre específico que lo identifica y describe su propósito.
### Contexto
- **Situación que origina la necesidad:** Identificación del problema o situación que crea la demanda del patrón.
- **Ámbito de la necesidad:** Contexto general donde surge la necesidad del patrón.
- **Descripción de las situaciones que la originan:**
    - **Descripción general:** Visión amplia del contexto y el problema.
    - **Descripción detallada:** Análisis más profundo y específico de las circunstancias que requieren la solución.
### Requerimiento
- **Descripción genérica de la necesidad:** Definición amplia del problema a resolver.
- **Define lo que se debe resolver:** Establecimiento de objetivos y resultados esperados.
- **Fuerzas presentes en el contexto:**
    - **Propiedades:** Características inherentes al problema.
    - **Requisitos:** Necesidades que deben ser satisfechas.
    - **Restricciones:** Limitaciones que deben ser consideradas.
### Solución
- **Esquema de solución de la necesidad:** Propuesta de solución para abordar el problema identificado.
- **Balance de fuerzas:** Equilibrio entre las distintas fuerzas presentes en el contexto.
- **Estructura:**
    - **Componentes:** Elementos de la solución.
    - **Relaciones:** Interacciones entre los componentes.
- **Comportamiento:**
    - **Organización de componentes:** Cómo se estructuran y funcionan los componentes en conjunto.
- **Priorización de fuerzas:** Ordenación de las fuerzas según su importancia y impacto en la solución.
# Clasificación de patrones 
## 1. Patrones simples
### A. Capas (Layers)
- **Estructura:** Aplicaciones descompuestas en tareas con diferentes niveles de abstracción.
- **Contexto:** Sistemas estructurados con diversos niveles de acción.
- **Requerimiento:** organización inadecuada genera problemas de escalabilidad y mantenibilidad
- **Solución:** Estructuración en esquema multi-capa.
	- **Características:**
		- La capa K se relaciona solamente con la capa K-1.
		- No hay otras dependencias entre capas.
		- Cada capa puede estar integrada por distintos componentes.
		- Los componentes pueden interactuar entre sí, pero quedan acoplados.
		- Cada capa expone una interfaz con los servicios que provee.
		- El comportamiento puede ser top-down o bottom-up.
	- **Implementación:**
		- Determinar el número de capas según el nivel de abstracción requerido.
		- Asignar responsabilidades a cada capa.
		- Especificar los servicios ofrecidos por cada capa.
		- Definir la estructura de cada capa.
		- Especificar la interfaz de cada capa.
		- Especificar el método de comunicación intercapas.
		- Definir el esquema para el manejo de errores.
	- **Análisis:**
		- **Ventajas:**
		    - Componentes estandarizados.
		    - Cambios afectan el nivel local.
		    - Reutilización de capas/componentes.
		- **Desventajas:**
		    - Cambios afectan en cascada.
		    - Ineficiencia.
		    - Complejo de definir.
### B. Tubos y filtros (Pipes and Filters)
- **Estructura:** Aplicaciones en actividades para procesar flujos de datos donde cada actividad es un filtro unido por un tubo a los filtros contiguos.
- **Contexto:** Procesar flujos de datos.
- **Requerimiento:**
	- Descomponer el procesamiento en una serie de actividades (filtros) que transforman datos de entrada en datos de salida.
	- Transformaciones independientes y sin estado.
- **Solución:**
	- **Tubos (pipes):**
	    - Conecta origen de datos con un filtro, filtro con filtro, y filtro con salida de datos.
	    - Esquema de procesamiento FIFO.
	- **Filtros (filters):**
	    - Aplica procesos de transformación de datos de entrada en datos de salida.
	    - Filtros independientes sin estado compartido y desconocimiento de otros filtros.
	- **Implementación:**
	    - Dividir el sistema en una secuencia de procesos ordenados e independientes.
	    - Definir el formato de los datos transmitidos por los tubos.
	    - Especificar el procesamiento de cada filtro.
	    - Construir los filtros.
	    - Definir el esquema para el manejo de errores.
	- **Análisis:**
	    - **Ventajas:**
	        - Arquitectura flexible.
	        - No requiere de archivos intermedios.
	        - Filtros reutilizables.
	        - Procesamiento paralelo.
	        - Construcción independiente.
	    - **Desventajas:**
	        - Información no compartida.
	        - Conversión de datos (ineficiencia).
	        - Errores pueden afectar el flujo de procesamiento.
### C. Pizarrón
- Patrón útil cuando no hay una solución completa y específica para un problema, participan varios sistemas que aportan su conocimiento. Ejemplos: inteligencia artificial, reconocimiento de imágenes, toma de decisiones.
- **Contexto:** Dominio en el que no hay una solución completa y específica para un problema.
- **Problema:** Conocimiento parcial de la solución, cada solución requiere diferentes paradigmas, el problema abarca muchas especialidades, no es factible una solución completa, módulos aportan parcialmente a la solución.
- **Solución:** Conjunto de sistemas independientes trabajando colaborativamente, datos compartidos en un repositorio centralizado, control centralizado que coordina la ejecución de los sistemas, sistemas especializados independientes leen y escriben en el pizarrón, monitoreo centralizado del estado del sistema, decisión centralizada de las acciones a seguir basada en el progreso alcanzado.
- **Ventajas:** Flexibilidad para incorporar diversas perspectivas y paradigmas, facilita la contribución de múltiples expertos en diversos campos, divide un problema grande en problemas más pequeños y manejables, permite la integración de soluciones parciales para obtener una solución más completa.
- **Desventajas:** Coordinación compleja entre múltiples sistemas, riesgo de generar soluciones parciales que no se integran bien en el conjunto, puede requerir gran ancho de banda y recursos de computación para gestionar la comunicación y los datos, más orientado a la investigación, puede carecer de aplicaciones comerciales directas.
- **Caso de uso:** Reconocimiento de patrones complejos, como el reconocimiento de voz. Pizarrón: Repositorio central donde los distintos agentes pueden leer y escribir. Contiene la grabación de la voz, las características extraídas, las hipótesis parciales sobre el contenido hablado, y la transcripción final. Knowledge Sources: Cada agente observa el pizarrón y actúa cuando encuentra que puede contribuir a la solución. Extracción de características: Analiza la señal de audio para extraer características relevantes (frecuencias, amplitudes, etc.). Reconocimiento de fonemas: Utiliza las características extraídas para identificar fonemas individuales. Reconocimiento de palabras: Combina fonemas para formar palabras basadas en un diccionario. Análisis de contexto: Utiliza reglas gramaticales y de contexto para mejorar la precisión de la transcripción. Controlador: Gestiona la coordinación y la activación de los agentes de conocimiento. Supervisa el proceso, activando agentes según sea necesario, por ejemplo, primero ejecuta el agente de extracción de características, luego el de reconocimiento de fonemas, y así sucesivamente.
### D. Repositorio
## 2. Sistemas interactivos
### A. Modelo Vista Controlador (MVC)
- **Qué es**
	- El sistema se divide en tres partes: Modelo, Vista, y Controlador.
	- Modelo: Datos y funcionalidad esencial.
	- Vista: Comunicación con el usuario.
	- Controlador: Controla cambios al modelo.
	- Interfaz de usuario: Vista + Controlador.
	- Lógica del negocio: Controlador + Modelo.
	- Controlador desacopla la vista del modelo.
- **Contexto:** Sistemas interactivos con interfaz flexible.
- **Requerimiento:**
	- Interfaz con diferente representación.
		- Texto, gráficos, listas, iconos
	- Paradigmas de ingreso diversos.
		- Digitación: cajas de texto
		- Selección: listas desplegables, iconos
		- Ingreso mixto
	- Interfaz cambiante: mejora, evolución.
	- Facilidad de modificación de la interfaz.
	- Funcionalidad nueva implica modifica interfaz.
	- Presentación de la información en multi-formato.
- **Solución:**
	- Tres componentes:
		- **Comunicación (Vista):** Envía requerimientos del usuario y recibe datos del modelo.
		- **Administración (Controlador):** Define el comportamiento del sistema y solicita servicios al modelo.
		- **Procesamiento (Modelo):** Provee la funcionalidad requerida por las vistas.
	- **Implementación**
		- Separa la funcionalidad de la interacción del usuario
		- Diseñar e implementar el modelo, las vistas, los controladores, y las relaciones entre vistas y controladores.
	- **Análisis:**
		- **Ventajas:**
		    - Modelo soporta múltiples vistas.
		    - Flexible, mantenible, adaptable.
		    - Frameworks implementan MVC.
		- **Desventajas:**
		    - Modelo acoplado con vistas y controladores.
		    - Vistas sin acceso a los datos (ineficiencia).
		    - Complejidad.
### B. Presentación Abstracción Control (PAC)
- **Estructura:** Jerárquica de agentes cooperativos, cada uno responsable de una parte de la funcionalidad.
- **Contexto:** Sistemas interactivos desarrollados utilizando agentes.
- **Requerimiento:**
	- Estructurar un sistema interactivo mediante agentes funcionando de forma integrada.
	- Generar interfaces flexibles de usuario.
	- Separar la presentación de la funcionalidad.
- **Solución**
	- Definir estructura jerárquica de tres niveles de agentes.
	    - Alto nivel: Funcionalidad central del sistema.
	    - Bajo nivel: Manejo de interfaces específicas de usuarios.
	    - Intermedios: Relacionan agentes de bajo nivel.
	- Cada agente está compuesto por:
	    - **Presentación:** Aspecto visible del agente.
	    - **Abstracción:** Modelo de datos interno y operaciones sobre ellos.
	    - **Control:** Conexión entre presentación y abstracción, y comunicación con otros agentes.
	- **Implementación:**
		- Definir la funcionalidad central del sistema.
		- Estructurar la jerarquía de agentes.
		- Definir e implementar cada agente
			- Funcionalidad
			- Interfaz
			- Modelo de datos
			- Mecanismo de control
	- **Análisis:**
		- **Ventajas:**
		    - Asigna responsabilidades específicas.
		    - Funcionamiento independiente.
		    - Soporta multitarea.
		- **Desventajas:**
		    - Sistema complejo.
		    - Baja eficiencia.
		    - Complejo mecanismo de control.
## 3. Patrones adaptables
## 4. Sistemas distribuidos
# Ejercicios
### Ejercicio 1: Club de Golf ArquiGolf

El exclusivo club de golf ArquiGolf requiere un sistema para la captación e ingreso de socios. El proceso se inicia cuando un ejecutivo de Atención de Clientes contacta al futuro socio para evaluar si cumple con los requisitos para pertenecer al club. Si los cumple, el futuro socio procede a llenar el formulario de ingreso y lo envía al departamento de Validación de antecedentes. En caso de ser exitosa la validación de los antecedentes aportados por el futuro socio, el formulario es aprobado y enviado al departamento de Finanzas, en donde se calculan las cuotas de ingreso y mensual, las que son informadas al futuro socio. Este tiene un plazo de 2 días para pagar las cuotas iniciales (ingreso y primer mes) utilizando los medios de pago que tienen convenio con el club. Una vez efectuado el pago, el proceso continua en el departamento de Atención de Socios, el que emite las credenciales correspondientes, las envía al nuevo socio e informa a la Portería del club que hay un nuevo socio que está autorizado a ingresar. Con ello, el socio ya puede ingresar a las dependencias del club y disfrutar de sus beneficios.

#### Solución: Justifique el patrón arquitectónico que propondría para este sistema, junto a una posible arquitectura genérica.

Lo que se describe es un flujo de trabajo (workflow), por lo tanto, la arquitectura más adecuada es Tubos y Filtros, en la que cada filtro implementa la funcionalidad de cada uno de los departamentos del club. Eventualmente, se podría proponer SOA, ya que cada servicio implementaría los requerimientos de cada departamento.

#### Solución: Describa los componentes principales del sistema e indique que funcionalidad implementaría cada uno de ellos.

- **Atención de Clientes:** Recibe el formulario que el futuro socio ha llenado, valida los datos, almacena en la base de datos y cambia el estado del formulario a "Iniciado".
- **Validación de Antecedentes:** Se activa al detectarse un formulario "Iniciado", valida los antecedentes y cambia el estado a "Validado".
- **Finanzas:** Calcula las cuotas y graba los datos, cambia el estado a "En-financiamiento".
- **Medios de Pago:** Gestiona el pago del futuro socio y cambia el estado a "Financiado".
- **Atención de Socios:** Emite credenciales, las envía al nuevo socio y lo marca como "Socio Activo", permitiendo su ingreso al club.

### Ejercicio 2: Tubos y Filtros

El objetivo del patrón Tubos y Filtros es procesar una cadena de procesos, la que se inicia en el tubo de entrada y luego va pasando filtro tras filtro hasta llegar al tubo de salida.

#### Solución: Justifique el funcionamiento del patrón

- **Correcto:** El procesamiento no inicia en el tubo, sino en el filtro que procesa la información.
- **Falso:** Los filtros no necesariamente conocen su predecesor ni sucesor, ya que son independientes.
- **Incorrecto:** Los tubos no realizan las transformaciones en los datos, sino que los filtros son quienes lo hacen.