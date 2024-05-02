# Globar Superstore
## Descripción de cada columna
1. **ID de Fila**: Tipo de dato entero, identificador único para cada fila en el dataset.
2. **ID de Pedido**: Tipo de dato texto, identificador único para cada pedido.
3. **Fecha de Pedido**: Tipo de dato fecha, fecha en la que se realizó el pedido.
4. **Fecha de Envío**: Tipo de dato fecha, fecha en la que se envió el pedido.
5. **Modo de Envío**: Tipo de dato texto, describe el método de envío utilizado para el pedido (por ejemplo, "Same Day", "Second Class", "First Class").
6. **ID de Cliente**: Tipo de dato texto, código único que identifica a cada cliente.
7. **Nombre de Cliente**: Tipo de dato texto, nombre completo del cliente.
8. **Segmento**: Tipo de dato texto, segmento del mercado al que pertenece el cliente (por ejemplo, "Consumer", "Corporate").
9. **Ciudad**: Tipo de dato texto, ciudad donde se realizó el pedido.
10. **Estado**: Tipo de dato texto, estado donde se realizó el pedido.
11. **País**: Tipo de dato texto, país donde se realizó el pedido.
12. **Código Postal**: Tipo de dato texto o entero, código postal donde se realizó el pedido.
13. **Mercado**: Tipo de dato texto, mercado geográfico del pedido.
14. **Región**: Tipo de dato texto, región geográfica del pedido.
15. **ID de Producto**: Tipo de dato texto, identificador único para cada producto.
16. **Categoría**: Tipo de dato texto, categoría general del producto (por ejemplo, "Technology", "Furniture").
17. **Subcategoría**: Tipo de dato texto, subcategoría específica del producto (por ejemplo, "Accessories", "Chairs", "Phones").
18. **Nombre del Producto**: Tipo de dato texto, nombre completo del producto.
19. **Ventas**: Tipo de dato numérico, cantidad total en dinero de las ventas del producto.
20. **Cantidad**: Tipo de dato entero, número de unidades del producto vendidas en el pedido.
21. **Descuento**: Tipo de dato numérico, porcentaje de descuento aplicado al producto.
22. **Ganancia**: Tipo de dato numérico, ganancia neta obtenida de la venta del producto.
23. **Costo de Envío**: Tipo de dato numérico, costo asociado al envío del producto.
24. **Prioridad de Pedido**: Tipo de dato texto, prioridad asignada al pedido (por ejemplo, "Critical", "Medium").

- Elementos a considerar
    - Segmentación de datos   [USADO]
    - Tabla   [USADO]
    - Matriz   
    - Velocímetro  [USADO]
    - Tarjeta   [USADO]
    - Tarjeta múltiple  
    - Gráficos  [USADO]
    - Mapas (debe idealmente mostrar información espacial)  
    - Debe realizar navegación entre páginas (ver detalle) y Tool Tip  
    - Uso jerarquía drill down drill up  
    - Considera un menú   [USADO]
    - Uso de calendario   [USADO]
    - Indicadores de gestión
## Páginas
### 1. **Dashboard Principal**

**Objetivo**: Proporcionar una vista rápida del rendimiento general del negocio.

**Datos Utilizados**: Ventas, Ganancia, Cantidad de Pedidos.

**Visualizaciones**:

- **Gráfico de Barras Compuestas** (Gráficos): Muestra las Ventas y Ganancias por categoría de producto, facilitando la comparación directa entre categorías y destacando las que tienen mayor rendimiento.
- **Top 5 Productos con Mayor Ganancia** (Tabla): Lista los cinco productos con las mayores ganancias, utilizando colores y formato claro para destacar los productos más rentables.
- **Top 5 Productos con Menor Ganancia** (Tabla): Presenta los cinco productos con las menores ganancias, utilizando colores distintivos para alertar sobre los productos menos rentables.
- **Selector de Año** (Segmentación de Datos): Permite a los usuarios seleccionar y visualizar datos de un año específico, influyendo en todas las visualizaciones del dashboard.
- **Meta de Ventas** (Velocímetro): Visualiza el progreso hacia la meta de ventas anual, con un diseño colorido que muestra visualmente qué tan cerca está el negocio de alcanzar sus objetivos.
- **Suma de Ventas y Ganancias por Año** (Tarjetas): Muestra el total de ventas y ganancias acumuladas por año, proporcionando un resumen rápido del rendimiento financiero.
- **Cantidad de Pedidos Realizados** (Tarjeta): Reporta el total de pedidos realizados hasta la fecha, ofreciendo un indicador de la actividad del negocio.

### 2. **Tendencias de Ventas y Ganancias**

