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
- Los procesos de operación de un organismo (por ejemplo, comunicación intercelular, ejecución de rutas metabólicas o lisis programada) 
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
## Ejemplos de funciones celulares
- **Repressilator:** Es el circuito #1 que surgió en biología sintética. Un oscilador que se enciende y se apaga, basado en represiones de genes.
![[Pasted image 20240816120813.png]]
- **Circuito bi-estable:** es el circuito #2 que surgió en biología sintética. Encender y apagar.
- **Ruta metabólica de la glucosa:** Los organismos no crecen si no tienen glucosa, si no tienen buscan otra fuente de energía que puede durar un rato hasta volver a encontrar glucosa.
- Desplazamiento de bacterias inducido por **propulsión flagelar**, esto puede verse fomentado por la busqueda de glucosa.
- **Reporter:** GFP (Green Fluorecent Protein)
 ![[Pasted image 20240816121149.png]]

## Células
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
# Clase 20-08
## Expresión genética: procesos y actores asociados
- A veces no se requiere de células para que los sistemas funcionen en la biología sintética.
- Hoy vamos a analizar, con un grado de abstracción más alto que el de las primeras clases, la acción del ADN, ARN y proteínas en la biología programable.
- **Dogma central de la biología: ** ADN → ARN → PROTEINAS

- Glosario
	- Componentes que son útiles en la construcción de sistemas biológicos![[Pasted image 20240820114812.png]]
		- En el promotor: ARN polimerasa, realiza la transcripción de ADN a ARN.
		- Ribosoma toma los codones de ARN (aminoacidos) y los traduce a proteina.
		- RBS es el "promotor" de la traduccion.
		- CDS es el molde de ADN que sirve de guía o plantilla.
		- Terminador: marca el termino de la region a transcribir.
	- Interacciones que nos son útiles para representar la dinámica entre los componentes presentados.![[Pasted image 20240820115018.png]]
		- Represión: no deja que se realice la transcripción por lo que no se produce la proteina. Compuerta logica NOT
		- Activación: Es aquella interacción que promueve la transcripción y posterior traducción de una secuencia de ADN. Compuerta YES
	- Agrupaciones para construcción de circuitos genéticos:
		- Operón: Conjunto de genes cuya transcripción y posterior traducción está regulado por un único promotor.
		- Plásmido: Fragmento circular de ADN que agrupa operones y que generalmente aisla funcionalidad específicas. 
		- ![[Pasted image 20240820122725.png]]

- Ejemplos:
	- Circuito 1:
		- ![[Pasted image 20240820123656.png]]
		- Promotor constitutivo (Pconst): no requiere ningun estimulo para estar activo.
		- Promotor BAD: requiere de arabinosa para activarse. Y cuando hay lugares donde igual se activa GFP donde "no deberia" es porque promotor BAD  se "rompió" o mutó, por lo que ya no hay condicion para que se produzca GFP.
	- Circuito 2:
		- ![[Pasted image 20240820124430.png]]
		- Es un NOT de la GFP.
		- El primero es constitutivo porque no tiene nada abajo.
		- Si hay lacl entonces no se prende gfp. Pero como siempre se genera entonces CHAO.
