## Redes: Capa Física

### El espectro electromagnético

- Representación gráfica del espectro electromagnético desde las frecuencias muy bajas (VLF) hasta la luz ultravioleta (UV).
- Tipos de transmisión asociados con distintas frecuencias: par trenzado, cable coaxial y transmisión óptica.
- **Abreviaciones:**
    - VLF: Very Low Frequency
    - LF: Low Frequency
    - MF: Medium Frequency
    - HF: High Frequency
    - VHF: Very High Frequency
    - UHF: Ultra High Frequency
    - SHF: Super High Frequency
    - EHF: Extra High Frequency
    - UV: Ultraviolet Light

### Propiedades de las frecuencias bajas

- Mayor penetración a través de objetos opacos a la luz visible.
- Menor ancho de banda por canal debido a regulación y capacidad de procesamiento.
- Potencia de transmisión y ciclo de trabajo regulados para asegurar convivencia en bandas no licenciadas (ISM).

### Asignación de frecuencias en Argentina

- Mapa del espectro en Argentina (2015), mostrando distribución y asignación de frecuencias para diversas aplicaciones y servicios.

### Bandas ISM en el mundo

- Bandas ISM típicas utilizadas globalmente:
    - 13,553 - 13,567 MHz
    - 26,957 - 27,283 MHz
    - 40,66 - 40,70 MHz
    - 433 - 464 MHz
    - 900 - 928 MHz
    - 2,4 - 2,5 GHz
    - 5,725 - 5,875 GHz
    - 24 - 24,25 GHz
    - 868 MHz (Europa)

### Principios de Transmisión Inalámbrica

- Señal compuesta de portadora y la información, expresada como s(t)=A(t)sin⁡(2πf(t)t)+θ(t)s(t) = A(t) \sin(2\pi f(t)t) + \theta(t)s(t)=A(t)sin(2πf(t)t)+θ(t).
- La información se modula en la portadora.
- Modulación analógica (valores reales dentro de un rango) o digital (valores limitados).

### Tipos de Modulación

- **ASK (Amplitude Shift Keying):** Modulación por desplazamiento de amplitud.
- **FSK (Frequency Shift Keying):** Modulación por desplazamiento de frecuencia.
- **PSK (Phase Shift Keying):** Modulación por desplazamiento de fase.

### Demodulación y probabilidad de error

- El receptor reconstruye los bits de la señal transmitida demodulándola.
- Menor probabilidad de error con señales digitales.

### Problemas típicos en la transmisión inalámbrica

- **Offset de frecuencia:** Requiere sincronización con la portadora del transmisor.
- **Sincronización de Bit o de Símbolo:** Encontrar los límites del símbolo.
- **Sincronización de Frame**
- **Detección (y posible corrección) de errores:** Utilizando ARQ (Automatic Repeat reQuest) y FEC (Forward Error Correction).

### Modelo de canal

- **Reflexión y refracción:** Señal combinada de la original con reflexiones y refracciones.
- **Ruido e interferencia:** Afectada por ruido térmico e interferencia de otras fuentes.
- **Atenuación:** Señal se atenúa con la distancia.
- **Difracción:** Genera nueva señal por bordes.
- **Difusión:** Señal se difumina por múltiples reflexiones en superficies rugosas.
- **Efecto Doppler:** Corrimientos en frecuencia para dispositivos en movimiento.

### Atenuación de espacio libre

- **Modelo de Friis:** Describe el efecto de la atenuación de espacio libre para campo lejano (d>d0d > d_0d>d0​).
- **Fórmula de atenuación:** Pr=Ptx⋅Gt⋅Gr⋅λ(4π)2⋅d2⋅LP_r = \frac{P_{tx} \cdot G_t \cdot G_r \cdot \lambda}{(4\pi)^2 \cdot d^2 \cdot L}Pr​=(4π)2⋅d2⋅LPtx​⋅Gt​⋅Gr​⋅λ​
- **Modificación para distancia d0d_0d0​:** Pr(d0)=Ptx⋅Gt⋅Gr⋅λ(4π)2⋅d02⋅L⋅(d0d)2P_r(d_0) = \frac{P_{tx} \cdot G_t \cdot G_r \cdot \lambda}{(4\pi)^2 \cdot d_0^2 \cdot L} \cdot \left(\frac{d_0}{d}\right)^2Pr​(d0​)=(4π)2⋅d02​⋅LPtx​⋅Gt​⋅Gr​⋅λ​⋅(dd0​​)2
- **Antenas direccionales:** Uso de antenas direccionales.

### Atenuación y canal selectivo en frecuencia

- La atenuación depende de la frecuencia utilizada, resultando en un canal selectivo en frecuencia.

### Efectos de reflexión y dispersión

- Modelado con múltiples rayos, dependientes de la frecuencia.
- **Delay Spread:** Canal selectivo en términos de frecuencia.
- **Fast Fading:** Cuando hay movimiento, el fenómeno se convierte en "fast fading".

### Modelo de elementos finitos

- Combina efectos de reflexión, dispersión y difracción.
- Ejemplos: análisis de estructura edilicia, propagación en Múnich, entorno rural.

### Fórmula de atenuación generalizada

- Factor γ\gammaγ, denominado exponente de pathloss: Precv(d)=Precv(d0)⋅(d0d)γP_{recv}(d) = P_{recv}(d_0) \cdot \left(\frac{d_0}{d}\right)^\gammaPrecv​(d)=Precv​(d0​)⋅(dd0​​)γ
- En términos logarítmicos: PL(d)[dB]=PL(d0)[dB]+10γlog⁡10(dd0)PL(d) [dB] = PL(d_0) [dB] + 10 \gamma \log_{10} \left(\frac{d}{d_0}\right)PL(d)[dB]=PL(d0​)[dB]+10γlog10​(d0​d​)
- **Fading lognormal:** Agregar una variable aleatoria para incluir los obstáculos.

### Capacidad de decodificación y SINR

- Depende de la relación señal a ruido e interferencia (SINR): SINR=10log⁡10(PrecvN0+∑i=1kIi)SINR = 10 \log_{10} \left(\frac{P_{recv}}{N_0 + \sum_{i=1}^{k} I_i}\right)SINR=10log10​(N0​+∑i=1k​Ii​Precv​​)
- Estimación del BER (bit error rate) para DPSK: BER(SINR)=0.5e−EbN0BER(SINR) = 0.5 e^{-\frac{E_b}{N_0}}BER(SINR)=0.5e−N0​Eb​​ EbN0=SINR⋅1R\frac{E_b}{N_0} = SINR \cdot \frac{1}{R}N0​Eb​​=SINR⋅R1​

