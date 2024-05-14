# Primera Clase
Correo profe: juan.giadach@mail.udp.cl
Sección 2
Solemne 1: introducción, propiedades no funcionales y arquitecturas de software genéricas.

**NOTA PRESENTACION:**
2 solemnes 60%
2 controles 10%
4 informes 20%
Presentación final 10%

**EXAMEN 30%**

**Eximición: TODAS las notas >= 4.0, NP>=5**

Solemne 1 -> Semana 24/04 - 30/04
Solemne 2 -> Semana 24/06 - 28/06
Controles -> C1 03/04 - C2 29/05
Informes -> I1 22/03 - I2 12/04 - I3 24/05 - I4 14/06
Presentación final -> Semanas 21/06 - 05/07

**Arquitectura para el proyecto: SOA**
-> Integrantes 3 o a lo mas 4

# 12-03-24
## **Arquitecto de software**
Su función es diseñar el sistema, mientras que la del ingeniero de software es construirlo.
1. **Administración de riesgo**: entregar soluciones respecto al riesgo del desarrollo, falta poco tiempo para terminar y aun queda mucho, por lo que se administraria que se puede eliminar del sistema para cumplir con los plazos, se modificaria el diseño.
2. **Conocimiento de la tecnología:** cuales son las tecnologias modernas para ver si aplican al diseño o no.
3. **Excelentes habilidades de diseño** 
**Arquitectura**:
- Componentes
- Relacion entre los componentes
- Ambiente

## Requerimientos no funcionales (Atributos de calidad del software)

Son requerimientos que no son impresindibles para el funcionamiento del sistema

1. Performance (Rendimiento): Capacidad de procesamiento
	1. Throughput (mide el flujo, mientras mejor es el flujo mejor será la experiencia del usuario)
	2. Tiempo de respuesta (Hay un usuario frente a pantalla esperando una respuesta)
	3. Plazos (Cuanto se va a demorar el proceso)
2. Escalabilidad: Manejar adecuadamente la carga de transacciones
	1. Carga(tps): Cual es la carga que tiene el sistema, y cuanto puede soportar en un segundo
	2. Conexiones simultáneas: cuantos equipos son soportados simultáneamente
	3. Volumen de datos: cantidad de información que es capaz de manejar sin bajar el rendimiento del sistema
	4. Despliegue: Se mide la facilidad de instalar una nueva instancia del sistema en un nuevo computador
# 19-03-24
Continuación de requerimientos no funcionales
3. Mantenibilidad: 
	1. Modificable
	2. Nuevos requerimientos funcionales
4. Seguridad: Protección de datos y procesos
	1. Autenticación: Identificar el usuario frente al sistema
	2. Autorización: Definir las funciones que un usuario puede tener en un sistema.
	3. Encriptación
	4. Integridad
	5. No repudio: Tener un mecanismo que permita verificar que quien hizo una transaccion efectivamente la hizo.
	Mientras más segura tenga un sistema más lento es generalmente.
5. Confiabilidad: 
	1. Disponible: Tiempo en el que el sistema está "arriba". 
	2. Recuperable: En cuanto tiempo el sistema se vuelve a reponer una vez se "cayó"
	3. Regla de los cinco nueves(99,999%)
6. Integrabilidad: Interacción con sistemas externos
	1. Agregación
	2. Interoperable
	3. API's
7. Portabilidad: (Segun profe no hay sistema portable)
	1. Independencia de plataforma
8. Verificabilidad: Que tenga elementos que permita herramientas de autocorrección, operacion que se hace antes del error, se anticipa al error
	1. Testeable
9. Soportabilidad: Podemos diagnosticar y corregir los errores, errores ya sucedieron
	1. Diagnóstico: Detectar error que se han producido en el sistema. Tener herramientas acotadas de verificación, tengo que saber donde falló. Archivos de vitácora que dicen que va sucediendo
	2. Corrección de incidencias: 

# 22-03-24
 ## Arquitecturas de software genéricas
 **Diseño de Software**
 1. Fase 0: Analizar el contexto → Donde se va a instalar
 2. Fase 1: Estructuración → Identificar componentes y sus relaciones
 3. Fase 2: Modelo de control → Comportamiento de los componentes
 4. Fase 3: Descomposición modular → Diseño detallado
 
 **Fase 0: Contexto**
 1. Requerimiento funcionales → Lo que debe hacer el sistema
 2. Requeriminetos no funcionales → Atributos de calidad requeridos
 3. Ambiente Operacional → Hardware y software involucrados
 4. Restricciones
 **Fase 1: Estructuración**
 - Descompone el sistema en un conjunto de subsistemas
 - Utiliza un diagrama de bloques que muestra la estructura del sistema
 - Indica el flujo de datos entre los componentes del sistema
 - Muestra las interfaces que provee el sistema. En programacion orientada a objetos las interfaces serian los atributos publicos dentro de una clase
