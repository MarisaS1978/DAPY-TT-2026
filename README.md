# Análisis de Ventas y Rendimiento de Campañas de Marketing (2024)

## Descripción del Proyecto
Este proyecto desarrolla un análisis integral de datos comerciales utilizando Python para auditar, limpiar, integrar y visualizar el rendimiento de ventas y el impacto de las campañas de marketing durante el año 2024. El objetivo principal es identificar patrones de compra, evaluar la rentabilidad por canal publicitario (ROI) y consolidar un set de datos estratégico para la toma de decisiones.

El flujo de trabajo abarca desde scripts básicos de lógica de negocio hasta la construcción de un dashboard analítico interactivo.

---

## Estructura de las Etapas

### Etapa 1: Recopilación y Exploración Inicial
*   Carga de fuentes de datos distribuidas en entornos web (`ventas`, `clientes` y `marketing`) mediante DataFrames de Pandas.
*   Auditoría de calidad: Identificación de registros duplicados (35 en el dataset de ventas) y valores nulos residuales.
*   Diagnóstico de formatos: Detección de caracteres especiales (símbolos de moneda `$`) e inconsistencias cronológicas en campos de fecha.

### Etapa 2: Preprocesamiento y Limpieza de Datos
*   **Saneamiento:** Remoción de duplicados y nulos mediante lógica estructurada.
*   **Normalización:** Limpieza de strings en variables de precios, casting a punto flotante (`float`) y conversión de variables de tiempo a objetos nativos `datetime`.
*   **Enriquecimiento:** Creación de la métrica de negocio `venta_neta` ($precio \times cantidad$).
*   **Integración:** Fusión de datos mediante un esquema *Left Join* por clave de producto para contrastar los eventos de venta con ventanas de campañas publicitarias activas.

### Etapa 3: Análisis Estadístico y Correlación
*   **Estadística Descriptiva:** Análisis del comportamiento de precios (Media: \$75.29), volúmenes transaccionados y variabilidad de ingresos.
*   **Cálculo de Performance:** Implementación de segmentación por percentiles (Percentil 75) para aislar productos de alto rendimiento.
*   **Análisis de Matriz de Correlación:**
    *   Fuerte correlación positiva entre cantidad e ingresos netos ($0.77$).
    *   Independencia estadística entre el precio unitario y el volumen de compra (correlación de $-0.002$), reflejando una demanda inelástica en el rango actual de precios.

### Etapa 4: Visualización de Datos y Dashboard
Análisis gráfico mediante librerías complementarias:
*   **Matplotlib:** Series temporales de evolución mensual, diagramas de dispersión de precios e ingresos, y análisis de distribución por trimestre.
*   **Seaborn:** Gráficos avanzados de distribución estadística (Boxplots, Violinplots y mapas de calor personalizados) para evaluar la concentración transaccional e identificar *outliers*.
*   **Plotly Express / Graph Objects:** Diseño de un dashboard interactivo unificado con lógica de filtrado dinámico mediante menús *Dropdown* para explorar la relación precio-ingreso según la categoría del producto.

---

## Tecnologías Utilizadas
*   **Lenguaje:** Python 3.x
*   **Entorno:** Google Colaboratory
*   **Librerías Clave:** Pandas, NumPy, Matplotlib, Seaborn, Plotly

---

## Principales Insights del Negocio
1.  **Motor de Ingresos:** El volumen de transacciones es el principal impulsor de la facturación general, por encima de los ajustes aislados en los precios.
2.  **Eficiencia Publicitaria (ROI):** El canal de **Email Marketing** se consolidó como la estrategia más eficiente y con mayor retorno de inversión, seguido de la televisión (TV), mientras que las redes sociales (RRSS) exhibieron el ROI más bajo relativo.
3.  **Balance de Cartera:** Existe una distribución equitativa de ingresos brutos entre las tres principales categorías del negocio (Electrodomésticos, Electrónica y Decoración), destacando los electrodomésticos con un ligero liderazgo en facturación acumulada.