### Relación entre SINR y BER

- Gráfico mostrando la relación entre SINR y BER para modulación coherente detectada BPSK y BFSK.

### Aplicación en IoT

- Rango de transmisión pequeño, delay spread en nanosegundos.
- Ancho de banda de coherencia mayor a 50MHz, no selectivo en frecuencia.
- Tabla con valores promedio de γ\gammaγ, σ2\sigma^2σ2 y rango de pérdida a 1m para diferentes ubicaciones.

### Actividad

- Investigación sobre tecnologías LPWAN (Low Power, Wide Area):
    - **LoRa (Long-Range)**
    - **SigFox**
    - **802.15.4g (Wi-Sun)**
    - **Weightless**
    - **NB-IoT**
- Investigar características de potencia, sensibilidad, capacidad, canalización, bandas, coberturas estimadas.
- Presentar la tecnología en un slide en formato PDF.

## Redes: Capa MAC

### Historia y desafíos de las capas MAC

- Propuestas de manera (semi) independiente a la existencia de un canal de comunicación no ideal.
- Definición de límites máximos y cotas mediante simulaciones y estudios analíticos.
- No siempre optimizados para consumo, capacidad limitada de procesamiento, escalabilidad o tiempo de convergencia.

### Desafíos en la transmisión y recepción

- No está permitido transmitir y recibir al mismo tiempo.
- La interferencia en el receptor es el factor determinante para la recepción.
- Un BER alto complica la señalización de ACKs y otros paquetes de gestión de red.
- Eficiencia en energía, poco overhead, alto throughput, bajo delay y baja cantidad de errores.

### Problemas de colisiones y costos de energía

- Las colisiones son complejas de manejar.
- Costo de escuchar paquetes no dirigidos al nodo receptor.
- Escuchar mientras nadie transmite consume energía.
- Overhead del protocolo en encabezados y otros paquetes.

### Clasificación de MAC inalámbricas

- **Centralizada:**
    - Basada en un Schedule (Asignación Fija, Asignación bajo demanda)
    - Basada en Contención
- **Distribuida:**
    - Basada en un Schedule (Asignación Fija, Asignación bajo demanda)
    - Basada en Contención

#### Protocolos basados en Schedule

- TSMP, IEEE 802.15.4, Arisha, PEDAMACS, BitMAC, G-MAC, SMACS, TRAMA, FLAMA, µMAC, EMACs, PMAC, PACT, BMA, MMAC, FlexiMAC, PMAC, O-MAC, PicoRadio, Wavenis, f-MAC, Multichannel LMAC, MMSN, Y-MAC, Practical Multichannel MAC, LMAC, AI-LMAC, SS-TDMA, RMAC

#### Protocolos basados en Periodo activo común

- SMAC, TMAC, E2MAC, SWMAC, Adaptive Listening, nanoMAC, DSMAC, FPA, DMAC, Q-MAC, MSMAC, GSA, RL-MAC, U-MAC, RMAC, E2RMAC

#### Protocolos basados en Preamble sampling

- Preamble-Sampling ALOHA, Preamble-Sampling CSMA, Cycled Receiver, LPL, Channel Polling, BMAC, EA-ALPL, CSMA-MPS, TICER, WOR, X-MAC, MH-MAC, DPS-MAC, CMAC, GeRAF, 1-hopMAC, RICER, WiseMAC, RATE EST, SP, SyncWUF, STEM, MFP, 1-hopMAC, SpeckMAC-D, MX-MAC

#### Protocolos Híbridos

- IEEE 802.15.4, ZMAC, Funneling MAC, MH-MAC, SCP, Crankshaft

### Detalles de MAC

#### MAC basada en schedule

- Define cuándo transmite cada estación (TDMA) o banda específica dentro de un espacio (CDMA).
- Puede ser fijo o calculado bajo demanda.
- Requiere sincronización.

#### MAC basada en contención

- Riesgo de colisionar incluido.
- Ahorro de overhead de coordinación.
- Mecanismos para reducir colisiones (RTS/CTS).
- Uso de aleatorización.

#### Ideas básicas: CSMA (y ALOHA...?)

- Gráfico mostrando la idea de terminal oculta con estaciones A, B, C, D.

#### RTS/CTS: MACA

- Gráfico mostrando el proceso RTS/CTS entre estaciones A, B, C, D.

#### RTS/CTS: Problemas de terminal expuesta/oculta

- Gráfico mostrando el problema de terminal expuesta/oculta.

#### Solución al tiempo de espera en escucha

- Mandar información en el beacon sobre paquetes pendientes (ej. ATIM).
- Nodos se duermen si no hay nada para ellos.
- Requiere infraestructura.
- Para RTS/CTS, mantener escucha permanente.

#### S-MAC

- Apagar y encender en periodos precisos simultáneamente.
- Intercambio de schedules.
- Fases de SYNCH, RTS, CTS.
- Gráfico mostrando la sincronización en S-MAC.

#### T-MAC

- Parte del S-MAC: Dormirse rápidamente si nadie transmite.
- Gráfico mostrando el proceso de T-MAC.

#### Muestreo de preámbulo

- Despertarse periódicamente para muestrear el preámbulo.
- Preambulos largos para asegurar detección.
- Ejemplo WISEMAC.
- Gráfico mostrando el proceso de preámbulo.

#### B-MAC

- Adapta el piso de ruido para detectar canal libre (Clear Channel Assessment).
- Muestras separadas exponencialmente.
- Usar random backoff si el canal está ocupado.
- ACK inmediato al recibir paquetes (opcional).

#### B-MAC II

- Escucha con bajo consumo (Preamble sampling).
- CCA, Timeout.
- No usa sincronización ni RTS/CTS, es simple.

#### LEACH

- Red densa con Sink: Agrupación en clusters controlados por un líder.
- Etapa de Setup.
- Rotación del rol de líder.
- Líderes se anuncian, nodos eligen líder con señal más fuerte.
- Gráfico mostrando el proceso LEACH.