# Clase 23-08
## Otras herramientas y consideraciones
- Sistema CRISPR/Cas9 (Clustered Regularly Intersapced Short Palindromic Repeats)
	- Se trata de un sistema inicialmente empleado alrededor del año 2012, y que proviene originalmente del “sistema inmune” de las bacterias y arqueas.
	- Dicho sistema fue cambiado de su propósito original para usarlo en la biología programable para la edici´on de cadenas de ADN.
	- Los componentes más importantes que integra este sistema son 2:
		- Proteína Cas9 (Misil teledirigido): Es una proteína que cumple la función de reconocer una cierta secuencia y “cortarla”. 
		- gRNA (Guia del misil): Se trata de una secuencia de ARN que sirve de guía para la proteína Cas9 y en base a la cual reconoce el sitio en la cadena de ADN que debe cortar.
	- De esta manera sabe donde debe cortar, donde quiere que vaya el misil teledirigido.
	- Aplicar Cas9 a una bacteria representa una carga metabólico significativa  por lo que el resto de procesos le costará más.
	- Si llega una infección traida por un fago, Cas9 toma ese trozo de ADN del virus y lo pega para "Acordarse de él en un futuro" y combatirlo. Y la misma Cas9 destruye al ADN infeccioso.
	- CRISPR/Cas9 se puede usar especificamente para:
		- ![[Pasted image 20240823120853.png]]
		- Insertar una porción precisa de ADN en una secuencia existente.
		- Eliminar una sección precisa de ADN de una secuencia existente.
		- Aplicar represión con dCas9: d significa death, eso ocurre cuando la rompen y Cas9 ya no "corta", por lo que desde el punto de vista funcional está muerta. Por lo que sirve de tope, ya que identifica el trozo de ADN pero no lo corta por lo que es un mecanismo de represión y de esta manera se dice "Para ahi y no dejes que pase la transcripción para allá"
		- Las dos primeras funcionalidades expuestas son cruciales, puesto que permiten modificar un circuito “en tiempo de ejecución”.
- Crecimiento y división celular
	- Es uno de los procesos básicos de la célula: consumen nutrientes y además de proveer la energía para llevar a cabo todos los procesos celulares necesarios para la vida, también se traduce en un aumento de la biomasa del ente. 
	- Dicho crecimiento conduce a la reproducción y proliferación de la células. 
	- Cada tipo de célula tiene su forma de dividirse
	- ![[Pasted image 20240823120912.png]]
	- El crecimiento es una métrica de que tan bien va la celula, o cuán "a gusto" está la célula en su condición actual. También mide cuánta carga metabólica tiene.
	- Los tiempos de división típicos van desde los 20 a 40 minutos. Por lo general las de 40 minutos son las que tienen circuitos y más funciones internas que producen más carga metabólica.
- Completando la asociación
	- Un YES ← y un NOT ->![[Pasted image 20240823121604.png]]
	- Dada la interpretación de estos circuitos, quisiéramos tener un par más de operaciones de la lógica para poder tener un control más acabado y completo sobre nuestros circuitos. ¿Qué funciones cumplen los siguientes circuitos? ![[Pasted image 20240823121734.png]]
	- El primero: El promotor constitutivo expresa proteina A y esta induce al Pa que expresa gfp. Igual con la B. Por lo que es un OR, ya que si está A se enciende, si está B se enciende, si están ambos se enciende, pero si no hay ninguno no se enciende.
	- El segundo: Es un ADN, requiere que estén A y B al mismo tiempo.
	- ¿Y este?![[Pasted image 20240823122147.png]]
	- Es un NAND ya que si está A y B expresa C, y C a su vez reprime Pc y no se enciende.
	- Tanto la compuerta **NAND** como la **NOR** son lo que se conoce como **compuertas lógicas universales**. Esto significa que puedes construir cualquier otra compuerta lógica (como AND, OR, NOT, XOR, etc.) utilizando solo compuertas NAND o solo compuertas NOR.
# Clase 27-08
## Diseño de circuitos
Lineamientos de diseño de circuitos y su interpretación para ser estudiados.

En los circuitos que hemos visto, los **transcripcionales** hay una estructura general en que cada operón del circuito se organiza de la siguiente forma:
- Promotor
- Operador
- RBS
- Genes
- Terminador
## Simplificación de notación de un circuito
![[Pasted image 20240827114021.png]]
SBOL, es un lenguaje gráfico de diseño de circuitos, sino que además provee de un ontología que vincula a los elementos de la biología y a su información.

