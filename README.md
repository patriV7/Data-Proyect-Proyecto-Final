Proyecto Final Data Analytics – Modelo de Ventas en Power BI
1. Objetivo del proyecto

El objetivo de este proyecto es desarrollar un análisis descriptivo de ventas y margen comercial a partir de un modelo de datos estructurado, aplicando buenas prácticas de Data Analytics: trazabilidad de datos, limpieza, análisis exploratorio, modelado dimensional, visualización e interpretación de resultados para la toma de decisiones de negocio.

2. Origen y descripción de los datos

El modelo original se construyó a partir de un conjunto de datos procedente de una base de datos SQL con información de clientes, productos, vendedores y albaranes de venta, posteriormente exportado a Excel.

Por motivos de confidencialidad, no es posible adjuntar el dataset original. En su lugar, se incluye un fichero Excel con una muestra anonimizada y sintética, que reproduce fielmente:

la estructura del modelo

las tablas

las relaciones

las cardinalidades

las reglas de negocio principales

Esta muestra permite reproducir el proyecto end-to-end.

📁 Fichero incluido:
data/Modelo_Ventas_sample.xlsx

3. Estructura del repositorio
4. ├── data/
│   └── Modelo_Ventas_sample.xlsx
├── notebooks/
│   └── EDA_ventas.ipynb
├── docs/
│   ├── data_dictionary.md
│   └── informe_insights.md
├── powerbi/
│   └── Modelo Ventas.pbix
├── README.md

4. Modelo de datos

El modelo sigue un esquema en estrella, con una tabla de hechos central y varias dimensiones:

Tabla de hechos

fVentas: ventas por albarán, con métricas de cantidad, importe neto y coste.

Dimensiones

dClientes

dProductos

dVendedores

dFecha

Las relaciones son 1:N desde las dimensiones hacia la tabla de hechos.
Las fechas automáticas y relaciones automáticas fueron desactivadas para un control manual del modelo.

5. Transformación y limpieza de datos

Las transformaciones se realizaron en Power Query e incluyeron:

Renombrado de columnas

Conversión de tipos de datos

Eliminación de duplicados y registros nulos

Selección de columnas relevantes

Combinación de cabeceras y líneas de albaranes

Creación de jerarquías (fechas, clientes, productos)

Ocultación de tablas técnicas

Estas transformaciones permiten garantizar un modelo limpio, consistente y orientado al análisis.

6. Análisis Exploratorio de Datos (EDA)

Se ha realizado un EDA reproducible en Python (Pandas) para:

evaluar la calidad de los datos

analizar distribuciones

detectar valores atípicos

validar coherencia de métricas

📓 Notebook incluido:
notebooks/EDA_ventas.ipynb

7. Dashboard en Power BI

El dashboard se estructura en distintas páginas:

Visión general de ventas y margen

Detalle por cliente, producto y familia

Análisis temporal con comparativas YoY

Incluye KPIs, filtros globales por año y navegación entre páginas.

8. Alcance y limitaciones

El proyecto tiene un alcance descriptivo y diagnóstico.
No se incluyen modelos predictivos ni inferenciales avanzados.

Limitaciones:

Uso de muestra anonimizada

Presencia de ventas sin vendedor asignado

Análisis centrado en ventas y margen (otros enfoques posibles)

9. Tecnologías utilizadas

Power BI

Power Query (M)

DAX

Python (Pandas, Matplotlib)

Excel

    