#### SMACS

- Múltiples canales, superframes de largo conocido.
- Enlaces direccionales entre nodos vecinos.
- El canal es elegido al azar, el slot de manera codiciosa.
- Receptores despiertan cuando corresponde.
- Construcción de un Schedule local.
- Gráfico mostrando el setup de un enlace en SMACS.

#### TRAMA

- Nodos sincronizados.
- Tiempo dividido en ciclos, con periodos de acceso aleatorio y con Schedule.
- Intercambio de listas de vecinos para conocer dispositivos a dos saltos.
- Actualización incremental.
- Intercambio de schedules.
- Sistema de prioridades para decidir qué slot utilizar.

## Especificaciones

### 802.15.4

- **Origen:** Estandarización de WSN.
- **Contexto:** Investigación -> Industria.
- **Organismo:** IEEE802 Standards.
- **Disponibilidad:** Gratuita (Publicación > 6 meses).
- **Objetivo:** MAC y PHY.
- **Última versión completa:** 2011.
- **Revisiones 2012:** e (tsch), f (RFID), g (Smart Meters).

### Introducción

#### 802.15: Wireless Personal Area Networks

- 802.15.4: Low Rate WPANs.
- Equipos fijos / móviles.
- Baja potencia de transmisión.
- Bajo consumo – Gran autonomía.
- Distancias cortas.
- Poca o nula infraestructura (no APs).

#### Clasificación de dispositivos

- **FFD:** Full Function Device (Coordinador PAN).
- **RFD:** Reduced Function Device (Sensado/actuación, se asocia a un solo FFD a la vez).
- **WPAN:** Al menos un FFD y varios RFDs.

#### Topologías

- **Estrella:** RFDs se comunican con FFD. El FFD inicia, termina o enruta comunicaciones. Dirección absoluta o corta asignada por el Coordinador. El coordinador elige el PAN ID de la red.
- **P2P:** Todos pueden comunicarse. Un coordinador elegido. Cluster tree: mayoría son FFDs, RFDs como leafs. El coordinador elige PAN ID y envía beacons. Asociaciones de vecinos como child devices.
- **Multicluster:** Coordinador asigna a un child como coordinador del grupo vecino.

## La capa MAC

### Funciones

- Manejo de Beacons (balizas).
- Acceso al canal.
- Administración de Time Slot garantizado.
- Validación de frames.
- ACKnowledges.
- Asociación y Des-asociación.
- Servicios para seguridad.

### Estructura de SuperFrame (coordinador)

- Gráfico mostrando estructura de SuperFrame.

### Beacons (balizas)

- Sincronización de dispositivos asociados.
- Identificador de PAN.
- Descripción de estructura de superframes.

### Contención

- Nodo compite con los demás usando Slotted-CSMA o ALOHA.
- Coordinador puede asignar GTS a aplicaciones sensibles al retardo (máx 7).
- Gráfico mostrando contención.

### Transmisión al coordinador

1. El nodo espera sincronización con el Beacon.
2. El nodo transmite en un período de contención.
3. El coordinador responde con ACK si fue solicitado.
4. Si no hay Beacon, transmite en cualquier momento.

### Transmisión del coordinador

1. El coordinador avisa en el Beacon que hay un mensaje pendiente.
2. El nodo solicita el mensaje al coordinador.
3. El coordinador responde con ACK.
4. El coordinador envía el dato al nodo.
5. El nodo manda ACK si es solicitado.

### Tipos de paquete

- **Beacon:** Sincronización y gestión de la red.
- **Data:** Contiene los datos útiles.
- **ACKnowledgement:** Confirma la recepción de otros paquetes.
- **MAC command:** Control de transferencias entre pares.

### Estructura del paquete

- **SHR (Sync):** Sincronización.
- **PHR (PHY):** Información de la capa física.
- **PSDU (Carga PHY):** Carga útil de la capa física.
- **MHR (MAC Header):** Cabecera de la capa MAC.
- **Carga MAC:** Datos específicos de la capa MAC.
- **MFR (MAC Footer):** Verificación y control.

### CSMA-CA (sin Beacons)

1. Espera un tiempo al azar.
2. Si el canal está desocupado, espera el random backoff.
3. Si aún sigue desocupado, transmite.
4. Si está ocupado, espera otro tiempo al azar y repite el ciclo.
5. El ACK no usa CSMA-CA.

### CSMA-CA (con Beacons)

- Usa slotted CSMA-CA.
- Períodos de backoff alineados con el inicio del Beacon.
- Períodos de backoff alineados entre los nodos de una PAN.

### Tiempos

- Tiempos mínimos entre frames.
- **Con ACKnowledge:** Frame largo → ACK → LIFS → Frame corto → ACK → SIFS.
- **Sin ACKnowledge:** Frame largo → LIFS → Frame corto → SIFS.

### Actividades

- **Descubrimiento:** Channel Scan.
- **Selección de canal:** ED (Energía en el canal).
- **Scan Activo:** Pide el Beacon al coordinador.
- **Scan Pasivo:** Escucha Beacons.
- **Usa un PANID de 0xFFFF para escuchar a todos los Beacons de los vecinos.**
- **Scan Huérfano:** Cuando el nodo se desincroniza del coordinador.
- **Adquisición de Sincronismo:** Beacon.

### Frame genérico

- **Frame Control:** Control del frame (2 bytes).
- **Seq Number:** Número de secuencia (1 byte).
- **Dest PANID:** Identificador de la red de destino (0/2 bytes).
- **Dest Address:** Dirección del nodo de destino (0/2/8 bytes).
- **Src PANID:** Identificador de la red de origen (0/2 bytes).
- **Src Address:** Dirección del nodo de origen (0/2/8 bytes).
- **Seguridad Auxiliar:** Información de seguridad (0/5/6/10/14 bytes).
- **Carga:** Datos útiles (variable).
- **FCS:** Campo de verificación del frame (2 bytes).

### Campo Frame Control

- **Bits 0-2:** Tipo de Frame (Beacon, Data, ACK, etc.).
- **Bit 3:** Seguridad Habilitada.
- **Bit 4:** Frame Pendiente.
- **Bit 5:** ACK Requerido.
- **Bit 6:** Compresión de PANID.
- **Bits 7-9:** Reservado.
- **Bits 12-13:** Versión del Frame.
- **Bits 14-15:** Source Addressing Mode.