# 26-03-24
 - **Modelos de estructuración**
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
		## Ejercicio pregunta del profe:
		**Arquitectura**: Modelo repositorio con almacenamiento distribuido y gestion centralizada en relación a la cercania de los ministerios a los datos que más les interesa ya que de esta manera todos los ministerios obtienen una consistencia entre los datos de los demás.
		**ventajas**: escalable, seguro
		**desventajas**: punto unico de falla, si falla el repositorio todos los ministerios fallan
		**req. no funcionales**: confiabilidad, seguridad, performance
# 02-04-24

**Preguntas tipo control:**
Analice el siguiente parrafo indicando y corrigiendo los errors:
- El objetivo del requerimiento funcional de mantenibilidad es mantener operativo el sistema el mayor tiempo posible. **R:// esta definición es de confiabilidad**
- El optimo a alcanzar es que opere al 99,999% del tiempo, regla conocida como la de los cinco nueves. **R:// Verdadero**
- Para lograr los cinco nueves, un sistema debe diseñarse con componen redundantes que puedan tomar el control de la operación del sistema en el caso que uno de ellos falle. **R:// Verdadero, porque tener componentes redundantes es una de las soluciones**
- Si esto ocurre, utilizando los procesos definidos al incluir el requerimiento de mantenibilidad se podra corregir el error y restaurar el sistema a su estado normal del procesamiento. **R:// falso, eso lo realiza soportabilidad**

- Continuación modelos de estructuración
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
	- Objetos distribuidos
# 09-04-24
- Continuación modelos de estructuración
	- Arquitectura orientada a servicios
		- Componentes de la arquitectura:
			- Bus
			- Servicios
	- Arquitectura Cloud

# 12-04-24
## Arquitectura SOA
**Ejercicio -SOA**:
Un banco requiere un sistema para manejar las cuentas corrientes de sus clientes el que debe comtemplar las siguientes operaciones:
- Consulta del saldo de una cuenta
- Deposito en una cuenta
- Giro desde una cuenta
- Transferencia entre cuentas
Se pide definir este sistema utilizando la arquitectura SOA.

1. Paso 1: Identificar los servicios. Por lo menos son 4 servicios, ya que se puede incluir un servicio de base de datos(este servicio se conecta directamente a la base de datos) o servicios que son utilizados por los 4 servicios principales (recordar que si un servicio quiere solicitar a otro servicio debe pasar por el Bus)
	1. Servicio de transferencias
	2. Servicio de Giros
	3. Servicio de Depósitos
	4. Servicio de consulta saldo
2. Paso 2: Definir las transacciones que se procesarán cada uno de los servicios:
	1. Servicio de consulta de saldos:
		1. INPUT
			1. COSAL
			2. Cuenta destino
		2. OUTPUT
			1. COSAL
			2. Monto Saldo
			3. Resultado Consulta Saldo
	2. Servicio de Depositos
		1. INPUT
			1. DEPOS
			2. Cuenta Origen
			3. Monto
		2. OUTPUT
			1. DEPOS
			2. Monto Nuevo Saldo
			3. Resultado Deposito
	3. Servicio de giros: debe hacer uso del servicio de consulta de saldo mediante el bus para saber si es posible hacer un giro, luego realiza el giro
	4. Servicio de transferencias: Debe realizar un giro y el giro a su vez debe hacer una consulta de saldo y luego debe hacer un deposito y para esto debe hacer uso del servicio de deposito todo esto mediante el bus
		1. INPUT:
			1. TRANS
			2. Cuenta Origen
			3. Cuenta Destino
			4. Monto a Transferir
		2. OUTPUT:
			1. TRANS
			2. Monto Nuevo Saldo Cuenta Origen
			3. Resultado Transferencia
3. Paso 3: Especificar las interacciones entre los servicios
	1. Servicio de giros
		1. Servicio de consulta de saldos
	2. Servicio de deposito
		1. Servicio de consulta de saldos
	3. Servicio de transferencias
		1. Servicio de consulta de saldos
		2. Servicio de giros
		3. Servicio de depositos
