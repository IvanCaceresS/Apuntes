# Global Superstore
URL: https://www.kaggle.com/datasets/shekpaul/global-superstore?ref=hackernoon.com

El objetivo general del dashboard del proyecto de Power BI basado en el conjunto de datos de Global Superstore es proporcionar una herramienta interactiva y comprensiva de análisis de ventas que permita a los usuarios explorar y entender el desempeño de la empresa a través de múltiples dimensiones. Mediante la utilización de segmentaciones de datos, tablas detalladas, matrices, visualizaciones dinámicas como velocímetros, tarjetas de KPI, gráficos variados y mapas geográficos, el dashboard busca ofrecer insights detallados sobre las tendencias de ventas, la rentabilidad de productos, la eficacia de las estrategias de descuentos, y la satisfacción del cliente. El uso de jerarquías para el drill down y drill up, junto con la navegación intuitiva entre páginas y la implementación de Tool Tips, permite a los usuarios realizar un análisis profundo desde una perspectiva general hasta llegar a detalles específicos de pedidos, clientes y productos. Los indicadores de gestión y los objetivos, como el crecimiento de las ventas, la optimización de la rentabilidad y la mejora en la relación con los clientes, están diseñados para guiar a los usuarios en la toma de decisiones estratégicas y operativas, mejorando así el desempeño general del negocio. Este dashboard sirve como una solución integral para monitorear, analizar y planificar acciones basadas en datos reales y tendencias del mercado, facilitando el camino hacia el éxito y la sustentabilidad del negocio en el competitivo entorno del comercio minorista global.
### 1. **Segmentación de Datos**
Para implementar segmentadores:
- En la vista de reporte, selecciona el icono de segmentación de datos en la barra de herramientas de visualizaciones.
- Arrastra los campos por los que deseas segmentar, como `Fecha del pedido`, `Segmento`, `País`, `Categoría` o `Subcategoría`, al área de valores del segmentador.
- Personaliza los segmentadores para mejorar la usabilidad, ajustando su diseño y formato según necesites.
### 2. **Tabla**
Para crear tablas detalladas:
- Elige la visualización de tabla.
- Arrastra los campos `ID de pedido`, `Fecha del pedido`, `Nombre del cliente`, `Nombre del producto`, y `Beneficio` al área de valores.
- Ajusta el formato de la tabla para mejorar la legibilidad, como el tamaño del texto y el color de fondo.
### 3. **Matriz**
Para usar una matriz:
- Selecciona la visualización de matriz.
- Arrastra `Categoría` y `Subcategoría` como filas, y quizás `Segmento` como columna.
- Usa `Ventas` y `Beneficio` como valores para analizar.
- Activa las opciones de subtotal y total general para obtener resúmenes automáticos.
### 4. **Velocímetro**
Para diseñar un velocímetro:
- Necesitarás usar las visualizaciones personalizadas disponibles en el mercado de Power BI.
- Busca "Gauge" o "Velocímetro" en el mercado de visualizaciones y añádelo a tu reporte.
- Configura el indicador con un valor actual, como las ventas totales del mes, y establece un objetivo o máximo basado en tu objetivo de ventas.
### 5. **Tarjeta y Tarjeta Múltiple**
Para mostrar KPIs mediante tarjetas:
- Utiliza la visualización de tarjeta para mostrar un único KPI, como `Ventas totales`.
- Para tarjetas múltiples, considera usar la visualización de KPI o buscar una visualización personalizada que permita mostrar múltiples KPIs simultáneamente.
- Configura cada tarjeta con su respectivo campo, como `Número total de pedidos` o `Número de clientes únicos`.
### 6. **Gráficos**
Para implementar diferentes tipos de gráficos:
- **Barras**: Compara las ventas o beneficios por país o región.
- **Líneas**: Muestra tendencias de ventas a lo largo del tiempo seleccionando `Fecha del pedido` como eje y `Ventas` como valor.
- **Torta**: Visualiza la distribución de ventas por categoría de producto utilizando `Categoría` como leyenda y `Ventas` como valor.
### 7. **Mapas**
Para visualizar datos geográficos:
- Elige la visualización de mapa.
- Usa `País` o `Ciudad` como ubicación y `Ventas` o `Beneficio` como valor.
- Considera mapas de burbujas para representar el tamaño de las ventas o beneficios por ubicación.
### 8. **Navegación entre Páginas y Tool Tip**
- Crea botones o imágenes que sirvan como enlaces a diferentes páginas del reporte para la navegación.
- En las visualizaciones, activa y configura los Tool Tips en el panel de formato para mostrar detalles adicionales sobre el dato que se esté examinando.
### 9. **Uso de Jerarquía Drill Down/Up**
- Crea jerarquías en el panel de campos arrastrando, por ejemplo, `Año`, `Mes` y `Día` para la fecha, o `País`, `Estado` y `Ciudad` para la ubicación.
- Utiliza estas jerarquías en tus visualizaciones de mapa o gráficos para permitir el análisis detallado por niveles mediante el botón de Drill Down.
### 10. **Menú**
- Crea una página que actúe como menú principal con botones o imágenes que redirijan a las diferentes secciones del dashboard.
- Personaliza la apariencia de este menú para hacerlo intuitivo y atractivo.
### 11. **Uso de Calendario**
- Aprovecha la funcionalidad de slicer de fecha para permitir a los usuarios seleccionar rangos específicos.
- Configura el slicer para mostrar un calendario desplegable y permite la selección de fechas específicas.
### Indicadores de Gestión y Objetivos
Basándote en este conjunto de datos, puedes:
- **Establecer objetivos de crecimiento de ventas** mensuales o anuales y visualizar el progreso hacia estos objetivos con velocímetros o tarjetas de KPI.
- **Analizar la rentabilidad** por categoría de producto o segmento de cliente para identificar áreas de alta y baja eficiencia.
- **Evaluar la eficiencia de los descuentos** correlacionando el porcentaje de descuento con un aumento en la cantidad de ventas o clientes.
- **Medir la satisfacción del cliente** a través del análisis de repitencia de pedidos o variaciones en el tamaño promedio de los pedidos por cliente.

