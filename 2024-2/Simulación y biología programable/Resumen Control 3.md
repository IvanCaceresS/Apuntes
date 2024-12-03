### **Patrones Espaciales**
Los patrones espaciales son un conjunto de características espaciales distintivas que se repiten y/o se mantienen constantes en el tiempo. Estas características pueden incluir formas, distribución de regiones, colores o ubicaciones específicas dentro de una colonia.
#### **Ejemplos de patrones espaciales**
- Formas.
- Distribución de regiones.
- Colores.
- Ubicaciones en lugares específicos de la colonia.
#### **¿Para qué sirven los patrones espaciales?**
1. **Biología del desarrollo:**
    - Ejemplo: Las líneas de los tigres o los caparazones de los caracoles.
    - Estas formaciones complejas son dirigidas por interacciones entre organismos y señales de comunicación específicas.
2. **Control a escala:**
    - Permiten establecer distribuciones precisas, como en:
        - Liberación controlada de fármacos.
        - Organización en la construcción de biomateriales.
3. **Identificación de características específicas en el espacio:**
    - Detectar lugares con concentraciones excesivas de sustancias en el medio.
    - Determinar límites entre diferentes regiones.
---
#### **Ejemplos específicos de patrones espaciales**
##### **1. Band Detector**
- **Descripción:** Circuito que detecta zonas de alta, media y baja concentración de una señal.
- **Componentes principales:**
    - **pHD:** Detecta altas concentraciones (representadas en celeste o rojo según la intensidad).
    - **pLD:** Detecta bajas concentraciones (representadas en verde; las áreas negras no pertenecen a alta ni baja).
    - **pSND:** Envía la señal a ser detectada.
- **Características adicionales:**
    - Es multicelular y utiliza el sistema de comunicación **Lux**.
    - Incluye dos variantes de LacI:
        - **LacI normal.**
        - **LacIM1**, menos efectivo en su represión.
- **Aplicaciones:** Delimitación precisa de regiones en colonias bacterianas.
- ![[Pasted image 20241011120123.png]]			
-  ![[Pasted image 20241011121503.png]]
---
##### **2. Edge Detector**
- **Descripción:** Identifica el borde entre zonas de luz y oscuridad mediante pigmento negro expresado solo en la luz.
- **Requisitos:**
    - Único color: **Pigmento negro.**
    - No se marcan las zonas de luz u oscuridad completas, solo el borde.
    - Se utiliza un único circuito en todas las bacterias de la colonia.
    - Se valida con distintas formas de máscaras de luz.
- **Condiciones:**
    - Funciona con proteína fotosensible.
    - Utiliza el sistema **Lux** para detectar las fronteras de luz/oscuridad.
    - El pigmento solo se expresa en zonas iluminadas.
- **Aplicaciones potenciales:** En lugar de pigmento negro, podría liberar un fármaco o marcar la presencia de un patógeno.
-  ![[Pasted image 20241011122901.png]]
---
##### **3. French Flag**
- **Descripción:** Se basa en la concentración de morfógenos, que generan zonas diferenciadas según umbrales de sensibilidad.
- **Características principales:**
    - **Patrones radiales:** Uso de n umbrales que generan n+1 zonas radiales.
    - **Patrones no radiales:** Si se detectan fronteras equidistantes entre morfógenos, es posible trazar patrones lineales o geométricos.
    - **Ejemplo:** Patrón cuadrado a partir de múltiples focos de emisión de morfógenos.
- **Aplicaciones:** Creación de patrones geométricos programables, útiles para control preciso en colonias bacterianas.
- ![[Pasted image 20241015114700.png]]
- ![[Pasted image 20241015115537.png]]
---
##### **4. Variante de Band Detector**
- **Descripción:** Circuito mejorado que divide el procesamiento en:
    - **Brazo largo:** Detecta concentraciones lejanas (ubicado en un plásmido específico).
    - **Brazo corto:** Detecta concentraciones cercanas (en otro plásmido).
- **Desafíos:**
    - Un plásmido de brazo largo ubicado en el centro de emisión es inútil, por lo que se "castiga" para evitar su proliferación.
    - Si un plásmido se encuentra en una posición favorable, se "premia" induciendo la adquisición de propiedades similares por bacterias cercanas mediante conjugación bacteriana.
