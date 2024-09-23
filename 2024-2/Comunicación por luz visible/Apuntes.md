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
			- Efecto fotoeléctrico
			- Responsividad (capacidad de transformar la luz en electricidad)
		- TIA
		- Procesamiento
	- Tipos de ruidos
		- Ruido térmico
			- A medida aumenta la frecuencia disminuye la densidad del ruido.
		- Ruido shot
			- Ocurre cuando se conecta un aparato o se energiza el circuito puede producirse un pick de voltaje en ese momento.
		- Ruido ambiental
			- Humedad que puede afectar en el fotodiodo, puede empañar el vidrio o plastico.
		- La cantidad de ruido depende del area del fotodiodo, a mayor area del fotodiodo mayor ruido
	- Interferencia
		- Se puede mitigar la interferencia mediante la creacion de un ADRs que es un arreglo de fotodiodos en forma de piramide donde por ejemplo son 4, cada uno de esos 4 recibe la señal de una manera distinta a alguna le llega mas interferencia que a otras, entonces luego se suman o se hace algun calculo a las 4 señales recibidas se puede mejorar la SINR
# Clase 03-09
## Modelo de canal
- Alámbrico
	- Medio físico:
		- Lineas de fuga
		- Fibra óptica
		- Cobre
		- Semiconductores
	- Modelamiento matemático probabilistico/estadístico.
	- Mientras más distancia, más atenuamiento. Pathloss.
- Inalámbrico
	- Medio físico:
		- Aire
		- Vacío
		- Agua
	- Mucha más atenuación, shadowing, scattering
- Configuraciones de tx y rx:
	- LoS imagen A
	- Solo Reflexion imagen C
	- Tracking LoS (angulo de incidencia) Imagen D
	- Reflexion y linea de vista. Imagen B
- Indoor optical wireless communication channel
# Clase 06-09
## LOS propagation model
- Linea de vista directa.
- No hay obstrucciones.
- Escenario ideal
### Light Source Model
![[Pasted image 20240906161521.png]]
(1) El ángulo de irradiancia es con respecto a la normal en el led, si el angulo del haz de luz está en 0° con respecto a la normal se alcanza el máximo de intensidad.
(2)
El semiángulo de la mitad de potencia va entre [60°-90°)]
Siendo 90°el peor
A medida que se amplía el angulo más se dispersa la luz, mientras que con menos angulo, mas concentrada está la potencia.

### Light Detectors
![[Pasted image 20240906162547.png]](3) Ángulo de incidencia, lo ideal es que sea 0°
(4) n es el coeficiente de reflexión

Todo se une en la siguiente formula:
![[Pasted image 20240906163656.png]]

Pauta Solemne 1 2022-2
**Calcular y graficar la respuesta al impulso ( magnitud vs tiempo) de la componente de canal LoS de un sistema** 
**Angulo de incidencia = 30°**
**Angulo de irradiancia = 45°**
**Posición del led = (2, 4, 4)**
**Posición del PD = (1, 4, 1)**
**Área efectiva del PD = 12 mm^2**
**Asumir ganancia unitaria y modo lambertiano de 1**

distancia se saca con los puntos = raiz(1+0+9) = raiz(10)
Aeff = Ap x cos(ang_inc)
Ap = 12 / cos(30°) = 10,39 mm^2
Ap = 1,39 x 10^-3
m se asume como 1
H_LoS = (1+1) x 1,39 x 10^-3  x cos(45) x cos (30) x 1 /(2 x pi x 10)
H_LoS = 2 x 1,39 x 10^-3  x 0,707106 x 0,866025 / (20 x pi)
**H_LoS = 2,71 x 10 ^-5**

tiempo que va a demorar en llegar al receptor
d/c = raiz(10) / (3x10^8) = **1,05 x 10^-8 segundos** = 0,105 nanosegundos
Ahora graficar eje X tiempo(ns) y eje Y (adimensional) se dibuja un pulso en los 0,105 ns con una altura de 2,71 x10^-5
# Clase 10-09
**PREGUNTAS TIPO SOLEMNE**
1. **El rango de longitudes de onda de trabajo de luz visible es:** 400nm a 700nm
2. **Intensity modulation/Direct Detection (IM/DD) se refiere a:** Real y positiva
3. **¿Cual es una limitación importante de la comunicación por luz visible?:** Dependencia de las condiciones del entorno
4. **¿Cuál es la funcion principal del modulador en un transmisor óptico?:** Modificar la intensidad o la fase de la señal óptica para llevar información
5. **¿Qúe componente se utilzia para separar las señales ópticas de diferentes longitudes de onda en un receptor óptico?:**  Filtro óptico
6. **¿Qué es la atenuación en la comunicación por luz visible en la componente LoS?:** La disminución de la intensidad de la señal a medida que viaja a través del
7. **¿Cómo afecta la distancia a la componente LoS en la comunicación por luz visible?**: A medida que la dist. aumenta, aumenta la atenuación
8. **¿Como se representa tipicamente la respuesta al impulso del canal en un sistema vlc?:** Como un grafico de barras en el tiempo
9. En un grafico la componente LoS es la que llega más rapido y es más alta, el resto son reflexiones, dispersiones. Si tienen la misma forma entonces tienen la misma cantidad de reflexiones. No se puede concluir el desempeño de los sitemas si no se tiene todo el contexto.
1. 
Angulo de incidencia = 30°
Angulo de irradiancia=45°
Area efectiva del PD = 12mm^2
Asumir ganancia unitaria y modo lambertiano de 1
DISTRACCION
tiempo se saca del grafico
TIEMPO = D/C
8,5ns = d/(3x10^8m/s)
d = (8,5 x 10^-9) x 3x10^8
d= 2,55 m
