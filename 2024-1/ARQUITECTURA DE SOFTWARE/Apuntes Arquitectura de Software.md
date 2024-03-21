# Primera Clase
Correo profe: juan.giadach@mail.udp.cl

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

1. Performance (Rendimiento)
	1. Throughput (mide el flujo, mientras mejor es el flujo mejor será la experiencia del usuario)
	2. Tiempo de respuesta (Hay un usuario frente a pantalla esperando una respuesta)
	3. Plazos (Cuanto se va a demorar el proceso)
2. Escalabilidad
	1. Carga(tps): Cual es la carga que tiene el sistema, y cuanto puede soportar en un segundo
	2. Conexiones simultáneas: cuantos equipos son soportados simultáneamente
	3. Volumen de datos: cantidad de información que es capaz de manejar sin bajar el rendimiento del sistema
	4. Despliegue: Se mide la facilidad de instalar una nueva instancia del sistema en un nuevo computador
# 19-03-24
Continuación de requerimientos no funcionales
3. Mantenibilidad
	1. Modificable
	2. Nuevos requerimientos funcionales
4. Seguridad
	1. Autenticación: Identificar el usuario frente al sistema
	2. Autorización: Definir las funciones que un usuario puede tener en un sistema.
	3. Encriptación
	4. Integridad
	5. No repudio: Tener un mecanismo que permita verificar que quien hizo una transaccion efectivamente la hizo.
		Mientras más segura tenga un sistema más lento es generalmente.
1. Confiabilidad:
	1. Disponible: Tiempo en el que el sistema está "arriba". 
	2. Recuperable: En cuanto tiempo el sistema se vuelve a reponer una vez se "cayó"
	3. Reglo de los cinco nueves(99,999%)
5. Integrabilidad
	1. Agregación
	2. Interoperable
	3. API's
6. Portabilidad
	1. Independencia de plataforma
7. Verificabilidad
	1. Testeable
8. Soportabilidad