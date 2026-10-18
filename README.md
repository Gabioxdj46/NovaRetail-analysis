# 📊 NovaRetail+ | Análisis de factores de comportamiento del cliente

## 📌 Descripción del proyecto

Este repositorio contiene un análisis exploratorio de los factores de comportamiento asociados con el ingreso anual generado por los clientes de **NovaRetail+**, una plataforma de comercio electrónico con operaciones en Latinoamérica.

El análisis se desarrolla utilizando información correspondiente al año 2024 y forma parte del Proyecto para mi formación como Análisis de Datos.

El proyecto utiliza técnicas estadísticas y visualizaciones para identificar relaciones entre variables de comportamiento, actividad, segmentación y valor económico.

**Importante:** este es un análisis correlacional, por lo tanto, las asociaciones identificadas no demuestran causalidad.

---

## 🎯 Objetivo del proyecto

Responder la pregunta principal de negocio:

> ¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado para NovaRetail+?

Para ello se analizan variables como:

- Frecuencia de compras.
- Visitas mensuales.
- Gasto en publicidad dirigida.
- Satisfacción del cliente.
- Edad y nivel de ingreso estimado.
- Pertenencia al programa premium.
- Abandono de clientes.
- Tipo de dispositivo y región.

La variable objetivo del análisis es `ingreso_anual`.

---

## 📂 Estructura del repositorio

```text
NovaRetail-analysis/
├── README.md
├── Project_NovaRetail.ipynb
└── data/
    └── novaretail_comportamiento_clientes_2024.csv
```

### Archivos principales

**`Project_NovaRetail.ipynb`**

Notebook principal con exploración de datos, preparación, visualizaciones, cálculos de correlación, interpretación de hallazgos y recomendaciones de negocio.

**`data/novaretail_comportamiento_clientes_2024.csv`**

Dataset utilizado para el análisis.

**`README.md`**

Documento que describe los objetivos, herramientas, metodología, principales hallazgos e instrucciones para reproducir el análisis.

---

## 📁 Dataset utilizado

El dataset contiene:

- **15.000 registros de clientes.**
- **12 columnas.**
- Información de comportamiento y actividad correspondiente a 2024.

### Variables del dataset

| Variable | Descripción |
|---|---|
| `id_cliente` | Identificador único del cliente |
| `edad` | Edad del cliente |
| `nivel_ingreso` | Ingreso anual estimado del cliente |
| `visitas_mes` | Cantidad de visitas mensuales |
| `compras_mes` | Número de compras mensuales |
| `gasto_publicidad_dirigida` | Gasto en publicidad asignado al cliente |
| `satisfaccion` | Calificación de satisfacción |
| `miembro_premium` | Estado premium, codificado como 0 o 1 |
| `abandono` | Indicador de abandono, codificado como 0 o 1 |
| `tipo_dispositivo` | Dispositivo utilizado |
| `region` | Región geográfica |
| `ingreso_anual` | Ingreso anual generado por el cliente para NovaRetail+ |

---

## 🛠️ Herramientas utilizadas

El proyecto fue desarrollado con:

- Python.
- pandas.
- NumPy.
- Matplotlib.
- Seaborn.
- SciPy.
- Jupyter Notebook.
- Google Colab.
- GitHub.

---

## 🔎 Metodología y etapas del análisis

### 1. Carga y exploración del dataset

Se revisaron las dimensiones, columnas, tipos de datos, valores faltantes y características generales del conjunto de datos.

### 2. Preparación de datos y documentación de supuestos

Se evaluaron las variables numéricas, binarias y categóricas.

Se verificó su estructura y se documentaron los supuestos necesarios para seleccionar correctamente los métodos de correlación.

### 3. Visualización de relaciones

Se utilizaron:

- Heatmap de correlaciones.
- Scatterplot general.
- Scatterplots para pares clave.

Estas visualizaciones permitieron identificar tendencias positivas, negativas y relaciones de distinta intensidad.

### 4. Cálculo de coeficientes de correlación

Se aplicaron diferentes métodos estadísticos según el tipo de variable:

| Método | Aplicación |
|---|---|
| Pearson | Relaciones lineales entre variables numéricas |
| Spearman | Relaciones monótonas entre variables numéricas |
| Punto-biserial | Variables binarias frente a variables numéricas |
| V de Cramér | Asociación entre variables categóricas |

### 5. Interpretación de resultados para el negocio

Se documentaron los principales hallazgos utilizando:

- Evidencia visual.
- Evidencia numérica.
- Interpretación no causal.
- Limitaciones.
- Implicaciones y recomendaciones de negocio.

