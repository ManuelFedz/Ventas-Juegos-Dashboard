<img width="1451" height="817" alt="{C944385B-92BF-44BC-B83C-896B56F226E1}" src="https://github.com/user-attachments/assets/e2817176-5ee7-4a0b-8453-2166e05e9ec6" />
# Video Games Global Sales — Power BI Dashboard & Data Analysis

Dashboard analítico e interactivo desarrollado en **Power BI Desktop** para explorar y visualizar el desempeño comercial histórico de la industria de los videojuegos a nivel mundial, abarcando más de **16,300 títulos** y más de tres décadas de historia (1980 en adelante).

---

## Descripción del Proyecto

Este proyecto analiza las ventas globales de copias de videojuegos segmentadas por plataformas, géneros, editoriales y regiones geográficas clave (Norteamérica, Europa, Japón y Resto del Mundo).

El reporte permite responder a preguntas estratégicas de negocio:
* ¿Cuáles han sido las plataformas de videojuegos más exitosas comercialmente?
* ¿Qué géneros dominan las preferencias en cada mercado regional?
* ¿Cómo ha evolucionado el volumen de ventas a lo largo de los años y ciclos de consolas?
* ¿Cuáles son las editoriales líderes en volumen de copias vendidas?

---

## Vistas y Componentes del Dashboard (`CopiasJuegos.pbix`)

El cuadro de mando interactivo cuenta con las siguientes visualizaciones y controles:

1. **Tarjeta KPI:**
   * **Venta Total:** Volumen agregado global de ventas (en millones de copias).
2. **Gráfico de Dona (Participación Regional):**
   * Distribución porcentual y comparativa de ventas entre regiones (`NA`, `EU`, `JP`, `Otros`).
3. **Gráfico de Barras (Ventas por Plataforma):**
   * Ranking de consolas y plataformas (Wii, DS, X360, PS3, PS2, etc.) desglosado por región.
4. **Gráfico de Columnas (Evolución Temporal):**
   * Tendencia histórica del volumen de ventas por `Año`.
5. **Gráfico de Barras (Ventas por Género):**
   * Análisis por categoría de juego (*Action, Sports, Shooter, Role-Playing, Platform*, etc.).
6. **Tabla Dinámica ("Detalle de ventas"):**
   * Matriz detallada con `Nombre` del videojuego, `Año` de lanzamiento y volumen de `Venta`.
7. **Panel de Filtros Interactivos (Segmentadores Dropdown):**
   * Filtro por **Editorial** *(Nintendo, Electronic Arts, Activision, etc.)*
   * Filtro por **Plataforma**
   * Filtro por **Año**
   * Filtro por **Región**
   * Filtro por **Género**

---

## Proceso ETL y Modelado de Datos

El dataset original se encuentra en el archivo [`Ventas Videojuegos.xlsx`](Ventas%20Videojuegos.xlsx). Para optimizar el análisis en Power BI, se aplicaron las siguientes transformaciones en **Power Query**:

1. **Extracción:** Carga de 16,350 registros desde la hoja `Ventas Videojuegos`.
2. **Normalización (Unpivot Columns):**
   * El dataset crudo presentaba las ventas en formato horizontal en 4 columnas territoriales (`Ventas NA`, `Ventas EU`, `Ventas JP`, `Ventas Otros`).
   * Se aplicó **Anulación de dinamización de columnas** (*Unpivot*) para convertir la estructura a formato vertical normalizado, generando las columnas:
     * **`Region`:** Identificador geográfico del mercado.
     * **`Venta`:** Cantidad de copias vendidas (en millones).
3. **Tipado y Calidad de Datos:** Verificación de tipos numéricos, fechas enteras y categorización de texto.

---

## Estructura del Repositorio

```
.
├── CopiasJuegos.pbix           # Archivo de reporte y modelo de datos en Power BI Desktop
├── Ventas Videojuegos.xlsx      # Dataset de origen con 16,350 registros
├── .gitignore                   # Exclusiones de archivos temporales de Office y Power BI
└── README.md                    # Documentación del proyecto
```

---

## Como explorar este proyecto?

1. Clona este repositorio en tu máquina local:
   ```bash
   git clone https://github.com/ManuelFedz/video-games-sales-dashboard.git
   ```
2. Abre el archivo **`CopiasJuegos.pbix`** con [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
3. Interactúa con los filtros desplegables para analizar el rendimiento por consola, distribuidor o región.
