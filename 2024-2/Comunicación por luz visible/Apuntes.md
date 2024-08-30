# Comunicaciones por luz visible para industrias inteligentes
- 1 Solemne. Primera solemne (30%)
- 1 Proyecto (40%)
	- Simulación en matlab con una app que se instala en matlab. Analisis de resultados y graficos que entrega el simulador.
- 2 Proyecto, se pueden elegir 3 formas (30%)
	-  Ensayo (2 personas)
	- Software (2 personas)
	- Hardware (3 personas)

- Tx
	- Leds
- Canal
	- LoS
	- non-LoS (reflexiones)
- Rx
	- Photodetector
	- Photoresistor

# Clase 13-08
- Motivación para nuevas tecnologías de comunicación inalámbricas
	- Limitaciones, todas las tecnologías tienen ventajas y desventajas, las desventajas de una son la oportunidad de innovar en otra.
	- Interferencias, ruido y saturación.
	- Masificación de equipos, genera saturación. (IoT)
- Alexander Graham Bell, creador del teléfono y el fotófono.
- Harald Haas, Creó el termino LiFi (Light Fidelity)

La tecnología VLC se basa en la modulación de la intensidad de la luz LED para transmitir datos de manera rápida y segura 

- OWC: Optical wireless communication
	- VLC (Visible Light Communication): Transmisor es un LED y el receptor es un fotoreceptor.
	- FSO (Free Space Optic): Transmisor es un Laser y el receptor es un fotoreceptor.
	- OCC (Optical Camera Communication): Transmisor es un arreglo de LED y el receptor es un arreglo de fotoreceptores o una camara. De esta manera si cada LED es de un color, cada color sería un canal de transmisión.

- Outdoor:
	- Free Space Optics
	- V2V/V2I: 
	- VLC outdoor LiFi
	- UWOC
	- OOC VLC-IoT
- Indoor:
	- IR WSN
	- VLP OCC VLC-IoT
	- VLC Indoor LiFi

El espectro visible va entre [380 nm - 780 nm] la frecuencia [411 THz - 789 THz]
f = c / long.onda


**Ventajas de la Comunicación por LED**
- **Velocidad de Transmisión**:  
    La comunicación por luz visible (VLC) puede alcanzar velocidades de hasta 224 Gbps, lo que es entre 100 y 400 veces más rápido que las velocidades típicas del WiFi.
- **Interferencia Electromagnética (EM)**:  
    No hay interferencia entre las bandas de WiFi y el espectro visible. Además, el espectro de luz visible es 10,000 veces mayor que el espectro electromagnético utilizado por el WiFi, lo que reduce significativamente la posibilidad de interferencias.
- **Seguridad y Costo**:
    - **Seguridad**: La luz no atraviesa paredes, por lo que un atacante debe estar dentro del área iluminada para intentar acceder a la red, lo que incrementa la seguridad.
    - **Costo**: No se requiere una gran inversión en cables y antenas, ya que las lámparas LED pueden sustituir esos elementos, reduciendo costos.
- **Aplicaciones**:
    - **Aplicaciones médicas**: Es crucial reducir las interferencias electromagnéticas en entornos médicos, y la comunicación por LED es ideal para estos casos.
    - **Comunicación bajo el agua**: VLC es útil en ambientes submarinos donde las señales de radio no se propagan eficientemente.
    - **Uso en aviones**: La tecnología VLC es ideal para la comunicación en aviones, donde la interferencia electromagnética puede ser problemática.
# Clase 16-08
## Transmisión óptica
- Configuración básica de un sistema VLC/LiFi
	- Sistema VLC/LiFi
		- Los datos tienen que llegar de algun lado, por ejemplo desde internet.
		- Lamp Driver: es un hardware que controla la electricidad que le llega al led para que no se queme.
		- LiFi Dongle: Recibe la luz como un fotoreceptor pero incluye un circuito para realizar un procesamiento y transformar la luz a electricidad.
	- Transmisión
		1. Modulación y codificación (OOK, PAM, OFOM)
		2. Pre-distorsionador: Añade distorsión para quitar otra distorción, la que generan los mismos LED.
		3. Conversión Digital/Analógica: la electricidad es analógica
		4. Pulse Shaping: Sirve para mitigar la ISI
		5. DC biasing: Suma a la corriente alterna una corriente continua, para mover la alterna en el eje +Y, de esta manera el led puede responder ya que no funciona con corriente negativa. Unipolar(positiva) y real(no complejo).
		6. No se usan ampolletas porque generan calor y ruido térmico.
		7. Lumenes: Cuantos rayos de luz se emiten en un área determinada.

# Clase 27-08
## Recepción óptica
- VLC Receiver: Se tiene un elemento que hace la transformación Optico a eléctrico, TIA (Trans-impedance amplifier) (Amplificación), DSP.
	- Una vez que la señal sale del transmisor y llega al receptor.
	- Factores a considerar en el transmisor:
		- Ruido (Ruido térmico, ocurre cuando la señal está ya en el receptor)
			- AWGN (Ruido ideal, gaussiana)
		- Interferencia (Se produce en el canal de transmision)
		- Luego de que llega la señal al receptor una vez se le añaden los ruidos se debe **sincronizar**. De esta manera se saben los tiempos de muestreo y poder muestrearla correctamente
		- **Matched filter:** Importante en entornos donde hay mucho ruido, asi se puede eliminar gran cantidad de ruido.
		- Una vez está lo más limpia posible la señal se realiza la conversion Analógica/Digital
		- Luego se utiliza un **Equalizador**, aumenta o disminuye la amplitud de la señal. Ayuda para reducir la ISI que se produce a altas velocidades, por lo que a velocidades bajas es practicamente inútil usarlo.
		- Demodulación y decodificación, respocto a la modulación y codificación usada. Se utilizan métricas para saber si llegó bien la señal. BER (Bit error rate) y SER (Symbol error rate).
	- Elementos que incluyen al receptor:
		- Optical filter and concetrator:
			- Filtro óptico:
				- Capa traslucida que permite pasar ciertos rangos de longitudes de onda.
				- La onda que atraviesa el filtro depende del angulo de incidencia
			- Concentrador:
				- Su funcion es concentrar la luz a un punto específico sin importar como llega o en que angulo llegue. Sin el concentrador no todas las ondas llegarian al foto receptor
		- Photo-diode:
			- Semiconductor de tipo P-I-N
			- Material: Silicon, Germanium, InGaAs. Cada material tiene su responsividad.
			- Tiene un AP (Area activa)
		- TIA
		- Procesamiento