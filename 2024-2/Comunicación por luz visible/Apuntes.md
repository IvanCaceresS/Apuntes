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