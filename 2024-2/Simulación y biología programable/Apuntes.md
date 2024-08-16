# Primera Clase 09-08
- Modelos basados en agentes (simulador)
[Simulador gro](https://depts.washington.edu/soslab/gro/download.php)

NC = (C1 + C2 + C3) / 3
NT = (T1 + T2 + T3) / 3
NP = NC x 0,6 + NT x 0,4

Eximición NP >= 5,0 y NT>=4,0
NF = NP x 0,7 + NEx x 0,3

Tesis doctoral profe → Cap 2 es lo básico.

---
# Clase 13-08
## Repaso de conceptos básicos de Biología Molecular
**Nota:** El sistema operativo de un organismo sería el genoma y el ADN sería el leguaje de programación.
Estas cadenas de ADN (genotipo) definen:  
- Las propiedades observables de un organismo (fenotipo) 
- Los procesos de operaci ́on de un organismo (por ejemplo, comunicación intercelular, ejecución de rutas metabólicas o lisis programada) 
- Patrones para la síntesis de proteínas

### Terminología
1. **ADN**: Compuesto químico que almacena las características y funciones de todo ser vivo.
	1. Pueden ser simples o dobles
	2. Están compuestas de combinaciones secuenciales de cuatro nucleótidos
	3. Patrones para la sintesis de proteínas
2. **ARN**: Ácido ribonucleico. Compuesto similar al ADN, que proviene de su transcripción. Cumple la función de ser una copia “móvil” del ADN y es posteriormente traducido a proteínas. Existen varias clasificaciones, a las que se les antepone una letra (por ejemplo: mRNA o gRNA). Timina se reemplaza por uracilo.
3. **Codón**: Tripleta de bases de ARN que se traduce a un aminoácido.
4. **Aminoácido**: Compuesto químico complejo que constituye una unidad básica para formar proteínas. Existen 20 aminoácidos diferentes.
5. **Proteína**: Producto final resultante de la traducción de codones, es decir, una secuencia de aminoácidos. Son fundamentales para las funciones de los organismos y suelen estar formadas en estructuras tridimensionales.
6. **(ADN/ARN) Polimerasa**: Enzima que sintetiza las bases del compuesto respectivo (ADN o ARN) a partir de nutrientes en el entorno. Realiza la transcripción.
7. **Ribosoma**: Orgánulo macromolecular encargado de sintetizar proteínas según el patrón indicado por el mRNA. El que ejecuta la traducción.

**Complementariedad de bases** o **emparejamiento complementario de bases**. En el ADN, la adenina (A) siempre se empareja con la timina (T) a través de dos enlaces de hidrógeno, mientras que la guanina (G) se empareja con la citosina (C) mediante tres enlaces de hidrógeno. Este emparejamiento es fundamental para la estructura de la doble hélice del ADN y para los procesos de replicación y transcripción del ADN. En el ARN, el uracilo (U) reemplaza a la timina (T) y se empareja con la adenina (A). Por lo tanto, en el ARN, la adenina (A) se empareja con el uracilo (U) en lugar de con la timina (T), como ocurre en el ADN.

![[Pasted image 20240813121959.png]]
![[Pasted image 20240813122011.png]]
# Clase 16-08
## Organismos, organismos modelo y su rol.
**La celula** está compuesta de una membrana, un núcleo y el citoplasma. Estos llevan a cabo funciones que mantienen al ente vivo. Se relacionan directamente con el lenguaje de los seres vivos (ADN). Es el elemento vivo más pequeño, la unidad mínima de ser vivo.

- Las proteínas son las responsables de la función celular y de gatillar a cabo funciones celulares.

# Ejemplos de funciones celulares
- **Repressilator:** Es el circuito #1 que surgió en biología sintética. Un oscilador que se enciende y se apaga, basado en represiones de genes.
![[Pasted image 20240816120813.png]]
- **Circuito bi-estable:** es el circuito #2 que surgió en biología sintética. Encender y apagar.
- **Ruta metabólica de la glucosa:** Los organismos no crecen si no tienen glucosa, si no tienen buscan otra fuente de energía que puede durar un rato hasta volver a encontrar glucosa.
- Desplazamiento de bacterias inducido por **propulsión flagelar**, esto puede verse fomentado por la busqueda de glucosa.
- **Reporter:** GFP (Green Fluorecent Protein)
 ![[Pasted image 20240816121149.png]]

# Células
- La célula es la unidad de operación/procesamiento para ejecutar estos circuitos los cuales están simplificados a una abstracción más alta que permite definir la implementación de funcionalidad.
- **Clases de células:**
	- **Eucariotas**: Son aquellas células que, dentro de su membrana exterior, poseen orgánulos que cumplen funciones específicas para la vida de la célula. Tienen un núcleo definido, rodeado por una membrana interna, que alberga el genoma. Este tipo de células comprende las células animales y la mayoría de los organismos pluricelulares. Como organismo modelo de estudio para este tipo de células, se utiliza _Saccharomyces cerevisiae_ (levadura).
	- **Procariotas**: Son células que presentan una estructura más simple; generalmente no tienen membrana interna, y su material genético se encuentra en el citoplasma. En esta categoría se incluyen las bacterias y las arqueas. Aunque estos organismos pueden vivir en consorcios (colonias) y actuar de manera coordinada, su funcionamiento es menos complejo que el de las eucariotas. El organismo modelo de estudio para las procariotas es _Escherichia coli_ (_E. coli_).
- **Funciones celulares:**
	- Conociendo la clasificación de las células, es importante identificar aquellas funciones principales que se deben considerar y, posiblemente, utilizar como herramientas:
		- **Expresión genética**: Aplicación del Dogma Central de la Biología, que constituye el origen y la operativa fundamental detrás de la biología programable para nuestros fines.
		- **Crecimiento y división**: Implica un ciclo mediante el cual la célula crece (producto de la absorción de nutrientes) y se reproduce.
		- **Señalización**: Es el proceso por el cual las células se comunican entre sí o con el entorno.
		- **Evolución**: Las células cambian a lo largo del tiempo, adaptándose y recogiendo características externas, efectuando los cambios necesarios para su propia supervivencia.