### Beacon

- **Frame Control (2 bytes):** Tipo de frame y propiedades.
- **Sequence Number (1 byte):** Número de secuencia.
- **Addressing Fields (4/10 bytes):** Campos de direccionamiento.
- **Aux Security (0/5/6/10/14 bytes):** Información de seguridad.
- **Superframe Spec (2 bytes):** Especificación del superframe.
- **GTS (variable):** Información sobre el Guaranteed Time Slot.
- **Pending Address (variable):** Direcciones pendientes.
- **Carga (variable):** Datos del frame.
- **FCS (2 bytes):** Frame Check Sequence para detección de errores.

### Data y ACK

- **Data Frame:**
    - **Frame Control (2 bytes):** Tipo y propiedades.
    - **Sequence Number (1 byte):** Número de secuencia.
    - **Addressing Fields (variable):** Campos de direccionamiento.
    - **Aux Security (0/5/6/10/14 bytes):** Información de seguridad.
    - **Carga (variable):** Datos del frame.
    - **FCS (2 bytes):** Secuencia de verificación.
- **ACK Frame:**
    - **Frame Control (2 bytes):** Tipo y propiedades.
    - **Sequence Number (1 byte):** Número de secuencia.
    - **FCS (2 bytes):** Secuencia de verificación.

## La capa PHY

### Responsabilidades

- Activación/Desactivación del transceiver RF.
- Detección de Energía en el canal (ED).
- Indicador de calidad de Enlace (LQI).
- Verificación de Canal Libre para CSMA-CA.
- Selección de frecuencia de canal.
- Transmisión y recepción de datos.
- Medición de distancia con UWB.

### Modulaciones

- **Señal de Banda Angosta:** Banda de frecuencia estrecha, pico en densidad espectral.
- **Señal Expandida:** Banda de frecuencia mayor, reducción de densidad espectral.

### Bandas de Frecuencias

- **780MHz (779-787):** 250kbps
- **868MHz (868-868.6):** 20kbps / 100kbps (O-QPSK) / 250kbps (ASK)
- **915MHz (902-928):** 40kbps / 250kbps (ASK)
- **950MHz (950-956):** 100kbps / 20kbps (DSSS)
- **2450MHz (2400-2483.5):** 250kbps (16 canales)
- **3-10GHz (UWB):** Comunicaciones de alta velocidad y precisión en medición de distancias.

### Tipos de Modulación

- **O-QPSK (Offset Quadrature Phase Shift Keying con DSSS):** Modulación por desplazamiento en cuadratura con espectro ensanchado.
- **BPSK (Binary Phase Shift Keying con DSSS):** Modulación por desplazamiento de fase binaria con espectro ensanchado.
- **ASK (Amplitude Shift Keying con PSSS):** Modulación por desplazamiento de amplitud con espectro ensanchado paralelo.

### Funciones

#### Medición de ED

- **Energía estimada dentro del ancho de banda del canal.**
    - Se mide durante 8 tiempos de símbolo

#### Cálculo de LQI

- **Caracterización de la potencia de recepción/calidad de un paquete.**
    - Escala de 0x00 a 0xFF, con al menos 8 niveles

#### Clear Channel Assessment

- **Modo 1:** Energía por encima de un umbral
- **Modo 2:** Sólo detección de portadora
- **Modo 3:** Energía por encima de un umbral y detección de portadora

## Modulación – Ejemplo: O-QPSK

### Paquete

- **Bytes:**
    - **Preambulo**
    - **Delimitador de Frame (SFD)**
    - **Inicio de Frame (SFD)**
    - **Longitud de Frame (7 bits)**
    - **Reservado (1 bit)**
    - **PSDU (Carga)**

### Detalles del Preambulo y Modulación

- **Preambulo:** 8 símbolos (4 bytes) en cero
- **Start of Frame Delimiter:** 1110 0101
- **Expansión y Modulación:**
    - 1.4 bits seleccionan una secuencia de pseudoruido
    - Se concatenan las secuencias
    - Se modula con O-QPSK
- **Velocidad de bit:** 250Kbps

### Símbolos a Chips

|Data symbol|Chip values (c0 c1 ... c30 c31)|
|---|---|
|0|11101101100110001001011000111011|
|1|11101101100110001001100101101111|
|2|00110110011000101100110110101100|
|3|00110110011000101101000110001100|
|4|00110001001011000100101101110100|
|5|00110001001011000101001101110101|
|6|11100110001000101100011101101100|
|7|11100110001000101101001101101100|
|8|11100101100110001001011000110010|
|9|11100101100110001001100101100011|
|10|00110101100110001001100101110101|
|11|00110101100110001001101101110101|
|12|00110101100110001001101001101100|
|13|00110101100110001001100101100011|
|14|00110001001011000101001101101100|
|15|00110001001011000101100101101100|

### Modulación O-QPSK

- **O-QPSK:**
    - La modulación O-QPSK (Offset Quadrature Phase Shift Keying) es una técnica de modulación en la que la señal en fase (I) y la señal en cuadratura (Q) se desplazan en el tiempo por la mitad de un intervalo de bit (Tc). Esto reduce la interferencia entre los dos componentes de la señal.

## Dispositivos

### Dispositivos Compatibles

- **TI – CHIPCON CC2420**
    - Ganancia: 9dB, 250Kbps, SPI
    - RSSI / LQI Digital
    - 17 mA consumo promedio TX/RX
- **ATMEL AT86RF230**
    - 16 mA consumo promedio TX/RX
    - 250Kbps, SPI
    - 20nA SLEEP

## Stacks Industrial IOT

### 802.15.4e / WirelessHART / ISA100.11a

||WirelessHART|ISA100.11a|IEEE/IETF|
|---|---|---|---|
|**Application**|Comando y respuesta|Objetos y métodos|CoAP|
|**Transport**|Servicio sin conexión|UDP|TCP / UDP|
|**Network**|Routing|IPv6|RPL IPv6 6tisch|
|**MAC**|TSCH|TSCH / Mesh Under|IEEE 802.15.4e|
|**PHY**|TSCH|TSCH|IEEE 802.15.4e|

### Explicación de las figuras

1. **Modulaciones:**

