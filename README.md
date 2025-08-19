# Priorización de Hipótesis y Análisis de Test A/B (E-commerce)

## Descripción del Proyecto
Este proyecto se desarrolló como parte de mi formación en Data Analytics para una gran tienda online. El objetivo principal fue optimizar los ingresos mediante la priorización estratégica de hipótesis y el análisis riguroso de los resultados de un test A/B. El proyecto abarca desde la preparación de datos hasta la toma de decisiones basada en significancia estadística.

## Problema de Negocio / Objetivo
Una tienda online busca aumentar sus ingresos y ha compilado varias hipótesis para lograrlo. Para maximizar el impacto de los esfuerzos de desarrollo y marketing, era necesario:
1.  Priorizar las hipótesis más prometedoras utilizando frameworks de negocio.
2.  Diseñar y analizar un test A/B para validar el impacto de una hipótesis seleccionada.
3.  Determinar la significancia estadística de las diferencias entre los grupos A y B en métricas clave como la conversión y el tamaño promedio de pedido.
4.  Tomar una decisión fundamentada sobre la continuación o finalización del test A/B y las acciones a seguir.

## Conjunto de Datos
Se utilizaron tres datasets principales:
* **`hypotheses_us.csv`**: Descripción de 9 hipótesis con métricas de `Reach`, `Impact`, `Confidence` y `Effort`.
* **`orders_us.csv`**: Datos de pedidos (`transactionId`, `visitorId`, `date`, `revenue`, `group`).
* **`visits_us.csv`**: Datos de visitas (`date`, `group`, `visits`).

## Herramientas y Tecnologías Utilizadas
* **Python:** Lenguaje principal para el análisis, manipulación, cálculo estadístico y visualización.
    * `pandas`: Para la carga, limpieza y transformación de los DataFrames.
    * `numpy`: Para operaciones numéricas.
    * `matplotlib` / `seaborn`: Para la creación de gráficos acumulados y de dispersión.
    * `scipy.stats`: Para realizar pruebas de significancia estadística (ej. prueba U de Mann-Whitney).
* **Jupyter Notebook:** Entorno interactivo para el desarrollo del análisis y la presentación de resultados.

## Metodología y Análisis
### Parte 1: Priorización de Hipótesis
* **Framework ICE:** Se aplicó la fórmula `(Impact * Confidence) / Effort` para priorizar las hipótesis.
* **Framework RICE:** Se aplicó la fórmula `(Reach * Impact * Confidence) / Effort` para priorizar las hipótesis, considerando el alcance al usuario.
* **Comparación y Explicación:** Análisis de cómo la inclusión de la métrica 'Reach' (Alcance) afectó el orden de priorización de las hipótesis, destacando las implicaciones para la estrategia.

### Parte 2: Análisis del Test A/B
* **Preprocesamiento de Datos:**
    * Verificación de la integridad de los datos (ej. usuarios que pertenecen a ambos grupos del test A/B).
    * Conversión de tipos de datos y manejo de inconsistencias.
* **Análisis Acumulativo Gráfico:**
    * Ingreso acumulado por grupo.
    * Tamaño de pedido promedio acumulado por grupo.
    * Diferencia relativa en el tamaño de pedido promedio acumulado.
    * Tasas de conversión diarias y acumuladas por grupo.
* **Detección de Anomalías:**
    * Gráficos de dispersión para el número de pedidos y precios de los pedidos por usuario.
    * Cálculo de percentiles 95 y 99 para identificar y filtrar valores atípicos (outliers).
* **Análisis de Significación Estadística:**
    * **Conversión:** Se aplicó la prueba U de Mann-Whitney para comparar la diferencia en la conversión entre los grupos A y B, tanto con datos brutos como con datos filtrados (excluyendo anomalías).
    * **Tamaño Promedio de Pedido:** Se realizó la prueba U de Mann-Whitney para comparar la diferencia en el tamaño promedio de pedido entre los grupos, también con datos brutos y filtrados.

## Resultados Clave y Decisión
*(Adapta esta sección con tus resultados reales y la decisión final)*
* El análisis de los gráficos acumulados y las pruebas estadísticas mostraron que [Grupo A/B] superó a [Grupo B/A] en [conversión/ingreso/etc.].
* La diferencia en [conversión/tamaño de pedido] fue estadísticamente significativa después de filtrar las anomalías, lo que sugiere un impacto real de la hipótesis probada.

* <img width="1376" height="788" alt="image" src="https://github.com/user-attachments/assets/fc682421-0ee4-47fe-b0ec-c7be23028503" />

* <img width="1028" height="548" alt="image" src="https://github.com/user-attachments/assets/254b10df-024d-4224-854e-3b32605b9e70" />

* <img width="1035" height="544" alt="image" src="https://github.com/user-attachments/assets/7e0a4c2f-27a4-4351-8501-5d8c1f7ae28d" />

* <img width="1012" height="545" alt="image" src="https://github.com/user-attachments/assets/05df954c-a0cf-4239-9a99-37fab261c731" />

* <img width="1023" height="549" alt="image" src="https://github.com/user-attachments/assets/ef45c5ff-e2a9-4b59-b8ef-35f55fca20c5" />

* 





* **Decisión:** Basado en los resultados, se decidió [Parar la prueba, considerar a uno de los grupos como líder / Parar la prueba, concluir que no hay diferencia / Continuar la prueba]. Se fundamentó esta decisión en las métricas clave como [mencionar métricas: p-value de conversión, mejora en ROMI, etc.].
