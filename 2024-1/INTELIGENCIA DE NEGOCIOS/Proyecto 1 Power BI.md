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
## Páginas
### 1. **Dashboard Principal**

**Objetivo**: Proporcionar una vista rápida del rendimiento general del negocio. **Datos Utilizados**: Ventas, Ganancia, Cantidad, Descuento, Costo de Envío. **Visualizaciones**:

- **Tarjetas de KPI** (Indicadores de gestión): Ventas Totales, Ganancia Total, Cantidad de Pedidos Total.
- **Velocímetro** (Indicadores de gestión): Compara ventas actuales contra objetivos de ventas.
- **Gráfico de Barras Compuestas** (Gráficos):Ventas y ganancias por categoría de producto.
- **Tabla de Resumen** (Tabla): Cinco productos más vendidos con Ventas y Cantidad.

### 2. **Tendencias de Ventas y Ganancias**

**Objetivo**: Analizar cómo las ventas y ganancias cambian a lo largo del tiempo. **Datos Utilizados**: Fecha de Pedido, Ventas, Ganancia. **Visualizaciones**:

- **Gráfico de Líneas Doble Eje** (Gráficos): Ventas y ganancias por mes.
- **Selector de Fecha** (Uso de calendario): Para filtrar los datos mostrados en el gráfico.
- **Tarjeta** (Tarjeta única): Para mostrar el total de descuentos en el periodo seleccionado.

### 3. **Análisis de Pedidos y Clientes**

**Objetivo**: Examinar los detalles de los pedidos y el comportamiento de compra de los clientes. **Datos Utilizados**: ID de Pedido, Fecha de Pedido, ID de Cliente, Nombre de Cliente, Segmento, Modo de Envío, Prioridad de Pedido, Ventas, Cantidad, Descuento, Ganancia. **Visualizaciones**:

- **Matriz** con Drill-Down (Matriz, Uso jerarquía drill down drill up): Por segmento de cliente, con posibilidad de ver detalles hasta el nivel de pedido individual.
- **Tool Tips** (Tool Tip): Mostrar detalles adicionales como el modo y prioridad de envío al pasar el cursor.
- **Navegación entre Páginas** (Navegación): Enlaces para acceder a detalles específicos de cada pedido.

### 4. **Segmentación y Comportamiento del Cliente**

**Objetivo**: Segmentar clientes y analizar diferencias en comportamiento de compra. **Datos Utilizados**: Segmento, Nombre de Cliente, Ciudad, Estado, Ventas, Cantidad. **Visualizaciones**:

- **Gráfico de Barras Apiladas** con Drill-Down (Gráficos, Uso jerarquía drill down drill up): Ventas por segmento de cliente, con drill-down a nivel de ciudad y estado.
- **Mapa de Calor** (Mapas): Distribución geográfica de ventas y cantidad de pedidos.

### 5. **Distribución Geográfica de Pedidos**

**Objetivo**: Visualizar dónde se realizan y envían más pedidos. **Datos Utilizados**: Ciudad, Estado, País, Ventas, Cantidad. **Visualizaciones**:

- **Mapa con Burbujas** (Mapas): Muestra la ubicación y el volumen de pedidos, con burbujas de tamaño variable según la cantidad de ventas.

### 6. **Desempeño de Productos**

**Objetivo**: Evaluar el rendimiento de diferentes productos y categorías. **Datos Utilizados**: Categoría, Subcategoría, Nombre del Producto, Ventas, Descuento, Ganancia. **Visualizaciones**:

- **Gráfico de Torta** (Gráficos): Ventas por subcategoría de productos.
- **Gráfico de Columnas Apiladas** (Gráficos): Descuento medio y ganancia por categoría de producto.
- **Tarjeta Múltiple** (Tarjeta múltiple): Para datos como precio promedio y tasa de retorno de cada categoría.

### 7. **Eficiencia de Envío y Prioridades**

**Objetivo**: Analizar la eficacia y costos de los métodos de envío. **Datos Utilizados**: Modo de Envío, Prioridad de Pedido, Fecha de Envío, Costo de Envío, Tiempo de Envío Estimado. **Visualizaciones**:

- **Gráfico de Área Apilada** (Gráficos): Pedidos por modo de envío a lo largo del tiempo.
- **Tabla Comparativa** (Tabla): Comparación de prioridad de pedido con tiempo de entrega promedio y costos de envío.

### Navegación y Funcionalidad Adicional

- **Menú de Navegación Global**: Incluido en todas las páginas para facilitar el movimiento entre secciones.
- **Interacciones y Filtros**: Configurar las interacciones entre gráficos para que la selección en una visualización afecte las visualizaciones relacionadas en la misma página.

Con esta estructura, cada página del informe tiene un propósito claro y explora diferentes aspectos del negocio, asegurando que cada dato utilizado aporte al análisis general.