- Describe diferentes técnicas de modulación utilizadas en la capa PHY.
- **CSS:** Utiliza DQPSK junto con Chirp Spread Spectrum.
- **UWB:** Emplea modulación BPSK con Burst Position Modulation.
- **M-PSK:** M-ary Phase Shift Keying.
- **GFSK:** Gaussian Frequency Shift Keying.

2. **Funciones:**

- Medición de ED: Proceso de medir la energía dentro del ancho de banda del canal.
- Cálculo de LQI: Evaluación de la calidad del enlace.
- Clear Channel Assessment: Diferentes modos para evaluar la ocupación del canal.

3. **Modulación – Ejemplo: O-QPSK:**

- Detalla la estructura de un paquete utilizando O-QPSK.
- Explicación del preámbulo, delimitador de frame, expansión y modulación.
- Conversión de símbolos a chips y representación visual de O-QPSK.

4. **Dispositivos:**

- Información sobre los dispositivos compatibles TI – CHIPCON CC2420 y ATMEL AT86RF230, incluyendo sus características y consumo de energía.

5. **Stacks Industrial IOT:**

- Comparación entre WirelessHART, ISA100.11a y IEEE/IETF en diferentes capas del modelo de red, destacando sus aplicaciones, transporte, red, MAC y PHY.

## Industrial IoT (IIoT) Stacks and Protocols

### Stacks Industrial IOT

#### Protocolo por capas IETF

Este diagrama muestra la pila de protocolos en capas de IETF utilizada en IoT industrial. Cada capa representa diferentes protocolos que interactúan entre sí para proporcionar comunicación y funcionalidad en redes IoT:

- **Aplicación**: PCEP, PCC, CoAP, DTLS, PANA, 6LoWPAN ND, RPL.
- **Transporte**: TCP, UDP, ICMP, RSVP.
- **Red**: IPv6.
- **Adaptación**: 6LoWPAN Header Compression, OTF.
- **Enlace de Datos**: 6top, IEEE 802.15.4e.
- **Física**: IEEE 802.15.4 PHY.

#### TSCH: Time-Slotted Channel Hopping

El protocolo TSCH (Time-Slotted Channel Hopping) organiza la comunicación en intervalos de tiempo sincronizados y frecuencias cambiantes para mejorar la robustez frente a interferencias y optimizar el consumo de energía. En el gráfico, se observa cómo diferentes nodos se comunican entre sí en distintos slots de tiempo y offsets de frecuencia.

#### Qué pasa durante una celda?

Este gráfico detalla la actividad durante una celda en TSCH. Muestra las interacciones entre el transmisor y el receptor, incluyendo el envío y recepción de paquetes y ACKs (acknowledgements). Los tiempos importantes son TsTxOffset, TsRxOffset, y TsRxAckDelay, que indican los momentos en los que se preparan y se transmiten/reciben datos.

#### Consumo TX/RX

El consumo de energía es crítico en IIoT. Aquí se muestra una comparación de diferentes dispositivos en términos de sensibilidad, corriente de transmisión y recepción. Con una batería de 2xAA (3000mAh), la duración puede variar significativamente dependiendo del ciclo de trabajo y el dispositivo utilizado, como el AT86RF231 y el LTC5800.

### Estrategias: Industrial IOT

#### Enrutamiento: Routing for Low-Power and Lossy Networks (RFC6550)

El protocolo de enrutamiento RPL (Routing Protocol for Low-Power and Lossy Networks) se utiliza para formar topologías en árboles dirigidos acíclicos (DAG). En el diagrama, se ilustra un DAG con nodos padres e hijos, donde el nodo raíz (DAGRoot) organiza la red.

#### Estructura TSCH

TSCH mejora la robustez frente a interferencias y optimiza el consumo de energía. La estructura de tiempos y canales permite comunicaciones predecibles y de baja latencia. En el gráfico, se observa cómo los nodos utilizan diferentes canales y slots de tiempo para comunicarse eficientemente.

### IIOT: Software/Firmware OpenWSN

#### Software/Firmware OpenWSN (parte 1)

OpenWSN es una implementación de software abierta para redes de sensores inalámbricos. El diagrama muestra las diferentes capas y módulos de OpenWSN, desde la aplicación hasta el enrutamiento y el acceso a la capa física.

#### Software/Firmware OpenWSN (parte 2)

Continuación del diagrama anterior, detallando más componentes y su interacción en OpenWSN. Muestra cómo se gestionan las colas, el cronograma y la sincronización dentro de la pila de protocolos.

### IIOT: Hardware

Se presentan dispositivos de hardware utilizados en IIoT, como OpenMote, CC2538, y soluciones de Dust Networks. Estos dispositivos soportan FreeRTOS y OpenWSN, y son adecuados para aplicaciones industriales con requisitos específicos de comunicación y energía.

### IIOT: Plataformas experimentales

FIT-IoT-Lab es una plataforma experimental que ofrece recursos para pruebas y desarrollo en IoT industrial. Permite a los usuarios realizar experimentos con diferentes nodos y configuraciones para evaluar el rendimiento y la eficiencia de sus aplicaciones y protocolos.

### IIOT: Under construction

- **Estandarización:**
    - IPv6 everywhere:
    - IETF:6tisch: On-the-Fly Scheduling Distributed/Hybrid Scheduling Security CoAP: COMI (Management Interface)
    - IETF:detnet: Gap Analysis

## Enrutamiento Unicast

- **Dada una red o un grafo,**
    - Cada nodo tiene un identificador único (ID).
- **El objetivo es derivar un mecanismo que permita a un paquete de un nodo cualquiera llegar a un nodo de destino específico.**
    - Este es el problema de enrutamiento y reenvío.
    - Para enrutar: Construir estructuras de datos que contengan información de cómo un destino puede ser alcanzado.
    - Reenvío: Consultar estas estructuras de datos para reenviar un paquete dado el siguiente salto.

### Desafíos

- Los nodos pueden moverse, las relaciones entre nodos cambian.
- Las métricas de optimización pueden ser más complicadas que el mínimo hop count, por ejemplo, eficiencia energética.

## Enrutamiento Ad-hoc

- **Debido a las restricciones de las redes de sensores, los métodos estándar de enrutamiento no son realmente aplicables.**
    
    - Demasiado overhead, demasiado lentas para reaccionar a cambios.
    - Ejemplo: Los algoritmos de Dijkstra y Bellman-Ford (DV).