4. Paso 4: Definir el modelo de datos
5. Paso 5: Especificar el funcionamiento de cada servicio
6. Paso 6: Definir la interfaz de usuario
7. Pasos siguientes: Codificar, Probar, etc.


# 16-04-24
## Revisión Control 1
1.  **Explique que se debe considerar en el proceso de seleccion de una arquitectura de software para diseñar un sistema.**
	R: Restricciones (del negocio, tecnicas), ambiente, requerimientos(funcionales y no funcionales)
2. **Priorice las tres competencias mas importantes que debe tener un arquitecto de software y explique los motivos que lo llevaron a dicha priorizacion.**
	R: 1. Buen diseño. 2.Buena comunicacion con cliente y equipo de trabajo. 3. Conocimiento de tecnologías actuales.
3. **A usted le han solicitado el desarrollo urgente de un sistema que tiene 8 requerimientos funcionales y cuya primera versión, con el 25% de los requerimientos funcionales implementados, debe estar operativa en dos semanas. Luego, tiene 4 semanas para finalizar la implementacion de los restantes. En este contexto, analice 3 requeriminetos no funcionales que no deberian ser considerados en el sistema porque le pueden retrasar y, por lo tanto, no cumplir con el plazo requerido.**
	R: Seguridad, Confiabilidad, Verificabilidad
4. Analice el siguiente párrafo indicando y corrigiendo los errores.
	1. **El objetivo del requerimiento no funcional de Verificabilidad es como su nombre lo indica, verificar que el sistema este operativo el mayor tiempo posible.** FALSO,esto es confiabilidad
	2. **Para lograr este objetivo, el arquitecto de software tuvo que incluir en el sistema un conjunto de procesos cuya misión es generar una traza de cada una de las transacciones procesadas de manera de ayudar a diagnosticar los posibles errores.** FALSO, esto es Soportabilidad
	3. **Utilizando esa información, el sistema tuvo que pasar por un proceso de verificacion de todas sus funcionalidades de manera de detectar y corregir posibles errores previo al proceso de puesta en producción.** FALSO, porque aqui se habla de QA, no tiene que ver con ningun requerimiento no funcional.

## Continuando con SOA
### Bus de servicios
- Punto focal de la arquitectura SOA
- Gestiona las transacciones que recibe
- Administra los clientes y servicios conectados
- Redirige las transacciones de los clientes hacia los servicios que van a procesarlas
- Retorna a los clientes correspondientes las transacciones de respuesta de los servicios
- Su ubicacion fisica es un contenedor docker y acepta conexiones en el puerto 5000
### Estructuras de transacciones
- TX-in - Transacción de requerimiento: 
	- Largo: cuantos caracteres vienen a continuación (5 caracteres)
	- Servi: Identificacion del servicio requerido (5 caracteres)
	- Datos: datos enviados al servicio para el procesamiento del req.
	- ej:

| 00017 | HOLAS | HOLA MUNDO!! |
| ----- | ----- | ------------ |
- TX-out - Transacción de respuesta del servicio
	- Largo: cuantos caracteres vienen a continuación (5 caracteres)
	- Servi: Identificacion del servicio que responde (5 caracteres)
	- Datos: datos con el resultado del proceso del req. recibido

- TX-out - Transacción de respuesta del bus
	- Largo: cuantos caracteres vienen a continuación (5 caracteres)
	- Servi: Identificacion del servicio que genera la transaccion (5 caracteres)
	- ST: Status de la transacción(OK:correcta O NK:erronea)
	- Datos: datos con el resultado del proceso del req. recibido

### Servicio
- Proceso que implementa una o mas funcionalidades
- Se conecta al bus y se identifica como servicio, usando la transaccion sinit
- Queda activo en espera de transacciones
SI ENTRA HASTA AQUI

# 19-04-24
## Modelo de capas
- Conjunto de capas de software que ofrecen servicios específicos
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
## Objetos distribuidos
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
## Arquitectura Cloud
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
## **Fase 2: Modelo de Control**
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
		- Manejador de Interrupciones
	- Usan modelo Publicador-Suscriptor
		- Componentes distribuidos
			- Publican servicios
			- Gatillan eventos
			- Suscriben eventos
	- Manejo de Interrupciones
		- Sistemas en tiempo de real
		- Manejador para cada tipo de interrupción
		- Respuesta inmediata
		- No bloqueante
		- Procesamiento paralelo
