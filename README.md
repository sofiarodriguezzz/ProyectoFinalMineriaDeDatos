# 🚕 Minería de Datos: Reservas de Uber y Ola Cabs

Proyecto final de la materia **Minería de Datos** (Grupo 5AM1, Equipo 6, ESCOM-IPN).

Análisis de **103,024 reservas** de viajes en Bangalore, India, siguiendo la metodología **CRISP-DM**. Se aplicaron segmentación con K-means, clasificación con árboles de decisión (CART) y reglas de asociación con Apriori, todo construido como un workflow en **KNIME**.

## 📁 Contenido

| Archivo | Descripción |
|---|---|
| `KNIME_proyecto_final_eq6.knwf` | Workflow completo de KNIME (se importa desde KNIME). |
| `PF_5AM1_eq6_reporte.pdf` | Reporte final del proyecto. |
| `PF_5AM1_eq6_codigos.txt` | Código Python usado dentro de los nodos *Python Script* de KNIME. |
| `Bookings.csv` | Dataset de reservas (fecha, tipo de vehículo, origen/destino, estado de la reserva, cancelaciones, valor, método de pago, distancia y calificaciones). |

## 🔍 Metodología (CRISP-DM)

1. **Comprensión de los datos:** exploración del dataset y estadísticas descriptivas (nodo *Statistics*).
2. **Preparación de los datos:**
   - Normalización de los nombres de columnas.
   - Limpieza de variables categóricas: los textos que significan "sin información" (`null`, `n/a`, `-`, etc.) se reemplazan con categorías semánticas como `No_Customer_Cancellation`, `No_Driver_Cancellation`, `No_Payment_Info` y `Not_Incomplete`, en lugar de eliminar registros.
   - Normalización de variables numéricas, filtrado de columnas, muestreo y partición en entrenamiento/prueba.
3. **Modelado:**
   - 🔮 **Clustering K-means**, evaluado con el coeficiente de silueta y visualizado con gráficas de dispersión.
   - 🌳 **Árbol de decisión (CART)** para clasificación, evaluado con matriz de confusión y métricas del nodo *Scorer*.
   - 🛒 **Reglas de asociación (Apriori)** con *Association Rule Learner*, ordenadas para extraer las reglas más relevantes (Top-k).
4. **Evaluación e interpretación:** resultados y conclusiones en el reporte PDF.

## 🛠️ Tecnologías

KNIME Analytics Platform · Python (pandas, NumPy) dentro de KNIME

## ▶️ Cómo abrirlo

1. Descarga o clona el repositorio:
   ```bash
   git clone https://github.com/sofiarodriguezzz/ProyectoFinalMineriaDeDatos.git
   ```
2. En KNIME: **File → Import KNIME Workflow...** y selecciona `KNIME_proyecto_final_eq6.knwf`.
3. Si es necesario, apunta el nodo *CSV Reader* a `Bookings.csv` y ejecuta el workflow.
4. Para los nodos *Python Script* necesitas la extensión de Python de KNIME con `pandas` y `numpy`.
