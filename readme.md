# Clasificación del Estado del Ojo con Machine Learning

Este proyecto utiliza diferentes algoritmos de Machine Learning para clasificar el estado del ojo (abierto o cerrado) utilizando un conjunto de datos de señales EEG. La combinación de varias técnicas permite obtener una visión más completa y precisa del problema, mejorando la clasificación final.

## Estructura del Proyecto

### Detección de Outliers

Para asegurar que los datos sean consistentes y no estén sesgados por valores atípicos, implementamos dos métodos de detección de outliers:

- **K-Nearest Neighbors (KNN)**: Identifica outliers en función de la distancia a los puntos más cercanos.
- **Isolation Forest (IF)**: Un algoritmo que utiliza particiones aleatorias del espacio para aislar valores atípicos.

Esta combinación de enfoques garantiza una detección robusta de outliers.

### Reducción de Dimensionalidad

Para visualizar mejor los datos y explorar posibles patrones entre las variables, se aplicó **Análisis de Componentes Principales (PCA)**, que reduce las dimensiones del dataset, permitiendo identificar visualmente la separación entre el estado del ojo (abierto o cerrado).

- ![Reducción PCA](reducciónPCA.png)

### División del Dataset

El dataset se dividió en dos partes para evaluar correctamente el rendimiento de los modelos en datos no vistos:

- **Entrenamiento (70%)**
- **Test (30%)**

Se utilizó la semilla 42 para garantizar la reproducibilidad de los resultados.

### Modelado Predictivo

Se probaron varios modelos de clasificación para predecir el estado del ojo:

1. **Regresión Logística**: Modelo lineal que predice la probabilidad de que el ojo esté abierto o cerrado.
2. **Árbol de Decisión**: Modelo no lineal que segmenta los datos en función de variables clave.
3. **Red Neuronal**: Modelo más complejo, con una capa oculta, para capturar relaciones no lineales entre las variables.
4. **Random Forest (BONUS)**: Un ensamblado de varios árboles de decisión que genera predicciones más robustas. Este fue el modelo que obtuvo los mejores resultados en términos de precisión.

### Evaluación de los Modelos

Se utilizaron varias métricas para evaluar el rendimiento de los modelos, incluyendo la **precisión**, **recall**, **F1-score** y la **curva ROC**. A continuación se muestran las curvas ROC de los modelos probados:

- ![ROC Árbol de Decisión](ROC-ArbolDecisión.png)
- ![ROC Red Neuronal](ROC-RNeuronal.png)
- ![ROC Regresión Logística](ROC-Rlogistica.png)

El modelo **Random Forest** fue el más preciso, superando a los demás en términos de predicción del estado del ojo.

### Conclusiones

Este proyecto demuestra que la combinación de técnicas avanzadas de Machine Learning puede mejorar significativamente la capacidad de predecir el estado del ojo. El modelo de **Random Forest** fue el más efectivo, aunque otros modelos también mostraron un rendimiento aceptable dependiendo del escenario.

El uso de **PCA** también resultó útil para visualizar la distribución de los datos y cómo las variables se correlacionan con el estado del ojo. Finalmente, la detección de outliers mediante KNN e Isolation Forest mejoró la calidad de los datos y, por ende, la precisión de los modelos.

## Requisitos

Para ejecutar este proyecto en tu entorno local, asegúrate de tener las siguientes librerías instaladas:

- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`

Puedes instalarlas utilizando el siguiente comando:

```bash
pip install -r requirements.txt


Analista

**Omar Zambrano Guevara**