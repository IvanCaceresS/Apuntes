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