- **Definición del patrón:** Depende de la movilidad o velocidad de conjugación del plásmido.
- **Aplicaciones:** Generación de patrones espaciales definidos mediante el control de señales intercelulares y movilidad bacteriana.
- ![[Pasted image 20241015121601.png]]
---
### **Patrones Temporales**
Los patrones temporales son aquellos que exhiben reproducibilidad y predicción en el tiempo. Aunque no siempre son visibles espacialmente, su comportamiento es predecible y repetitivo.
#### **Características principales**
- **Reproducibilidad:** El comportamiento del patrón se repite en el tiempo.
- **Predicción:** Es posible prever el momento en que ciertos eventos ocurrirán dentro del sistema.
#### **Circuitos relacionados con patrones temporales**
##### **1. Repressilator**
- **Descripción:** Este circuito realiza oscilaciones cíclicas entre tres genes que se expresan secuencialmente.
- **Características:**
    - La expresión de los genes sigue un orden predecible gracias a la represión secuencial.
    - Aunque el patrón no sea visible, su funcionamiento es automático y reproducible.
- **Aplicaciones:** Control preciso de procesos temporales mediante la manipulación de parámetros genéticos.
---
##### **2. Autonomous Bioreactor**
- **Descripción:** Circuito diseñado para encadenar tareas específicas mediante pulsos secuenciales, representados por tres colores (rojo, amarillo, verde).
- **Funcionamiento:**
    - **Rojo:** El AHL rojo corta P1 y activa la señal amarilla.
    - **Amarillo:** El AHL amarillo corta P2 y activa la señal verde.
    - **Verde:** El AHL verde corta P3, cerrando el ciclo.
- **Aplicaciones:** Regulación autónoma de procesos en bioreactores bacterianos.
- ![[Pasted image 20241022123146.png]]
---
### **Control de Población de Bacterias**
#### **Descripción**
- **Mecanismo:** Usa el sistema QS para medir la densidad de organismos. Si la concentración supera un umbral, se activa el gen **ccdB** (toxina), que induce apoptosis en las bacterias.
- **Características:**
    - La activación no es binaria; las concentraciones intermedias de proteínas y la afinidad de los promotores evitan que toda la colonia muera simultáneamente.
    - Oscila en densidad poblacional, similar al comportamiento del **Repressilator**.
- **Aplicaciones:** Regulación de poblaciones bacterianas para evitar sobrecrecimiento, manteniendo un nivel poblacional controlado.
- ![[Pasted image 20241025115705.png]]
---
### **Medición de Crosstalk**
#### **Descripción**
- **Propósito:** Determinar qué sistemas QS muestran interferencia (crosstalk) para evitar combinarlos en un circuito.
- **Metodología:**
    - Experimentos donde se cambia el AHL de un sistema X.
    - Se usan receptores de un sistema Y y se activa un promotor de un sistema Z.
- **Resultados:**
    - Pocos sistemas QS disponibles.
    - Muchos presentan crosstalk, lo que exige cuidado en su selección.
- **Aplicaciones:** Optimización en la elección de sistemas QS para evitar interferencias en circuitos genéticos complejos.
- ![[Pasted image 20241025123203.png]]
### **Tabla Resumen 1: Patrones Espaciales y Temporales**

|**Tipo de Patrón**|**Definición**|**Ejemplos**|**Aplicaciones**|
|---|---|---|---|
|**Espaciales**|Conjunto de características espaciales distintivas que se repiten y/o se mantienen constantes en el tiempo.|Formas, distribución de regiones, colores, ubicaciones específicas de la colonia.|- Biología del desarrollo (líneas de tigres, caparazones).  <br>- Control preciso a escala (fármacos, biomateriales).  <br>- Identificación de límites o concentraciones.|
|**Temporales**|Comportamiento reproducible y predecible en el tiempo; no necesariamente visible espacialmente.|Secuencias cíclicas de genes expresados.|- Control programable de procesos secuenciales.  <br>- Regulación autónoma en bioreactores.|

---
### **Tabla Resumen 2: Patrones Espaciales**