## **Fase 3: Descomposición Modular**
- Componentes divididos en módulos
- Posibilita visualizar 
### Modelo de Objetos
- Conjunto de clases bien definidas
- Identifica atributos y métodos
- Objetos creados a partir de las clases
- Coordinación de operaciones entre objetos
### Modelo de Flujo de Datos
- Descomposición en procesos funcionales
- Transformación de entradas en salidas
- Dependencia entre procesos
- Flujo predeterminado
- Adecuado para procesos batch
---
			FIN DE ARQUITECTURAS GENÉRICAS
--
# 23-04-24
## Arquitecturas de Dominio Específico
- Modelos específicos para algún dominio
- Arquitecturas genéricas
	- Generalización de sistemas reales
	- Análisis de sistemas existentes
- Arquitecturas de referencia
	- Idealización de una arquitectura específica
	- Estudio del dominio de una aplicación
	- Estándar de facto en su dominio
- Diferencia entre estas arquitecturas: La generica dice, esta es la arquitectura, implementala.. la deja lista. La de referencia es similar pero no es aplicable a la realidad, es lo que deberias tener pero no necesariamente lo tendrás, ejemplo de arquitectura de referencia puede ser.

# 10-05-24
## Patrones de arquitectura
- Solución de diseño a un problema
- Características
	- Esquema genérico
	- Probado
	- Recurrente
- Especificación
	- Componentes
	- Responsabilidades
	- Relaciones
#### Descripción de un Patrón
- Nombre del patrón
- Contexto
	- Situacion que origina el problema
- Problema (Requerimiento)
	- Descripción genérica del problema
	- Define lo que se debe resolver
	- Fuerzas presentes en el contexto
		- Propiedades
		- Requisitos (funcionales y no funcionales)
		- Restricciones
- Solución
	- Esquema de solución del problema
	- Balance de fuerzas
	- Estructura
		- Componentes
		- Relaciones
	- Comportamiento
		- Organización de componentes
	- Priorización de fuerzas
# 14-05-24
#### Clasificación de patrones
##### Patrones simples
- Capas
	- Estructura aplicaciones descomponiendolas en tareas con diferentes niveles de abstracción
	- **Contexto**: Sistemas estructurados con diversos niveles de acción
	- **Requerimiento**: Organización inadecuada genera problemas de escalabilidad y mantenibilidad.
	- **Solución**: Estructuración en esquema multi-capa
		- Capa base con nivel de abstracción más bajo
		- Avanzar capa a capa utilizando los servicios de la capa inmediatamente anterior.
		- Componentes estructurados en módulos relacionados
		- Características:
			- La capa K se relaciona solamente con la capa K-1.
			- No hay otras dependencias entre capas.
			- Cada capa puede estar integrada por distintos componentes.
			- Los componentes pueden interactuar entre sí, pero quedan acoplados.
			- Cada capa expone una interfaz con los servicios que provee.
			- El comportamiento puede ser top-down o bottom-up.
		- Implementación:
			- Determinar el número de capas según el nivel de abstracción requerido.
			- Asignar responsabilidades a cada capa.
			- Especificar los servicios ofrecidos por cada capa.
			- Definir la estructura de cada capa.
			- Especificar la interfaz de cada capa.
			- Especificar el método de comunicación intercapas.
			- Definir el esquema para el manejo de errores.
	- Analisis
		- Ventajas:
			- Componentes estandarizados
			- Cambios afectan el nivel local
			- Reutilizacion de capas/componentes
		- Desventajas
			- Cambios afectan en cascada
			- Ineficiencia
			- Complejo de definir
	- Ejercicio
		- Un banco requiere un sistema para manejar las cuentas corrientes de sus clientes. Especificamente requiere las siguientes operaciones:
			- Consulta del saldo de una cuenta
			- Deposito en una cuenta
			- Giro desde una cuenta
			- Transferencia entre cuentas
		- Se pide definir este sistema utilizando la arquitectura de Capas
		- Solución:
			- Definir Capas:
				- UI
				- Transferencia
				- Giro | Deposito
				- Consulta.
				- Datos
- Tubos y filtros
	- Estructura aplicaciones en actividades para procesar flujos de datos en que cada actividad (o transformación) es un filtro que está unido por un tubo a los filtros contiguos. 
	- Contexto: Procesar flujos de datos.
- Pizarrón
- Repositorio

