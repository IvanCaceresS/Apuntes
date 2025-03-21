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
# Clase 24-09
SIMULACIÓN CON GRO
'kdiff': que tanto se esparse la gota
'kdeg': que tanto se degrada la difusion
'genes': es un operón
	'proteins': es la salida del operón
	'promoter': define la logica del promotor (YES, TRUE, NOT)
	'transcription_factors': Que activa al promotor
	'noise': simula fallos como, toOff probabilidad de que se pague el promotor si o si, toOn probalidad que este encendido si o si, noise_time tiempo desde el que comienza a regir estas probabilidades
	'prot_act_times': tiempo en minutos con distribucion normal que simula la subida en la concentración de las proteinas
	'prot_deg_times': tiempo en minutos con distribucion normal que simula la bajada en la concentración de las proteinas
'plasmids_genes': define los operones dentro del plasmido
'c_ecolis': c_ecolis(100,0,0,80,{"pYES"}, program p()) 
	define un circulo con :cantidad de ecolis 100, en el centro (0,0) el radio es 80, que ciruito se aplica a esta colonia
'action': pintar o QS(quorum sensitive)
	'd_paint': define como cambian los colores con ausencia o expresión de por ej gfp, cuando es 1 significa que se va encendiendo y con -1 va apagandose. el resto de 0,0,0 son como rgb pero b es cyan.
	's_get_QS':huele la arabinosa por ejemplo cuando la concentración es mayor a 0,5 entonces se activa arac
	'set_growth_rate': define cuando se duplican por ej 0.017 son 40 minutos.
En el main se aplican cosas acada fotograma relacionadas con el entorno completo
	's_set_signal': es como dejar caer una gota de por ej arabinosa de 20 en 20 cada fotograma en 0,0.
# Clase 08-10
**Control 2:** Materia que se dejó antes de las solemnes y un poco de lo visto en estas clases.
## Biología sintética y de sistemas I

Ya habiendo visto una gran variedad de elementos que participan en la implementación de circuitos, ahora nos centraremos en analizar los usos principales que se les da a circuitos y sistemas del área.

**¿Qué es un sistema?**
- Conjunto de organismos o entes que actúan coordinadamente mostrando un comportamiento único y que apunta a un objetivo particular.
- Un ejemplo de estos sistemas es el **Repressilator**

La biología programable toca dos áreas de estudio:
- Biología sintética:
	- Rama de la biología que consiste en construir circuitos/sistemas que exhiben un comportamiento artificial
	- Es la ingeniería de la biología
	- Parte en el año 2000 con la publicación de 2 circuitos funcionales:
		- Repressilator:
			- Sistema oscilatorio integrado por tres operones que se reprimen en secuencia y generan un periodo de expresión de cada una de las proteínas de cada operon.
			- Funciona con Feedback negativo: Es como un oscilador pero estabilizador al mediano/largo plazo, ya que va a variar las concentraciones hasta que se estabiliza(autorregulación). Ya que se estabiliza, un repressilator al mediano/largo plazo tambien se estabilizará.
			- Patrones temporales: Cada gen se expresa regularmente después de un periodo de tiempo transcurrido.
			- Automatización: El circuito funciona solo una vez que ha iniciado su operación.
		- Toggle Switch:
			- ![[Pasted image 20241008122223.png]]
			- Interruptor que trabaja con una represión mutua entre dos genes, ya que debo introducir señales externas para que funcione.
			- Circuito biestable, como un bit
			- Las represiones pueden ser interrumpidas por una señal del ambiente. Por ejemplo IPTG interrumple la represion causada por LacI y aTc se encarga de interrumpir la represión causada por TetR.
			- Memoria a largo plazo: El sistema mantiene su estado invariable a lo largo del tiempo si es que las condiciones se preservan.
- Biología de sistemas


