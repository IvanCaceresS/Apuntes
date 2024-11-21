Intercell 1->3 y SSB 1.
Analizar el circuito en su conjunto, como sistema. Más macro.
Analizar desde un punto de vista más global, circuito.
Saber la función del circuito en si.
![[Pasted image 20241017194404.png]]

| Método de Comunicación      | Mecanismo                                                                                                                                                                                 | Características                                                                                                                                                                                                             | Ventajas                                                                                                                 | Desventajas                                                                                                                               | Usos Principales                                                                                                                       |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Quorum Sensing (QS)         | Liberación y recepción de autoinductores (AHL)                                                                                                                                            | - Comunicación basada en pequeñas moléculas llamadas autoinductores  <br>- Sistema lux: luxI genera AHL, luxR los detecta  <br>- Coordinación basada en la densidad poblacional                                             | - Simple de programar  <br>- Comunicación de largo alcance  <br>- Bajo peso metabólico  <br>- Comunicación inter-especie | - Baja cantidad de información transmitida  <br>- No direccionable, es un broadcast  <br>- Posible crosstalk con otros sistemas similares | - Construcción de consorcios intercelulares  <br>- Biología sintética (ej. bioluminiscencia)                                           |
| Infección por bacteriófagos | Transferencia de ADN/ARN mediante fagos                                                                                                                                                   | - Los fagos son virus que insertan su material genético en la célula huésped  <br>- Ciclo lisogénico: el ADN viral se integra en la bacteria  <br>- Ciclo lítico: el fago usa la célula para replicarse y luego la destruye | - Permite transportar circuitos completos  <br>- Mayor cantidad de información que en QS  <br>- Largo alcance            | - Difícil de controlar  <br>- No responden a antibióticos  <br>- No direccionable                                                         | - Phage therapy  <br>- Phage display  <br>- Ingeniería genética en biología sintética                                                  |
| Conjugación bacteriana      | Transferencia de plásmidos a través de un puente citoplasmático. Relaxasa corta una de las 2 hebras de adn, T4CP guía esa hebra hasta T4SS que es el pilus que conecta a la otra bacteria | - Transferencia horizontal de genes  <br>- Requiere contacto entre bacterias  <br>- Involucra plásmidos y el sistema de secreción T4SS para la transferencia de ADN                                                         | - Muy programable  <br>- Mayor cantidad de información que QS y fagos  <br>- Comunicación más controlada                 | - Comunicación lenta  <br>- No direccionable completamente  <br>- Diseñar plásmidos puede ser complicado                                  | - Transferencia de rasgos beneficiosos  <br>- Neutralización de resistencia a antibióticos  <br>- Compartir información genética local |

## Comunicación intercelular I
Para generar la red de organismos es necesario conectar a las células.
- Quorum sensing (QS): Sistema descubierto en 1970. Cada organismo puede estimar la densidad poblacional que le rodea de modo de efectuar o no alguna accion de forma coordinada. El sistema trabaja con pequeñas moléculas que se expelen/sienten en el entorno y denominadas **autoinductores**.
- ¿Qué son los autoinductores?
	- Son moléculas emitidas por las células al ambiente. Imaginar como gritar en la sala y si hay mucho ruido se sabe que hay mucha gente se puede realizar una estimación.
	- Permite a la célula estimar a cantidad de organismos próximos (y no tan próximos) que tiene al sentir la concentración de autoinductores en el ambiente.
	- Los autoinductores no sirven como vehiculo de ADN. No transportan una gran cantidad de información ni mucho menos un circuito.
- Así como se emiten, tambien se reciben
	- Ya que se envían autoinductores, es porque se deben leer por los demás organismos, para esto esta el sistema **lux**
	- Sistema lux
		- Proviene de un circuito responsable de bioluminiscencia.
		- El sistema consiste de un gen de emisión (luxl) de autoinductores (AHL) y otro gen distinto de recepción (luxR) de AHL que genera (esos pacman) que captan los AHL.
		- 
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
	- **Ciclo Lítico:** En este ciclo, el ADN del fago utiliza la maquinaria de la bacteria para producir nuevos virus. Durante la fase de ensamblaje ("assembly"), se ensamblan nuevas partículas de fago dentro de la bacteria. Finalmente, en la fase de lisis ("lysis"), la bacteria se rompe (o lisis), liberando los nuevos fagos, lo que resulta en la muerte de la célula bacteriana.
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
	- b) T4CP(la azul), agarra el ADN desde el ori T y lo arrastra a T4SS(la verde, el pilus).
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

## Biología sintética y de sistemas I
**Control 2:** Materia que se dejó antes de las solemnes y un poco de lo visto en estas clases.

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