## En que cancha jugamos
- Genoma y plásmido, no conviene generalmente alterar el genoma ya que se pueden tocar funciones vitales, por eso se hace generalmente en el plásmido.
- Por que querriamos hacerlo en el plásmido:
	- Control: Permite aislamiento (de ADN)
	- Maleabilidad evolutiva: Si el plásmido es muy pesado metabólicamente hablando, al dividirse van a intentar dejarlo de lado, perdiendose en las futuras generaciones, y si es muy liviando puede haber una proliferación descontrolada. Al ser los plásmidos elementos móviles e independientes, estos se pueden perder (y adquirir) en el proceso evolutivo de forma mucho más simple que respecto de un cambio en el genoma.
	- "Instalación" del circuito: Es más simple integrar un circuito al organismo en un plásmido que intervenir su genoma. Para ello, las bacterias se transforman con el plásmido (transformar es un proceso, ej: Electrocutarlas y que se "traguen" el ADN al "abrir" la membrana).
- Ahora, ya sabiendo donde conviene alojar los circuitos sinteticos (en el plásmido). Estos son otros lineamientos:
	- Carga metabólica: Es importante considerarlo, el circuito podría dañar el correcto desarrollo del organismo, asi como ser eliminado por evolución. **¿Que pasa si queremos diseñar un circuito complejo?** R: Hay alternativas que tratan con ese problema.
	- Hay sistemas o partes más complejas que ya están definidas y se pueden integrar directamente a los circuitos. (SynBioHub, Biobricks o iGem).

## Circuitos Complejos
¿Cómo hacemos si necesitamos trabajar con circuitos más complejos?
- Varias posibles miradas para poder diseñar e implementar circuitos complejos: 
	- **Simplemente diseñar y adosar el circuito al organismo.** Esta vía es muy arriesgada y posiblemente falle por razones metabólicas y evolutivas.
	- **Vincular el circuito diseñado a algún proceso vital del organismo.** En el ejemplo de la glucosa, la asimilación de ATP es un proceso importante para el organismo, por lo que se privilegiará la optimización evolutiva y permanencia del circuito que hace posible el proceso.
	- **Alojamiento del circuito en un chassis mínimo del organismo objetivo.** Hay un área avanzada de investigación que guarda relación con la búsqueda de una organización genética mínima para la vida. Usando estos chassis, es posible cargar al organismo metabólicamente. (Célula que se le quita muchas cosas teniendo lo minimo, así va a tener menos peso metabólico)
	- **Comunicación celular.** Usando conjuntos de organismos (consorcios), es posible atacar tareas complejas al repartir computación entre los organismos. En esta asignatura, nosotros nos enfocaremos en esta estrategia y mostraremos varias formas de comunicación y su uso combinado.
# Clase 30-08
## Comunicación intercelular I
Es necesario conectar a las células.
- Quorum sensing (QS): Sistema descubierto en 1979. Cada organismo puede estimar la densidad poblacional que le rodea de modo de efectuar o no alguna accion de forma coordinada. El sistema trabaja con pequeñas moléculas que se expelen/sienten en el entorno y denominadas **autoinductores**
- ¿Qué son los autoinductores?
	- Son moléculas emitidas por las células al ambiente. Imaginar como gritar en la sala y si hay mucho ruido se sabe que hay mucha gente se puede realizar una estimación.
	- Permite a la célula estimar a cantidad de organismos próximos (y no tan próximos) que tiene al sentir la concentración de autoinductores en el ambiente.
	- Los autoinductores no sirven como vehiculo de ADN. No transportan una gran cantidad de información ni mucho menos un circuito.