- **La solución más simple: Inundación.**
    
    - No requiere información (tablas de ruteo). Es simple.
    - Los paquetes generalmente llegan a destino.
    - El overhead es prohibitivo, y usualmente no aceptable.
- Hacen falta protocolos de ruteo ad-hoc específicos.
    

## Clasificación de protocolos Ad-Hoc

- **La pregunta principal: ¿Cuándo opera un protocolo de enrutamiento?**
    
- **Opción 1: El protocolo de ruteo siempre intenta mantener sus datos de ruteo actualizados.**
    
    - Entonces el protocolo es proactivo. (Activo antes de que las tablas sean realmente requeridas) También se denomina “manejado por tablas”.
- **Opción 2: La ruta solamente es determinada cuando ésta es requerida.**
    
    - Se dice que el protocolo actúa bajo demanda.
- **Opción 3: Combinar las opciones anteriores.**
    
    - Protocolos Híbridos.
- **La red se puede considerar plana o jerárquica.**
    
    - Se debe comparar el control de topología y el enrutamiento tradicional.
- **¿Qué datos se utilizan para identificar nodos?**
    
    - Un identificador arbitrario.
    - La posición de un nodo:
        - Puede ser utilizado para asistir en protocolos de enrutamiento geográfico, dado que la elección del siguiente salto puede ser calculada basada en la dirección de destino.
    - Identificadores que no son arbitrarios pero que llevan cierta estructura:
        - Como en el enrutamiento tradicional.
        - Estructurarlo de acuerdo a una posición o a un nivel lógico.

## Protocolos Proactivos - DSDV

- **Idea: Partir de un protocolo de enrutamiento estándar y luego adaptarlo.**
    - DV (Distance-Vector) Adaptado: _Destination Sequence Distance Vector (DSDV)_.
        - Basado en un procedimiento de Bellman Ford distribuido.
        - Agregar información de edad de la ruta para rutar información propagada por intercambios de Vector-Distancia. Ayuda a evitar ciclos.
        - Enviar periódicamente actualizaciones completas de rutas.
        - Frente a un cambio de topología, enviar cambios incrementales de rutas.
        - Actualizaciones de rutas inestables son retardadas.
        - ... + otros cambios menores.

## Protocolos Proactivos - OLSR

- **Combina un protocolo de estado de enlace y control de topología.**
    - _Optimized Link State Routing (OLSR)_.
        - Componente de control de topología: Cada nodo elige el conjunto mínimo dominante para su vecindario de dos saltos.
            - Se llaman relays multipunto (retransmisores multipunto).
            - Sólo estos nodos son utilizados para reenvío.
            - Permite la inundación eficiente (o restringida).
        - Componente de estado de enlace: Esencialmente un algoritmo de estado de enlace para esta topología reducida.
            - La idea clave es reducir el overhead de inundación, en este caso cambiando la topología.

## Protocolos Proactivos - Ojo de Pescado (Fisheye)

- **Fisheye State Routing (FSR) hace una observación básica: Cuando un destino es lejano, los detalles sobre el camino no son relevantes, solo en el vecindario los detalles hacen falta.**
    
    - Ver a los gráficos como si se utilizaran lentes de ojo de pescado.
    - Las regiones tienen distintos niveles de exactitud de información de ruteo.
- **En la práctica:**
    
    - Cada nodo mantiene una tabla de topología de una red.
    - Solamente distribuye las actualizaciones de estado de enlace localmente.
    - Usa actualizaciones de enrutamiento más frecuentes para nodos con menor alcance.

## Protocolos Reactivos: DSR

- **En un protocolo reactivo, ¿cómo reenviar un paquete a un destino específico?**
    
    - Inicialmente, no hay información sobre si el próximo salto está disponible.
    - Solamente un único recurso: Enviar el paquete a todos los vecinos – inundar la red.
    - Esperanza: En algún punto, el paquete va a llegar a destino, y la respuesta es enviada al origen. Se usa esta respuesta para aprender hacia atrás (backward learning) la ruta del destino a la fuente.
- **En la práctica se llama: Dynamic Source Routing (DSR).**
    
    - Usa paquetes distintos para requerimiento de ruta y respuesta de ruta (_route request/route reply_) para descubrir la ruta.
        - Los paquetes de datos son enviados una vez que la ruta ha sido establecida.
        - Los paquetes de descubrimiento son más pequeños que los paquetes de datos.
    - Se almacena la información de ruta en los paquetes de descubrimiento.

### Procedimiento de descubrimiento de ruta

#### Figura: Procedimiento de descubrimiento de ruta

- **Buscar una ruta de 1 a 5:**
    1. Nodo 1 envía una solicitud de ruta [1].
    2. Nodo 2 recibe la solicitud de ruta y reenvía [1,2].
    3. Este proceso continúa hasta que el nodo 5 recibe la solicitud [1,2,...,5].
    4. Nodo 5 usa la información de ruteo guardada en RREQ para enviar de retorno, a través del source routing, una respuesta [5,3,7,1].

## Modificaciones y extensiones al DSR

- **Los nodos intermedios pueden enviar respuesta de rutas (route replies) si ya conocen la ruta.**
    
    - Problema: Las rutas pueden estar desactualizadas.
- **Funcionamiento promiscuo de los dispositivos de radio: Los nodos pueden aprender sobre una topología escuchando los mensajes de control.**
    
- **Retardos al azar para generar respuesta de rutas:**
    
    - Muchos nodos pueden tener una respuesta: tormentas de respuestas.
    - NO necesariamente para acceso al medio: Es un tema de la MAC.
- **Reparación local:**
    
    - Cuando un error es detectado, usualmente el transmisor genera un timeout y construye una nueva ruta.
    - En su lugar: Intentar cambiar localmente la ruta designada por la fuente (source).
- **Mecanismos de gestión de Cache:**
    
    - Para remover los caches desactualizados rápidamente.
    - Tiempo de vida fijo o adaptivo, mensajes para retirar una ruta del caché.

## Protocolos Reactivos

### AODV (Ad hoc On Demand Distance Vector)

- **Protocolo muy popular**
- Esencialmente la misma idea del DSR para el procedimiento de descubrimiento
- Los nodos mantienen tablas de enrutamiento en lugar de enrutamiento a fuente (source)
- Se agregan números de secuencia para manejar los caches desactualizados
- Los nodos recuerdan de dónde vino un paquete y llenan sus tablas de enrutamiento con esa información.

