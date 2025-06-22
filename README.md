# 🚴 Evaluación de la calidad de los datos de OpenStreetMap sobre infraestructuras ciclistas en Barcelona (2024)

Este proyecto analiza la fiabilidad de los datos colaborativos de OpenStreetMap (OSM) para representar la infraestructura ciclista en Barcelona, comparándolos con la cartografía oficial del Ayuntamiento. Incluye un pipeline completo que automatiza el cálculo de métricas de calidad, la generación de mapas y la validación visual mediante Google Street View.

---

## 📌 Objetivos principales

- Evaluar la **cobertura espacial** de OSM frente a la red oficial.
- Medir la **precisión geométrica** y detección de errores del dato colaborativo.
- Analizar el **valor añadido** de OSM (segmentos no oficiales confirmados).
- Detectar **patrones espaciales de error** en la calidad del dato OSM.

---

## 🧰 ¿Qué incluye este repositorio?

- `v15.py`: Script principal que ejecuta todo el análisis.
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

## 📂 Estructura esperada de resultados

- `metricas_automaticas_prevalidacion.xlsx`
- `metricas_validadas_post_GSV.xlsx`
- `validacion_visual_unificada_*.xlsx`
- `mapas_resultado/*.png`
- `outputs/shapefiles/*.shp`

---

## 📊 Métricas generadas

- `Completeness (%)`
- `Accuracy (%)`
- `SCI (Índice de Completitud Espacial)`
- `Precision (%)`
- Detección de `Commissions` y `Omissions`

---

## 📦 Bibliotecas utilizadas

Este proyecto fue desarrollado con Python e integra las siguientes bibliotecas:

- [pandas](https://pandas.pydata.org/)
- [geopandas](https://geopandas.org/)
- [matplotlib](https://matplotlib.org/)
- [shapely](https://shapely.readthedocs.io/)
- [openpyxl](https://openpyxl.readthedocs.io/)
- [ohsome-py](https://github.com/GIScience/ohsome-py) (acceso a datos históricos OSM)

---

## ✍️ Autora

Este análisis forma parte del Trabajo de Fin de Máster (TFM) en Geoinformación 2024.  
**Autora:** Zulema Orellana H. 
**Universidad:** Universidad Autónoma de Barcelona

---

## 📥 Descarga del proyecto

Puedes clonar este repositorio o descargarlo como archivo `.zip` desde:  
[https://github.com/TU_USUARIO/NOMBRE_REPO](https://github.com/TU_USUARIO/NOMBRE_REPO)

Haz clic en el botón verde `<> Code` > `Download ZIP`.

---

## 📄 Licencia

Este proyecto está distribuido bajo una licencia académica para fines de investigación y docencia. Para reutilización, contactar con la autora.