- Así como se emiten, tambien se reciben
	- Ya que se envían autoinductores, es porque se deben leer por los demás organismos, para esto esta el sistema **lux**
	- Sistema lux
		- Proviene de un circuito responsable de bioluminiscencia.
		- El sistema consiste de un gen de emisión (luxl) de autoinductores (AHL) y otro gen distinto de recepción (luxR) de AHL que genera (esos pacman) que captan los AHL.
		- ![[Pasted image 20240830115116.png]] 
		- ![[Pasted image 20240830115248.png]]Los más importantes son
		-  El promotor de luxR siempre está activo pero con una pequeña actividad (actividad basal), generando poca cantidad de AHL pero cuando ya recibe más genera más
		- El promotor lux tambien está activo con una pequeña cantidad.
		- Es por esto que se genera está actividad cuando existe mucha densidad de organismos, osea que se aumenta la concentración de AHL, lo que interesa es el circulo completo de AHL.
		- **Caracterización del sistema lux**
			- Es un método de comunicación y coordinación intercelular de largo alcance para construir consorcios.
			- Los AHL se expelen al ambiente.
			- Señal que el organismo difunde en el entorno.
			- El sistema es programable, ya que se pueden colocar genes que estén downstream (aguas abajo) del operón de recepción y que hagan un tarea (ej: brillo verde).
			- Información transportada mínima.
			- El alcance se determina por si sigue generando o no AHL, ya que el nuevo empuja al viejo llegando más lejos. AHL es tan pequeño que simplemente atraviesa la membrana.
		- **¿Qué es lo bueno del sistema lux?**
			- Simple de programar.
			- Comunicación de largo alcance.
			- Peso metabólico bajo para el organismo.
			- Método de comunicacón inter-especie.
			- Sistema más usado en la biología programable.
		- **¿Qué es lo malo?**
			- Baja cantidad de información transmitida.
			- No es posible direccionar información ya que es un broadcast.
			- Puede haber crosstalk con sistemas parecidos (por ejemplo sistema Las).
			- No se determina con exactitud la densidad celular, sino que se utilizan umbrales de concentración de autoinductores.
# Clase 03-09
## Comunicación intercelular II
Otro método de comunicación entre células: **Infección por bacteriófagos**
- Los fagos son virus (no vivos) que infectan a la células.
- Llevan carga genética, una hebra de ADN.
- Son muy especificos, un fago buscará un tipo específico de organísmo.
- No tienen un proceso autónomo ni procesos centrales para la vida.
- **¿Qué hacen los fagos?**
	- Infecta a la célula insertando el ADN/ARN que trae a través de la membrana celular.
	- Este ADN/ARN trae todas las instrucciones para secuestrar la maquinaria de la célula para replicarse.
- **¿Cómo funciona?**
	- ![[Pasted image 20240903115056.png]]
	- ![[Pasted image 20240903120827.png]]
	- **Ciclo Lisogénico:** En este ciclo, el fago (virus) inserta su ADN en el genoma de la bacteria. Este ADN viral se integra en el ADN bacteriano y se replica de manera silenciosa y asintomática a medida que la bacteria se divide. En este estado, el virus no destruye la célula huésped inmediatamente.
	- **Ciclo Lítico:** En este ciclo, el ADN del fago utiliza la maquinaria de la bacteria para producir nuevos virus. Durante la fase de ensamblaje ("assembly"), se ensamblan nuevas partículas de fago dentro de la bacteria. Finalmente, en la fase de lisis ("lysis"), la bacteria se rompe (o lisa), liberando los nuevos fagos, lo que resulta en la muerte de la célula bacteriana.
- **¿Por qué hariamos esto a nuestras bacterias?**
	- El ADN/ARN no tiene por que ser maligno, puede ser benéfico como información de otras amenazas.
- **Caracterización del uso de fagos**
	- Beneficios
		- Se puede ver como un metodo de comuncación y coordinación intercelular de largo alcance.
		- Permite programabilidad a la célula
		- La señal de información transportada es mayor que en el caso del QS, es posible entregar circuitos completos en el destino
	- Los malo
		- No es posible direccionar la comunicación completamente
		- Se debe ser preciso y cuidadoso con la organización del circuito a transportar.
		- No responden a antibióticos, son muy dificiles de controlar puesto que no tiene un proceso de vida.
	- Uso
		- El uso es muy bajo aún, porque es un campo que se ha estudiado poco aún.
		- Técnicas basadas en el uso de fagos
			- Phage therapy
			- Phage display
			- Lispeza por fagos (carne)
