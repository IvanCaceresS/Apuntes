La materia a evaluar corresponde a la primera parte, hasta Modelos de Control (Incluyendola)
# Funciones de la Arquitectura de un Sistema

La arquitectura de un sistema:

- **Define la estructura** del mismo, identificando sus componentes principales (por ejemplo, módulos, clases, o paquetes) y la forma en que estos componentes se organizan y se interconectan.
- **Especifica la comunicación entre componentes**, detallando cómo los diferentes elementos del sistema interactúan entre sí para cumplir con los objetivos del sistema. Esto puede incluir la definición de interfaces, protocolos de comunicación, y mecanismos de intercambio de datos.
- **Plantea los requerimientos no funcionales**, los cuales incluyen:
    - **Restricciones técnicas**: Limitaciones en el uso de ciertas tecnologías, estándares de codificación, o herramientas específicas.
    - **Restricciones de negocio**: Reglas derivadas de las necesidades del negocio, como el cumplimiento de regulaciones específicas o la necesidad de integrarse con sistemas existentes.
    - **Atributos de calidad**: Expectativas sobre el comportamiento del sistema en áreas como rendimiento, seguridad, fiabilidad, y usabilidad.
- **Es una abstracción del sistema**, proporcionando una vista simplificada y conceptual del mismo, que ayuda a comprender su estructura y funcionamiento sin necesidad de entrar en los detalles de implementación.
- **Tiene diversas vistas**, cada una enfocada en aspectos específicos del sistema:
    - **Vista Lógica**: Muestra los principales elementos funcionales del sistema y cómo interactúan.
    - **Vista de Proceso**: Se enfoca en los procesos del sistema, su interacción, y cómo se maneja la información.
    - **Vista Física**: Describe cómo se distribuye el sistema en el hardware o la infraestructura de red.
    - **Vista de Desarrollo**: Se centra en el aspecto del desarrollo del software, mostrando la organización del código, las bibliotecas, y las dependencias.

**Ejemplo**: Imaginemos un sistema de comercio electrónico. La vista lógica mostraría cómo interactúan los componentes como el carrito de compras, la gestión de inventario, y el procesamiento de pagos. La vista de proceso podría describir el flujo de un pedido desde que es colocado hasta que se entrega. La vista física detallaría cómo se despliega el sistema en servidores cloud y la vista de desarrollo podría organizar el código en módulos según la funcionalidad (frontend, backend, base de datos, etc.).

# Los tres pilares básicos de cualquier arquitectura de software son:

1. **Componentes**: Son las unidades fundamentales de software o módulos que realizan un conjunto específico de funciones dentro del sistema. Los componentes son partes discretas del sistema que pueden desarrollarse, probarse y mantenerse de manera independiente. Pueden ser simples, como una función o una clase en un lenguaje de programación, o pueden ser complejos, como un servicio web o un microservicio que realiza una serie de tareas. Los componentes son cruciales porque encapsulan la lógica del negocio, los procesos de datos, y las interfaces de usuario, entre otras cosas.
    
    **Ejemplo**: En un sistema de comercio electrónico, algunos componentes podrían ser el sistema de gestión de inventarios, el procesador de pagos, y la interfaz de usuario del carrito de compras.
    
2. **Relación entre los componentes**: Se refiere a cómo interactúan o se comunican estos componentes entre sí. Esto incluye la definición de interfaces, protocolos de comunicación, y cualquier otro mecanismo que facilite el intercambio de información o la coordinación de actividades entre componentes. La forma en que se definen estas relaciones afecta directamente la modularidad, la escalabilidad, y la mantenibilidad del sistema.
    
    **Ejemplo**: En el sistema de comercio electrónico mencionado, el componente del carrito de compras necesita comunicarse con el sistema de gestión de inventarios para verificar la disponibilidad de productos y con el procesador de pagos para completar transacciones.
    
3. **Ambiente**: También conocido como el entorno de operación, incluye la infraestructura sobre la cual se despliegan los componentes del sistema, así como otros factores externos que influyen en su diseño, como los sistemas operativos, el hardware, las redes, y las interacciones con otros sistemas software. El ambiente también abarca las condiciones operativas, como la carga de trabajo esperada, requisitos de disponibilidad, y estrategias de despliegue y mantenimiento.
    
    **Ejemplo**: El ambiente para el sistema de comercio electrónico podría incluir servidores en la nube para alojar la aplicación, bases de datos para almacenar información del producto y de los clientes, y la integración con servicios de terceros para pagos y logística.
    