### TORA (Temporally Ordered Routing Algorithm)

- **Observación**: En un terreno montañoso, ir hacia la desembocadura del río es simple: solo hace falta ir montaña abajo.
- **Idea**: Convertir la red en un terreno montañoso
    - Usar un “paisaje” para cada destino
    - Asignar “Alturas” a los nodos cuando van montaña abajo y así se alcanza el destino. En efecto: es como orientar las aristas entre los vecinos
    - Hace falta que el grafo orientado no tenga ciclos.
- **Reacción a cambios de topología**
    - Cuando el enlace es removido (considerando que fuera la única salida del nodo) Se revierte la dirección de todos los demás enlaces para incrementar la altura
    - Reaplicar continuamente hasta que cada nodo, a excepción del destino que tiene un único conector. Esto va a tener éxito en un gráfico conectado.

## Propuesta alternativa: Ruteo por chisme o rumor

- **Dar vuelta el problema**: Pensar en un agente paseándose en la red buscando datos (eventos, ...)
    - El agente inicialmente hace una caminata al azar (random walk)
    - Deja “trazas” en la red
    - Luego los agentes pueden utilizar estas trazas para encontrar datos
- **Esencialmente trabaja debido a la alta probabilidad de intersección de líneas.**

## Unicast eficiente en energía

- **Métrica**: Eficiencia energética
- **Objetivos**
    - Minimizar la energía por bit
        - Ejemplo: A-B-E-H
    - Maximizar el tiempo de vida de la red
        - Tiempo hasta que el primer nodo falla, se pierda cobertura o suceda una partición
- **Se ve trivial** – usar métricas de enlace/camino (no cantidad de saltos y ruteo standard)

## Opciones básicas de métricas de camino

- **Capacidad total disponible máxima**
    - Métrica (Path): Suma de los niveles de batería
    - Ejemplo: A-C-F-H
- **Ruteo por mínimo costo de batería**
    - Métrica (Path): Suma de los niveles recíprocos de batería
    - Ejemplo: A-D-H
- **Ruteo condicional con capacidad max-min**
    - Solamente tomar el nivel de batería en cuenta cuando está por debajo de un nivel dado
- **Minimiza la varianza en los valores de potencia**
- **Mínima potencia total de transmisión**

## Una métrica no trivial

- Las métricas previas no corren particularmente bien wij=eij(λαi−1)w_{ij} = e_{ij} (\lambda^{\alpha_i} - 1)wij​=eij​(λαi​−1)
- **Un peso de enlace no trivial**:
    - wijw_{ij}wij​ es el peso del enlace entre el nodo iii y el nodo jjj
    - eije_{ij}eij​ energía requerida, λ\lambdaλ una constante, αi\alpha_iαi​ fracción de la batería del nodo iii ya gastada
- **Métrica de camino**: Suma de los pesos de los enlaces
    - Usar el camino con la métrica más pequeña
- **Propiedades**: Muchos mensajes pueden ser enviados, tiempo red alto.
    - Con control de admisión, incluso una relación logarítmica competitiva respecto del tamaño de la red puede ser utilizada.

## Enrutamiento Multipath

- En lugar de un camino simple, puede ser útil calcular múltiples caminos entre un par origen-destino.
- Múltiples caminos pueden ser disjuntos o cruzados.
- Pueden ser usados simultáneamente, alternativamente, al azar…

## Broadcast & multicast (eficiente en energía)

- **Distribuir un paquete a todos los nodos alcanzables (broadcast) o a un subgrupo (multicast)**
- **Opciones básicas**:
    - Árbol basado en la fuente (source-based tree): Construir un árbol (uno para cada fuente) para llegar a todas las direcciones
        - Minimiza el costo total (= suma de los pesos de los enlaces) del árbol
        - Minimiza el máximo costo a cada destino
        - Árboles compartidos, basados en el mismo tronco
        - Usa un mismo árbol para todas las fuentes
        - Cada fuente envía paquetes al árbol y luego son distribuidos
    - Malla
        - Los árboles tienen profundidad de 1: Usar mallas provee alta redundancia y robustez en ambientes móviles

## Objetivos de optimización para árboles orientados a fuente

- **Para cada fuente, minimizar el costo total**
    - Este es el problema del árbol de Steiner
- **Para cada fuente, minimizar el máximo costo a cada destino**
    - Esto se obtiene mediante la superposición de los caminos más cortos individuales calculados por un protocolo de ruteo normal.

## Resumen de opciones (broadcast/multicast)

- **Broadcast**
- **Multicast**
    - Un árbol por fuente
        - Minimizar el costo total (Árbol de Steiner)
        - Minimizar el costo a cada nodo (ej., Dijkstra)
    - Árbol compartido
        - Tronco simple
        - Tronco múltiple
    - Malla

## Ventaja del Multicast Inalámbrico

- **Broad-/Multicast en el ámbito inalámbrico es distinto al cableado**
    - **Cableado**: distribuir localmente un paquete a _n_ vecinos: _n_ veces el costo de un paquete unicast.
    - **Inalámbrico**: Enviar a _n_ vecinos puede generar costos:
        - Tan altos como enviar a un vecino solo si no se consideran los costos de recibir.
        - Tan altos como enviar una vez, recibir _n_ veces, siempre que la recepción sea habilitada en el momento correcto.
        - Tan alto como mandar _n_ paquetes unicast, si el protocolo MAC no soporta multicast local.

Si el multicast local es más barato que repetir unicasts, entonces hay una ventaja de multicast inalámbrico.

- Es una suposición realista.

---

## Aproximaciones al Árbol de Steiner

- Calcular un árbol de Steiner es un problema NP completo.
- **Una aproximación simple**:
    - Tomar un orden arbitrario para todos los nodos de destino + el nodo de origen.
    - Sucesivamente agregar estos nodos al árbol: Para cada nodo, construir el camino más corto a otro nodo dentro del árbol.
    - Funciona razonablemente bien en la práctica.
- **Heurística de Takahashi Matsuyama**:
    - Similar, pero deja al algoritmo decidir cuál es el próximo nodo que será agregado.
    - Empezar con un nodo origen, sumar el nodo destino al árbol que tenga el camino más corto.
    - Iterar, tomando el destino que tiene el camino más corto a algún nodo que ya esté en el árbol.

