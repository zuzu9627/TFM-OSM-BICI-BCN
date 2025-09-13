# 🚴 Evaluación de la calidad de los datos de OpenStreetMap sobre infraestructuras ciclistas en Barcelona (2024)

Este proyecto analiza la fiabilidad de los datos colaborativos de OpenStreetMap (OSM) para representar la infraestructura ciclista en Barcelona, comparándolos con la cartografía oficial del Ayuntamiento. Incluye un pipeline completo que automatiza el cálculo de métricas de calidad, la generación de mapas y la validación visual mediante Google Street View.

---

## 📌 Objetivos principales

- Evaluar la **cobertura espacial** de OSM frente a la red oficial.
- Medir la **precisión geométrica** y detección de errores del dato colaborativo.
- Analizar el **valor añadido** de OSM (segmentos no oficiales confirmados).
- Detectar **patrones espaciales de error** en distritos y zonas urbanas.
- Ofrecer un **marco replicable** para la validación de datos de movilidad activa.

---

## 🧰 ¿Qué incluye este repositorio?

- `v15.py`: Script principal que ejecuta el análisis optimizado (diagnóstico + post-validación).
- `utils.py`: Funciones auxiliares para:
  - Normalización de códigos (`MUNDISSEC`).
  - Formato automático y validación en Excel.
  - Consolidación de métricas automáticas y validadas.
  - Análisis por **distrito** y por **subzonas** (densidad / proximidad al centro).
  - Exportación de resultados a tablas comparativas.
- `requirements.txt`: Lista de dependencias necesarias.
- `.gitignore`: Configuración para excluir archivos no deseados del control de versiones.
---

## ⚙️ Cómo ejecutar

```bash
# Instalar dependencias
pip install -r requirements.txt

# Ejecutar análisis completo (fase automática o validación)
python v15.py auto
```

O puedes lanzar fases específicas:

```bash
python v15.py diagnostico
python v15.py post_validacion
python v15.py forzar_diagnostico
```

---
## 📂 Estructura de resultados esperada

- **Resultados automáticos (fase 1):**
  - `metricas_automaticas_prevalidacion.xlsx`
  - `graficos_metricas_automaticas.png`
  - `mapas_tematicos_metricas.png`
  - `comparativa_redes_*.png` (mapas OSM vs oficial)

- **Archivos de validación:**
  - `validacion_visual_unificada_*.xlsx`

- **Resultados post-validación (fase 2):**
  - `metricas_validadas_post_GSV.xlsx`
  - `resumen_metricas_validadas_por_tipo.xlsx`
  - `metricas_con_infraestructura_validacion.xlsx`
  - `metricas_sin_infraestructura_validacion.xlsx`
  - `media_resumen_metricas_validados.xlsx`

- **Tablas interpretativas (utils):**
  - `TABLAS_RESULTADOS_INTERPRETACIONES/*.xlsx`
  - `tabla_resumen_validacion_distrital.xlsx`
  - `resumen_metricas_por_zona_*.xlsx`

---
## 📊 Métricas generadas

- **Automáticas (prevalidación):**
  - `Completeness (%)`
  - `Accuracy (%)`
  - `SCI` (Índice de Completitud Espacial)

- **Validadas (post-GSV):**
  - `Correción Completeness (%)`
  - `Correción Accuracy (%)`
  - `Correción Accuracy (%)`
  - `SCI` (Índice de Completitud Espacial)`

Además, detección de:
- `Commission` (segmentos OSM sin referencia oficial).
- `Omission` (segmentos oficiales ausentes en OSM).
- `Partial Match` (coincidencias bufferizadas).


---

## 📦 Bibliotecas utilizadas

Este proyecto fue desarrollado con Python e integra las siguientes bibliotecas:

- [pandas](https://pandas.pydata.org/)
- [geopandas](https://geopandas.org/)
- [matplotlib](https://matplotlib.org/)
- [shapely](https://shapely.readthedocs.io/)
- [openpyxl](https://openpyxl.readthedocs.io/)
- [ohsome-py](https://github.com/GIScience/ohsome-py) (acceso a datos históricos OSM)
- [arcpy](https://github.com/GIScience/ohsome-py) ( generación de secciones censales))
---

## ✍️ Autora

Este análisis forma parte del Trabajo de Fin de Máster (TFM) en Geoinformación 2024.  
**Autora:** Zulema Orellana H. 
**Universidad:** Universidad Autónoma de Barcelona

---

## 📥 Descarga del proyecto

Puedes clonar este repositorio o descargarlo como archivo `.zip` desde:  
[https://github.com/zuzu9627/TFM-OSM-BICI-BCN](https://github.com/zuzu9627/TFM-OSM-BICI-BCN)

Haz clic en el botón verde `<> Code` > `Download ZIP`.

---

## 📄 Licencia

Este proyecto está distribuido bajo una licencia académica para fines de investigación y docencia. Para reutilización, contactar con la autora.
