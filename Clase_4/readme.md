# Hipótesis Realizadas en el Entrenamiento del Modelo

A continuación se presentan las hipótesis realizadas durante el proceso de entrenamiento de un modelo sobre el conjunto de datos **MNIST**, y los resultados obtenidos:

## 1. Datos desbalanceados
Se consideró que los datos podrían estar desbalanceados, pero tras una revisión se observa que los datos están balanceados. Además, se confirma que cada ejemplo en el conjunto de datos es único, tal como se documenta en la documentación oficial de MNIST: [MNIST Official Documentation](https://yann.lecun.com/exdb/mnist/).

**Resultado**: No se encontró que el desbalanceo de los datos fuera el problema.

## 2. Número insuficiente de épocas
Se consideró que el número de épocas era insuficiente, ya que con 5 épocas solo se alcanzaba un 90% de precisión. Se aumentó el número de épocas a 50, pero el modelo continuó con un rendimiento del 90%.

**Resultado**: Aumentar el número de épocas no mejoró el accuracy. El problema no parece estar relacionado con el número de épocas.

## 3. Definición del optimizador
Se sospechó que el optimizador no estaba bien definido, por lo que se cambió a **Adam** (Estimación adaptativa del momento), que es más efectivo en entornos con mucho ruido y mejora la eficiencia computacional. Sin embargo, no hubo mejora en el accuracy.

**Resultado**: El cambio de optimizador no afectó el rendimiento.

## 4. Cambio de **AveragePooling** a **MaxPooling**
Se cambió de **AveragePooling** a **MaxPooling**, con la idea de que **MaxPooling** preservaría mejor las características importantes. No obstante, el cambio no tuvo efecto en el accuracy.

**Resultado**: El cambio de tipo de pooling no produjo ninguna mejora en el rendimiento.

## 5. Inclusión de capas de **Dropout**
Se añadieron capas de **Dropout** para intentar mejorar la generalización mediante el apagado aleatorio de algunas neuronas durante el entrenamiento. Sin embargo, el accuracy se mantuvo igual.

**Resultado**: La adición de capas de **Dropout** no tuvo efecto en el accuracy.

## 6. Agregar más capas densas
Se agregaron más capas densas con la esperanza de que la red pudiera aprender representaciones más complejas de los datos. Esto no generó mejoras en el accuracy.

**Resultado**: Aumentar el número de capas densas no mejoró el rendimiento del modelo.

## 7. Aumento de neuronas por capa
Se incrementó el número de neuronas por capa para intentar aumentar la capacidad del modelo. Sin embargo, esto tampoco condujo a un aumento en el accuracy.

**Resultado**: Aumentar el número de neuronas por capa no produjo ninguna mejora en el rendimiento.

## 8. Cambio de la función de activación de **tanh** a **ReLU**
Se cambió la función de activación de **tanh** a **ReLU**, dado que **ReLU** es conocida por ser más efectiva en redes complejas y mejorar la precisión. Sin embargo, el accuracy no mejoró.

**Resultado**: El cambio a **ReLU** no tuvo impacto en el rendimiento del modelo.

## Conclusión
Tras realizar todos estos ajustes, una posible hipótesis es que la estructura actual de la red neuronal no permite una generalización completa. A pesar de haber probado distintas modificaciones, el modelo parece estar limitado por su arquitectura o por algún otro factor que impide un mejor rendimiento.
