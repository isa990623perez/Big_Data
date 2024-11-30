# Proyecto de Procesamiento de Imágenes con Keras y OpenCV

Este proyecto implementa un pipeline básico para procesar imágenes en escala de grises y aplicar operaciones utilizando redes neuronales convolucionales en Python. 

## Características Principales

1. **Creación y Manipulación de Imágenes Sintéticas**:  
   - Se genera un arreglo de ceros (negro) con un rectángulo blanco en su interior.  
   - Dentro del rectángulo blanco, se agrega otro rectángulo gris para visualizar diferentes niveles de intensidad.  

2. **Lectura y Preprocesamiento de Imágenes**:  
   - Se lee una imagen externa en escala de grises utilizando OpenCV.  
   - Se redimensiona para adaptarla a los modelos de redes neuronales.

3. **Implementación de Modelos Convolucionales en Keras**:  
   - Creación de modelos con capas `Conv2D` para aplicar diferentes filtros personalizados.  
   - Los filtros permiten detectar bordes y patrones específicos en las imágenes.

4. **Visualización de Resultados**:  
   - Los resultados de los filtros se muestran en imágenes que destacan las características detectadas.  
