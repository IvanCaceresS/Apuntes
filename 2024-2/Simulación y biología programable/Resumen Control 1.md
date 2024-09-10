Hasta la clase 27-08 incluyendola
## **Introducción a la Biología Molecular y Computación Biomolecular**
**1. Lenguaje en Computación y Biología Molecular**
- **Lenguaje Computacional Tradicional**: Durante la carrera se ha utilizado el sistema binario (0 y 1) como base de la representación de voltajes, fundamental en la operación de hardware electrónico.
- **Nuevo Lenguaje Biológico**: En biología programable, el ADN es la representación de base. Las cadenas de ADN están compuestas por cuatro bases: A (adenina), C (citosina), T (timina), y G (guanina).
**2. ADN: El Lenguaje de los Organismos**
- El ADN es la base química de la caracterización de los organismos. Está compuesto por secuencias de las cuatro bases mencionadas, que determinan el **genotipo** y el **fenotipo** del organismo, así como las rutas para la síntesis de proteínas y otros procesos vitales.
**3. Terminología Esencial**
- **ADN**: Almacena características y funciones de los seres vivos.
- **ARN**: Copia transcrita del ADN que se traduce a proteína. Tipos: mRNA, gRNA.
- **Codón**: Tripleta de bases de ARN que codifica un aminoácido.
- **Aminoácido**: Unidad básica de las proteínas (20 tipos).
- **Proteína**: Resultado de la traducción de codones. Son clave para las funciones biológicas.
- **Polimerasa (ADN/ARN)**: Enzimas que sintetizan bases.
- **Ribosoma**: Orgánulo encargado de sintetizar proteínas.
## **Biología Computacional: El ADN como un Lenguaje Fundamental**
**1. Combinatoria y Complejidad**
- El ADN tiene una combinatoria mayor que los bits: **4^n combinaciones** en ADN versus **2^n combinaciones** en bits.
**2. Complementariedad de Watson-Crick**
- Las cadenas de ADN interactúan mediante la complementariedad entre sus bases. Este principio es la base del **DNA computing**.
**3. Dogma Central de la Biología**
- El ADN funciona como un código fuente. Los procesos biológicos que corresponden a la compilación/interacción de este código son la **transcripción** (ADN a ARN) y la **traducción** (ARN a proteína).
## **Organismos, Modelos y Funciones en Biología Programable**
**1. La Célula como Unidad Básica**
- Las células son la unidad mínima de vida. Están formadas por membrana, núcleo y citoplasma, y se relacionan directamente con el ADN.
**2. Tipos de Células**
- **Eucariotas**: Tienen orgánulos y un núcleo definido (Ej: _S. cerevisiae_).
- **Procariotas**: Estructura simple, sin membrana interna (Ej: _E. coli_).
**3. Funciones Celulares de Interés**
- **Expresión genética**: Aplicación del Dogma Central de la Biología.
- **Crecimiento y división**: Ciclo de crecimiento y reproducción.
- **Señalización**: Comunicación entre células.
- **Evolución**: Adaptación celular.
## **Expresión Genética: Procesos y Actores**
**1. Transcripción y Traducción en Programación Biológica**
- La transcripción convierte ADN en ARN, y la traducción convierte ARN en proteínas. Estas funciones son esenciales para la biología programable.
**2. Glosario de Elementos Claves**
- **Promotor**: Región del ADN a la que se une la ARN polimerasa y desde donde se inicia la transcripción.
- **Ribosome Binding Site (RBS)**: Región de ARN donde se une el ribosoma y se inicia la traducción. "Promotor" de la traducción.
- **Secuencia Codificante (CDS)**: Secuencia de ADN que sirve de plantilla para la transcripción a ARN y posterior traducción.
- **Terminador**: Marca el final de la transcripción.
**3. Interacciones Genéticas**
- **Represión**: Representa la interacción que bloquea la transcripción en un promotor.
- **Activación**: Representa la interacción que promueve la transcripción y posterior traducción.
**4. Operones y Plásmidos**
- **Operón**: Conjunto de genes bajo un promotor común.
- **Plásmido**: Fragmento circular de ADN móvil, usado para implementar circuitos genéticos.
## **Diseño de Circuitos Genéticos**
**1. Estructura de un Circuito Genético**
- Los circuitos están formados por elementos como el **promotor**, **operador**, **RBS**, **genes**, y **terminador**. Factores externos pueden influir en su funcionamiento.
**2. Simplificación del Diseño con SBOL**
- SBOL es un lenguaje gráfico que facilita el diseño de circuitos genéticos y proporciona una ontología de los elementos biológicos.
**3. Plásmidos como Plataforma Ideal para Circuitos**
- Los plásmidos permiten un control eficiente, son evolutivamente maleables y más fáciles de integrar que los cambios en el genoma.
## **Herramientas Avanzadas: CRISPR y Circuitos Complejos**
**1. Sistema CRISPR/Cas9**
- CRISPR/Cas9 permite insertar, eliminar o modificar secuencias de ADN. Sus componentes clave son la **proteína Cas9** y el **gRNA** (ARN guía).
**2. Circuitos Complejos**
- Los circuitos complejos pueden diseñarse usando estrategias como la vinculación a procesos vitales, el uso de chassis mínimos y la **comunicación intercelular** para repartir tareas entre organismos.
**3. Comunicación Celular**
- La comunicación celular permite que consorcios de organismos colaboren en tareas complejas, distribuyendo la carga metabólica y mejorando la eficiencia en la ejecución de circuitos biológicos.

# Control Nº 1 2022
![[Pasted image 20240909185002.png]]
**R:** 
En dos partes:
- primero cuando no hay IPTG:
	- El funcionamiento del circuito sin considerar en primera instancia IPTG es el siguiente: Al haber lacI se inhibe la expresión de lacI ya que el promotor P_lac se regula negativamente por lacI y luego al no haber lacI se comienza a producir nuevamente siendo esto un oscilador y ya que gfp se expresa al haber lacI se forman esos patrones.
- Cuando si hay IPTG:
	- El funcionamiento del circuito cuando está presente una alta concentración de IPTG es el siguiente: IPTG reprime la represión de lacI hacia P_lac, por lo que lacI es producida sin parar, y a su vez, se expresa gfp sin parar, es por esto que al centro de la muestra (cuando hay alta concentración de IPTG) está brillando verde siempre

![[Pasted image 20240909185031.png]]
a) 
![[Pasted image 20240910001522.png]]
Cuando hay aTc se anula la represión de tetR hacia P_tet por lo que siempre se está produciendo cI cumpliendose 1 de las 2 condiciones de P_lac,ci por lo que ahora oscilaría la generación de gfp 

# Control 1 2023
![[Pasted image 20240909204258.png]]
Repressilator con cuatro proteínas
 ![[Pasted image 20240909213753.png]]
 No funcionaría con las mismas caracteristicas 
![[Pasted image 20240909204304.png]]
4. Circuito lógico
El circuito lógico D = OR(A, B, NOT(C)) puede implementarse utilizando tres entradas. La señal "A" activa directamente la salida, al igual que la señal "B". La señal "C" pasa por una compuerta NOT antes de alimentar la entrada de la compuerta OR, de modo que "C" represada inhibe la activación de la salida a menos que "A" o "B" estén activas. Un circuito biológico de este tipo podría implementarse usando proteínas represoras y activadoras que actúan de manera similar a las compuertas lógicas AND, OR y NOT.