Estos tres elementos trabajan conjuntamente para definir la arquitectura de un sistema de software, y cada uno de ellos debe ser cuidadosamente considerado y diseñado para asegurar que el sistema final sea robusto, escalable, y capaz de satisfacer las necesidades de sus usuarios y las demandas del negocio.
# Arquitecto de Software

Su función principal es diseñar el sistema de manera que cumpla con los requisitos tanto funcionales como no funcionales, mientras que la del ingeniero de software es implementar este diseño, construyendo el sistema con base en las especificaciones proporcionadas por el arquitecto.

1. **Administración de riesgo**: Evalúa y propone estrategias para mitigar riesgos asociados al desarrollo del proyecto. Por ejemplo, si se identifica que el plazo de entrega es insuficiente, el arquitecto puede sugerir simplificar ciertas características o explorar soluciones tecnológicas que aceleren el desarrollo.
    
2. **Conocimiento de la tecnología**: Está al tanto de las últimas tecnologías y decide cuáles son las más adecuadas para el proyecto en función de los requisitos y restricciones. Por ejemplo, podría elegir entre utilizar microservicios o una arquitectura monolítica basándose en la escala y complejidad del sistema.
    
3. **Excelentes habilidades de diseño**: Capaz de crear soluciones técnicas innovadoras y efectivas, asegurando que el sistema sea escalable, mantenible, y seguro.
    
4. **Interfaz entre el cliente y el equipo técnico**: Actúa como mediador, traduciendo las necesidades del negocio en requerimientos técnicos y asegurando que el equipo de desarrollo comprenda las expectativas del cliente.
    
5. **Promoción de buenas prácticas de desarrollo**: Fomenta el uso de metodologías de desarrollo eficaces, estándares de codificación, y herramientas que mejoren la calidad del software y la eficiencia del equipo.
    
6. **Puente de comunicación entre los equipos de desarrollo**: Facilita la colaboración y comunicación entre diferentes equipos de desarrollo, especialmente en organizaciones grandes donde pueden existir múltiples equipos trabajando en diferentes aspectos del mismo proyecto.
    

**Ejemplo**: Un arquitecto de software en un proyecto de desarrollo de una aplicación móvil puede optar por usar Flutter para aprovechar su capacidad de compilar hacia múltiples plataformas móviles a partir de una única base de código, promoviendo así la eficiencia y reduciendo los tiempos de desarrollo. También podría trabajar estrechamente con el equipo de seguridad para asegurar que la arquitectura de la aplicación cumple con los estándares de seguridad más recientes, mitigando así los riesgos asociados con la protección de datos del usuario.
# Requerimientos no Funcionales (Atributos de Calidad del Software)

Los requerimientos no funcionales son esenciales para garantizar la calidad, eficiencia y satisfacción del usuario en el uso de un sistema. A diferencia de los requerimientos funcionales, que describen lo que el sistema debe hacer, los RNF definen cómo debe comportarse el sistema en términos de rendimiento, seguridad, mantenibilidad, etc.

1. **Rendimiento (Performance)**: Se refiere a la capacidad del sistema para realizar sus tareas dentro de parámetros específicos.

	- **Throughput**: Mide el número de operaciones o transacciones que el sistema puede procesar en un tiempo determinado. Ejemplo: Un servicio de streaming que puede entregar 100,000 vídeos por segundo a sus usuarios.
	- **Tiempo de respuesta**: El tiempo que tarda el sistema en responder a una entrada específica. Ejemplo: Un motor de búsqueda que devuelve resultados en menos de un segundo.
	- **Plazos (Deadlines)**: Tiempo máximo permitido para que se complete una operación específica. Ejemplo: Un sistema de procesamiento de pagos que garantiza la autorización de la transacción en menos de 3 segundos.

2. **Escalabilidad**: Capacidad del sistema para manejar el aumento de carga de trabajo sin comprometer el rendimiento.

	- **Carga (TPS, transacciones por segundo)**: Máxima carga de transacciones que el sistema puede manejar eficientemente. Ejemplo: Un sitio web de comercio electrónico que soporta 50,000 transacciones por segundo durante el Black Friday.
	- **Conexiones simultáneas**: Número máximo de usuarios o dispositivos que pueden interactuar con el sistema al mismo tiempo. Ejemplo: Un juego en línea que puede soportar 1 millón de jugadores conectados simultáneamente.
	- **Volumen de datos**: Capacidad del sistema para manejar grandes volúmenes de datos. Ejemplo: Una base de datos de clientes que puede gestionar registros de 100 millones de clientes sin degradar el rendimiento.
	- **Despliegue**: Facilidad con la que se puede instalar o desplegar el sistema en nuevos entornos. Ejemplo: Software que ofrece contenedores Docker para facilitar su despliegue en cualquier infraestructura cloud.