**Objetivo**: Analizar cómo las ventas y ganancias cambian a lo largo del tiempo.

**Datos Utilizados**: Fecha de Pedido, Ventas, Ganancia.

**Visualizaciones**:

- **Gráfico de Líneas Doble Eje** (Gráficos): Ilustra las tendencias de Ventas y Ganancias a lo largo del tiempo, con un eje para cada métrica, permitiendo comparar la correlación entre ventas y rentabilidad por cada período.
- **Selector de Fecha** (Uso de calendario): Ofrece la capacidad de filtrar los datos mostrados en el gráfico según un rango de fechas seleccionado, afectando la visualización de las tendencias.
- **Margen de Ganancia Promedio** (Tarjeta): Destaca el porcentaje promedio de ganancia sobre las ventas, ofreciendo una vista rápida de la eficiencia operativa del negocio.

### 3. **Análisis de Pedidos y Clientes**

**Objetivo**: Examinar detalladamente los pedidos y el comportamiento de compra de los clientes.

**Datos Utilizados**: ID de Pedido, Fecha de Pedido, ID de Cliente, Nombre de Cliente, Segmento, Modo de Envío, Prioridad de Pedido, Ventas, Cantidad, Descuento, Ganancia.

**Visualizaciones**:

- **Matriz con Drill-Down (Matriz, Uso jerarquía drill down/drill up)**:
    
    - **Descripción**: Explora las ventas por segmento de cliente, permitiendo drill-down hasta el pedido individual.
    - **Campos**: Segmento de Cliente → ID de Cliente → ID de Pedido.
    - **Valores mostrados**: Ventas, Cantidad, Ganancia.
    - **Interactividad**: Activación del drill-down para profundizar desde el nivel de segmento hasta detalles del pedido.
- **Mapa de Calor para Ubicación de Pedidos (Mapas)**:
    
    - **Descripción**: Visualiza la distribución geográfica de los pedidos basada en la ubicación del cliente.
    - **Datos Mostrados**: Ubicaciones de los clientes, con tamaños de marcadores basados en la cantidad de pedidos.
- **Tarjeta de Tooltips (Tool Tip)**:
    
    - **Descripción**: Muestra detalles adicionales como Modo de Envío y Prioridad de Pedido al pasar el cursor.

### 4. **Segmentación y Comportamiento del Cliente**

**Objetivo**: Segmentar clientes y analizar diferencias en comportamiento de compra.

**Datos Utilizados**: Segmento, Nombre de Cliente, Ciudad, Estado, Ventas, Cantidad.

**Visualizaciones**:

- **Gráfico de Barras Apiladas con Drill-Down (Gráficos, Uso jerarquía drill down drill up)**:
    
    - **Descripción**: Analiza las ventas por segmento de cliente con capacidad de drill-down hasta el nivel de ciudad y estado.
    - **Interactividad**: Permite explorar datos específicos al hacer clic en las barras.
- **Selector de Fecha (Uso de calendario)**:
    
    - **Descripción**: Filtra los datos mostrados en el gráfico por rango de fechas seleccionado.

### 5. **Distribución Geográfica de Pedidos**

**Objetivo**: Visualizar dónde se realizan y envían más pedidos.

**Datos Utilizados**: Ciudad, Estado, País, Ventas, Cantidad.

**Visualizaciones**:

- **Mapa con Burbujas (Mapas)**:
    - **Descripción**: Muestra la ubicación y el volumen de pedidos, con burbujas de tamaño variable según la cantidad de ventas.

### 6. **Desempeño de Productos**

**Objetivo**: Evaluar el rendimiento de diferentes productos y categorías. **Datos Utilizados**: Categoría, Subcategoría, Nombre del Producto, Ventas, Descuento, Ganancia. **Visualizaciones**:

- **Gráfico de Torta** (Gráficos): Ventas por subcategoría de productos.
- **Gráfico de Columnas Apiladas** (Gráficos): Descuento medio y ganancia por categoría de producto.
- **Tarjeta Múltiple** (Tarjeta múltiple): Para datos como precio promedio y tasa de retorno de cada categoría.

### 7. **Eficiencia de Envío y Prioridades**

**Objetivo**: Analizar la eficacia y costos de los métodos de envío.

**Datos Utilizados**: Modo de Envío, Prioridad de Pedido, Fecha de Envío, Costo de Envío, Tiempo de Envío Estimado.

**Visualizaciones**:

- **Velocímetro (Indicadores de gestión)**:
    
    - **Descripción**: Muestra el cumplimiento de metas de eficiencia en envíos.
- **Tabla Comparativa (Tabla)**:
    
    - **Descripción**: Compara prioridad de pedido con tiempo de entrega promedio y costos de envío.