# Clase 06-09
## Comunicación intercelular III
La conjugación bacteriana consiste en el traspaso de un plásmido completo desde una bacteria portadora a otra vecina. Es un método de transferencia **horizontal** de genes (HGT)
- Transferencia horizontal:
	- Es cuando los microbios intercambian material genético entre individuos que no son descendientes directos. Esto ocurre entre microbios de la misma o incluso diferentes especies. Hay tres principales formas de transferencia horizontal en microbios:
	- **Transformación**: Una célula capta ADN libre del entorno.
	- **Conjugación**: Dos células se unen y transfieren ADN a través de un puente citoplasmático.
	- **Transducción**: Un virus bacteriófago transfiere ADN de una bacteria a otra.
- Transferencia vertical:
	- Es la transmisión de material genético de una generación a la siguiente, es decir, de "padre a hijo". En los microbios, esto ocurre cuando una célula madre se divide y transmite su ADN a sus descendientes. Es el tipo de herencia tradicional, similar a lo que ocurre en organismos multicelulares.
- **¿Cómo sucede esto exactamente?**
	- ![[Pasted image 20240906114627.png]] Bacteria de la izq. conjugando el plásmido rojo a la bacteria de la derecha
- **¿Cuándo sucede la conjugación?**
	- Existen condiciones (supuestas, ya que aun no está totalmente desvelado)
		- Hay un tiempo suficiente de ese contacto entre organismos.
		- Existe un plásmido que se puede trasladar
		- El plásmido debe tener la capacidad de formar un pilus de tipo T4SS (Secretion System). Este es el puente de transporte.
		- La membrana de la bacteria receptora es capaz de dejar pasar y alojar el plásmido en su citoplasma.
	- ![[Pasted image 20240906115213.png]]
	- a) Relaxasa, es una proteina que es causante de la conjugación. Corta una de las 2 hebras de ADN justo en ori T.
	- b) T4CP(la azul), agarra el ADN desde el ori T y lo arrastra a T4SS(la verde, el pilus),
	- c) Ambos organismos tienen la información genética.
- **¿Programabilidad?**
	- Se puede programar en 2 niveles:
		- A nivel de plásmido, hay estapas que se pueden condicionar al estar controladas por proteínas específicas:
			- Corte de una de las hebras del plásmido (Relaxasa - Rel) en la zona del origen de transferencia (oriT)
			- Ensamblaje del canal de transferencia hacia la otra bacteria (T4SS)
			- Desenrollado y guía de la hebra hacia el canal de transmisión (T4CP)
		- El segundo nivel es el de la bacteria de destino, es posible programar la membrana de modo que implemente exclusión y el canal de la bacteria emisora no pueda acceder a la receptora.
- **Caracterización de la conjugación bacteriana**
	- La transferencia de información que causa la conjugación es muchisimo mayor que la de QS y la de fagos pues transporta un plasmido de ADN.
	- Es comunicación local (corta distancia)
	- Es posible dirigir ( hasta cierto punto) por medio de exclusión de entrada a las bacterias receptoras. No es preciso.
	- Es programable.
- **Ventajas**
	- El nivel de programabilidad de la conjugación bacteriana es muy elevado. Mucha alteración posible a los circuitos.
	- Mayor cantidad de información trasladada.
	- La comunicación es de corto alcance y bastante más controlada que en QS y los fagos.
- **Desventajas**
	- Muy lento
	- No es posible direccionar completamente la comunicación.
	- Se debe ser cuidadoso con el diseño del plásmido a transportar, ya que el peso metabólico adicional implique que se diluya evolutivamente.
- **Uso**
	- El uso de esta técnica en biología programable es algo poco usado aun.
	- Compartir rasgos beneficiosos con la colonia.
	- Neutralizar la resistencia a antibióticos y trasladar 