# Clase 11-10
## Biología sintética y de sistemas II
Control 2: Viernes 18-10 (intercelular y clase pasada. Probablemente entre análisis de una red)
Tarea 2: Semana del 28 de octubre (simulador gro)
- **Patrones espaciales**: conjunto de características espaciales distintivas que se repiten y/o se mantienen constantes en el tiempo-
	- Ej:
		- Formas
		- Distribución de regiones
		- Colores
		- Ubicaciones dadas en lugares específicos de la colonia
	- ¿De qué sirven?
		- Biología del desarrollo:
			- Lineas de los tigres, caparazones de los caracoles. Son las interacciones entre organismos de acuerdo a señales de omunicación son las que dirigen esas formaciones complejas sobre las que nos preguntamos
		- Control a escala:
			- Como consecuencia de poder formar patrones, poder establecer distribuciones lo más precisas posible, por ejemplo para liberación de farmacos o la organizacion para construcción de biomateriales.
		- Identificación de características específicas en el espacio: Poder medir cual es el lugar a partir del cual la concentración de cierta sustancia en el medio es excesiva.
	- Ejemplos de patrones
		- Brand detector
			- Una detección de concentraciones (alta, media, baja)
			- Tres plásmidos (pHD, pLD, pSND)
			- ![[Pasted image 20241011120123.png]]
			- celeste maxima concentración, rojo alta, verde muy baja. El halo negro es el rango que no considera ninguna de las otras, por eso es como medio.
			- Usa 2 LacI(uno normal y otro modificado)
			- ![[Pasted image 20241011121503.png]]
		- Edge detector
			- Hacen el borde de la máscara de lo que está brillando (el borde entre donde hay luz y donde no la hay)
			- Requisitos
				- Único color: pigmento negro.
				- No marcan las zonas de luz y las zonas de oscuridad
				- Se busca un único circuito en todas las bacterias de la colonia
				- Se valida su funcionamiento usando distintas formas de mascaras de luz
				- Desde la oscuridad las bacterias emiten una señal
				- Las bacterias que están en la luz, si están en la luz y detectan señal entonces me pinto negro.
			- Condiciones
				- Trabaja con proteína fotosensible
				- Usa el sistema luz para atravesar la frontera luz-oscuridad
				- El pigmento solo se expresa en la luz.
			- ![[Pasted image 20241011122901.png]]
			- En vez de pintar negro, se podria liberar un farmaco y que en vez de luz sea que existe un patógeno.
# Clase 15-10
## Biología sintética y de sistemas III
- French flag
	- Se basa en la concentración de morfógenos (algo que genera una forma, una señal que indica hacer algo. por ejemplo en el brand detector es la señal del centro)
	- El uso de n umbrales da lugar a n+1 zonas radiales detectadas
	- ![[Pasted image 20241015114700.png]]
	- Si se identifica una frontera equidistantes, es decir que se detecta la misma concentración de ambos morfógenos es posible trazar patrones no radiales (lineales)
	- ![[Pasted image 20241015115537.png]]
	- Patrón cuadrado a partir de diversos focos de morfógenos.
- Variante de Brand detector
	- Dividir el procesamiento, un brazo largo(detecta concentración dejana) en un plásmido, un brazo corto(detecta concentracion a corta distancia) en otro plásmido.
	- Esto tiene un problema porque si un plásmido de brazo largo está en el centro donde se tiró el morfógeno no tiene sentido porque es inutil. por lo que se le castiga diciendo que no prolifere. Y en caso de que un plásmido esté en una posición favorable o donde debe ser, se le premia induciendo que las demás cercanas adquieran esta propiedad(conjugación bacteriana).
	- ![[Pasted image 20241015121601.png]]
	- El nivel de definición del patrón depende de la movilidad o velocidad de conjugación del plásmido.
	- Es un patrón espacial.
# Clase 22-10
## Biología sintética y de sistemas IV

- Patrones temporales:
	- No necesariamente hay una posibilidad de ver lo que hace el patrón.
	- Exhiben **reproducibilidad** o **predicción** en lo que ocurrirá en el tiempo
	- Predecible y repetitivo
	- **Circuitos relacionados:**
		- **Repressilator**
			- La expresión de los genes del circuito se lleva a cabo secuencialmente y de forma cíclica. Entonces es predecible y se reproduce automáticamente(aunque no sea visible)
		- **Autonomous bioreactor**
			- ![[Pasted image 20241022123146.png]]
			- Se genera rojo,el ahl de rojo corta P1, ahl rojo  activa amarillo, ahl amarillo corta P2, ahl amarillo activa verde, ahl verde corta P3.