3. **Mantenibilidad**: Facilidad con la que el sistema puede ser modificado para corregir defectos, mejorar rendimiento o adaptarse a cambios en el entorno.

	- **Modificable**: Capacidad de realizar cambios sin afectar negativamente el sistema. Ejemplo: Un sistema con una arquitectura modular que permite actualizar componentes individuales sin interrumpir el servicio.
	- **Adaptabilidad a nuevos requerimientos funcionales**: Facilidad para incorporar nuevas funciones. Ejemplo: Un CMS que permite añadir nuevos tipos de contenido mediante plugins o módulos.

4. **Seguridad**: Protección de la información y los procesos del sistema contra accesos no autorizados, uso indebido o malintencionado. Mientras más seguridad tenga un sistema más lento es generalmente.

	- **Autenticación y Autorización**: Verificar la identidad de los usuarios y restringir el acceso a recursos basado en permisos. Ejemplo: Un sistema bancario online que utiliza autenticación multifactor y roles de usuario para proteger las cuentas y transacciones.
	- **Encriptación**: Uso de algoritmos para proteger la información sensible. Ejemplo: Un servicio de mensajería que utiliza encriptación de extremo a extremo para proteger la privacidad de las comunicaciones.
	- **Integridad y No repudio**: Garantizar que la información no sea alterada y que las acciones no puedan ser negadas posteriormente. Ejemplo: Un sistema de votación electrónica que utiliza firmas digitales para asegurar la integridad del voto y el no repudio.

5. **Confiabilidad (Reliability)**: Capacidad del sistema para funcionar correctamente y sin fallos durante un período determinado bajo condiciones específicas.

	- **Disponibilidad**: Porcentaje de tiempo que el sistema está operativo y accesible. Ejemplo: Un servicio en la nube que ofrece un SLA (Acuerdo de Nivel de Servicio) con una disponibilidad del 99.999% (cinco nueves).
	- **Recuperable**: Capacidad del sistema para recuperarse rápidamente después de una falla. Ejemplo: Un sistema de base de datos que utiliza réplicas y backups automáticos para restaurar el servicio en minutos después de un fallo.

6. **Integrabilidad**: Capacidad del sistema para interactuar y operar con otros sistemas, internos o externos.

	- **Interoperabilidad y APIs**: Facilidad con la que el sistema puede comunicarse e intercambiar datos con otros sistemas. Ejemplo: Una aplicación de gestión empresarial que proporciona API REST para integrarse con sistemas de contabilidad y recursos humanos.

7. **Portabilidad**: Capacidad del sistema para operar en diferentes entornos de hardware o software.(Segun profe no hay sistema portable)

	- **Independencia de plataforma**: Diseño del sistema de manera que pueda funcionar en distintos sistemas operativos o dispositivos sin necesidad de modificaciones. Ejemplo: Un software de procesamiento de texto disponible para Windows, macOS y Linux.

8. **Verificabilidad**: Capacidad del sistema para incorporar elementos o mecanismos que no solo permitan su evaluación a través de pruebas, sino también faciliten la autocorrección y la prevención de errores antes de que estos afecten al usuario o al funcionamiento del sistema
	1. Testeable: Indica cuán fácilmente se puede comprobar un sistema para asegurar que cumple con los requisitos definidos. Un sistema testeable facilita la identificación y corrección de errores, permitiendo pruebas eficientes de sus componentes individuales y de su funcionamiento global. Ejemplo: Una aplicación web de comercio electrónico estructurada para permitir pruebas automatizadas de su función de búsqueda y proceso de pago, garantizando que los usuarios puedan buscar productos y completar compras sin errores tras cada actualización.
9. **Soportabilidad**: Capacidad para diagnosticar, reportar y corregir errores encontrados en el sistema.

	- **Diagnóstico y Corrección de incidencias**: Herramientas y procedimientos para identificar y solucionar problemas. Ejemplo: Un sistema operativo que proporciona herramientas de diagnóstico y parches regulares para corregir vulnerabilidades y errores.