| **Patrón Espacial**        | **Descripción**                                                                                                                                          | **Requisitos/Condiciones**                                                                         | **Aplicaciones**                                                                                     |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Band Detector**          | Detecta zonas de alta, media y baja concentración usando tres plásmidos (pHD, pLD, pSND). Es multicelular y utiliza sistema Lux y dos variantes de LacI. | Comunicación entre bacterias vía Lux; diferenciación en alta, media y baja concentración.          | Delimitación precisa de regiones en colonias bacterianas.                                            |
| **Edge Detector**          | Detecta bordes entre luz y oscuridad; pigmento negro se expresa solo en la luz. Usa proteína fotosensible y señal Lux para marcar fronteras luminosas.   | Único color, circuito único en la colonia, pruebas con máscaras de luz.                            | Detección de bordes; podría liberar fármacos en áreas iluminadas o en presencia de un patógeno.      |
| **French Flag**            | Usa gradientes de morfógenos para formar zonas radiales (n+1 zonas con n umbrales); permite patrones no radiales en fronteras equidistantes.             | Concentración radial de morfógenos; umbrales programables para definir zonas específicas.          | Creación de patrones geométricos (líneas, cuadrados) útiles para organización en biología sintética. |
| **Variante Band Detector** | Procesamiento distribuido en plásmidos móviles según zonas de corta o larga distancia. Conjugación bacteriana premia/castiga según ubicación favorable.  | Control de movilidad de plásmidos; detección de zonas específicas mediante señales intercelulares. | Generación de patrones definidos adaptando movilidad bacteriana.                                     |

---
### **Tabla Resumen 3: Patrones Temporales**

| **Patrón Temporal**       | **Descripción**                                                                                                                 | **Requisitos/Condiciones**                                                                   | **Aplicaciones**                                                    |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **Repressilator**         | Oscilación cíclica entre tres genes que se expresan secuencialmente, predecible y reproducible automáticamente.                 | Modificación de velocidad de expresión y degradación genética para ajustar las oscilaciones. | Control temporal en procesos genéticos repetitivos.                 |
| **Autonomous Bioreactor** | Pulsos secuenciales para encadenar tareas específicas; utiliza tres señales representadas como colores (rojo, amarillo, verde). | Comunicación QS para coordinar acciones, velocidad de CRISPR ajusta ejecución de tareas.     | Control autónomo y eficiente de tareas en bioreactores bacterianos. |

---
### **Tabla Resumen 4: Control de Población y Medición de Crosstalk**

|**Tema**|**Descripción**|**Requisitos/Condiciones**|**Aplicaciones**|
|---|---|---|---|
|**Control de Población**|Sistema QS regula densidad bacteriana; activa ccdB (toxina) a concentraciones específicas. Oscila en densidad poblacional.|Afinidad del promotor y concentraciones intermedias evitan la eliminación total de la colonia.|Prevención de sobrecrecimiento en poblaciones bacterianas; regulación ambiental específica.|
|**Medición de Crosstalk**|Identifica sistemas QS que presentan interferencias (crosstalk) entre señales; evalúa compatibilidad entre sistemas.|Experimentos cambian señales AHL y receptores para medir ortogonalidad y evitar señales cruzadas.|Optimización de circuitos genéticos mediante elección de sistemas QS con mínima interferencia.|
### **Metodología con Detalles de las Pruebas**
#### **Modelo Híbrido (Autoencoder)**
- **Filtrado Colaborativo:**  
    El sistema utiliza interacciones usuario-canción basadas en las playlists para identificar patrones de preferencia. Esto detecta relaciones implícitas entre usuarios y canciones basándose en los historiales de reproducción.
- **Filtrado Basado en Contenido:**  
    Se incorporan características contextuales, como la popularidad de las playlists (número de seguidores promedio), para personalizar las recomendaciones. Este enfoque aborda limitaciones del filtrado colaborativo, como la falta de diversidad.
#### **Entrenamiento del Modelo**
- **Regularización y Dropout:**  
    Implementados para reducir el sobreajuste y mejorar la capacidad de generalización del modelo, esenciales al trabajar con datos de alta dimensionalidad como playlists y canciones.
- **Early Stopping:**  
    Detiene el entrenamiento cuando no se observa mejora en la pérdida de validación, optimizando recursos y evitando un entrenamiento excesivo.
