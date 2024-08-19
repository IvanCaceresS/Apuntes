# Primera clase 08-08
[Programa del curso](https://docs.google.com/document/d/1Ropg7rWHqegwa842KWYS8QWFQlQFYosbU7WQL8W1GRc/edit)
[Planificación de fechas](https://docs.google.com/spreadsheets/d/1OwyUQys_vm3X_waL8k6gh57PFALVQyJBvOjxjk6xwv8/edit?gid=0#gid=0)
Nota Final = (40% Trabajos individuales + 30% Informes + 30% Presentaciones)

_Algunas de las herramientas a utilizar en este curso son:
- wireshark
- PGrouting
- QGIS
- Gurobi
- Mentimeter

2 Trabajos individuales
1 Trabajo grupal a lo largo de todo el semestre (Informe con presentaciones)

# Clase de 12-08
## Traceroute
- Traceroute no siempre muestra la ruta exacta que siguen los datos
- Traceroute puede ser afectado por el balanceo de carga, que distribuye el tráfico entre diferentes rutas según la disponibilidad o el rendimiento. 
- Traceroute puede ser bloqueado o alterado por firewalls o políticas de filtrado, que impiden el paso o la respuesta de los paquetes ICMP.  
- Traceroute puede ser inexacto o inconsistente debido a factores como el congestionamiento de la red, las variaciones del tiempo de propagación, o los errores de transmisión.

Vantage Points
- Son puntos de observación que se utilizan para realizar mediciones. Existen proyectos que los utilizan tales como: CAIDA y RIPE 
# Clase 19-08
## Metadata
Es información adicional sobre algo que yo ya conozco, y me permite tomar mejores decisiones.
Ejemplos o herramientas:
- **Geolocation**: no siempre fiarse de las coordenadas porque no siempre son correctas, por eso se debe limpiar la información.
- **IP2Trace:** Segun la IP, dice por que ciudades va pasando el traceroute, de igual manera se debe investigar si realmente existe un datacenter en esa ciudad, para verificar que la info que otorga IP2Trace es correcta.
- **IP2Location:** Es una API, donde se consulta por una IP y entrega datos geográficos más confiables.
- **Maxmind:** Otra API similar.
- **LatLon 2 Address:** Otra API similar.
- **RapidAPI:** API Search Engine, para buscar APIs.
- **Hurricane Electric Internet Services:** Tiene mucha info, pero no está actualizada, por lo que generalmente no sirve.
- **Shodan search engine:** Es un metabuscador, permite buscar información sobre IPs, hace consultas a distintos puertos de las maquinas para obtener esa información
- **Shodan API:** Es la API de shodan search engine, entrega la ip en bits, junta todos los octetos y los pasa a un numero.
- **CVE:** Busca vulnerabilidades.
- **TOR + Proxychains4:** Se utilizan para realizar solicitudes web a través de la red Tor, con el fin de ocultar la dirección IP real del usuario y navegar de manera anónima.
- **Escaneo de Puertos (Masscan con Proxychains4):** Realizar un escaneo de puertos sobre una lista de direcciones IP (u objetivos) de manera anónima.

## Trabajo, excel se publica a las 21:00 hrs
Elegir la infraestructura (temática), cual es la metadata que voy a asociar a esa infraestructura (verificar que se puedan obtener las metadatas) y cuales son las amenazas (son temporales, no es que sucedan siempre).