Problema: La ventaja de multicast inalámbrico no se aprovecha.

- Y además no se ajusta realmente a la definición del árbol de Steiner.

---

## Enrutamiento Geográfico

- Las tablas de ruteo contienen información hacia dónde el siguiente salto debe ser reenviado.
- Está construido explícitamente.
- **Alternativa**: Inferir implícitamente esta información del lugar físico de los nodos.
    - Posición del nodo actual, de los vecinos, conociendo el destino. Enviar a un vecino en la dirección correcta como próximo salto.
- **Opciones**:
    - Mandar a cualquier nodo en un área determinada (geocasting).
    - Usar información de posición para ayudar en el ruteo (position-based routing).
        - Puede necesitar un sistema de ubicación para mapear un ID de nodo a una posición.

---

## ABC del Enrutamiento por Posición

- **"La mayoría reenvía dentro del rango r"**:
    - Enviar al nodo que realiza la mayor cantidad de reenvíos hacia el destino.
    - NO: El más alejado del transmisor.
- **El nodo más cercano con cualquier estadística de reenvío**:
    - Idea: Minimizar la potencia de transmisión.
- **Ruteo direccional**:
    - Elegir el próximo salto que está angularmente cerca de su destino.
    - Elegir el próximo salto que está cerca de la línea de conexión con su destino.
    - Problema: Puede generar ciclos.

---

## Problema: Calles sin Salida

Las estrategias simples pueden enviar un paquete a una calle sin salida.

## La Regla de la Mano Derecha para Evitar Calles sin Salida - GPSR

- **Idea básica de la calle sin salida**: Ponga la mano derecha en la pared, siga la pared.
    - No funciona si es una pared interna: va a caminar en círculos.
    - Necesita reglas adicionales para detectar estos círculos.
- **Geometric Perimeter State Routing (GPSR)**:
    - Versiones tempranas: Compass (Brújula) Routing II, face-2 routing.
    - Usa ruteo codicioso "más reenviado" tanto como sea posible.
    - Si no es posible, conmuta a enrutamiento "face":
        - Face: Región lo más amplia posible del plano que no es cortada por una arista del grafo, puede ser interior o exterior.
        - Enviar el paquete alrededor de la "Face" usando la regla de la mano derecha.
        - Usar una posición donde la "Face" fue dato y la posición de destino para determinar cuándo la "Face" puede ser abandonada. En ese momento, conmutar a ruteo codicioso.

Requiere: un gráfico plano, algo que se puede asegurar con control de topología.

---

## Geographic Routing sin Posiciones - GEM

- **Contradicción**: Geográfico pero sin posición?
- Construir coordenadas virtuales que preserven suficiente información de vecindad para ser útiles en ruteo geográfico pero que no requiere determinación real de la posición. Usa coordenadas polares desde un punto central.
    - Asigna un "rango angular virtual" a los vecinos de un nodo, con un radio mayor.
    - Los ángulos son recursivamente distribuidos a los nodos hijos.

---

## GeRaF

- **Cómo combinar el conocimiento de la posición con nodos encendiéndose y apagándose?**
    
    - Objetivo: Transmitir el mensaje sobre múltiples saltos al nodo de destino, gestionar una topología en constante cambio debido al encendido y apagado de los nodos.
    - Idea: Reenvío iniciado por el Receptor: _Receiver-initiated forwarding_.
    - El nodo de reenvío _S_ simplemente envía un paquete por broadcast sin especificar el nodo siguiente.
    - Algún nodo _T_ va a tomarlo (idealmente el más cercano a la fuente) y reenviarlo.
- **Problema**: Cómo gestionar múltiples reenviadores?
    
    - Aleatorización de la posición informada: Cuanto más cerca del destino está el nodo que reenvía, lo menos que duda de reenviar un paquete.
    - Usar varios anillos puede simplificar el problema, se deben agrupar los nodos de acuerdo a la distancia, aunque aún pueden existir colisiones.

---

## Multicast basado en la ubicación (LBM)

### Geocasting mediante inundación geográficamente restringida

### Definir una zona de "forwarding" (reenvío)

Los nodos en esta zona van a reenviar el paquete para lograr que llegue a la zona de destino.

- **La zona de reenvío** puede estar especificada en el paquete o recalculada en el camino.
- **Zona estática**: El rectángulo más pequeño contiene la fuente original y la zona de destino.
- **Zona adaptativa**: El rectángulo más pequeño contiene al nodo de reenvío y a la zona de destino.
    - Otra vez, pueden haber calles sin salida.
- **Distancias adaptativas**: El paquete es reenviado por un nodo `u` si el nodo `u` está más cerca del centro de la zona de destino que su predecesor (nodo `v`) (el paquete ha progresado).

El paquete siempre es reenviado por nodos dentro de la zona de destino.

---

## Geocasting usando ruteo ad hoc - GeoTORA

### Recordar TORA

Los nodos calculan un DAG cuyo destino es un solo Sink.

### Observación

Reenvío a través del DAG todavía funciona si múltiples nodos son el destino. (El grafo tiene múltiples Sinks)

### GeoTORA

Todos los nodos de la región de destino actúan como Sinks.

- Se reenvía a través del DAG, todos los Sinks también reenvían como broadcast el paquete en la región de destino.

### Nota

Esto funciona también para anycasting, donde los nodos de destino no necesariamente son vecinos.

- El paquete es enviado a alguno (no necesariamente el más cercano) de los miembros del grupo.

---

## Reenvío basado en trayectoria (TBF)

### Concepto

Piense en términos de un "agente": Debe viajar a través de la red recolectando medidas.

- El reenvío al azar puede tomar mucho tiempo.

### Idea

Proveer al agente con una cierta trayectoria sobre la cual viajar.

- Descripta, por ejemplo, por una curva simple.
    - Reenvío al nodo más cercano a esta trayectoria.

### Figura Explicativa

La figura muestra una red de nodos donde un agente sigue una trayectoria definida. El agente se mueve de nodo en nodo siguiendo una curva predeterminada, lo que optimiza el reenvío de paquetes al asegurarse que siempre se envían al nodo más cercano a dicha trayectoria.