- **Incremento en Dataset:**  
    El entrenamiento se realizó utilizando datasets de tamaños crecientes (`max_files = [1, 2, 3]`). Esto permite evaluar la escalabilidad y la capacidad del modelo para adaptarse a volúmenes mayores de datos.
#### **Pruebas y Configuración**
- **Usuarios y Canciones Simuladas:**
    - **Número de Usuarios:** `num_users = 500`.
    - **Canciones por Usuario:** `songs_per_user = 200`.
    - **Proporción de Canciones Omitidas:** `skipped_ratio = 0.2`.  
        Estas configuraciones simulan un entorno diverso con usuarios interactuando con un amplio catálogo musical.
- **Recomendaciones Generadas:**
    - **Top-N Canciones:** Se evaluaron las recomendaciones principales para cada usuario, utilizando `top_n = 20`. Esto permitió priorizar tanto precisión como diversidad.
    - Se excluyeron canciones conocidas por el usuario, incentivando la exploración y reduciendo la repetición.
- **Métricas Evaluadas:**
    - **Precisión:** Proporción de recomendaciones relevantes respecto al total de recomendaciones.
    - **Recall:** Proporción de canciones relevantes recomendadas respecto al total de canciones "gustadas".
    - **Diversidad:** Proporción de canciones únicas recomendadas entre los usuarios.
    - **Tasa de Saltos (_Skip Rate_):** Proporción de canciones omitidas entre las recomendaciones.
    - **Pérdida (Train vs Validation):** Para evaluar el ajuste del modelo y la presencia de sobreajuste.
#### **Visualización**
- Los resultados se plasmaron gráficamente, permitiendo comparar métricas clave y analizar el impacto del tamaño del dataset en el rendimiento del modelo. Este enfoque facilita una validación clara y transparente del desempeño general.

---
### **Explicación de los Gráficos Obtenidos**

#### **1. Diversidad de Recomendaciones**
- **Gráfico:** "Diversidad de recomendaciones entre usuarios por modelo".
- **Interpretación:**
    - La diversidad permaneció constante (~0.002) independientemente del tamaño del dataset.
    - Esto indica un balance logrado entre personalización y descubrimiento, asegurando que los usuarios reciban recomendaciones variadas.
---
#### **2. Precisión y Recall**

- **Gráfico:** "Precisión y Recall por modelo".
- **Interpretación:**
    - **Precisión:** Disminuyó a medida que aumentó el tamaño del dataset, lo cual es esperable al priorizar exploración sobre coincidencias exactas.
    - **Recall:** También disminuyó ligeramente, reflejando que, aunque se diversificaron las recomendaciones, algunas canciones relevantes pudieron no ser seleccionadas.
    - Este comportamiento es característico de sistemas que equilibran personalización y diversidad.

---
#### **3. Skip Rate (Tasa de Saltos)**

- **Gráfico:** "Skip Rate por modelo".
- **Interpretación:**
    - La tasa de saltos disminuyó significativamente al pasar de 1 a 2 archivos, indicando que el sistema identificó mejor las canciones relevantes.
    - Al usar 3 archivos, el skip rate aumentó ligeramente, probablemente debido a un aumento en la exploración que introdujo canciones menos ajustadas a las preferencias exactas de los usuarios.
---
#### **4. Pérdida (Train vs Validation) y Overfitting**

- **Gráfico:** "Comparación de Train Loss y Validation Loss entre modelos".
- **Interpretación:**
    - La diferencia entre pérdida de entrenamiento y validación disminuyó con datasets más grandes, pasando de 18.38% (1 archivo) a 10.63% (3 archivos), lo que demuestra una mejora en la generalización del modelo.
    - La reducción en la pérdida total refleja una mayor eficacia del modelo al aprender patrones relevantes.

---
#### **5. Tiempo de Entrenamiento**

- **Gráfico:** "Tiempo total de entrenamiento para cada modelo".
- **Interpretación:**
    - El tiempo de entrenamiento creció de forma proporcional al tamaño del dataset, desde 0.18 minutos (1 archivo) hasta 0.64 minutos (3 archivos).
    - Esto confirma la escalabilidad del sistema y su capacidad para manejar volúmenes crecientes de datos sin un impacto significativo en la eficiencia.