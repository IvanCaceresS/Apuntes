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


- Ventajas de la comunicación por LED
	- Velocidad de transmición, una conexión VLC puede alcanzar los 224Gbps, es decir entre 100 y 400 veces superior a la que es capaz de hacerlo WiFi.
	- Interferencia EM: No es posible que se interfieran entre las bandas de WiFi con las del espectro visible.
		- El espectro de luz visible es 10000 veces mayor al espectro electromanético WiFi
	- Seguridad y Costo: 
		- El atacante debe tener acceso a la luz, ya que la luz no traspasa paredes, por tanto tiene que estar iluminado por la misma luz que ellos quieran vulnerar.
		- No es necesario un gran gasto en cables y antenas, ya que todo eso pasaráa ser sustituido por una lámpara de luz LED
	- Aplicaciones:
		- Aplicaciones médicas: es crítico disminuir interferencias electromagnéticas
		- Bajo el agua.
		- En aviones
		- 