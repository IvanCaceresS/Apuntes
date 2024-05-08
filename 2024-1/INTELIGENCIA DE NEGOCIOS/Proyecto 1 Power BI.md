# Globar Superstore
## Descripción de cada columna
1. **ID de Fila**: Tipo de dato entero, identificador único para cada fila en el dataset.
2. **ID de Pedido**: Tipo de dato texto, identificador único para cada pedido.
3. **Fecha de Pedido**: Tipo de dato fecha, fecha en la que se realizó el pedido.
4. **Fecha de Envío**: Tipo de dato fecha, fecha en la que se envió el pedido.
5. **Modo de Envío**: Tipo de dato texto, describe el método de envío utilizado para el pedido (por ejemplo, "El mismo Día", "Segunda Clase", "Primera Clase").
6. **ID de Cliente**: Tipo de dato texto, código único que identifica a cada cliente.
7. **Nombre de Cliente**: Tipo de dato texto, nombre completo del cliente.
8. **Segmento**: Tipo de dato texto, segmento del mercado al que pertenece el cliente (por ejemplo, "Cliente", "Corporativo").
9. **Ciudad**: Tipo de dato texto, ciudad donde se realizó el pedido.
10. **Estado**: Tipo de dato texto, estado donde se realizó el pedido.
11. **País**: Tipo de dato texto, país donde se realizó el pedido.
12. **Código Postal**: Tipo de dato texto o entero, código postal donde se realizó el pedido.
13. **Mercado**: Tipo de dato texto, mercado geográfico del pedido.
14. **Región**: Tipo de dato texto, región geográfica del pedido.
15. **ID de Producto**: Tipo de dato texto, identificador único para cada producto.
16. **Categoría**: Tipo de dato texto, categoría general del producto (por ejemplo, "Tecnología", "Muebles").
17. **Subcategoría**: Tipo de dato texto, subcategoría específica del producto (por ejemplo, "Accesorios", "Sillas", "Teléfonos").
18. **Nombre del Producto**: Tipo de dato texto, nombre completo del producto.
19. **Ventas**: Tipo de dato numérico, cantidad total en dinero de las ventas del producto.
20. **Cantidad**: Tipo de dato entero, número de unidades del producto vendidas en el pedido.
21. **Descuento**: Tipo de dato numérico, porcentaje de descuento aplicado al producto.
22. **Ganancia**: Tipo de dato numérico, ganancia neta obtenida de la venta del producto.
23. **Costo de Envío**: Tipo de dato numérico, costo asociado al envío del producto.
24. **Prioridad de Pedido**: Tipo de dato texto, prioridad asignada al pedido (por ejemplo, "Crítico", "Medio").

- Elementos a considerar
    - Segmentación de datos
    - Tabla 
    - Matriz   
    - Velocímetro
    - Tarjeta
    - Tarjeta múltiple  
    - Gráficos
    - Mapas (debe idealmente mostrar información espacial)  
    - Debe realizar navegación entre páginas (ver detalle) y Tool Tip  
    - Uso jerarquía drill down drill up  
    - Considera un menú 
    - Uso de calendario
    - Indicadores de gestión
### 1. Tienda Mundial

**Objetivo**: Analizar ventas y ganancias por categoría, además de destacar productos con mayores ganancias y pérdidas. **Visualizaciones**:

- **Gráfico de barras agrupadas**: Ventas y ganancia por categoría.
- **Listas de top 5**: Productos con mayor ganancia y mayor pérdida.
- **Indicadores**: Ventas totales, meta de ventas, ganancias totales, y cantidad de pedidos realizados.

### 2. Tendencias Anuales de Ventas y Ganancias

**Objetivo**: Mostrar la evolución temporal de ventas y ganancias. **Visualizaciones**:

- **Gráfico de líneas**: Evolución de ventas y ganancias por mes.
- **Indicador de margen de ganancia promedio**.

### 3. Análisis de Clientes y sus Pedidos

**Objetivo**: Segmentar clientes y mostrar su distribución geográfica. **Visualizaciones**:

- **Tabla**: Detalle de pedidos por segmento de cliente.
- **Mapa**: Distribución geográfica de clientes.

### 4. Segmentación Geográfica de Clientes

**Objetivo**: Analizar la distribución de ventas por países y segmentos de clientes. **Visualizaciones**:

- **Gráfico de barras**: Ventas por país y segmento de cliente.

### 5. Análisis de Distribución Global de Pedidos

**Objetivo**: Visualizar la distribución global y temporal de los pedidos. **Visualizaciones**:

- **Gráfico de barras y mapa**: Cantidad de pedidos por país y su evolución anual.

### 6. Análisis Detallado del Rendimiento de Productos

**Objetivo**: Evaluar el rendimiento de ventas y ganancias por categoría de productos. **Visualizaciones**:

- **Gráfico combinado de líneas y barras**: Distribución de la cantidad vendida por fecha y categoría.
- **Gráficos de barras y circular**: Análisis de ventas y ganancias por categoría y descuentos aplicados.

### 7. Análisis de Eficiencia y Costos de Envío

**Objetivo**: Evaluar la eficiencia y costos asociados con diferentes métodos de envío. **Visualizaciones**:

- **Gráficos de barras y líneas**: Comparativa de costos y tiempos de entrega, evolución de los costos de envío, y rendimiento de envío frente al promedio.