# Clase 25-10
## Biología sintética y de sistemas V
- Un circuito para control de población de bacterias
	- ccdB (gen de toxina, induce a la apoptosis)
	- Con el QS al determinar cierta concentración de organismos se puede liberar este ccdB para controlar la población.
	- ![[Pasted image 20241025115705.png]]
	- E: corresponde a ccdB
	- Depende de la concentraciones intermedias de proteínas y de la afinidad de expresión de promotor. Por esto no se muere toda la colonia de una vez.
	- Se asemeja al repressitalor, ya que oscila igualemente, pero oscila en densidad poblacional.
- Medición de crosstalk
	- Es útil para saber cuáles son los sistemas que muestran crosstalk para no colocarlos en un mismo circuito, y cuales sistemas si.
	- Los experimentos consisten en ir cambiando el AHL de un sistema X, usar proteínas receptoras de un sistem aY, y activar un promotor de un sistema Z.
	- ![[Pasted image 20241025123203.png]]
	- En resumen, hay muy pocos sistemas de comunicación de QS.
	- Hay que tener sumo cuidado al elegirlos para implementar circuitos, porque de los pocos que hay, además presentan crosstalk.
# Clase 05-11
## Clase especial, lo que vió el profe en el congreso.
Congreso sobre bacteriófagos, casi nada computacional.
Usar bacteriofagos para bioremediar plantas de aji, el fago es sensible al ultravioleta.
# Clase 08-11
## Estándares de datos de SynBio
- FASTA/FASTQ
	- Son archivos de texto que describen una secuencia de nucleótido/aminoácidos con anotaciones, es como anotarlo en binario pero con nucleotidos(A,C,T,G)
- Genbank
	- Se diferencia de FASTA en que está más organizado y ya hay más información de la data.
	- Indica los pares de bases que hay y más información.
- SBOL
	- Es un diagrama de clases
	- Está escrito en RDF
	- El lenguaje de consulta de RDF es SPARQL
	- Es jerárquico, un componente dentro de un componente y asi..
	- Es muy automatizable el acceso a toda la información
	- Formato por defecto en la comunidad.
	- Desventajas: La diversidad de versiones del estándar y poco avance hacia la ultima. Con SBOL 2 hay posibilidad de incluir mucha información pero con SBOL 3 se pueden hacer muchas más cosas y el cambio en el formato es muy grande.
- Repositorios
	- Synbiohub (https://synbiohub.org)
	- iGEM Registry (https://technology.igem.org)
	- Estos repositorios se nutren de la competencia internacional de diseño y creación de circuitos sintéticos de estudiantes y de los resultados obtenidos por investigadores en todo el mundo.
- Herramientas que trabajan con estos datos
	- iBioSim (v3)
		- Simulador de circuitos que usa SBOL (v2) y SBML
	- pyBrick-DNA
# Clase 12-11
Control 3: Solo patrones
## Biología sintética y de sistemas VI
- Aplicaciónes "computacionales" (Dos papers)
	- **Decodificación de una señal BCD a 7 segmentos**
		- Binary coded digit
		- Primero se describe el circuito digital a su forma electrónica
		- Luego se usa el software Cello que transforma el circuito a su equivalente en términos de circuitos basados en compuertas NOT, OR y NOR y con asignación de factores de transcripción.
	- **Almacenamiento de datos en bacterias usando ADN**
		- Con 42 bits se puede almacenar 4TB. 2^42
		- Con nucleótidos al ser 4 entonces es con 21 nucleótidos. 4^21
		- Almacenamiento de una foto y un gif.
# Clase 15-11
## Inteligencia Artificial in-vivo
- IA: Persigue emular comportamientos o algoritmos inteligentes que llevaría a cabo un humano.
- Cambio de paradigma: Aprovechar el procemiento de los bichos y codificar un tipo distinto de IA.
	- Ventajas: podemos aprovechar su replicación, comunicación y evolución.
	- Desventajas: Velocidad y complejidad de cálculos realizados.
	- Trabajos relacionados
		- Algoritmos Genéticos
			- BAGA (Bacterial Agent Genetic Algorithm)
		- Framework Metaheurísticas
		- Redes Neuronales: Red se entrena en computador y se pasa a cello la funciona que describe el modelo y lo traduce a un circuito genético que se carga a los organismos.
# Clase 19-11
