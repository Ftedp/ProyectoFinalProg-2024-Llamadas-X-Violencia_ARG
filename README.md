# 📊 Análisis de Llamadas a la Línea 144 — Violencia de Género en Argentina (2020–2022)
 
Proyecto final de la materia **Programación 2** — TUIA, Universidad Nacional de Rosario.  
Análisis exploratorio de datos sobre llamadas recibidas por la **Línea 144**, el servicio nacional de atención a personas en situación de violencia de género (Ley N° 26.485).
 
**Integrantes:** Rocío Quispe · Facundo Torino — Comisión 2
 
---
 
## 📁 Estructura del repositorio
 
```
ProyectoFinalProg-2024-Llamadas-X-Violencia_ARG/
└── ProyectoFinalProg[2]_2024_Llamadas_x_Violencia_ARG_[Pandas].ipynb
```
 
---
 
## 🗂️ Dataset
 
- **Fuente:** [datos.gob.ar — Base de datos Línea 144](https://www.datos.gob.ar/dataset/generos-base-datos-linea-144)
- **Período analizado:** 2020, 2021 y 2022 (3 archivos CSV)
- **Total de registros procesados:** ~64.000 llamadas (tras limpieza)
- **Variables principales:** fecha, provincia de residencia, género de la víctima, edad, país de nacimiento, tipo de violencia (física, psicológica, sexual, económica, simbólica, doméstica), modalidad de violencia, vínculo con el agresor, género del agresor
---
 
## 🔧 Proceso de análisis
 
### 1. Carga y unificación de datos
- Carga de tres archivos CSV independientes (uno por año)
- Detección de inconsistencias entre esquemas: columna `fecha` con nombre diferente en 2022, columna vacía `Unnamed: 19`
- Corrección y concatenación en un único DataFrame de ~79.500 registros
### 2. Limpieza y transformación
- Conversión de `fecha` a `datetime`
- Normalización de nombres de provincias (`Cordoba` → `Córdoba`, `Santiago Del Estero` → `Santiago del Estero`)
- Normalización de géneros y países de nacimiento (estandarización de mayúsculas, abreviaturas y variantes)
- Imputación de valores nulos con `'No especificado'` en variables categóricas clave
- Eliminación de edades inválidas (> 100 años, como un registro con 127 años)
- Conversión de columnas de tipo de violencia de `'Si'/'No'` a booleanos
### 3. Análisis descriptivo
- Distribución de edades: media de **35 años**, rango intercuartil entre 27 y 42 años
- Boxplot por género: las mujeres abarcan todo el espectro etario registrado (1–100 años)
- Histograma de frecuencia de edades: pico a los 35 años, caída pronunciada a partir de los 40
### 4. Análisis temporal
- Evolución mensual de llamadas entre enero 2020 y diciembre 2022
- Comparación año a año por mes
- Identificación del **pico de llamadas en marzo–abril 2020**, coincidente con el inicio del ASPO (confinamiento por COVID-19)
- Tendencia decreciente en los años siguientes
### 5. Preguntas de investigación respondidas
 
**¿Cuál es el tipo de violencia predominante por provincia?**  
La violencia psicológica es la más reportada en la mayoría de las provincias. En segundo lugar aparece la violencia doméstica.
 
**¿Cuál fue la evolución de llamadas por género de la víctima?**  
Las mujeres representan la gran mayoría de los casos en todos los meses analizados. Se observa un pico pronunciado en el período de confinamiento (marzo–abril 2020).
 
**¿Cómo se distribuyen los casos de violencia en menores de 18 años en Santa Fe?**  
62 casos registrados. Los meses de mayor incidencia fueron enero y junio. El vínculo agresor más frecuente fue la pareja (17 casos), seguido de "Otro" (14) y padre o tutor (12). La edad más vulnerable fue los 15–16 años.
 
---
 
## 📌 Principales hallazgos
 
- **Buenos Aires** concentra más de 35.000 llamadas en el período, siendo la provincia con mayor volumen absoluto.
- El **género masculino** representa casi 60.000 casos como agresor sobre el total analizado.
- Los vínculos **ex pareja** (+30.000 casos) y **pareja** (+20.000 casos) son los más frecuentes entre agresor y víctima.
- El **confinamiento de 2020** generó un incremento significativo de llamadas, con descenso sostenido en 2021 y 2022.
- La **violencia psicológica** es transversal a todas las provincias.
---
 
## 🛠️ Tecnologías utilizadas
 
| Librería | Uso |
|---|---|
| `pandas` | Manipulación y análisis de datos |
| `numpy` | Operaciones numéricas |
| `matplotlib` | Visualizaciones |
| `seaborn` | Gráficos estadísticos |
 
---
 
## ⚙️ Instalación y uso
 
```bash
git clone https://github.com/Ftedp/ProyectoFinalProg-2024-Llamadas-X-Violencia_ARG.git
cd ProyectoFinalProg-2024-Llamadas-X-Violencia_ARG
pip install pandas numpy matplotlib seaborn
jupyter notebook
```
 
> Los archivos CSV del dataset se descargan automáticamente en el notebook mediante `gdown` desde Google Drive.
 
---
 
## 🏫 Contexto académico
 
| Campo | Detalle |
|---|---|
| Materia | Programación 2 |
| Carrera | TUIA — Tecnicatura Universitaria en Inteligencia Artificial |
| Universidad | Universidad Nacional de Rosario (UNR) |
| Año | 2024 |