### 6. Limitaciones y próximos pasos

Se identificaron limitaciones metodológicas y se propusieron análisis adicionales para validar los hallazgos.

---

## 📊 Principales hallazgos

### 1. Compras mensuales e ingreso anual

La asociación más fuerte se encontró entre `compras_mes` e `ingreso_anual`.

- Pearson: **0.967**
- Spearman: **0.967**

Esto indica una asociación positiva muy fuerte.

Los clientes con mayor frecuencia de compra tienden a generar mayor ingreso anual.

### 2. Visitas mensuales e ingreso anual

- Pearson: **0.337**
- Spearman: **0.321**

Se identificó una asociación positiva de magnitud débil a moderada.

Los clientes con más visitas tienden a generar mayor ingreso anual, aunque la relación es considerablemente menor que la observada con las compras.

### 3. Publicidad dirigida e ingreso anual

- Pearson: **0.197**
- Spearman: **0.185**

Se identificó una asociación positiva débil.

El gasto publicitario dirigido también presenta una correlación Pearson de **0.579** con `visitas_mes`, lo que indica una relación moderada con la actividad de visitas.

### 4. Variables binarias y categóricas

En el análisis punto-biserial se obtuvo:

- `miembro_premium` vs `ingreso_anual`: **0.0931**.
- `abandono` vs `ingreso_anual`: **-0.0028**.

Ambas asociaciones presentan magnitudes muy bajas.

En el análisis categórico, la mayor V de Cramér fue de **0.1202**, correspondiente a `miembro_premium` y `abandono`.

Esto representa una asociación débil entre ambas variables.

---

## 💡 Implicaciones y recomendaciones de negocio

A partir de los resultados, se recomienda evaluar las siguientes oportunidades:

**1. Frecuencia de compra**

Analizar estrategias de recompra y fidelización, debido a la asociación muy fuerte observada entre `compras_mes` e `ingreso_anual`.

**2. Conversión de visitas**

Investigar cómo mejorar la conversión de visitas en compras, ya que `visitas_mes` presenta una asociación positiva con el ingreso anual, pero menor que la frecuencia de compras.

**3. Eficiencia publicitaria**

Evaluar el gasto publicitario mediante indicadores adicionales, como conversión y retorno sobre inversión, antes de incrementar presupuestos.

**4. Análisis por segmentos**

Complementar el análisis de comportamiento con variables como región, dispositivo y pertenencia premium, evitando utilizarlas como explicaciones causales del ingreso.

Estas recomendaciones representan oportunidades de análisis y experimentación; los resultados actuales no garantizan que las acciones propuestas aumenten los ingresos.

---

## ⚠️ Limitaciones

- La correlación no demuestra causalidad.
- Las relaciones pueden estar influenciadas por variables no incluidas en el dataset.
- La asociación muy fuerte entre `compras_mes` e `ingreso_anual` debe interpretarse considerando que ambas variables están relacionadas conceptualmente con el comportamiento de compra.
- Los resultados corresponden al conjunto de datos analizado y no necesariamente se generalizan a otros periodos.
- Para validar efectos causales se requieren análisis adicionales o experimentos controlados.

---

## ▶️ Abrir el proyecto en Google Colab

Haz clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Gabioxdj46/NovaRetail-analysis/blob/main/Project_NovaRetail.ipynb)


---

## 📘 Cómo reproducir el análisis

Para ejecutar el proyecto:

1. Abre `Project_NovaRetail.ipynb` en Google Colab.
2. Verifica que el dataset esté disponible en `data/novaretail_comportamiento_clientes_2024.csv` dentro del repositorio.
3. El notebook está configurado para leer los datos desde el enlace público de GitHub.
4. Ejecuta las celdas del notebook en orden.
5. Revisa los resultados de exploración, visualizaciones, correlaciones y conclusiones.

El proyecto utiliza librerías habituales de análisis de datos en Python.

---

## 📌 Conclusión general

El análisis muestra que las variables relacionadas con el comportamiento de compra presentan las asociaciones más relevantes con `ingreso_anual`.

En particular, `compras_mes` muestra una asociación positiva muy fuerte, mientras que `visitas_mes` y `gasto_publicidad_dirigida` presentan relaciones positivas de menor magnitud.

Las variables binarias y las asociaciones categóricas analizadas no muestran relaciones fuertes.

Los resultados constituyen evidencia exploratoria que puede orientar análisis posteriores y futuras decisiones de crecimiento y retención.

**Correlación no implica causalidad.**

---

## 👤 Autor

Proyecto desarrollado por Gabriel Tacuri como parte de su formación como Análista de Datos.