# Arquitecturas de software genéricas
 - **Modelo de repositorio**: Ocurre cuando hay grandes cantidades de datos que deben ser compartidos
		 - Gestion centralizada de datos
		 - Almacenamiento centralizado / distribuido
		 - Modelo pasivo: A petición del usuario se verifica si existió un cambio o nueva publicación en el repositorio
		 - Modelo proactivo: Avisa a los usuarios interesados a con los datos que existió un cambio o nueva publicación en el repositorio
		 - Ventajas:
			 - Modo eficiente de compartir datos
			 - Administracion centralizada de los datos
			 - Seguridad, escalabilidad, mantenibilidad
		- Desventajas:
			- Fuerza un modelo de datos (Una vez se define es muy complejo de modificar)
			- Dificil cambio del modelo de datos
			- Politica centralizada de administración
			- Punto único de falla
- Cliente/Servidor:
		- Estructurado en base a:
			- Servidores que ofrecen servicios especificos
			- Clientes que requieren serviios
			- Redes de comunicacion que conectan ambos
		- Es un modelo parcialmente distribuido (el procesamiento está dividido tanto en el cliente como en el servidor)
		- Ventajas
			- Procesamiento distribuido
			- Datos distribuidos
			- Escalable (definir más instancias de los servidor)
		- Desventajas
			- Datos no compartidos (cada servidor tiene sus propios datos)
			- Administración de datos en cada servidor
			- Performance deteriorada (ya que existe un medio de comunicacipon entre cliente y servidor, el cuello de botella es la red)
			- No hay registro centralizado de servicios (No se que servicios están operativos y cuales no, tampoco se donde estan. Todo es en base a prueba y error)
- Modelo de capas:
	- Conjunto de capas de software que ofrecen servicios especificos
	- Cada capa tiene una interfaz claramente definida
	- Desarrollo independiente de las capas
	- Ventajas:
		- Desarrollo incremental
		- Flexible
		- Mantenible
	- Desventajas
		- Díficil estructuración
		- Dependencias cruzadas
		- Baja performance
- Objetos distribuidos:
	- Cada componente (objeto) define los datos y metodos que pueden ser invocados
	- Cada objeto puede proveer y recibir servicios
	- Objetos se comunican a través del sistea ORB (Object Request Broker)
	- Arquitectura compleja
	- Ventajas
		- Diseño flexible(yo defino las clases que yo quiera)
		- Facil agregar objetos
		- Configuración dinámica
		- Escalabilidad, mantenibilidad
	- Desventajas
		- Compleja construcción
		- Bajo rendimiento
- Arquitectura orientada a servicios
	- Componentes de la arquitectura:
		-  Bus de servicios
			- Punto focal de la arquitectura SOA
			- Gestiona las transacciones que recibe
			- Administra los clientes y servicios conectados
			- Redirige las transacciones de los clientes hacia los servicios que van a procesarlas
			- Retorna a los clientes correspondientes las transacciones de respuesta de los servicios
			- Su ubicacion fisica es un contenedor docker y acepta conexiones en el puerto 5000
		- Servicios:
			- Proceso que implementa una o mas funcionalidades
			- Se conecta al bus y se identifica como servicio, usando la transaccion sinit
			- Queda activo en espera de transacciones
- **Arquitectura Cloud**:
	- Externalización de servicios computacionales
		- Infraestructura - IaaS
		- Plataforma - PaaS
		- Aplicación - SaaS
	- Recursos elásticos (pay what you use)
	- Ventajas
		- Servicios ubicuos
		- Reducción de costos
		- Disponibilidad, escalabilidad, elasticidad
		- Flexibilidad, movilidad
	- Desventajas
		- Dependencia de ente externo
			- Seguridad
			- Confidencialidad
			- Conectividad
# Modelo de Control
- Control del flujo entre componentes
- Control Centralizado:
	- Un componente controla la ejecucion del sistema
	- Modelo Call-Return
		- Simple 
		- Predecible
		- Rigido
		- Testeable
		- Bloqueante
		- Complejo manejo de excepciones
	- Modelo Administrador
		- No bloqueante
		- Coordinación de procesos
		- Lógica centralizada
		- Posible cuello de botella
- Control Basado en Eventos
	- Control descentralizado
	- Control no bloqueante
	- Manejan eventos generados externamente
		- Transmisión Múltiple (Broadcast)
			- Usan modelo Publicador-Suscriptor
				- Componentes distribuidos
					- Publican servicios
					- Gatillan eventos
					- Suscriben eventos
			- Ventajas:
				- Activación descentralizada de componentes  
				- Distribución de componentes  
				- Evolución simple
			- Desventajas  
				- Respuesta incierta  
				- Varios manejadores del mismo evento
		- Manejo de Interrupciones
			- Sistemas en tiempo de real
			- Manejador para cada tipo de interrupción
			- Respuesta inmediata
			- No bloqueante
			- Procesamiento paralelo