# Organizacion:
### 1. **Página Principal (Dashboard)**

- **KPIs Clave:** Usa tarjetas grandes en la parte superior para mostrar ventas totales, número de pedidos, y beneficio total.
- **Mapa Mundial Pequeño:** En el centro, para mostrar ventas por región con colores que varíen según el volumen de ventas.
- **Gráficos de Barras y Líneas:** Debajo o al lado del mapa, para mostrar las tendencias de ventas mensuales y comparación anual.

### 2. **Análisis de Ventas**

- **Gráfico de Líneas:** Visualiza las tendencias de ventas a lo largo del tiempo, con un eje de tiempo y ventas acumuladas.
- **Gráfico de Barras:** Para comparar las ventas por regiones, con un segmentador para seleccionar rangos de fechas o regiones específicas.
- **Segmentadores de Datos:** Colocados estratégicamente para filtrar por fecha, categoría, o región.

### 3. **Rendimiento de Productos**

- **Matriz Detallada:** Con filas para categorías y subcategorías, y columnas mostrando ventas y beneficios.
- **Gráficos de Columna:** Para destacar los productos más vendidos o más rentables.
- **Jerarquías Drill Down/Up:** Permitiendo a los usuarios explorar desde categorías generales a productos específicos.

### 4. **Análisis de Clientes**

- **Gráfico de Torta:** Para visualizar la proporción de clientes por segmento o región.
- **Tabla de Detalles:** Mostrando información como nombre del cliente, número de pedidos, y volumen de ventas.
- **Tarjetas de KPIs:** Para métricas como número total de clientes y tasa de retención.

### 5. **Eficiencia de Descuentos**

- **Gráficos de Dispersión:** Para correlacionar el porcentaje de descuento con las ventas o el número de pedidos.
- **Barras de Comparación:** Para ver cómo diferentes niveles de descuentos afectan las ventas en distintas categorías.
- **Segmentadores de Datos:** Para ajustar las visualizaciones basadas en rangos de descuentos o periodos específicos.

### 6. **Satisfacción y Fidelización de Clientes**

- **Histogramas o Gráficos de Líneas:** Para mostrar la frecuencia de pedidos por cliente o el tamaño promedio de los pedidos.
- **Gráficos de Área:** Para visualizar la lealtad del cliente a lo largo del tiempo.
- **Detalles de Feedback del Cliente:** Si están disponibles, incluir comentarios o puntuaciones de satisfacción.

### 7. **Configuración y Herramientas de Análisis**

- **Segmentadores de Fecha Avanzados:** Un panel de control con opciones de calendario para seleccionar rangos de fechas.
- **Botones de Navegación Detallados:** Para drill down/up, con iconos intuitivos.
- **Espacio para Notas o Guías:** Un área donde se puedan añadir instrucciones o consejos sobre cómo utilizar el dashboard.