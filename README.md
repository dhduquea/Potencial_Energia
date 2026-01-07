# Análisis y Limpieza de Fuentes de Energía (Colombia) 🇨🇴⚡

Este proyecto se centra en la **extracción, limpieza y procesamiento de datos hidrometeorológicos** de Colombia, obtenidos a través del IDEAM y datos.gov.co. El objetivo principal es estandarizar la información de vientos, radiación solar y caudales para facilitar análisis posteriores de potencial energético.

> ## ⚠️ Nota Importante sobre la Ejecución
> Este proyecto fue desarrollado y ejecutado originalmente en la plataforma **Kaggle**.
> * **Rutas de archivos:** Las rutas de lectura de datos en el código (inputs) están configuradas para la estructura de directorios de Kaggle. Si ejecutas esto localmente, deberás ajustar las rutas a la ubicación de tus archivos descargados.
> * **Proyecto Original:** Para ver el entorno original y los datasets conectados, visita:
> 👉 [Kaggle: Proyecto Energía - dhduquea](https://www.kaggle.com/code/dhduquea/proyecto-energia)

## ⚙️ Funcionalidades del Proyecto

El notebook (`proyecto-energia.ipynb`) realiza un flujo completo de Data Cleaning que incluye:

* **Catálogo de Estaciones:** Limpieza de nombres de municipios (eliminación de tildes y caracteres especiales con `unicodedata`) y filtrado de columnas técnicas no relevantes.
* **Análisis de Vientos:**
    * Filtrado temporal para trabajar con datos recientes (post-2016).
    * Conversión de tipos de datos a `datetime`.
    * Agregación de valores máximos diarios por estación.
* **Radiación Solar:** Procesamiento de múltiples fuentes de datos de radiación global horaria.
* **Visualización:** Generación de mapas de calor (Heatmaps) y gráficos de barras para comparar el comportamiento de las variables por municipio y año.

## 🛠️ Tecnologías Utilizadas

Para correr este proyecto se utilizaron las siguientes librerías de Python:

* **Pandas:** Manipulación y limpieza de estructuras de datos (DataFrames).
* **Matplotlib & Seaborn:** Creación de visualizaciones estadísticas y mapas de calor.
* **Time & Datetime:** Gestión de formatos temporales y filtrado de series de tiempo.
* **Unicodedata:** Normalización de cadenas de texto.

## 📂 Estructura de Salida

El flujo de trabajo genera archivos limpios listos para su uso:

| Archivo | Descripción |
| :--- | :--- |
| `catalogoNacionalClean.csv` | Información de estaciones estandarizada. |
| `vientosClean.csv` | Mediciones de velocidad del viento procesadas por día. |

## 🚀 Cómo ejecutar el proyecto localmente

1.  Asegúrate de tener instalado **Python 3.12+**.
2.  Clona este repositorio y crea tu entorno virtual:
    ```bash
    python -m venv venv
    .\venv\Scripts\Activate
    ```
3.  Instala las dependencias:
    ```bash
    pip install pandas matplotlib seaborn
    ```
4.  **Descarga los datos** desde el link de Kaggle proporcionado arriba y colócalos en tu carpeta del proyecto.
5.  **Ajusta las rutas** en el notebook (`pd.read_csv('tu_ruta_local.csv')`) y ejecuta.

---
*Este proyecto fue desarrollado como parte de un análisis de viabilidad energética utilizando datos abiertos.*